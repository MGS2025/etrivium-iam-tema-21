# Tema 21 — Test de Autoevaluación

> **Título**: La arquitectura Java EE: características de funcionamiento. Elementos constitutivos. Productos y herramientas.
> **Formato**: 60 preguntas tipo test A/B/C (formato oficial oposición)
> **Nivel**: C1 — Técnico Auxiliar TIC, Ayuntamiento de Madrid
> **Versión**: v1.0 — Pendiente validación
> **Fecha**: 2026-07-13
> **Fuentes**: ver tema-21-fuentes.md

---

## Instrucciones

- Cada pregunta tiene **3 opciones** (A, B, C). Solo una es correcta.
- Penalización en examen real: respuesta incorrecta descuenta **1/3** del valor de una correcta.
- Tiempo orientativo: 1 minuto por pregunta.
- Distribución: Introducción y evolución (P1-P8), Componentes transversales (P9-P24), Arquitectura de capas (P25-P26), Capa de presentación/integración (P27-P34), Capa de negocio (P35-P42), Capa de persistencia y datos (P43-P52), Herramientas de desarrollo (P53-P58), Tendencias actuales (P59-P60).

---

### Pregunta 1

**¿Qué distingue fundamentalmente a Java EE de escribir una aplicación en Java SE «a pelo»?**

A) El contenedor gestiona el ciclo de vida y presta servicios transversales de forma declarativa (inversión de control)
B) Java EE usa una sintaxis de lenguaje distinta a Java SE
C) Java EE no permite usar clases de Java SE

<details><summary>Respuesta</summary>

**Correcta: A) El contenedor gestiona el ciclo de vida y presta servicios transversales de forma declarativa (inversión de control)** El desarrollador describe qué necesita el componente; el contenedor lo crea, invoca sus métodos y le inyecta lo necesario.

*Referencia: §1.1 [JAKARTA-PLAT]*
</details>

---

### Pregunta 2

**En Java EE/Jakarta EE, ¿qué relación existe entre una especificación (p. ej. JAX-RS) y un servidor de aplicaciones como GlassFish o WildFly?**

A) El servidor de aplicaciones define la especificación y las bibliotecas la implementan
B) La especificación define un contrato normativo; el servidor de aplicaciones es una implementación que debe superar un TCK para certificarse compatible
C) No existe relación formal entre ambos conceptos

<details><summary>Respuesta</summary>

**Correcta: B) La especificación define un contrato normativo; el servidor de aplicaciones es una implementación que debe superar un TCK para certificarse compatible** Es la misma separación especificación/implementación que en el Tema 19 distingue el estándar SQL de sus motores.

*Referencia: §1.1 [JAKARTA-PLAT]*
</details>

---

### Pregunta 3

**¿En qué año nace la plataforma, bajo el nombre J2EE 1.2?**

A) 2006
B) 2017
C) 1999

<details><summary>Respuesta</summary>

**Correcta: C) 1999** J2EE 1.2 es la primera versión de la plataforma, impulsada por Sun Microsystems.

*Referencia: §1.2 [GONCALVES, cap. 1]*
</details>

---

### Pregunta 4

**¿Qué cambio introduce Java EE 5 (2006) respecto a las versiones anteriores de J2EE?**

A) Sustituye buena parte de la configuración XML por anotaciones, simplificando el modelo de programación
B) Introduce por primera vez el modelo de componentes EJB
C) Elimina el contenedor de servlets

<details><summary>Respuesta</summary>

**Correcta: A) Sustituye buena parte de la configuración XML por anotaciones, simplificando el modelo de programación** Es uno de los tres hitos de la evolución de la plataforma.

*Referencia: §1.2 [GONCALVES, cap. 1]*
</details>

---

### Pregunta 5

**¿Cuál fue el motivo declarado por Oracle para transferir Java EE a la Eclipse Foundation en 2017?**

A) Reducir el coste de mantenimiento de la plataforma
B) Acelerar la evolución de la plataforma fuera del proceso más lento del Java Community Process (JCP)
C) Eliminar la plataforma por falta de uso

<details><summary>Respuesta</summary>

**Correcta: B) Acelerar la evolución de la plataforma fuera del proceso más lento del Java Community Process (JCP)** El proceso de especificación abierto de Eclipse (JESP) sustituye al JCP para esta plataforma.

*Referencia: §1.3 [JAKARTA-PLAT]*
</details>

---

### Pregunta 6

**¿Por qué la plataforma se renombró de «Java EE» a «Jakarta EE» tras la transferencia a la Eclipse Foundation?**

A) Por decisión técnica de modernización de marca
B) Por votación de la comunidad sin motivo legal
C) Porque Oracle conservó la marca registrada «Java» y no autorizó su uso a la nueva gobernanza

<details><summary>Respuesta</summary>

**Correcta: C) Porque Oracle conservó la marca registrada «Java» y no autorizó su uso a la nueva gobernanza** Es la consecuencia legal directa de la retención de la marca, no una decisión técnica ni de marketing.

