# Tema 21 — Casos Prácticos

> **Título oficial**: La arquitectura Java EE: características de funcionamiento. Elementos constitutivos. Productos y herramientas.
>
> **Formato**: 3 casos prácticos sobre supuestos reales del Ayuntamiento de Madrid. Cada caso suma **10 puntos**.
> **Nivel**: C1 — Técnico Auxiliar TIC, Ayuntamiento de Madrid

Los tres casos recorren la aplicación de referencia **«Gestión de Expedientes y Tributos»** (ver tema-21-contenido.md, «Convenciones»): el **Caso 1** trabaja la **capa de presentación/integración** (REST y seguridad) invocando la capa de negocio; el **Caso 2**, el **modelo de componentes de negocio** (EJB y CDI) de un asistente multipaso; y el **Caso 3**, la **capa de persistencia y transacciones** (JPA, JTA, JCache).

---

## Caso 1 — API REST segura de consulta y liquidación de tributos

### Enunciado

El área de Hacienda necesita exponer, como **servicio REST**, la consulta y liquidación de tributos del ciudadano, reutilizando la lógica de negocio ya existente en el EJB `LiquidacionTributoService` (§2.4.1 del contenido). Solo el perfil **«gestor tributario»** puede liquidar; cualquier ciudadano autenticado puede consultar sus propios tributos.

### Cuestiones

**Cuestión 1 — Recurso REST (2 puntos).** Anote la clase `TributoResource` para exponerla como recurso REST en `/tributos`, con un método `consultar(Long id)` que responda en JSON al verbo GET sobre `/tributos/{id}`.

**Cuestión 2 — Seguridad declarativa (2 puntos).** Añada la anotación necesaria para que **solo** el rol `GESTOR_TRIBUTARIO` pueda invocar un método `liquidar(...)` de ese mismo recurso.

**Cuestión 3 — Inyección de la capa de negocio (3 puntos).** Inyecte el EJB `LiquidacionTributoService` dentro del recurso REST y delegue en él el cálculo de la liquidación, sin implementar la lógica de negocio dentro del propio recurso.

**Cuestión 4 — Atributo transaccional (3 puntos).** El método `liquidar()` del EJB debe ejecutarse siempre dentro de una transacción, uniéndose a la existente si la hay. Indique y justifique el atributo `@TransactionAttribute` adecuado.

### Solución orientativa

- **C1**: anotaciones `@Path`, `@GET`, `@Produces(MediaType.APPLICATION_JSON)` (§2.3.2).

```java
@Path("/tributos")
@ApplicationScoped
public class TributoResource {

    @GET
    @Path("/{id}")
    @Produces(MediaType.APPLICATION_JSON)
    public Response consultar(@PathParam("id") Long id) {
        Tributo t = service.buscarPorId(id);
        return (t != null) ? Response.ok(t).build()
                            : Response.status(Response.Status.NOT_FOUND).build();
    }
}
```

- **C2**: `@RolesAllowed`, interceptado por el contenedor antes de ejecutar el método (§2.1.1).

```java
@POST
@Path("/{id}/liquidar")
@RolesAllowed("GESTOR_TRIBUTARIO")
public Response liquidar(@PathParam("id") Long id, LiquidacionRequest req) { /* ... */ }
```

- **C3**: inyección con `@Inject` (o `@EJB`), delegando la lógica en la capa de negocio (§2.4.2, §2.2 — la presentación no debe contener lógica de negocio).

```java
@Inject
private LiquidacionTributoService service;
```

- **C4**: `REQUIRED` (§2.5.3), el atributo por defecto: se une a la transacción del llamador si existe, o crea una nueva si no la hay — es exactamente el comportamiento que pide el enunciado.

```java
@Stateless
@TransactionAttribute(TransactionAttributeType.REQUIRED)
public class LiquidacionTributoService { /* ... */ }
```

### Criterios de evaluación

