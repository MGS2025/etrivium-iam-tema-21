# Tema 21 — Catálogo de Diagramas

> **Título oficial**: La arquitectura Java EE: características de funcionamiento. Elementos constitutivos. Productos y herramientas.
>
> **Versión**: v1.0
> **Fecha**: 2026-07-13
> **Autor**: ETRIVIUM
> **Formato**: SVG inline (zero-dependencias, escalable, imprimible, accesible con role/aria-label)
> **Paleta**: Ayuntamiento de Madrid #0055a0 (primario) + #d13c3c (alertas) + #2d8659 (ventajas) + #e89822 (callouts)
> **Nota técnica**: las clases CSS de cada SVG llevan sufijo numérico único (`.t1`, `.h1`…) para evitar colisiones de estilos entre los 12 diagramas embebidos en la misma página.

---

## Índice de diagramas

| ID | Título | Sección | Tipo | Formato |
|---|---|---|---|---|
| D1 | De J2EE a Jakarta EE: línea de tiempo | §1.3 | Línea de tiempo | 680×320 |
| D2 | Arquitectura de capas y contenedores | §2.2 | Bloques apilados | 680×340 |
| D3 | Servicios transversales del contenedor | §2.1 | Radial | 660×360 |
| D4 | JAAS/Jakarta Security: flujo de autenticación y autorización | §2.1.1 | Flujo | 680×320 |
| D5 | Empaquetado: WAR / EJB-JAR / EAR | §2.1.4 | Jerarquía | 640×320 |
| D6 | JVM tradicional (JIT) frente a GraalVM Native Image (AOT) | §2.1.5 | Comparativa | 680×320 |
| D7 | Ciclo de vida de una petición Servlet/JSF | §2.3.1 | Flujo | 680×320 |
| D8 | REST (JAX-RS) frente a SOAP (JAX-WS) | §2.3.2 | Comparativa | 680×320 |
| D9 | Tipos de EJB: Stateless, Stateful, Singleton, MDB | §2.4.1 | Cheat sheet | 680×340 |
| D10 | CDI: ámbitos (scopes) e inyección de dependencias | §2.4.2 | Bloques | 680×340 |
| D11 | Capa de persistencia: JDBC → JPA → JTA | §2.5 | Flujo | 680×340 |
| D12 | Pirámide de pruebas y observabilidad | §3.1-3.3 | Pirámide | 640×360 |

---

## D1 · De J2EE a Jakarta EE: línea de tiempo