*Referencia: §1.3 [JAKARTA-PLAT]*
</details>

---

### Pregunta 7

**¿Qué versión de la plataforma introduce el cambio de paquete javax.* a jakarta.* en todas las APIs?**

A) Jakarta EE 9
B) Java EE 8
C) Jakarta EE 11

<details><summary>Respuesta</summary>

**Correcta: A) Jakarta EE 9** Es la llamada «Gran Renombración» (Big Bang Renaming), de 2020.

*Referencia: §1.3 [JAKARTA-PLAT]*
</details>

---

### Pregunta 8

**El cambio de namespace javax.* a jakarta.* en Jakarta EE 9 es...**

A) Un cambio puramente cosmético, sin impacto en el código compilado
B) Una ruptura binaria: el código compilado contra javax.* no es compatible en tiempo de ejecución con un contenedor que solo soporte jakarta.*
C) Reversible automáticamente por el servidor de aplicaciones sin recompilar

<details><summary>Respuesta</summary>

**Correcta: B) Una ruptura binaria: el código compilado contra javax.* no es compatible en tiempo de ejecución con un contenedor que solo soporte jakarta.*** Las aplicaciones existentes requirieron una migración explícita, aunque las APIs se mantuvieron semánticamente casi idénticas.

*Referencia: §1.3 [JAKARTA-PLAT]*
</details>

---

### Pregunta 9

**En el modelo de seguridad JAAS/Jakarta Security, ¿qué pregunta responde la AUTORIZACIÓN?**

A) ¿Quién eres?
B) ¿Cuánto tiempo dura tu sesión?
C) ¿Qué puedes hacer, una vez identificado?

<details><summary>Respuesta</summary>

**Correcta: C) ¿Qué puedes hacer, una vez identificado?** La autenticación responde «¿quién eres?»; la autorización, «¿qué puedes hacer?», normalmente basándose en roles.

*Referencia: §2.1.1 [JAKARTA-SEC]*
</details>

---

### Pregunta 10

**En el vocabulario JAAS, ¿qué representa un LoginModule?**

A) Un componente conectable que implementa un mecanismo concreto de autenticación (usuario/contraseña, certificado, LDAP…)
B) El resultado final de una autenticación exitosa
C) El registro de auditoría de accesos al sistema

<details><summary>Respuesta</summary>

**Correcta: A) Un componente conectable que implementa un mecanismo concreto de autenticación (usuario/contraseña, certificado, LDAP…)** Sigue un patrón de complementos (*pluggable authentication*).

*Referencia: §2.1.1 [JAKARTA-SEC]*
</details>

---

### Pregunta 11

**¿Cómo se expresa habitualmente la autorización por rol sobre un recurso Jakarta EE (p. ej. un endpoint REST)?**

A) Comprobando el rol manualmente dentro del código de negocio en cada método
B) De forma declarativa, con la anotación @RolesAllowed, interceptada por el contenedor antes de ejecutar el método
C) No es posible declarar restricciones de rol a nivel de endpoint

<details><summary>Respuesta</summary>

**Correcta: B) De forma declarativa, con la anotación @RolesAllowed, interceptada por el contenedor antes de ejecutar el método** Es el contenedor, no el código de negocio, quien verifica el rol.

*Referencia: §2.1.1 [JAKARTA-SEC]*
</details>

---

### Pregunta 12

**¿Cómo resuelve JNDI la localización de un recurso como un DataSource?**

A) Por el tipo Java de la clase, igual que CDI
B) Por la dirección IP del servidor de base de datos
C) Por un nombre lógico jerárquico, independiente de la configuración física del recurso

<details><summary>Respuesta</summary>

**Correcta: C) Por un nombre lógico jerárquico, independiente de la configuración física del recurso** JNDI resuelve por nombre; CDI (§2.4.2), en cambio, resuelve por tipo.

*Referencia: §2.1.2 [ORACLE-JNDI]*
</details>

---

### Pregunta 13

**¿Qué ventaja principal aporta usar un nombre JNDI lógico (p. ej. jdbc/ExpedientesDS) en lugar de credenciales embebidas en el código?**

A) Permite cambiar de entorno (desarrollo→producción) reconfigurando el servidor, sin recompilar la aplicación
B) Elimina por completo la necesidad de un pool de conexiones
C) Sustituye a JPA como mecanismo de persistencia

<details><summary>Respuesta</summary>

**Correcta: A) Permite cambiar de entorno (desarrollo→producción) reconfigurando el servidor, sin recompilar la aplicación** El nombre lógico desacopla el código de la configuración física del recurso.

*Referencia: §2.1.2 [ORACLE-JNDI]*
</details>

---

### Pregunta 14

**En Apache Maven, ¿qué encadena el ciclo de vida estándar de construcción?**

A) Un grafo de tareas con caché incremental, sin fases fijas
B) Una secuencia de fases fijas: validate → compile → test → package → verify → install → deploy
C) Un único paso que compila y despliega simultáneamente

<details><summary>Respuesta</summary>