| Criterio | Puntos |
|---|---|
| Recurso REST correctamente anotado (@Path/@GET/@Produces) | 2 |
| @RolesAllowed aplicado al método correcto, con el rol exacto | 2 |
| Inyección del EJB de negocio, sin lógica de negocio en el recurso REST | 3 |
| Atributo transaccional REQUIRED correctamente justificado | 3 |

---

## Caso 2 — Asistente multipaso de alta de expediente

### Enunciado

Se necesita un **asistente web de tres pasos** (datos del contribuyente → datos del expediente → confirmación) para dar de alta un nuevo expediente, que debe **recordar** los datos introducidos en cada paso hasta la confirmación final, momento en el que se persiste el expediente y se **notifica** de forma asíncrona a otros sistemas municipales.

### Cuestiones

**Cuestión 1 — Tipo de EJB (2 puntos).** ¿Qué tipo de Session Bean (Stateless/Stateful/Singleton) usaría para gestionar el estado del asistente entre los tres pasos? Justifique frente a las otras dos opciones.

**Cuestión 2 — Ámbito CDI (3 puntos).** Si el asistente se implementa en JSF con un *managed bean* CDI en lugar de un EJB con estado, ¿qué ámbito (`@RequestScoped`/`@SessionScoped`/`@ConversationScoped`) es el más adecuado para el flujo de tres pasos, y por qué no los otros dos?

**Cuestión 3 — Inyección de dependencias (3 puntos).** El bean del asistente necesita invocar el servicio de negocio que crea el expediente al confirmar. Escriba la inyección con CDI y explique por qué CDI resuelve por tipo y no por nombre.

**Cuestión 4 — Notificación asíncrona (2 puntos).** Al confirmar el alta, debe notificarse el nuevo expediente a dos sistemas municipales independientes sin acoplar el asistente a ninguno de los dos. ¿Qué mecanismo de JMS usaría y qué componente de negocio consumiría el mensaje?

### Solución orientativa

- **C1**: **Stateful** (§2.4.1): el asistente necesita recordar los datos de los pasos anteriores hasta la confirmación, algo que **Stateless** (sin conversación) no permite y que **Singleton** (una sola instancia para toda la aplicación) mezclaría entre usuarios distintos de forma incorrecta.

- **C2**: **`@ConversationScoped`** (§2.4.2): dura exactamente el flujo definido explícitamente por el desarrollador (los tres pasos del asistente), a diferencia de `@RequestScoped` (se perdería el estado entre pasos, cada uno es una petición distinta) y de `@SessionScoped` (viviría más allá del asistente, durante toda la sesión del usuario, aunque abandone el flujo sin terminar).

```java
@Named
@ConversationScoped
public class AltaExpedienteBean implements Serializable {
    @Inject
    private Conversation conversation;
    @Inject
    private ExpedienteService service;
    // datos acumulados de los tres pasos
}
```

- **C3**: `@Inject` inyecta por el **tipo** `ExpedienteService` (§2.4.2); si existiera más de una implementación de ese tipo, se resolvería con un *qualifier*, no por un nombre de cadena de texto como en JNDI.

```java
@Inject
private ExpedienteService service;
```

- **C4**: un **Topic** JMS (publicación/suscripción, §2.5.1), porque **varios** sistemas independientes deben recibir la misma notificación; un **Message-Driven Bean** en cada sistema consumidor se suscribe al topic y reacciona al mensaje sin que el asistente conozca su existencia.

```java
@Inject
private JMSContext contexto;
@Resource(lookup = "jms/TopicExpedienteCreado")
private Topic topic;

public void confirmar(Expediente e) {
    service.crear(e);
    contexto.createProducer().send(topic, "Expediente " + e.getId() + " creado");
}
```

### Criterios de evaluación

| Criterio | Puntos |
|---|---|
| Stateful correctamente elegido y justificado frente a Stateless/Singleton | 2 |
| @ConversationScoped correctamente elegido y justificado frente a los otros dos ámbitos | 3 |
| Inyección @Inject correcta, con explicación de resolución por tipo | 3 |
| Topic JMS + MDB correctamente identificados para notificación desacoplada a varios sistemas | 2 |

---

## Caso 3 — Persistencia, transacciones y caché de catálogo

