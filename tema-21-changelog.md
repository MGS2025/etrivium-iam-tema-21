# Tema 21 — Changelog

> **Título oficial**: La arquitectura Java EE: características de funcionamiento. Elementos constitutivos. Productos y herramientas.

---

## v1.3 — 2026-10-01 — Normas vigentes y correcciones comunes de la revisión

**Motivo**: revisión de la serie del 01-10-2026 (decisiones de Joan y María): normas caducadas con el patrón de dos filas en Fuentes y correcciones comunes (referencias al cliente y al origen del material, promesas sobre el examen, AP → AAPP).

### Cambios

- **ISO/IEC 25010:2011 → 25010:2023** en Fuentes (vigente + histórica); «portabilidad» → «flexibilidad (la antigua portabilidad)»; la cita en línea de §3 dice «ISO/IEC 25010:2023».
- Leyenda de las cajas: se quita «con alta probabilidad de aparecer en el test oficial».
- Fuera las promesas sobre el examen en contenido, diagrama D10 y explicaciones de cuatro preguntas del test (sin cambio de enunciado, opciones ni respuesta).
- Fuera las menciones «decisión de Joan» (contenido, caso práctico y fuentes).
- Títulos de las cajas homogeneizados con los temas 1-10 (revisión jurídica): «Dato clave», «Ejemplo de aplicación en el Ayto» y «Relación con otros temas»; las cajas «Ejercicio resuelto» no cambian.

---

## v1.2 — 2026-09-06 — Corrección de formato en el conversor

**Estado**: pendiente de validación por el IAM.

**Motivo**: el texto mostraba marcas de Markdown sin convertir (`**`) en la pestaña de Contenido y en la de Fuentes.

### Alcance

- Se porta a este tema el **arreglo del conversor** que la serie incorporó a partir del Tema 28: la negrita se procesa **antes** que la cursiva y sin ser codiciosa, de modo que `**negrita con *cursiva* dentro**` se convierte bien.
- Se reescriben dos frases donde la negrita envolvía un fragmento de código con asterisco (`` `jakarta.*` ``, `` `javax.*` ``), que el conversor no podía emparejar.
- **Sin cambios de contenido**: solo formato. El defecto venía de la primera publicación del tema.

---

## v1.2 — 2026-09-06 — Marcado del apartado complementario

**Estado**: pendiente de validación por el IAM.

**Motivo**: criterio de literalidad del título fijado por el IAM (Jesús Cuadrado, 02-09-2026).

### Alcance

- El apartado final que **el enunciado oficial del tema no nombra** queda marcado como **material complementario**, en el índice y al principio del propio apartado, con la advertencia de que lo exigible es lo que enumera el título.
- **Sin cambios de contenido**: el apartado se mantiene íntegro.

---

## v1.1 — 2026-09-06 — Ficha de extensión y tiempo de estudio

**Estado**: sin cambios de contenido. Solo se añade información sobre el propio tema.

**Motivo**: petición del IAM (Jesús Cuadrado, 02-09-2026) al validar el Tema 30. Acepta la extensión de los temas «compuestos» a condición de que se informe de «su extensión en palabras y tiempo estimado de estudio». Al revisarlo se vio que ese dato solo aparecía en 16 de los 40 temas, y que faltaba justo en los más largos.

### Alcance

- Ficha bajo la cabecera del tema, y al final de la pestaña Índice donde esa pestaña existe:
  - **Extensión**: ~11.000 palabras · 12 diagramas · 60 preguntas de test
  - **Tiempo estimado de estudio**: 11-13 horas (primera vuelta completa, sin contar repasos)
- La cifra de palabras de la tabla de entregables se sincroniza con la ficha, para que el tema no muestre dos recuentos distintos.
- Las horas salen de una fórmula común a los 40 temas, para que sean comparables entre sí: contenido a 1.500 palabras/hora (ritmo de estudio activo), diagramas a una hora por cada cinco y test a dos minutos por pregunta. Se publica como intervalo de dos horas.
- Generado con `_tools-qa/ficha_estudio.py`, idempotente y reejecutable tras cualquier regeneración con `build_tNN.py`.

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