**Correcta: B) Una secuencia de fases fijas: validate → compile → test → package → verify → install → deploy** El grafo de tareas con caché incremental es, en cambio, el modelo de Gradle.

*Referencia: §2.1.3 [MAVEN-DOC]*
</details>

---

### Pregunta 15

**¿Qué identifica de forma única una dependencia declarada en un pom.xml de Maven?**

A) Solo el nombre del archivo JAR
B) La ruta absoluta en el disco del desarrollador
C) La coordenada groupId:artifactId:version

<details><summary>Respuesta</summary>

**Correcta: C) La coordenada groupId:artifactId:version** Esa coordenada se resuelve automáticamente desde un repositorio (Maven Central o uno interno).

*Referencia: §2.1.3 [MAVEN-DOC]*
</details>

---

### Pregunta 16

**¿Por qué la dependencia de la propia API Jakarta EE se declara con scope provided en Maven?**

A) Porque el servidor de aplicaciones ya proporciona esa API en tiempo de ejecución; empaquetarla también causaría conflictos de clases duplicadas
B) Porque esa API no es necesaria para compilar el proyecto
C) Porque Maven no permite declarar dependencias de la plataforma

<details><summary>Respuesta</summary>

**Correcta: A) Porque el servidor de aplicaciones ya proporciona esa API en tiempo de ejecución; empaquetarla también causaría conflictos de clases duplicadas** La API se necesita para compilar, pero no para empaquetar dentro del artefacto final.

*Referencia: §2.1.3 [MAVEN-DOC]*
</details>

---

### Pregunta 17

**¿Qué distingue a Gradle de Maven en su modelo de construcción?**

A) Gradle no admite gestión de dependencias transitivas
B) Gradle usa un DSL programable (Groovy/Kotlin) y un motor de ejecución basado en un grafo de tareas con caché incremental
C) Gradle solo puede usarse en proyectos Android, nunca en Java EE

<details><summary>Respuesta</summary>

**Correcta: B) Gradle usa un DSL programable (Groovy/Kotlin) y un motor de ejecución basado en un grafo de tareas con caché incremental** Solo re-ejecuta las tareas cuyas entradas han cambiado.

*Referencia: §2.1.3 [GRADLE-DOC]*
</details>

---

### Pregunta 18

**¿Qué contiene típicamente un archivo WAR (Web Archive)?**

A) Únicamente EJB de sesión
B) Un conector JCA a un sistema externo
C) Un módulo web: servlets, JSF, recursos estáticos y su descriptor de despliegue

<details><summary>Respuesta</summary>

**Correcta: C) Un módulo web: servlets, JSF, recursos estáticos y su descriptor de despliegue** El descriptor `web.xml` es opcional desde que las anotaciones cubren la mayor parte de la configuración.

*Referencia: §2.1.4 [JAKARTA-SERVLET]*
</details>

---

### Pregunta 19

**¿Qué relación de contención es correcta entre los formatos de empaquetado Java EE?**

A) Un EAR puede contener varios WAR y EJB-JAR; un WAR no puede contener un EAR
B) Un WAR puede contener varios EAR
C) Un EJB-JAR y un EAR son formatos incompatibles entre sí

<details><summary>Respuesta</summary>

**Correcta: A) Un EAR puede contener varios WAR y EJB-JAR; un WAR no puede contener un EAR** Es la jerarquía de empaquetado de la plataforma.

*Referencia: §2.1.4 [JAKARTA-PLAT]*
</details>

---

### Pregunta 20

**¿Qué aísla el classloader hijo asignado a cada módulo dentro de un EAR desplegado?**

A) El acceso a la red del servidor
B) Las dependencias de cada módulo, evitando colisiones aunque dos módulos usen versiones distintas de una misma biblioteca
C) Las transacciones JTA de cada módulo

<details><summary>Respuesta</summary>

**Correcta: B) Las dependencias de cada módulo, evitando colisiones aunque dos módulos usen versiones distintas de una misma biblioteca** Cada WAR/EJB-JAR obtiene su propio classloader hijo del classloader de la aplicación.

*Referencia: §2.1.4 [JAKARTA-PLAT]*
</details>

---

### Pregunta 21

**¿Qué diferencia fundamental hay entre la compilación JIT de la JVM tradicional y GraalVM Native Image?**

A) Ambas compilan en el mismo momento, solo cambia el formato del ejecutable
B) JIT compila en tiempo de construcción; Native Image compila en tiempo de ejecución
C) JIT compila de forma progresiva en tiempo de ejecución; Native Image compila por completo en tiempo de construcción (ahead-of-time)

<details><summary>Respuesta</summary>

**Correcta: C) JIT compila de forma progresiva en tiempo de ejecución; Native Image compila por completo en tiempo de construcción (ahead-of-time)** Es la distinción JIT/AOT central de este epígrafe.

*Referencia: §2.1.5 [GRAALVM-DOC]*
</details>

---

### Pregunta 22

**¿Qué ventaja aporta principalmente un ejecutable generado con GraalVM Native Image frente al arranque de una JVM tradicional?**

