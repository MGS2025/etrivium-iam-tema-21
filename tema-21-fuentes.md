# Tema 21 — Fuentes

> **Título oficial**: La arquitectura Java EE.
>
> **Criterio**: todo dato del contenido cita un **ID** inline (p. ej. `[JAKARTA-PLAT]`). Tier 1 = especificaciones oficiales de la plataforma (Eclipse Foundation / antes JCP-Oracle) y obras canónicas de arquitectura de software empresarial; Tier 2 = documentación oficial de implementaciones y herramientas concretas (servidores de aplicaciones, frameworks, herramientas de build y de pruebas), citada para ilustrar sin atar el tema a un único producto; Tier 3 = material de apoyo y marco del puesto, no citado como contenido técnico.

---

## Tier 1 — Especificaciones oficiales y obras canónicas

| ID | Referencia |
|---|---|
| `[JAKARTA-PLAT]` | Eclipse Foundation. *Jakarta EE Platform Specification*, versión 10/11. jakarta.ee/specifications/platform. Especificación vigente de la plataforma, gobernada por el Jakarta EE Working Group desde la transferencia de Oracle en 2017-2019. |
| `[JSR366]` | Oracle/JCP. *JSR 366: Java Platform, Enterprise Edition 8 (Java EE 8) Specification* (2017). Última especificación de la plataforma bajo gobernanza Oracle/JCP antes de la transferencia a Eclipse. |
| `[JAKARTA-SERVLET]` | Eclipse Foundation. *Jakarta Servlet Specification*, versión 6.x (heredera de JSR 340/369). jakarta.ee/specifications/servlet. |
| `[JAKARTA-FACES]` | Eclipse Foundation. *Jakarta Faces (JSF) Specification*, versión 4.x (heredera de JSR 372). jakarta.ee/specifications/faces. |
| `[JAKARTA-REST]` | Eclipse Foundation. *Jakarta RESTful Web Services (JAX-RS) Specification*, versión 3.x (heredera de JSR 370/339/311). jakarta.ee/specifications/restful-ws. |
| `[JAKARTA-XMLWS]` | Eclipse Foundation / Oracle. *Jakarta XML Web Services (JAX-WS) Specification* (heredera de JSR 224), y *JAX-WS User Guide*. |
| `[JAKARTA-EJB]` | Eclipse Foundation. *Jakarta Enterprise Beans Specification*, versión 4.x (heredera de JSR 345/318). jakarta.ee/specifications/enterprise-beans. |
| `[JAKARTA-CDI]` | Eclipse Foundation. *Jakarta Contexts and Dependency Injection (CDI) Specification*, versión 4.x (heredera de JSR 365/346/299). jakarta.ee/specifications/cdi. |
| `[JAKARTA-BATCH]` | Eclipse Foundation / Oracle. *Jakarta Batch Specification*, versión 2.x (heredera de JSR 352). jakarta.ee/specifications/batch. |
| `[JAKARTA-MSG]` | Eclipse Foundation. *Jakarta Messaging (JMS) Specification*, versión 3.x (heredera de JSR 914/343). jakarta.ee/specifications/messaging. |
| `[JAKARTA-JTA]` | Eclipse Foundation. *Jakarta Transactions (JTA) Specification*, versión 2.x (heredera de JSR 907). jakarta.ee/specifications/transactions. |
| `[JAKARTA-JPA]` | Eclipse Foundation. *Jakarta Persistence (JPA) Specification*, versión 3.x (heredera de JSR 338/220). jakarta.ee/specifications/persistence. |
| `[JAKARTA-CACHE]` | JCP. *JSR 107: JCache — Java Temporary Caching API*. jcp.org/en/jsr/detail?id=107. |
| `[JAKARTA-SEC]` | Eclipse Foundation. *Jakarta Security Specification*, versión 3.x (heredera de JSR 375), y especificación histórica **JAAS** (*Java Authentication and Authorization Service*, JSR incorporado en J2SE 1.4). |
| `[ORACLE-JNDI]` | Oracle Corporation. *The Java Tutorials — Java Naming and Directory Interface (JNDI)*. docs.oracle.com/javase/jndi. API de Java SE (`javax.naming`), base de la localización de recursos en Java EE. |
| `[GONCALVES]` | Goncalves, A. *Beginning Jakarta EE* (Apress, ed. más reciente). Manual de referencia integral de la plataforma, capa por capa. |
| `[BIEN]` | Bien, A. *Real World Java EE Patterns — Rethinking Best Practices*. Patrones de diseño aplicados y simplificación arquitectónica en EJB/CDI moderno. |
| `[FOWLER-EAA]` | Fowler, M. *Patterns of Enterprise Application Architecture* (Addison-Wesley, 2002). Fundamento de los patrones de capas (*Layers*), *Data Access Object*, *Data Mapper*, *Service Layer* aplicables a Java EE. |
| `[GOF]` | Gamma, E.; Helm, R.; Johnson, R.; Vlissides, J. *Design Patterns: Elements of Reusable Object-Oriented Software* (Addison-Wesley, 1994). Base de los patrones que informan Factory/Proxy/Decorator usados por los contenedores EJB/CDI. |
| `[JOHNSON2002]` | Johnson, R. *Expert One-on-One J2EE Design and Development* (Wrox, 2002). Crítica influyente a la complejidad de EJB 2.x que impulsó la creación de Spring Framework. |
| `[FIELDING2000]` | Fielding, R. T. *Architectural Styles and the Design of Network-based Software Architectures* (tesis doctoral, UC Irvine, 2000). Origen del estilo arquitectónico **REST**, fundamento teórico de JAX-RS. |
| `[SOAP12]` | W3C. *SOAP Version 1.2 Specification*. w3.org/TR/soap12. |
| `[WSDL20]` | W3C. *Web Services Description Language (WSDL) Version 2.0*. w3.org/TR/wsdl20. |
| `[UDDI3]` | OASIS. *UDDI Version 3.0.2 Specification*. Especificación del registro de servicios web *Universal Description, Discovery and Integration*. |

