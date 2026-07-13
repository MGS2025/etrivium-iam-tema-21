# Tema 21 — Checklist de Validación

> **Título oficial**: La arquitectura Java EE: características de funcionamiento. Elementos constitutivos. Productos y herramientas.
> **Versión**: v1.0 — Pendiente validación
> **Fecha**: 2026-07-13
> **Revisores**: María y Ana (eTrivium) · revisión técnica IAM (Jesús Cuadrado)
> **Instrucciones**: marcar cada ítem. Los cambios no se guardan en la web (imprimir o exportar a PDF si se desea fijarlos).

---

## 1. Cobertura del temario oficial

- [ ] **Introducción a Java EE**: principios de la plataforma, evolución y contexto tecnológico, transferencia a Jakarta EE — §1.1-1.3
- [ ] **Elementos constitutivos**: componentes transversales (seguridad, JNDI, construcción, empaquetado, nativo, servidores), arquitectura de capas, capa de presentación/integración, capa de negocio, capa de persistencia y datos — §2.1-2.5
- [ ] **Herramientas de desarrollo**: APM, pruebas unitarias (JUnit/Mockito), pruebas de carga (JMeter), frameworks (Spring, Quarkus) — §3.1-3.4

## 2. Contenido teórico

- [ ] El nivel de profundidad (ampliado, con sección extra de Tendencias) es adecuado para C1 (¿hay que ampliar o recortar alguna sección?)
- [ ] Las definiciones de contenedor/inversión de control, especificación vs implementación, y la jerarquía de empaquetado son correctas
- [ ] La decisión de usar **snippets de código Java/Jakarta reales** (namespace `jakarta.*`) en lugar de pseudocódigo neutro es adecuada (¿o se prefiere un enfoque más conceptual, sin código?)
- [ ] La decisión de usar `jakarta.*` como namespace principal, con `javax.*` señalado como legado, es adecuada (¿o el entorno real del Ayuntamiento sigue en `javax.*` y conviene invertir el énfasis?)
- [ ] La frontera con el Tema 20 (POO, patrones de diseño), el Tema 22 (arquitecturas cliente/servidor y servicios web) y el Tema 23 (aplicaciones web front-end) está clara
- [ ] Los ejemplos Ayto Madrid (aplicación «Gestión de Expedientes y Tributos») son verosímiles y coherentes con el esquema de datos del Tema 19

## 3. Fuentes

- [ ] Todas las afirmaciones técnicas están respaldadas por fuente Tier 1 (especificaciones Jakarta EE/JSR u obras canónicas)
- [ ] Las referencias inline se corresponden con `tema-21-fuentes.md`
- [ ] Atribuciones históricas correctas (J2EE 1999, Java EE 5 anotaciones 2006, CDI 2009, transferencia a Eclipse 2017-2019, namespace jakarta.* 2020)

## 4. Test (60 preguntas)

- [ ] Cada pregunta tiene una sola respuesta correcta e inequívoca
- [ ] Los distractores (A/B/C) son plausibles
- [ ] La distribución de la opción correcta entre A/B/C está equilibrada (20/20/20)
- [ ] Las explicaciones y referencias de cada respuesta son correctas

## 5. Casos prácticos (3)

- [ ] Realistas y propios del Ayuntamiento (API REST de tributos, asistente de expedientes, persistencia y auditoría)
- [ ] Soluciones orientativas técnicamente correctas (código Java/Jakarta compilable en su forma simplificada)
- [ ] La puntuación de cada caso suma 10 puntos

## 6. Diagramas (12 SVG)

- [ ] Cada diagrama es correcto y legible (también impreso en B/N)
- [ ] Accesibilidad: todos tienen `role="img"` y `aria-label`
- [ ] Sin desbordes de texto ni colisiones de estilo entre SVG (clases con sufijo único, QA de caja contenedora)

## 7. Referencias cruzadas a otros temas

- [ ] Validadas contra BOAM 10.032 (T18, T19, T20, T22, T23, T25, T39)
- [ ] Ninguna referencia cruzada cita un enunciado de tema incorrecto

## 8. Calidad editorial

- [ ] Ortografía verificada (tildes y ñ) — sin diacríticos perdidos
- [ ] Coherencia de versión (v1.0) en title, badges, banner y footer del `index.html`
- [ ] El `index.html` abre, navega entre las 8 pestañas y el motor de test funciona
- [ ] Las listas anidadas del Contenido se muestran con sus niveles (sin aplanar)
- [ ] Los bloques de código Java/Jakarta se muestran correctamente formateados, sin markdown crudo

---

## Observaciones abiertas

_(Espacio para anotaciones de María, Ana y la revisión IAM.)_