A) Arranque en milisegundos y huella de memoria de partida sensiblemente menor
B) Mejor rendimiento sostenido tras horas de ejecución continua
C) Elimina la necesidad de declarar reflexión o proxies dinámicos

<details><summary>Respuesta</summary>

**Correcta: A) Arranque en milisegundos y huella de memoria de partida sensiblemente menor** A cambio, un análisis estático más restrictivo: la reflexión y los proxies dinámicos deben declararse explícitamente.

*Referencia: §2.1.5 [GRAALVM-DOC]*
</details>

---

### Pregunta 23

**¿Cuál es la relación correcta entre GraalVM Native Image y Quarkus?**

A) Son sinónimos exactos del mismo producto
B) GraalVM Native Image es una tecnología de compilación; Quarkus es un framework que la aprovecha (entre otras estrategias) para ofrecer aplicaciones nativas
C) Quarkus sustituyó a GraalVM Native Image en 2020

<details><summary>Respuesta</summary>

**Correcta: B) GraalVM Native Image es una tecnología de compilación; Quarkus es un framework que la aprovecha (entre otras estrategias) para ofrecer aplicaciones nativas** Quarkus también puede ejecutarse en modo JVM tradicional sin compilación nativa.

*Referencia: §2.1.5 [QUARKUS-DOC]*
</details>

---

### Pregunta 24

**¿Por qué Apache Tomcat, por sí solo, no se considera un servidor de aplicaciones Jakarta EE completo?**

A) Porque no puede ejecutar ningún componente Java
B) Porque no permite desplegar aplicaciones web
C) Porque implementa solo una parte de la especificación (servlets/JSF) pero le faltan EJB completo, JMS y JTA distribuido nativos

<details><summary>Respuesta</summary>

**Correcta: C) Porque implementa solo una parte de la especificación (servlets/JSF) pero le faltan EJB completo, JMS y JTA distribuido nativos** TomEE añade esas piezas sobre Tomcat.

*Referencia: §2.1.6 [WILDFLY-DOC]*
</details>

---

### Pregunta 25

**¿Qué principio rige las dependencias entre las capas de una aplicación Java EE en capas (presentación/negocio/persistencia)?**

A) Cada capa solo depende de la inmediatamente inferior; la dependencia es unidireccional hacia abajo
B) Cada capa puede invocar directamente a cualquier otra capa sin restricción
C) La capa de persistencia conoce y depende de la capa de presentación

<details><summary>Respuesta</summary>

**Correcta: A) Cada capa solo depende de la inmediatamente inferior; la dependencia es unidireccional hacia abajo** Este aislamiento permite sustituir una capa sin tocar las demás.

*Referencia: §2.2 [FOWLER-EAA]*
</details>

---

### Pregunta 26

**¿Qué contenedores del servidor de aplicaciones gestionan típicamente, respectivamente, la capa de presentación y la capa de negocio implementada con EJB?**

A) Ambas capas comparten un único contenedor sin distinción
B) El contenedor web gestiona la presentación (servlets/JSF/JAX-RS); el contenedor EJB gestiona la capa de negocio basada en Enterprise JavaBeans
C) El contenedor de persistencia gestiona ambas capas

<details><summary>Respuesta</summary>

**Correcta: B) El contenedor web gestiona la presentación (servlets/JSF/JAX-RS); el contenedor EJB gestiona la capa de negocio basada en Enterprise JavaBeans** Ambos contenedores conviven en el mismo servidor de aplicaciones y comparten servicios transversales.

*Referencia: §2.2 [GONCALVES, cap. 2]*
</details>

---

### Pregunta 27

**¿Cuántas instancias de un mismo servlet crea, por diseño, el contenedor web?**

A) Una instancia nueva por cada petición HTTP recibida
B) Una instancia por cada usuario autenticado
C) Una única instancia, que atiende todas las peticiones concurrentes en hilos distintos

<details><summary>Respuesta</summary>

**Correcta: C) Una única instancia, que atiende todas las peticiones concurrentes en hilos distintos** El contenedor despacha cada petición a un hilo distinto que invoca `service()`.

*Referencia: §2.3.1 [JAKARTA-SERVLET]*
</details>

---

### Pregunta 28

**¿Qué consecuencia práctica tiene que un servlet sea, por diseño, singleton?**

A) No debe guardar estado mutable de una petición en variables de instancia sin sincronización, por riesgo de errores de concurrencia
B) No puede recibir peticiones POST
C) Debe reiniciarse tras cada petición

<details><summary>Respuesta</summary>

**Correcta: A) No debe guardar estado mutable de una petición en variables de instancia sin sincronización, por riesgo de errores de concurrencia** El estado por petición se guarda en `HttpServletRequest`; el estado por usuario, en `HttpSession`.

*Referencia: §2.3.1 [JAKARTA-SERVLET]*
</details>

---

### Pregunta 29

**¿Sobre qué componente del contenedor web se construye JavaServer Faces (JSF)?**