**Sección**: §1.3 — De Java EE a Jakarta EE: evolución y gobernanza
**Propósito**: Fijar los hitos 1999 (J2EE), 2006 (anotaciones), 2017-2019 (transferencia a Eclipse) y 2020 (namespace jakarta.*).

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 320" role="img" aria-label="Línea de tiempo de J2EE 1999 a Jakarta EE actual, con los hitos de introducción de anotaciones en 2006, transferencia a la Eclipse Foundation en 2017-2019 y cambio de namespace javax a jakarta en 2020">
  <style>.t1{font:700 11px system-ui,sans-serif;fill:#fff}.s1{font:9.5px system-ui,sans-serif;fill:#fff}.l1{font:11px system-ui,sans-serif;fill:#444}.h1{font:700 13px system-ui,sans-serif;fill:#0055a0}</style>
  <text x="340" y="22" text-anchor="middle" class="h1">De J2EE (1999) a Jakarta EE (actual)</text>
  <line x1="40" y1="60" x2="640" y2="60" stroke="#0055a0" stroke-width="3"/>
  <circle cx="60" cy="60" r="7" fill="#0055a0"/><text x="60" y="42" text-anchor="middle" class="l1">1999</text><text x="60" y="80" text-anchor="middle" style="font:700 10.5px system-ui;fill:#0055a0">J2EE 1.2</text>
  <circle cx="200" cy="60" r="7" fill="#0055a0"/><text x="200" y="42" text-anchor="middle" class="l1">2006</text><text x="200" y="80" text-anchor="middle" style="font:700 10.5px system-ui;fill:#0055a0">Java EE 5</text>
  <circle cx="320" cy="60" r="6" fill="#888"/><text x="320" y="42" text-anchor="middle" class="l1">2009</text><text x="320" y="80" text-anchor="middle" class="l1">Java EE 6</text>
  <circle cx="440" cy="60" r="6" fill="#888"/><text x="440" y="42" text-anchor="middle" class="l1">2017</text><text x="440" y="80" text-anchor="middle" class="l1">Java EE 8</text>
  <circle cx="540" cy="60" r="7" fill="#d13c3c"/><text x="540" y="42" text-anchor="middle" class="l1">2018-19</text><text x="540" y="80" text-anchor="middle" style="font:700 10.5px system-ui;fill:#d13c3c">→ Eclipse</text>
  <circle cx="620" cy="60" r="7" fill="#d13c3c"/><text x="620" y="42" text-anchor="middle" class="l1">2020</text><text x="620" y="80" text-anchor="middle" style="font:700 10.5px system-ui;fill:#d13c3c">Jakarta 9</text>
  <rect x="20" y="100" width="220" height="50" rx="5" fill="#0055a0"/><text x="130" y="122" text-anchor="middle" class="t1">J2EE 1.2 (1999)</text><text x="130" y="140" text-anchor="middle" class="s1">Modelo pesado, mucho XML</text>
  <rect x="250" y="100" width="220" height="50" rx="5" fill="#3778b5"/><text x="360" y="122" text-anchor="middle" class="t1">Java EE 5 (2006)</text><text x="360" y="140" text-anchor="middle" class="s1">Giro a ANOTACIONES, menos XML</text>
  <rect x="480" y="100" width="180" height="50" rx="5" fill="#2d8659"/><text x="570" y="122" text-anchor="middle" class="t1">Java EE 6 (2009)</text><text x="570" y="140" text-anchor="middle" class="s1">Nace CDI</text>
  <rect x="60" y="164" width="260" height="54" rx="5" fill="#d13c3c"/><text x="190" y="186" text-anchor="middle" class="t1">Transferencia a Eclipse (2018-19)</text><text x="190" y="204" text-anchor="middle" class="s1">Oracle conserva la marca «Java» → renombrado</text>
  <rect x="340" y="164" width="280" height="54" rx="5" fill="#e89822"/><text x="480" y="186" text-anchor="middle" class="t1">Jakarta EE 9 (2020)</text><text x="480" y="204" text-anchor="middle" class="s1">«Big Bang Renaming»: javax.* → jakarta.*</text>
  <text x="340" y="248" text-anchor="middle" style="font:700 11px system-ui;fill:#0055a0">El renombrado es consecuencia LEGAL (marca), no una decisión técnica</text>
  <text x="340" y="268" text-anchor="middle" class="l1">jakarta.* es una ruptura binaria, no solo un cambio de nombre de paquete</text>
  <text x="670" y="312" text-anchor="end" style="font:11px system-ui;fill:#666">[Fuente: JAKARTA-PLAT; GONCALVES]</text>
</svg>
```

---

## D2 · Arquitectura de capas y contenedores

**Sección**: §2.2 — Arquitectura de capas
**Propósito**: Mostrar las tres capas (presentación, negocio, persistencia) y su relación con los contenedores web y EJB del servidor de aplicaciones.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 340" role="img" aria-label="Arquitectura de capas Java EE: capa de presentación e integración con contenedor web, capa de negocio con contenedor EJB, y capa de persistencia y datos, con dependencias unidireccionales de arriba hacia abajo">
  <style>.t2{font:700 12px system-ui,sans-serif;fill:#fff}.s2{font:10.5px system-ui,sans-serif;fill:#fff}.l2{font:11px system-ui,sans-serif;fill:#444}.h2{font:700 13px system-ui,sans-serif;fill:#0055a0}</style>
  <text x="340" y="20" text-anchor="middle" class="h2">Arquitectura de capas: dependencias unidireccionales ↓</text>
  <rect x="70" y="36" width="540" height="70" rx="6" fill="#0055a0"/>
  <text x="340" y="58" text-anchor="middle" class="t2">CAPA DE PRESENTACIÓN / INTEGRACIÓN (§2.3)</text>
  <text x="340" y="76" text-anchor="middle" class="s2">Servlets · JSF · JAX-RS (REST) · JAX-WS (SOAP)</text>
  <text x="340" y="94" text-anchor="middle" class="s2">Contenedor WEB</text>
  <path d="M340 106 L340 130" stroke="#888" stroke-width="3" marker-end="url(#a2)"/>
  <rect x="70" y="132" width="540" height="70" rx="6" fill="#2d8659"/>
  <text x="340" y="154" text-anchor="middle" class="t2">CAPA DE NEGOCIO (§2.4)</text>
  <text x="340" y="172" text-anchor="middle" class="s2">EJB (Session/MDB) · CDI · Jakarta Batch</text>
  <text x="340" y="190" text-anchor="middle" class="s2">Contenedor EJB</text>
  <path d="M340 202 L340 226" stroke="#888" stroke-width="3" marker-end="url(#a2)"/>
  <rect x="70" y="228" width="540" height="70" rx="6" fill="#e89822"/>
  <text x="340" y="250" text-anchor="middle" class="t2">CAPA DE PERSISTENCIA Y DATOS (§2.5)</text>
  <text x="340" y="268" text-anchor="middle" class="s2">JMS · JDBC · JTA · JPA · JCache</text>
  <text x="340" y="286" text-anchor="middle" class="s2">Base de datos / colas / recursos externos</text>
  <defs><marker id="a2" markerWidth="9" markerHeight="9" refX="4.5" refY="4.5" orient="auto"><path d="M0 0 L9 4.5 L0 9 z" fill="#888"/></marker></defs>
  <text x="340" y="316" text-anchor="middle" style="font:700 11px system-ui;fill:#d13c3c">La persistencia NUNCA conoce la presentación — el acoplamiento va solo hacia abajo</text>
  <text x="670" y="332" text-anchor="end" style="font:11px system-ui;fill:#666">[Fuente: FOWLER-EAA; GONCALVES, cap. 2]</text>
</svg>
```

---

## D3 · Servicios transversales del contenedor

**Sección**: §2.1 — Componentes transversales
**Propósito**: Situar los cinco servicios transversales que el contenedor presta a todas las capas.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 660 360" role="img" aria-label="Cinco servicios transversales que el contenedor presta a todas las capas: seguridad JAAS, servicios de directorio JNDI, gestión de dependencias con Maven o Gradle, empaquetado y ciclo de vida, y servidores de aplicaciones">
  <style>.t3{font:700 11px system-ui,sans-serif;fill:#fff}.s3{font:9.5px system-ui,sans-serif;fill:#fff}.l3{font:11px system-ui,sans-serif;fill:#444}.h3{font:700 13px system-ui,sans-serif;fill:#0055a0}</style>
  <text x="330" y="22" text-anchor="middle" class="h3">Servicios transversales — comunes a todas las capas</text>
  <circle cx="330" cy="190" r="58" fill="#0055a0"/>
  <text x="330" y="184" text-anchor="middle" class="t3">CONTENEDOR</text>
  <text x="330" y="200" text-anchor="middle" class="s3">servidor de</text>
  <text x="330" y="212" text-anchor="middle" class="s3">aplicaciones</text>
  <rect x="30" y="50" width="170" height="54" rx="6" fill="#3778b5"/><text x="115" y="72" text-anchor="middle" class="t3">§2.1.1 Seguridad</text><text x="115" y="90" text-anchor="middle" class="s3">JAAS / Jakarta Security</text>
  <rect x="460" y="50" width="170" height="54" rx="6" fill="#2d8659"/><text x="545" y="72" text-anchor="middle" class="t3">§2.1.2 Directorio</text><text x="545" y="90" text-anchor="middle" class="s3">JNDI (recursos por nombre)</text>
  <rect x="30" y="256" width="170" height="54" rx="6" fill="#e89822"/><text x="115" y="278" text-anchor="middle" class="t3">§2.1.3 Construcción</text><text x="115" y="296" text-anchor="middle" class="s3">Maven / Gradle</text>
  <rect x="460" y="256" width="170" height="54" rx="6" fill="#c98a1f"/><text x="545" y="278" text-anchor="middle" class="t3">§2.1.4 Empaquetado</text><text x="545" y="296" text-anchor="middle" class="s3">WAR / EJB-JAR / EAR</text>
  <rect x="245" y="300" width="170" height="46" rx="6" fill="#d13c3c"/><text x="330" y="320" text-anchor="middle" class="t3">§2.1.5-6</text><text x="330" y="336" text-anchor="middle" class="s3">Nativo (GraalVM) · Servidores</text>
  <line x1="200" y1="77" x2="278" y2="160" stroke="#888" stroke-width="2"/>
  <line x1="460" y1="77" x2="382" y2="160" stroke="#888" stroke-width="2"/>
  <line x1="200" y1="283" x2="278" y2="216" stroke="#888" stroke-width="2"/>
  <line x1="460" y1="283" x2="382" y2="216" stroke="#888" stroke-width="2"/>
  <line x1="330" y1="248" x2="330" y2="300" stroke="#888" stroke-width="2"/>
  <text x="650" y="356" text-anchor="end" style="font:11px system-ui;fill:#666">[Fuente: JAKARTA-PLAT; GONCALVES, cap. 3]</text>
</svg>
```

---

## D4 · JAAS/Jakarta Security: flujo de autenticación y autorización

**Sección**: §2.1.1 — Seguridad y autenticación
**Propósito**: Trazar el flujo Subject → LoginModule → Realm y la separación autenticación/autorización.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 320" role="img" aria-label="Flujo de autenticación y autorización con JAAS: el subject se autentica mediante un LoginModule contra un realm, obtiene principals de usuario y rol, y después la autorización por rol decide si puede ejecutar la acción">
  <style>.t4{font:700 11px system-ui,sans-serif;fill:#fff}.s4{font:10px system-ui,sans-serif;fill:#fff}.l4{font:11px system-ui,sans-serif;fill:#444}.h4{font:700 13px system-ui,sans-serif;fill:#0055a0}</style>
  <text x="340" y="20" text-anchor="middle" class="h4">Autenticación (¿quién eres?) → Autorización (¿qué puedes hacer?)</text>
  <rect x="20" y="42" width="130" height="54" rx="6" fill="#0055a0"/><text x="85" y="64" text-anchor="middle" class="t4">SUBJECT</text><text x="85" y="82" text-anchor="middle" class="s4">usuario a autenticar</text>
  <path d="M150 69 L178 69" stroke="#888" stroke-width="2" marker-end="url(#a4)"/>
  <rect x="180" y="42" width="150" height="54" rx="6" fill="#3778b5"/><text x="255" y="64" text-anchor="middle" class="t4">LOGINMODULE</text><text x="255" y="82" text-anchor="middle" class="s4">mecanismo conectable</text>
  <path d="M330 69 L358 69" stroke="#888" stroke-width="2" marker-end="url(#a4)"/>
  <rect x="360" y="42" width="130" height="54" rx="6" fill="#2d8659"/><text x="425" y="64" text-anchor="middle" class="t4">REALM</text><text x="425" y="82" text-anchor="middle" class="s4">almacén de identidades</text>
  <path d="M425 96 L425 122" stroke="#888" stroke-width="2" marker-end="url(#a4)"/>
  <rect x="330" y="124" width="190" height="46" rx="6" fill="#e89822"/><text x="425" y="144" text-anchor="middle" class="t4">PRINCIPALS</text><text x="425" y="160" text-anchor="middle" class="s4">usuario + roles del Subject</text>
  <rect x="60" y="192" width="560" height="46" rx="6" fill="#fdf3e3" stroke="#e89822"/>
  <text x="340" y="220" text-anchor="middle" style="font:700 12px system-ui;fill:#8a5a00">AUTENTICACIÓN — verifica la identidad (¿quién eres?)</text>
  <rect x="60" y="248" width="560" height="46" rx="6" fill="#fdecec" stroke="#d13c3c"/>
  <text x="340" y="276" text-anchor="middle" style="font:700 12px system-ui;fill:#8a1f1f">AUTORIZACIÓN — @RolesAllowed decide si el Principal puede ejecutar la acción</text>
  <defs><marker id="a4" markerWidth="8" markerHeight="8" refX="4" refY="4" orient="auto"><path d="M0 0 L8 4 L0 8 z" fill="#888"/></marker></defs>
  <text x="670" y="312" text-anchor="end" style="font:11px system-ui;fill:#666">[Fuente: JAKARTA-SEC]</text>
</svg>
```

---

## D5 · Empaquetado: WAR / EJB-JAR / EAR

**Sección**: §2.1.4 — Empaquetado y ciclo de vida de las aplicaciones
**Propósito**: Fijar la jerarquía de contención EAR ⊃ {WAR, EJB-JAR, RAR}.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 640 320" role="img" aria-label="Jerarquía de empaquetado Java EE: el EAR contiene varios módulos WAR, EJB-JAR y RAR, cada uno con su propio classloader hijo, mientras que un WAR o EJB-JAR no puede contener un EAR">
  <style>.t5{font:700 12px system-ui,sans-serif;fill:#fff}.s5{font:10px system-ui,sans-serif;fill:#fff}.l5{font:11px system-ui,sans-serif;fill:#444}.h5{font:700 13px system-ui,sans-serif;fill:#0055a0}</style>
  <text x="320" y="20" text-anchor="middle" class="h5">EAR contiene WAR + EJB-JAR (+ RAR) — nunca al revés</text>
  <rect x="40" y="40" width="560" height="180" rx="8" fill="none" stroke="#0055a0" stroke-width="2" stroke-dasharray="6,4"/>
  <text x="320" y="60" text-anchor="middle" class="h5">EAR — Enterprise Archive (application.xml)</text>
  <rect x="70" y="76" width="150" height="60" rx="6" fill="#0055a0"/><text x="145" y="100" text-anchor="middle" class="t5">WAR</text><text x="145" y="118" text-anchor="middle" class="s5">presentación</text>
  <rect x="245" y="76" width="150" height="60" rx="6" fill="#2d8659"/><text x="320" y="100" text-anchor="middle" class="t5">EJB-JAR</text><text x="320" y="118" text-anchor="middle" class="s5">negocio</text>
  <rect x="420" y="76" width="150" height="60" rx="6" fill="#888"/><text x="495" y="100" text-anchor="middle" class="t5">RAR</text><text x="495" y="118" text-anchor="middle" class="s5">conector JCA</text>
  <text x="320" y="164" text-anchor="middle" class="l5">Cada módulo obtiene su propio classloader hijo</text>
  <text x="320" y="182" text-anchor="middle" class="l5">dentro del classloader de la aplicación (aislamiento de dependencias)</text>
  <text x="320" y="200" text-anchor="middle" style="font:700 11px system-ui;fill:#d13c3c">WAR/EJB-JAR NO pueden contener un EAR dentro</text>
  <rect x="60" y="236" width="520" height="56" rx="6" fill="#eef4fa" stroke="#0055a0"/>
  <text x="320" y="258" text-anchor="middle" style="font:700 12px system-ui;fill:#0055a0">Despliegue: copiar → deploy (classloader + inicialización) → ejecutando → undeploy</text>
  <text x="320" y="278" text-anchor="middle" class="l5">El servidor de aplicaciones gestiona todo el ciclo automáticamente</text>
  <text x="630" y="312" text-anchor="end" style="font:11px system-ui;fill:#666">[Fuente: JAKARTA-PLAT; JAKARTA-SERVLET]</text>
</svg>
```

---

## D6 · JVM tradicional (JIT) frente a GraalVM Native Image (AOT)

**Sección**: §2.1.5 — Compilación a nativo: GraalVM, Spring Boot y Quarkus
**Propósito**: Contrastar arranque, memoria y escenario idóneo de ambos modelos de compilación.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 320" role="img" aria-label="Comparación entre la JVM tradicional con compilación JIT en tiempo de ejecución, arranque en segundos, y GraalVM Native Image con compilación AOT en tiempo de construcción, arranque en milisegundos, usado por Quarkus y Spring Boot">
  <style>.t6{font:700 12px system-ui,sans-serif;fill:#fff}.s6{font:10.5px system-ui,sans-serif;fill:#fff}.l6{font:11px system-ui,sans-serif;fill:#444}.h6{font:700 13px system-ui,sans-serif;fill:#0055a0}</style>
  <text x="340" y="22" text-anchor="middle" class="h6">Dos estrategias de compilación para Java</text>
  <rect x="40" y="44" width="280" height="150" rx="8" fill="#3778b5"/>
  <text x="180" y="70" text-anchor="middle" class="t6">JVM TRADICIONAL (JIT)</text>
  <text x="180" y="94" text-anchor="middle" class="s6">Compila en tiempo de EJECUCIÓN</text>
  <text x="180" y="114" text-anchor="middle" class="s6">Arranque: SEGUNDOS</text>
  <text x="180" y="134" text-anchor="middle" class="s6">Memoria de partida: mayor</text>
  <text x="180" y="154" text-anchor="middle" class="s6">Óptimo: procesos de larga duración</text>
  <text x="180" y="174" text-anchor="middle" class="s6">Servidores Jakarta EE clásicos</text>
  <rect x="360" y="44" width="280" height="150" rx="8" fill="#2d8659"/>
  <text x="500" y="70" text-anchor="middle" class="t6">GRAALVM NATIVE IMAGE (AOT)</text>
  <text x="500" y="94" text-anchor="middle" class="s6">Compila en tiempo de CONSTRUCCIÓN</text>
  <text x="500" y="114" text-anchor="middle" class="s6">Arranque: MILISEGUNDOS</text>
  <text x="500" y="134" text-anchor="middle" class="s6">Memoria de partida: menor</text>
  <text x="500" y="154" text-anchor="middle" class="s6">Óptimo: contenedores efímeros, serverless</text>
  <text x="500" y="174" text-anchor="middle" class="s6">Usado por Quarkus y Spring Boot 3+</text>
  <text x="340" y="222" text-anchor="middle" style="font:700 11px system-ui;fill:#e89822">Native Image es una TECNOLOGÍA; Quarkus/Spring Boot son FRAMEWORKS que la aprovechan</text>
  <text x="340" y="244" text-anchor="middle" class="l6">Reflexión y proxies dinámicos requieren configuración explícita en compilación AOT</text>
  <text x="670" y="312" text-anchor="end" style="font:11px system-ui;fill:#666">[Fuente: GRAALVM-DOC; QUARKUS-DOC]</text>
</svg>
```

---

## D7 · Ciclo de vida de una petición Servlet/JSF

**Sección**: §2.3.1 — Servlets y JavaServer Faces
**Propósito**: Mostrar cómo una petición HTTP recorre el contenedor web hasta el servlet o JSF.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 320" role="img" aria-label="Ciclo de una petición HTTP en el contenedor web: llega al servlet único que despacha por verbo HTTP a doGet o doPost, o al FacesServlet que ejecuta el ciclo de seis fases de JSF sobre un managed bean CDI">
  <style>.t7{font:700 11px system-ui,sans-serif;fill:#fff}.s7{font:9.5px system-ui,sans-serif;fill:#fff}.l7{font:11px system-ui,sans-serif;fill:#444}.h7{font:700 13px system-ui,sans-serif;fill:#0055a0}</style>
  <text x="340" y="20" text-anchor="middle" class="h7">Petición HTTP → contenedor web → Servlet / JSF</text>
  <rect x="30" y="42" width="140" height="50" rx="6" fill="#0055a0"/><text x="100" y="62" text-anchor="middle" class="t7">Petición HTTP</text><text x="100" y="78" text-anchor="middle" class="s7">del navegador</text>
  <path d="M170 67 L198 67" stroke="#888" stroke-width="2" marker-end="url(#a7)"/>
  <rect x="200" y="42" width="150" height="50" rx="6" fill="#3778b5"/><text x="275" y="62" text-anchor="middle" class="t7">Contenedor web</text><text x="275" y="78" text-anchor="middle" class="s7">una instancia por servlet</text>
  <path d="M275 92 C 210 120 210 140 245 156" stroke="#2d8659" stroke-width="2" fill="none" marker-end="url(#a7)"/>
  <path d="M275 92 C 340 120 340 140 305 156" stroke="#e89822" stroke-width="2" fill="none" marker-end="url(#a7)"/>
  <rect x="120" y="158" width="180" height="50" rx="6" fill="#2d8659"/><text x="210" y="178" text-anchor="middle" class="t7">Servlet directo</text><text x="210" y="194" text-anchor="middle" class="s7">doGet() / doPost()</text>
  <rect x="330" y="158" width="220" height="50" rx="6" fill="#e89822"/><text x="440" y="178" text-anchor="middle" class="t7">FacesServlet (JSF)</text><text x="440" y="194" text-anchor="middle" class="s7">ciclo de 6 fases → managed bean CDI</text>
  <rect x="140" y="230" width="440" height="56" rx="6" fill="#eef4fa" stroke="#0055a0"/>
  <text x="360" y="252" text-anchor="middle" style="font:700 12px system-ui;fill:#0055a0">Una sola instancia atiende todas las peticiones (hilos distintos)</text>
  <text x="360" y="270" text-anchor="middle" class="l7">No guardar estado mutable en variables de instancia del servlet</text>
  <defs><marker id="a7" markerWidth="8" markerHeight="8" refX="4" refY="4" orient="auto"><path d="M0 0 L8 4 L0 8 z" fill="#888"/></marker></defs>
  <text x="670" y="312" text-anchor="end" style="font:11px system-ui;fill:#666">[Fuente: JAKARTA-SERVLET; JAKARTA-FACES]</text>
</svg>
```

---

## D8 · REST (JAX-RS) frente a SOAP (JAX-WS)

**Sección**: §2.3.2 — Servicios web: REST y SOAP
**Propósito**: Contrastar estilo/protocolo, formato, contrato y estado.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 320" role="img" aria-label="Comparación entre REST implementado con JAX-RS, un estilo arquitectónico sin estado sobre HTTP con JSON y contrato informal OpenAPI, y SOAP implementado con JAX-WS, un protocolo con sobre XML y contrato formal WSDL">
  <style>.t8{font:700 12px system-ui,sans-serif;fill:#fff}.s8{font:10.5px system-ui,sans-serif;fill:#fff}.l8{font:10.5px system-ui,sans-serif;fill:#444}.h8{font:700 13px system-ui,sans-serif;fill:#0055a0}</style>
  <text x="340" y="22" text-anchor="middle" class="h8">Dos modelos de servicio web en Jakarta EE</text>
  <rect x="30" y="42" width="300" height="150" rx="8" fill="#0055a0"/>
  <text x="180" y="66" text-anchor="middle" class="t8">REST — JAX-RS</text>
  <text x="180" y="88" text-anchor="middle" class="s8">Estilo arquitectónico sobre HTTP</text>
  <text x="180" y="106" text-anchor="middle" class="s8">Formato habitual: JSON</text>
  <text x="180" y="124" text-anchor="middle" class="s8">Contrato informal: OpenAPI/Swagger</text>
  <text x="180" y="142" text-anchor="middle" class="s8">SIN estado (stateless)</text>
  <text x="180" y="160" text-anchor="middle" class="s8">@Path @GET @POST @Produces</text>
  <rect x="350" y="42" width="300" height="150" rx="8" fill="#d13c3c"/>
  <text x="500" y="66" text-anchor="middle" class="t8">SOAP — JAX-WS</text>
  <text x="500" y="88" text-anchor="middle" class="s8">Protocolo de mensajería XML</text>
  <text x="500" y="106" text-anchor="middle" class="s8">Formato estricto: sobre XML + XSD</text>
  <text x="500" y="124" text-anchor="middle" class="s8">Contrato formal obligatorio: WSDL</text>
  <text x="500" y="142" text-anchor="middle" class="s8">Puede llevar estado en cabeceras</text>
  <text x="500" y="160" text-anchor="middle" class="s8">@WebService @WebMethod</text>
  <text x="340" y="222" text-anchor="middle" style="font:700 11px system-ui;fill:#0055a0">REST es un ESTILO, no un estándar cerrado — SOAP EXIGE sobre XML normalizado</text>
  <text x="340" y="242" text-anchor="middle" class="l8">Elección según el contexto de integración, no «cuál es mejor» de forma absoluta</text>
  <text x="670" y="312" text-anchor="end" style="font:11px system-ui;fill:#666">[Fuente: FIELDING2000; SOAP12]</text>
</svg>
```

---

## D9 · Tipos de EJB: Stateless, Stateful, Singleton, MDB

**Sección**: §2.4.1 — Enterprise JavaBeans
**Propósito**: Cheat sheet de los cuatro tipos de EJB vigentes (Entity Bean marcada como obsoleta).

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 340" role="img" aria-label="Cuatro tipos de EJB: Stateless sin estado con pool de instancias, Stateful con conversación e instancia dedicada, Singleton con una única instancia por aplicación, y Message-Driven Bean invocado de forma asíncrona por JMS">
  <style>.t9{font:700 11px system-ui,sans-serif;fill:#fff}.s9{font:9.5px system-ui,sans-serif;fill:#fff}.l9{font:11px system-ui,sans-serif;fill:#444}.h9{font:700 13px system-ui,sans-serif;fill:#0055a0}</style>
  <text x="340" y="20" text-anchor="middle" class="h9">Session Beans (Stateless/Stateful/Singleton) + Message-Driven Bean</text>
  <rect x="20" y="40" width="150" height="90" rx="6" fill="#0055a0"/><text x="95" y="62" text-anchor="middle" class="t9">STATELESS</text><text x="95" y="80" text-anchor="middle" class="s9">sin conversación</text><text x="95" y="94" text-anchor="middle" class="s9">pool de instancias</text><text x="95" y="108" text-anchor="middle" class="s9">intercambiables</text>
  <rect x="185" y="40" width="150" height="90" rx="6" fill="#3778b5"/><text x="260" y="62" text-anchor="middle" class="t9">STATEFUL</text><text x="260" y="80" text-anchor="middle" class="s9">con conversación</text><text x="260" y="94" text-anchor="middle" class="s9">instancia dedicada</text><text x="260" y="108" text-anchor="middle" class="s9">por cliente</text>
  <rect x="350" y="40" width="150" height="90" rx="6" fill="#2d8659"/><text x="425" y="62" text-anchor="middle" class="t9">SINGLETON</text><text x="425" y="80" text-anchor="middle" class="s9">una única instancia</text><text x="425" y="94" text-anchor="middle" class="s9">para toda la</text><text x="425" y="108" text-anchor="middle" class="s9">aplicación</text>
  <rect x="515" y="40" width="150" height="90" rx="6" fill="#e89822"/><text x="590" y="62" text-anchor="middle" class="t9">MDB</text><text x="590" y="80" text-anchor="middle" class="s9">invocación asíncrona</text><text x="590" y="94" text-anchor="middle" class="s9">consume mensajes</text><text x="590" y="108" text-anchor="middle" class="s9">JMS (§2.5.1)</text>
  <rect x="60" y="150" width="560" height="70" rx="6" fill="#fdecec" stroke="#d13c3c"/>
  <text x="340" y="172" text-anchor="middle" style="font:700 12px system-ui;fill:#8a1f1f">Entity Beans — MODELO OBSOLETO (Java EE 1.x-5)</text>
  <text x="340" y="192" text-anchor="middle" class="l9">Sustituidas por completo por JPA (§2.5.4) desde 2006 — no forman parte del modelo actual</text>
  <rect x="60" y="234" width="560" height="70" rx="6" fill="#eef4fa" stroke="#0055a0"/>
  <text x="340" y="256" text-anchor="middle" style="font:700 12px system-ui;fill:#0055a0">Todos gestionados por el contenedor EJB: transacciones, seguridad, concurrencia</text>
  <text x="340" y="276" text-anchor="middle" class="l9">@Stateless es el tipo por defecto y el más habitual en la capa de negocio</text>
  <text x="670" y="332" text-anchor="end" style="font:11px system-ui;fill:#666">[Fuente: JAKARTA-EJB]</text>
</svg>
```

---

## D10 · CDI: ámbitos (scopes) e inyección de dependencias

**Sección**: §2.4.2 — Contexts and Dependency Injection
**Propósito**: Cheat sheet de los cinco ámbitos CDI y del mecanismo de inyección por tipo.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 340" role="img" aria-label="Ámbitos CDI: RequestScoped dura una petición, SessionScoped dura la sesión del usuario, ApplicationScoped es una única instancia compartida por toda la aplicación, ConversationScoped dura un flujo definido, y Dependent hereda el ciclo de vida de quien lo inyecta">
  <style>.t10{font:700 11px system-ui,sans-serif;fill:#fff}.s10{font:9.5px system-ui,sans-serif;fill:#fff}.l10{font:11px system-ui,sans-serif;fill:#444}.h10{font:700 13px system-ui,sans-serif;fill:#0055a0}</style>
  <text x="340" y="20" text-anchor="middle" class="h10">@Inject resuelve por TIPO — cada bean vive en un ámbito (scope)</text>
  <rect x="20" y="40" width="200" height="60" rx="6" fill="#0055a0"/><text x="120" y="62" text-anchor="middle" class="t10">@RequestScoped</text><text x="120" y="80" text-anchor="middle" class="s10">dura UNA petición HTTP</text>
  <rect x="230" y="40" width="200" height="60" rx="6" fill="#3778b5"/><text x="330" y="62" text-anchor="middle" class="t10">@SessionScoped</text><text x="330" y="80" text-anchor="middle" class="s10">dura la sesión del usuario</text>
  <rect x="440" y="40" width="220" height="60" rx="6" fill="#2d8659"/><text x="550" y="62" text-anchor="middle" class="t10">@ApplicationScoped</text><text x="550" y="80" text-anchor="middle" class="s10">1 instancia · toda la app</text>
  <rect x="20" y="112" width="300" height="60" rx="6" fill="#e89822"/><text x="170" y="134" text-anchor="middle" class="t10">@ConversationScoped</text><text x="170" y="152" text-anchor="middle" class="s10">dura un flujo multipaso definido</text>
  <rect x="340" y="112" width="320" height="60" rx="6" fill="#888"/><text x="500" y="134" text-anchor="middle" class="t10">@Dependent (por defecto)</text><text x="500" y="152" text-anchor="middle" class="s10">hereda el ciclo de vida del bean que lo inyecta</text>
  <rect x="60" y="192" width="560" height="70" rx="6" fill="#eef4fa" stroke="#0055a0"/>
  <text x="340" y="214" text-anchor="middle" style="font:700 12px system-ui;fill:#0055a0">@Inject resuelve por TIPO (con qualifiers si hay ambigüedad)</text>
  <text x="340" y="234" text-anchor="middle" class="l10">JNDI (§2.1.2), en cambio, resuelve por NOMBRE — distinción clave de examen</text>
  <rect x="60" y="272" width="560" height="52" rx="6" fill="#fdf3e3" stroke="#e89822"/>
  <text x="340" y="294" text-anchor="middle" style="font:700 11.5px system-ui;fill:#8a5a00">@ApplicationScoped ≈ patrón Singleton (Tema 20) gestionado por el contenedor</text>
  <text x="340" y="312" text-anchor="middle" class="l10">@Observes (eventos) aplica el patrón Observer de forma declarativa</text>
  <text x="670" y="336" text-anchor="end" style="font:11px system-ui;fill:#666">[Fuente: JAKARTA-CDI]</text>
</svg>
```

---

## D11 · Capa de persistencia: JDBC → JPA → JTA

**Sección**: §2.5 — Capa de persistencia y datos
**Propósito**: Trazar el flujo completo desde un bean de negocio hasta la base de datos, con JTA coordinando la transacción.

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 680 340" role="img" aria-label="Flujo de persistencia: un EJB o CDI bean con transacción gestionada por el contenedor usa el EntityManager de JPA, que internamente genera SQL ejecutado vía JDBC sobre un DataSource localizado por JNDI, todo coordinado por JTA con commit en dos fases si hay varios recursos">
  <style>.t11{font:700 11px system-ui,sans-serif;fill:#fff}.s11{font:9.5px system-ui,sans-serif;fill:#fff}.l11{font:11px system-ui,sans-serif;fill:#444}.h11{font:700 13px system-ui,sans-serif;fill:#0055a0}</style>
  <text x="340" y="20" text-anchor="middle" class="h11">EJB/CDI → JPA (EntityManager) → JDBC (DataSource) → BD</text>
  <rect x="20" y="42" width="140" height="56" rx="6" fill="#0055a0"/><text x="90" y="64" text-anchor="middle" class="t11">EJB / CDI</text><text x="90" y="82" text-anchor="middle" class="s11">lógica de negocio</text>
  <path d="M160 70 L188 70" stroke="#888" stroke-width="2" marker-end="url(#a11)"/>
  <rect x="190" y="42" width="150" height="56" rx="6" fill="#3778b5"/><text x="265" y="64" text-anchor="middle" class="t11">JPA</text><text x="265" y="82" text-anchor="middle" class="s11">EntityManager · JPQL</text>
  <path d="M340 70 L368 70" stroke="#888" stroke-width="2" marker-end="url(#a11)"/>
  <rect x="370" y="42" width="150" height="56" rx="6" fill="#2d8659"/><text x="445" y="64" text-anchor="middle" class="t11">JDBC</text><text x="445" y="82" text-anchor="middle" class="s11">DataSource (JNDI)</text>
  <path d="M520 70 L548 70" stroke="#888" stroke-width="2" marker-end="url(#a11)"/>
  <rect x="550" y="42" width="110" height="56" rx="6" fill="#888"/><text x="605" y="64" text-anchor="middle" class="t11">BD</text><text x="605" y="82" text-anchor="middle" class="s11">relacional</text>
  <rect x="120" y="132" width="460" height="70" rx="6" fill="#e89822"/>
  <text x="350" y="156" text-anchor="middle" style="font:700 12px system-ui;fill:#fff">JTA — coordina la transacción</text>
  <text x="350" y="176" text-anchor="middle" class="s11">CMT (contenedor, por defecto) o BMT (programático)</text>
  <text x="350" y="192" text-anchor="middle" class="s11">Varios recursos → commit en dos fases (2PC)</text>
  <path d="M265 98 L280 132" stroke="#888" stroke-width="1.5" fill="none"/>
  <path d="M445 98 L420 132" stroke="#888" stroke-width="1.5" fill="none"/>
  <rect x="60" y="224" width="560" height="52" rx="6" fill="#eef4fa" stroke="#0055a0"/>
  <text x="340" y="246" text-anchor="middle" style="font:700 11.5px system-ui;fill:#0055a0">JPA NO sustituye JDBC — el proveedor JPA genera y ejecuta SQL vía JDBC</text>
  <text x="340" y="264" text-anchor="middle" class="l11">JPQL opera sobre entidades; SQL opera sobre tablas y columnas físicas</text>
  <text x="670" y="332" text-anchor="end" style="font:11px system-ui;fill:#666">[Fuente: JAKARTA-JPA; JAKARTA-JTA]</text>
</svg>
```

---

## D12 · Pirámide de pruebas y observabilidad

**Sección**: §3.1-3.3 — APM, pruebas unitarias y pruebas de carga
**Propósito**: Situar JUnit/Mockito, JMeter y APM en sus fases del ciclo de vida (desarrollo/preproducción/producción).

```svg
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 640 360" role="img" aria-label="Pirámide de pruebas: base ancha de pruebas unitarias con JUnit y Mockito, nivel intermedio de pruebas de carga con JMeter antes del despliegue, y vigilancia continua en producción con herramientas APM">
  <style>.t12{font:700 11px system-ui,sans-serif;fill:#fff}.s12{font:9.5px system-ui,sans-serif;fill:#fff}.l12{font:11px system-ui,sans-serif;fill:#444}.h12{font:700 13px system-ui,sans-serif;fill:#0055a0}</style>
  <text x="320" y="20" text-anchor="middle" class="h12">De la pirámide de pruebas a la observabilidad en producción</text>
  <polygon points="320,40 420,110 220,110" fill="#d13c3c"/>
  <text x="320" y="82" text-anchor="middle" class="t12">APM</text>
  <text x="320" y="98" text-anchor="middle" class="s12">producción, continuo</text>
  <polygon points="220,112 420,112 460,182 180,182" fill="#e89822"/>
  <text x="320" y="140" text-anchor="middle" class="t12">JMETER</text>
  <text x="320" y="158" text-anchor="middle" class="s12">carga / estrés / resistencia</text>
  <text x="320" y="174" text-anchor="middle" class="s12">antes del despliegue</text>
  <polygon points="180,184 460,184 520,280 120,280" fill="#2d8659"/>
  <text x="320" y="220" text-anchor="middle" class="t12">JUNIT + MOCKITO</text>
  <text x="320" y="240" text-anchor="middle" class="s12">pruebas unitarias con mocks</text>
  <text x="320" y="258" text-anchor="middle" class="s12">base de la pirámide, ejecución continua</text>
  <rect x="60" y="296" width="520" height="52" rx="6" fill="#eef4fa" stroke="#0055a0"/>
  <text x="320" y="318" text-anchor="middle" style="font:700 11.5px system-ui;fill:#0055a0">JUnit organiza y ejecuta · Mockito aísla dependencias · JMeter carga · APM observa</text>
  <text x="320" y="336" text-anchor="middle" class="l12">APM monitoriza en continuo; las pruebas de carga son puntuales, antes de desplegar</text>
  <text x="630" y="356" text-anchor="end" style="font:11px system-ui;fill:#666">[Fuente: JUNIT5-DOC; MOCKITO-DOC; JMETER-DOC]</text>
</svg>
```

---

*Los 12 diagramas usan la misma paleta y convenciones de accesibilidad que el resto de la serie técnica (T11-T20). Ver QA de caja contenedora en tema-21-validacion.md.*
