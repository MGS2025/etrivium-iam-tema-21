# Tema 21 — Índice

> **Título oficial**: La arquitectura Java EE.
>
> **Bloque**: Parte II — Técnico (Temas 11-40)
> **Nivel**: C1 — Técnico Auxiliar TIC, Ayuntamiento de Madrid

---

## Estructura del tema

1. **Introducción a Java EE**
   1.1. Principios de la plataforma
   1.2. Evolución y contexto tecnológico
   1.3. De Java EE a Jakarta EE: evolución y gobernanza

2. **Elementos constitutivos**
   2.1. Componentes transversales
   2.1.1. Seguridad y autenticación (JAAS / Jakarta Security)
   2.1.2. Servicios de directorio (JNDI)
   2.1.3. Construcción: Maven, Gradle. Gestión de dependencias
   2.1.4. Empaquetado y ciclo de vida de las aplicaciones
   2.1.5. Compilación a nativo: GraalVM, Spring Boot y Quarkus
   2.1.6. Servidores de aplicaciones
   2.2. Arquitectura de capas
   2.3. Capa de presentación/integración
   2.3.1. Servlets y JavaServer Faces (JSF / Jakarta Faces)
   2.3.2. Servicios web: REST (JAX-RS) y SOAP (JAX-WS)
   2.3.3. Gobierno de APIs: Swagger, WSDL y UDDI
   2.4. Capa de negocio
   2.4.1. Enterprise JavaBeans (EJB): tipos (session, message-driven, entidad)
   2.4.2. Contexts and Dependency Injection (CDI)
   2.4.3. Jakarta Batch (JSR 352)
   2.5. Capa de persistencia y datos
   2.5.1. Mensajería asíncrona Java (JMS)
   2.5.2. Conectividad con bases de datos (JDBC)
   2.5.3. Gestión de transacciones (JTA)
   2.5.4. Java Persistence API (JPA)
   2.5.5. JCache (JSR 107)

3. **Herramientas de desarrollo**
   3.1. Gestión del rendimiento: Application Performance Manager (APM)
   3.2. Pruebas unitarias: JUnit, Mockito
   3.3. Pruebas de carga: JMeter
   3.4. Frameworks de desarrollo
   3.4.1. Spring (Core, MVC, Data, Batch, Cloud)
   3.4.2. Quarkus

4. **Tendencias actuales en el desarrollo de aplicaciones empresariales Java**

---

## Conceptos clave para memorizar

| Concepto | Dato clave |
|---|---|
| Java EE / Jakarta EE | Conjunto de especificaciones sobre Java SE para construir aplicaciones empresariales distribuidas, multicapa y gestionadas por un contenedor |
| Contenedor | Entorno de ejecución que gestiona el ciclo de vida, la seguridad, las transacciones y la concurrencia de los componentes, aplicando **inversión de control** |
| Especificación vs implementación | Java EE/Jakarta EE define **interfaces y contratos** (JSR / especificación Eclipse); cada servidor (GlassFish, WildFly, Payara…) es una **implementación** certificada |
| 2017-2019: transferencia a Eclipse | Oracle cede Java EE a la Eclipse Foundation; por conflicto de marca con «Java», el proyecto se renombra **Jakarta EE** |
| javax.* → jakarta.* | Desde **Jakarta EE 9** (2020) todas las APIs cambian de paquete `javax.*` a `jakarta.*` — ruptura binaria, no solo de nombre |
| JAAS / Jakarta Security | Autenticación (quién eres) y autorización (qué puedes hacer) declarativas mediante `LoginModule`, `Realm`, roles |
| JNDI | API de localización de recursos por nombre (`DataSource`, EJB, colas JMS) en un árbol jerárquico, desacoplando la aplicación de la configuración física |
| WAR / EJB-JAR / EAR | Unidades de empaquetado: aplicación web / módulo de lógica de negocio / ensamblado completo de varios módulos |
| GraalVM Native Image | Compila Java **ahead-of-time** a un ejecutable nativo: arranque en milisegundos y memoria reducida, frente al arranque JIT de la JVM tradicional |
| Arquitectura de capas | Presentación → Negocio → Persistencia, con dependencias **unidireccionales** hacia abajo (patrón *Layers*) |
| Servlet | Componente que gestiona el ciclo `request-response` HTTP en el contenedor web; JSF se apoya en el mismo contenedor con un modelo de componentes de UI |
| REST vs SOAP | REST es un **estilo arquitectónico** sobre HTTP, orientado a recursos; SOAP es un **protocolo** con envoltura XML y contrato formal WSDL |
| EJB: Session/MDB/Entidad | Session (Stateless/Stateful/Singleton) para lógica de negocio invocada; Message-Driven para consumo asíncrono de JMS; Entidad (histórica, sustituida por JPA) |
| CDI | Inyección de dependencias **tipada** (`@Inject`) con ámbitos (`@RequestScoped`, `@SessionScoped`, `@ApplicationScoped`, `@Dependent`), unifica el modelo de componentes de toda la plataforma |
| JTA | Coordina transacciones **distribuidas** entre varios recursos (dos bases de datos, una BD y una cola JMS) mediante el protocolo de **commit en dos fases (2PC)** |
| JPA | Estándar de mapeo objeto-relacional (ORM): entidades anotadas, `EntityManager`, JPQL |
| Contenedor gestiona vs bean gestiona (BMT/CMT) | Las transacciones EJB pueden ser gestionadas por el **contenedor** (`CMT`, por defecto, declarativo) o por el **bean** (`BMT`, programático) |
| Pirámide de pruebas | Muchas pruebas unitarias (JUnit/Mockito) en la base, menos de integración, pocas de carga/end-to-end (JMeter) en la cima |

---

*Tiempo estimado de estudio: 13-15 horas*
*Extensión del contenido: ~11.000 palabras · 12 diagramas SVG embebidos*