A) Sobre un contenedor EJB independiente
B) Sobre el propio contenedor de servlets, mediante un único servlet especial (FacesServlet) que despacha todas las peticiones JSF
C) JSF no depende de ningún componente del contenedor web

<details><summary>Respuesta</summary>

**Correcta: B) Sobre el propio contenedor de servlets, mediante un único servlet especial (FacesServlet) que despacha todas las peticiones JSF** JSF añade un ciclo de vida de petición en seis fases sobre ese modelo base.

*Referencia: §2.3.1 [JAKARTA-FACES]*
</details>

---

### Pregunta 30

**Según la tesis de Roy Fielding (2000), ¿qué es REST?**

A) Un protocolo de mensajería con sobre XML normalizado
B) Una implementación concreta de JAX-WS
C) Un estilo arquitectónico que aprovecha las primitivas nativas de HTTP para operar sobre recursos identificados por URI

<details><summary>Respuesta</summary>

**Correcta: C) Un estilo arquitectónico que aprovecha las primitivas nativas de HTTP para operar sobre recursos identificados por URI** No es un protocolo cerrado, a diferencia de SOAP.

*Referencia: §2.3.2 [FIELDING2000]*
</details>

---

### Pregunta 31

**¿Qué anotación de JAX-RS identifica la URI base de un recurso REST?**

A) @Path
B) @WebService
C) @Entity

<details><summary>Respuesta</summary>

**Correcta: A) @Path** `@WebService` pertenece a JAX-WS; `@Entity` pertenece a JPA.

*Referencia: §2.3.2 [JAKARTA-REST]*
</details>

---

### Pregunta 32

**¿Qué caracteriza a SOAP frente a REST?**

A) SOAP no exige ningún formato de mensaje concreto
B) SOAP es un protocolo que exige un sobre XML normalizado, habitualmente descrito por un contrato WSDL formal
C) SOAP solo puede transportarse sobre FTP, nunca sobre HTTP

<details><summary>Respuesta</summary>

**Correcta: B) SOAP es un protocolo que exige un sobre XML normalizado, habitualmente descrito por un contrato WSDL formal** SOAP suele transportarse sobre HTTP, aunque no está ligado exclusivamente a él.

*Referencia: §2.3.2 [SOAP12]*
</details>

---

### Pregunta 33

**¿Qué documento describe formalmente el contrato de un servicio SOAP (operaciones, mensajes, tipos, endpoint)?**

A) OpenAPI
B) UDDI
C) WSDL

<details><summary>Respuesta</summary>

**Correcta: C) WSDL** OpenAPI cumple ese papel para REST; UDDI es el registro de descubrimiento, no el contrato.

*Referencia: §2.3.3 [WSDL20]*
</details>

---

### Pregunta 34

**¿Qué papel cumple UDDI en el ecosistema de servicios web SOAP?**

A) Un registro centralizado donde publicar y descubrir servicios, análogo a unas «páginas amarillas» de servicios web
B) El lenguaje de descripción del contrato de un servicio SOAP
C) El framework de implementación de servicios REST equivalente a JAX-RS

<details><summary>Respuesta</summary>

**Correcta: A) Un registro centralizado donde publicar y descubrir servicios, análogo a unas «páginas amarillas» de servicios web** Tuvo una adopción muy limitada fuera de grandes integraciones corporativas.

*Referencia: §2.3.3 [UDDI3]*
</details>

---

### Pregunta 35

**¿Qué caracteriza a un Stateless Session Bean?**

A) Mantiene una instancia dedicada por cada cliente durante toda la conversación
B) No mantiene estado conversacional entre invocaciones; el contenedor gestiona un pool de instancias intercambiables
C) Es la única instancia compartida por toda la aplicación

<details><summary>Respuesta</summary>

**Correcta: B) No mantiene estado conversacional entre invocaciones; el contenedor gestiona un pool de instancias intercambiables** Es la variante más escalable y la más habitual en la capa de negocio.

*Referencia: §2.4.1 [JAKARTA-EJB]*
</details>

---

### Pregunta 36

**¿Qué tipo de EJB es el adecuado para un asistente web de varios pasos que debe recordar los datos introducidos en pasos anteriores?**

A) Stateless
B) Singleton
C) Stateful

<details><summary>Respuesta</summary>

**Correcta: C) Stateful** El contenedor asocia una instancia dedicada a cada cliente durante toda la conversación.

*Referencia: §2.4.1 [JAKARTA-EJB]*
</details>

---

### Pregunta 37

**¿Qué ocurrió con las Entity Beans, el modelo histórico de persistencia gestionado por el contenedor EJB?**

A) Fueron sustituidas por completo por JPA desde Java EE 5 (2006), por su complejidad y rendimiento deficiente
B) Siguen siendo el estándar vigente de persistencia en Jakarta EE
C) Se fusionaron con los Message-Driven Beans

<details><summary>Respuesta</summary>

**Correcta: A) Fueron sustituidas por completo por JPA desde Java EE 5 (2006), por su complejidad y rendimiento deficiente** Mencionarlas como forma actual de persistencia es un error frecuente.