## Tier 2 — Documentación de implementaciones y herramientas

| ID | Referencia |
|---|---|
| `[SPRING-DOC]` | VMware/Spring Team. *Spring Framework Reference Documentation* (Core, MVC, Data, Batch, Cloud). docs.spring.io. |
| `[QUARKUS-DOC]` | Red Hat. *Quarkus Documentation* — «Supersonic Subatomic Java», compilación nativa con GraalVM. quarkus.io/guides. |
| `[GRAALVM-DOC]` | Oracle Labs. *GraalVM Native Image Reference Manual*. graalvm.org/reference-manual/native-image. |
| `[MAVEN-DOC]` | Apache Software Foundation. *Apache Maven — Introduction to the Build Lifecycle*. maven.apache.org/guides. |
| `[GRADLE-DOC]` | Gradle Inc. *Gradle User Manual — Build Lifecycle*. docs.gradle.org. |
| `[JUNIT5-DOC]` | JUnit Team. *JUnit 5 User Guide*. junit.org/junit5/docs/current/user-guide. |
| `[MOCKITO-DOC]` | Mockito contributors. *Mockito Framework Site*. javadoc.io/doc/org.mockito/mockito-core. |
| `[JMETER-DOC]` | Apache Software Foundation. *Apache JMeter User's Manual*. jmeter.apache.org/usermanual. |
| `[GLASSFISH-DOC]` | Eclipse Foundation. *Eclipse GlassFish Documentation* — servidor de referencia (RI) de Jakarta EE. glassfish.org. |
| `[WILDFLY-DOC]` | Red Hat. *WildFly Documentation*. docs.wildfly.org. |
| `[OPENAPI]` | OpenAPI Initiative. *OpenAPI Specification* (evolución de Swagger). spec.openapis.org. |

## Tier 3 — Marco de calidad y del puesto (contexto, no contenido técnico)

| ID | Referencia |
|---|---|
| `[ISO25010]` | ISO/IEC 25010:2023 *Systems and software Quality Requirements and Evaluation (SQuaRE) — Product quality model*. Anula y sustituye a la ISO/IEC 25010:2011: es la edición vigente del modelo de calidad del producto — mantenibilidad, flexibilidad (la antigua «portabilidad») y eficiencia de desempeño, aplicables a la elección de arquitectura de capas y a la compilación nativa. |
| `[ISO25010-2011]` | ISO/IEC 25010:2011 *Systems and software Quality Requirements and Evaluation (SQuaRE) — System and software quality models*. Anulada y sustituida por la ISO/IEC 25010:2023. Se conserva la referencia porque es la que recogen los temarios al uso. |
| `[ENS]` | Real Decreto 311/2022, Esquema Nacional de Seguridad — requisitos de autenticación, trazabilidad y cifrado en transporte, relevantes para la capa de seguridad de una aplicación Java EE municipal. |
| `[BOAM10032]` | BOAM 10.032 (23-dic-2025). Bases específicas TIC C1 Ayto. Madrid — temario oficial. |

---

*Las referencias Tier 1 fijan el fundamento normativo (especificaciones Jakarta EE, herederas de las de Java EE/J2EE bajo JCP-Oracle) y las obras canónicas de arquitectura empresarial, y son la base de todo el contenido; Tier 2 documenta las implementaciones y herramientas concretas citadas como ejemplo (Spring, Quarkus, GraalVM, Maven/Gradle, JUnit/Mockito, JMeter, GlassFish/WildFly) sin que el tema dependa de ninguna en particular; Tier 3 enmarca la calidad y la seguridad aplicables en el Ayuntamiento de Madrid. Los ejemplos de código usan el **namespace `jakarta.*`** vigente desde Jakarta EE 9, señalando el namespace histórico `javax.*` como legado allí donde es relevante.*
