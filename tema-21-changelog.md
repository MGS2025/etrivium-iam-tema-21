# Tema 21 — Changelog

> **Título oficial**: La arquitectura Java EE: características de funcionamiento. Elementos constitutivos. Productos y herramientas.

---

## v1.0 — 2026-07-13 — Primera versión

**Estado**: pendiente de validación por María y Ana, y de revisión técnica del IAM (Jesús Cuadrado).

**Motivo**: desarrollo del Tema 21, dentro de la serie de temas técnicos generados desde cero (tras T11-T19), replicando la estructura y el formato de los Temas 1, 11, 17, 18 y 19 ya consolidados, con pestaña Índice y listas anidadas correctas desde el inicio. Generado a petición expresa de Joan, saltando T20 (POO) en la cola para atender primero este tema.

### Alcance de la v1.0

| Entregable | Cantidad |
|---|---|
| Contenido teórico | ~11.000 palabras · 4 secciones (3 del esqueleto oficial + Tendencias) con 25 epígrafes numerados |
| Diagramas SVG inline | 12 (accesibles con `role`/`aria-label`, clases con sufijo único anti-colisión) |
| Banco de preguntas tipo test | 60 preguntas A/B/C con explicación y referencia, balanceadas **20/20/20** |
| Casos prácticos | 3 (API REST segura de tributos; asistente multipaso de expedientes con EJB/CDI; persistencia JPA/JTA y caché de catálogo) · 10 puntos cada uno |
| Fuentes Tier 1 | 22 referencias canónicas (especificaciones Jakarta EE/JCP y obras de arquitectura empresarial: Goncalves, Bien, Fowler, GoF, Johnson, Fielding, SOAP/WSDL/UDDI) |

### Decisiones de generación

1. **Sin material de cliente**: solo el esqueleto `Test_Prompting/temas junio/21.md`. Desarrollado desde fuentes canónicas (especificaciones Jakarta EE/Eclipse Foundation, herederas de los JSR de Java EE/JCP) y obras de arquitectura empresarial, todas referenciadas.
2. **Estructura fiel al esqueleto oficial**, con numeración jerárquica de tres niveles en la sección «Elementos constitutivos» (2.1.1 … 2.5.5) para reflejar la profundidad real del esqueleto (H2 > H3 > H4), ampliada con una cuarta sección «Tendencias actuales en el desarrollo de aplicaciones empresariales Java» (decisión de Joan, mismo criterio que T18/T19).
3. **Ejemplos de código en Java/Jakarta EE reales** (decisión de Joan, a diferencia del pseudocódigo neutro de T18 o el ANSI SQL/pseudocódigo de T19): el tema trata específicamente de esta plataforma y sus APIs concretas — anotaciones `@Stateless`, `@Entity`, `@Path`, `@Inject`, etc.
4. **Namespace `jakarta.*` como convención principal** (decisión de Joan), vigente desde Jakarta EE 9 (2020), señalando `javax.*` como legado histórico donde es relevante para el examen (§1.3).
5. **Cuarta sección «Tendencias actuales» con marco duradero** (mismo criterio que T18/T19): cloud-native y contenedores, MicroProfile, programación reactiva, migración continua desde sistemas heredados, convergencia de ecosistemas — sin números de versión de producto que caduquen, subrayando que amplían el contexto de despliegue sin sustituir los fundamentos.
6. **Contexto Ayuntamiento de Madrid** con una aplicación de referencia única para todo el tema: «Gestión de Expedientes y Tributos» (front-end JSF/REST, negocio EJB/CDI, persistencia JPA sobre el esquema del Tema 19, notificaciones JMS), reutilizada en contenido, diagramas y casos.
7. **Frontera con temas vecinos** cuidada: POO y patrones de diseño al Tema 20 (base de EJB/CDI); arquitecturas cliente/servidor multicapa y protocolos de servicios web en general al Tema 22 (este tema se centra en cómo Java EE los implementa); desarrollo web front-end (HTML/XML/scripting) al Tema 23; SQL/JDBC de bajo nivel al Tema 19; ENS/seguridad normativa al Tema 39.
8. **Referencias cruzadas validadas contra BOAM 10.032**: T18 (procedimientos/funciones generales), T19 (SQL, JDBC), T20 (POO, patrones), T22 (arquitecturas multicapa y protocolos de servicios web), T23 (desarrollo web front-end), T39 (ENS). Todas comprobadas contra el enunciado oficial de cada tema.
9. **Anti-colisión de SVG**: las clases CSS de cada diagrama llevan **sufijo numérico único** (`.t1`…`.t12`), evitando el bug sistémico de estilos que leakean entre los 12 SVG embebidos en la misma página (lección de T5).

### Pendientes para QA / próxima iteración

- Validación de profundidad por María/Ana/IAM (¿alguna sección a ampliar o recortar, dada la amplitud del temario oficial de este tema?).
- Confirmación de si el entorno real del Ayuntamiento usa todavía `javax.*` en producción, lo que podría justificar invertir el énfasis del namespace en una v1.1.
- Verificación ortográfica con corrector es_ES (cuidado con falsos positivos por términos técnicos en inglés: contenedor de *servlets*, *pool*, *singleton*, *stateless*, *namespace*, *cloud-native*, *serverless*…).

### Origen

Generado el 2026-07-13 en el flujo de trabajo de eTrivium, replicando el patrón de los Temas 1 (v2.1), 11 (v3.2), 17 (v1.0), 18 (v1.0) y 19 (v1.0). `build_t21.py` y `_build_css.txt` persistidos en el repo.