*Referencia: §2.4.1 [JAKARTA-EJB]*
</details>

---

### Pregunta 38

**¿Cómo resuelve CDI qué implementación inyectar con @Inject?**

A) Por el nombre JNDI del recurso
B) Por el tipo Java declarado (con qualifiers para desambiguar si hay varias implementaciones)
C) Por el orden alfabético de las clases candidatas

<details><summary>Respuesta</summary>

**Correcta: B) Por el tipo Java declarado (con qualifiers para desambiguar si hay varias implementaciones)** JNDI, en cambio, resuelve por nombre.

*Referencia: §2.4.2 [JAKARTA-CDI]*
</details>

---

### Pregunta 39

**¿Cuánto dura la instancia de un bean CDI anotado con @RequestScoped?**

A) Toda la sesión del usuario
B) Toda la vida de la aplicación
C) Una única petición HTTP; se crea una nueva instancia en cada petición

<details><summary>Respuesta</summary>

**Correcta: C) Una única petición HTTP; se crea una nueva instancia en cada petición** `@SessionScoped` dura la sesión; `@ApplicationScoped`, toda la aplicación.

*Referencia: §2.4.2 [JAKARTA-CDI]*
</details>

---

### Pregunta 40

**¿A qué patrón de diseño del Tema 20 equivale, en esencia, un bean CDI @ApplicationScoped?**

A) Singleton, gestionado automáticamente por el contenedor en lugar de codificado a mano
B) Factory Method
C) Adapter

<details><summary>Respuesta</summary>

**Correcta: A) Singleton, gestionado automáticamente por el contenedor en lugar de codificado a mano** Una única instancia compartida por toda la aplicación.

*Referencia: §2.4.2 [JAKARTA-CDI]*
</details>

---

### Pregunta 41

**¿Qué tres componentes intercambiables sigue habitualmente un step de Jakarta Batch en el patrón ETL?**

A) Controller, Service, Repository
B) ItemReader, ItemProcessor, ItemWriter
C) Producer, Consumer, Broker

<details><summary>Respuesta</summary>

**Correcta: B) ItemReader, ItemProcessor, ItemWriter** Leen, transforman/validan y escriben los elementos, agrupados en fragmentos (chunks).

*Referencia: §2.4.3 [JAKARTA-BATCH]*
</details>

---

### Pregunta 42

**¿En qué momento confirma la transacción el procesamiento por fragmentos (chunk-oriented) de Jakarta Batch?**

A) Solo al finalizar todo el job completo, nunca antes
B) Nunca; Jakarta Batch no usa transacciones
C) Por cada fragmento (chunk) procesado, lo que permite reiniciar desde el último fragmento confirmado si el job falla

<details><summary>Respuesta</summary>

**Correcta: C) Por cada fragmento (chunk) procesado, lo que permite reiniciar desde el último fragmento confirmado si el job falla** Un fallo en el fragmento 500 de 1.000 no obliga a reprocesar los 499 anteriores.

*Referencia: §2.4.3 [JAKARTA-BATCH]*
</details>

---

### Pregunta 43

**En JMS, ¿qué modelo de mensajería garantiza que cada mensaje lo consuma un único receptor, aunque haya varios consumidores escuchando?**

A) Punto a punto, sobre una Queue
B) Publicación/suscripción, sobre un Topic
C) Difusión (broadcast) sin destino definido

<details><summary>Respuesta</summary>

**Correcta: A) Punto a punto, sobre una Queue** Varios consumidores se reparten los mensajes, no los duplican.

*Referencia: §2.5.1 [JAKARTA-MSG]*
</details>

---

### Pregunta 44

**¿Qué modelo JMS es el adecuado para notificar un mismo suceso a varios sistemas interesados de forma independiente?**

A) Punto a punto, sobre una Queue
B) Publicación/suscripción, sobre un Topic
C) Solicitud-respuesta síncrona

<details><summary>Respuesta</summary>

**Correcta: B) Publicación/suscripción, sobre un Topic** Todos los suscriptores activos en el momento del envío reciben el mensaje.

*Referencia: §2.5.1 [JAKARTA-MSG]*
</details>

---

### Pregunta 45

**¿Qué defensa estándar frente a la inyección SQL ofrece el uso de PreparedStatement con parámetros en JDBC?**

A) Cifra automáticamente la conexión con la base de datos
B) Elimina la necesidad de un pool de conexiones
C) Separa el código SQL fijo, precompilado, de los datos (parámetros), de modo que un valor de entrada no puede alterar la estructura de la sentencia

<details><summary>Respuesta</summary>

**Correcta: C) Separa el código SQL fijo, precompilado, de los datos (parámetros), de modo que un valor de entrada no puede alterar la estructura de la sentencia** Conecta con el SQL dinámico frente a estático del Tema 19.

*Referencia: §2.5.2 [ORACLE-JNDI]*
</details>

---

### Pregunta 46