### Enunciado

La entidad `Tributo` debe persistirse con JPA sobre la tabla `TRIBUTO` del Tema 19. Al liquidar un tributo, además de insertar el registro, debe **registrarse siempre una entrada de auditoría**, incluso si la liquidación en sí fallase y se deshiciera. El catálogo `DISTRITO`, de solo lectura y muy poco cambiante, debe evitarse consultarlo repetidamente en cada petición.

### Cuestiones

**Cuestión 1 — Entidad JPA (3 puntos).** Anote la clase `Tributo` como entidad JPA sobre la tabla `TRIBUTO`, con clave primaria autogenerada y una relación `@ManyToOne` hacia `Contribuyente`.

**Cuestión 2 — Consulta JPQL (2 puntos).** Escriba, con JPQL, la consulta que devuelve los tributos de importe superior a un parámetro, sobre el modelo de entidades (no sobre las tablas físicas).

**Cuestión 3 — Transacciones separadas (3 puntos).** Explique, con el atributo `@TransactionAttribute` adecuado, cómo garantizar que el registro de auditoría se confirme **con independencia** de si la liquidación principal acaba haciendo `rollback`.

**Cuestión 4 — Caché del catálogo (2 puntos).** Justifique el uso de JCache para el catálogo `DISTRITO` y qué riesgo introduce que debe mitigarse.

### Solución orientativa

- **C1**: entidad anotada (§2.5.4), con `@GeneratedValue` para la clave autonumérica y `@ManyToOne`/`@JoinColumn` para la relación.

```java
@Entity
@Table(name = "TRIBUTO")
public class Tributo {
    @Id @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long idTributo;
    private double importe;

    @ManyToOne
    @JoinColumn(name = "dni_contribuyente")
    private Contribuyente contribuyente;
}
```

- **C2**: JPQL opera sobre el **modelo de entidades**, no sobre las tablas físicas (§2.5.4).

```java
List<Tributo> altos = em.createQuery(
    "SELECT t FROM Tributo t WHERE t.importe > :minimo", Tributo.class)
    .setParameter("minimo", 500.0)
    .getResultList();
```

- **C3**: el método que registra la auditoría se anota con `@TransactionAttribute(TransactionAttributeType.REQUIRES_NEW)` (§2.5.3): suspende la transacción del llamador (la de la liquidación) y crea siempre una **nueva** transacción independiente, de modo que su `COMMIT` no depende de si la liquidación principal confirma o deshace.

```java
@Stateless
public class AuditoriaService {
    @TransactionAttribute(TransactionAttributeType.REQUIRES_NEW)
    public void registrar(String evento) { /* INSERT independiente */ }
}
```

- **C4**: `DISTRITO` es un catálogo de **solo lectura y muy poco cambiante** (§2.5.5), un candidato ideal para JCache: evita repetir la misma consulta en cada petición que necesita mostrar un distrito. El riesgo es servir un dato **obsoleto** (*stale*) si el catálogo cambia y la caché no se invalida a tiempo; se mitiga con una política de expiración razonable o, mejor aún, invalidando explícitamente la entrada afectada en el momento (excepcional) en que se modifica el catálogo.

```java
@CacheResult(cacheName = "distritos")
public Distrito buscarDistrito(int idDistrito) {
    return em.find(Distrito.class, idDistrito);
}
```

### Criterios de evaluación

| Criterio | Puntos |
|---|---|
| Entidad JPA correctamente anotada (@Entity/@Id/@GeneratedValue/@ManyToOne) | 3 |
| Consulta JPQL correcta sobre el modelo de entidades | 2 |
| REQUIRES_NEW correctamente identificado y justificado para independizar la auditoría | 3 |
| JCache justificado para el catálogo, con el riesgo de datos obsoletos identificado | 2 |

---

*Los tres casos son orientativos y pensados para la autoevaluación; las soluciones muestran una vía correcta, no la única posible. Todos los ejemplos usan anotaciones Jakarta EE reales (namespace `jakarta.*`), sin pseudocódigo neutro.*