**¿Qué gestiona un DataSource localizado por JNDI en una aplicación Java EE?**

A) Un pool de conexiones físicas ya abiertas y reutilizables, evitando el coste de abrir una conexión TCP nueva en cada operación
B) La sintaxis JPQL de las consultas
C) El renderizado de la vista JSF

<details><summary>Respuesta</summary>

**Correcta: A) Un pool de conexiones físicas ya abiertas y reutilizables, evitando el coste de abrir una conexión TCP nueva en cada operación** La conexión no se abre directamente con credenciales embebidas en el código.

*Referencia: §2.5.2 [ORACLE-JNDI]*
</details>

---

### Pregunta 47

**¿Qué protocolo implementa el coordinador de transacciones de JTA para garantizar ACID en transacciones que abarcan varios recursos?**

A) Two-Way Handshake
B) Commit en dos fases (Two-Phase Commit, 2PC): fase de preparación y fase de confirmación/deshecho
C) Round-robin de confirmaciones

<details><summary>Respuesta</summary>

**Correcta: B) Commit en dos fases (Two-Phase Commit, 2PC): fase de preparación y fase de confirmación/deshecho** Si algún recurso no está listo, se ordena el rollback a todos.

*Referencia: §2.5.3 [JAKARTA-JTA]*
</details>

---

### Pregunta 48

**¿Qué diferencia CMT de BMT en la gestión transaccional de un EJB?**

A) CMT solo funciona con bases de datos NoSQL
B) BMT es el modelo por defecto y el más habitual
C) En CMT el contenedor gestiona la transacción de forma declarativa (atributos); en BMT el propio componente la controla explícitamente mediante programación

<details><summary>Respuesta</summary>

**Correcta: C) En CMT el contenedor gestiona la transacción de forma declarativa (atributos); en BMT el propio componente la controla explícitamente mediante programación** CMT es el modelo por defecto, no BMT.

*Referencia: §2.5.3 [JAKARTA-JTA]*
</details>

---

### Pregunta 49

**¿Qué hace el atributo transaccional REQUIRED (por defecto en CMT) si el método se invoca sin ninguna transacción activa?**

A) Crea una nueva transacción
B) Lanza una excepción obligatoriamente
C) Ejecuta el método sin ninguna transacción

<details><summary>Respuesta</summary>

**Correcta: A) Crea una nueva transacción** Si ya existe una transacción activa, `REQUIRED` se une a ella en lugar de crear una nueva.

*Referencia: §2.5.3 [JAKARTA-JTA]*
</details>

---

### Pregunta 50

**¿Qué mecanismo de JPA detecta automáticamente los cambios realizados sobre una entidad gestionada, sin invocar explícitamente un UPDATE?**

A) JNDI lookup
B) El dirty checking del contexto de persistencia del EntityManager
C) El pool de conexiones JDBC

<details><summary>Respuesta</summary>

**Correcta: B) El dirty checking del contexto de persistencia del EntityManager** Los cambios se sincronizan con la base de datos al confirmar la transacción.

*Referencia: §2.5.4 [JAKARTA-JPA]*
</details>

---

### Pregunta 51

**¿Sobre qué opera JPQL, a diferencia de SQL?**

A) Sobre las tablas y columnas físicas de la base de datos
B) Sobre los ficheros de configuración XML del servidor
C) Sobre el modelo de entidades y sus atributos Java, no directamente sobre tablas y columnas físicas

<details><summary>Respuesta</summary>

**Correcta: C) Sobre el modelo de entidades y sus atributos Java, no directamente sobre tablas y columnas físicas** El proveedor JPA lo traduce internamente a SQL.

*Referencia: §2.5.4 [JAKARTA-JPA]*
</details>

---

### Pregunta 52

**¿Qué es JCache (JSR 107)?**

A) Una especificación transversal de caché en memoria, aplicable tanto dentro como fuera de Jakarta EE
B) Un sinónimo del contexto de persistencia de primer nivel de JPA
C) Un tipo de EJB especializado en almacenamiento temporal

<details><summary>Respuesta</summary>

**Correcta: A) Una especificación transversal de caché en memoria, aplicable tanto dentro como fuera de Jakarta EE** No debe confundirse con el contexto de persistencia de JPA, que es una caché de primer nivel implícita y limitada a la transacción.

*Referencia: §2.5.5 [JAKARTA-CACHE]*
</details>

---

### Pregunta 53

**¿Qué diferencia principal hay entre una herramienta APM y una prueba de carga?**

A) Ambas se ejecutan siempre en el mismo momento del ciclo de vida
B) El APM monitoriza el sistema en producción de forma continua; la prueba de carga se ejecuta de forma puntual, antes del despliegue
C) La prueba de carga sustituye por completo al APM en producción

<details><summary>Respuesta</summary>

**Correcta: B) El APM monitoriza el sistema en producción de forma continua; la prueba de carga se ejecuta de forma puntual, antes del despliegue** Son complementarios, no sustitutos.

*Referencia: §3.1 [ISO25010]*
</details>

---

### Pregunta 54

**¿Qué papel cumple JUnit en las pruebas de una aplicación Java EE?**

A) Simula miles de usuarios concurrentes contra el sistema
B) Crea dobles de prueba (mocks) de las dependencias
C) Ejecuta y organiza las pruebas: aserciones y ciclo de vida (@BeforeEach/@AfterEach)

<details><summary>Respuesta</summary>

**Correcta: C) Ejecuta y organiza las pruebas: aserciones y ciclo de vida (@BeforeEach/@AfterEach)** Simular usuarios concurrentes es tarea de JMeter; crear mocks, de Mockito.

*Referencia: §3.2 [JUNIT5-DOC]*
</details>

---

### Pregunta 55

**¿Qué problema resuelve Mockito al probar la lógica de negocio de un EJB o CDI bean?**

A) Permite simular el comportamiento de sus dependencias reales (otro servicio, un EntityManager) sin ejecutarlas de verdad
B) Sustituye por completo a JUnit como framework de ejecución de pruebas
C) Genera automáticamente pruebas de carga con JMeter

<details><summary>Respuesta</summary>

**Correcta: A) Permite simular el comportamiento de sus dependencias reales (otro servicio, un EntityManager) sin ejecutarlas de verdad** Así la prueba se mantiene aislada, rápida y no frágil frente a recursos externos.

*Referencia: §3.2 [MOCKITO-DOC]*
</details>

---

### Pregunta 56

**¿Qué tipo de prueba con JMeter busca encontrar el punto de ruptura del sistema, más allá de la capacidad prevista?**

A) Prueba de resistencia (soak testing)
B) Prueba de estrés (stress testing)
C) Prueba unitaria

<details><summary>Respuesta</summary>

**Correcta: B) Prueba de estrés (stress testing)** La prueba de resistencia usa carga moderada sostenida en el tiempo; la unitaria no es una prueba de carga.

*Referencia: §3.3 [JMETER-DOC]*
</details>

---

### Pregunta 57

**¿Cuál es la relación correcta entre Spring Framework y Jakarta EE?**

A) Spring es la implementación de referencia oficial de Jakarta EE
B) Spring solo puede ejecutarse dentro de un servidor de aplicaciones Jakarta EE completo
C) Spring es un framework alternativo e independiente, aunque puede interoperar con especificaciones concretas como JPA

<details><summary>Respuesta</summary>

**Correcta: C) Spring es un framework alternativo e independiente, aunque puede interoperar con especificaciones concretas como JPA** Nace en 2003 como respuesta a la complejidad de EJB 2.x.

*Referencia: §3.4.1 [SPRING-DOC]*
</details>

---

### Pregunta 58

**¿Sobre qué estándares se construye explícitamente Quarkus, a diferencia de Spring?**

A) Estándares Jakarta EE/MicroProfile: CDI, JAX-RS, JPA
B) Un modelo de inyección de dependencias propio, sin relación con CDI
C) Únicamente sobre JDBC, sin soporte de inyección de dependencias

<details><summary>Respuesta</summary>

**Correcta: A) Estándares Jakarta EE/MicroProfile: CDI, JAX-RS, JPA** A diferencia de Spring, que es histórica e independiente de la plataforma estándar.

*Referencia: §3.4.2 [QUARKUS-DOC]*
</details>

---

### Pregunta 59

**¿Qué aporta MicroProfile sobre el subconjunto de especificaciones Jakarta EE que utiliza (CDI, JAX-RS, JSON-P)?**

A) Sustituye por completo a Jakarta EE como plataforma independiente sin relación con ella
B) Extensiones específicas de microservicios no cubiertas por la plataforma tradicional: tolerancia a fallos, configuración externa, métricas y health checks
C) Un nuevo lenguaje de programación distinto de Java

<details><summary>Respuesta</summary>

**Correcta: B) Extensiones específicas de microservicios no cubiertas por la plataforma tradicional: tolerancia a fallos, configuración externa, métricas y health checks** Se apoya en CDI/JAX-RS/JSON-P, no los sustituye.

*Referencia: §4 [QUARKUS-DOC]*
</details>

---

### Pregunta 60

**¿Qué relación tienen las tendencias actuales (cloud-native, MicroProfile, programación reactiva) con los fundamentos arquitectónicos de este tema?**

A) Sustituyen por completo el modelo de contenedor y la arquitectura de capas
B) No tienen ninguna relación con la plataforma Jakarta EE tradicional
C) Amplían el contexto de despliegue sin sustituir los fundamentos: el modelo de contenedor, la arquitectura de capas y los componentes constitutivos siguen siendo la base

<details><summary>Respuesta</summary>

**Correcta: C) Amplían el contexto de despliegue sin sustituir los fundamentos: el modelo de contenedor, la arquitectura de capas y los componentes constitutivos siguen siendo la base** Tanto un servidor Jakarta EE tradicional como un microservicio Quarkus en Kubernetes comparten esa misma base conceptual.

*Referencia: §4 [JAKARTA-PLAT]*
</details>

---
