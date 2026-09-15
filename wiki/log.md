# Registro (Log) — Cerebro Digital

Registro cronológico append-only. Cada entrada empieza con un prefijo consistente:
`## [AAAA-MM-DD] ingest|query|lint | descripción`.

Filtrar con: `grep "^## \[" wiki/log.md | tail -5`

---

## [2026-08-13] init | Inicialización del cerebro digital

Se instancia el patrón "LLM Wiki" para el área (mixta: contable · legal · operativa).
Creada la estructura de tres capas (`raw/`, `wiki/`, `CLAUDE.md`), los archivos base
(`index.md`, `log.md`, `overview.md`) y las carpetas de categorías. Listo para ingerir
las primeras fuentes.

## [2026-08-13] ingest | Manual de Políticas Contables y Financieras — Manta Seguros

Ingerido el `.docx` fundacional del área (48 secciones, 9 partes; + 6 comentarios de
revisión de Alex Swift). Movido a `raw/documentos/manual-politicas-contables-financieras-manta.docx`.

- **Fuente:** [[fuentes/manual-politicas-contables-manta]].
- **Síntesis:** [[sintesis/libros-contables-de-manta]] (responde la consulta previa sobre los libros).
- **Entidades creadas (6):** manta-seguros, superintendencia-financiera, adres, ansv, netsuite, erika-guerrero.
- **Conceptos creados (15):** estructura-multi-book, soat, niif-17, niif-4, paa, lrc-y-lic,
  reservas-tecnicas-soat, cuif, columna-contexto, reaseguro-quota-share, ajuste-por-riesgo-no-financiero,
  transferencias-adres-ansv, instrumentos-financieros-niif-9, patrimonio-y-solvencia, marco-normativo.
- **Funciones creadas (3):** cierre-contable-mensual, calculo-de-reservas-tecnicas, segregacion-de-funciones.
- **Overview e index actualizados.**
- ⚠️ **Contradicción marcada:** método del ajuste por riesgo (percentil 75, manual) vs. Costo de Capital
  (CoC 5,5%, Decreto 1272/2024, citado en el Estudio de Factibilidad). Pendiente de resolver con el responsable
  actuarial. Otros pendientes: sección 15 faltante, control de versiones inconsistente (V2.0 portada vs. V1.0/V4.0
  tabla), confirmar condiciones de cesión del reaseguro.
- **Fuentes referenciadas por ingerir:** Nota Técnica SOAT V14, Hoja de Trabajo SOAT.xlsx, Estudio de
  Factibilidad, Plantilla de Contexto Contable.

## [2026-08-13] query | ¿Cuáles son los libros que vamos a usar en Manta?

Resuelta con la ingesta del manual. Respuesta archivada en [[sintesis/libros-contables-de-manta]]:
tres libros multi-book (NIIF 17 principal · NIIF 4/CUIF secundario · Fiscal).

## [2026-09-15] ingest | Lote de 5 fuentes (README proyecto, spec de emisión, 3 diagramas de reservas)

Ingesta en lote de los archivos subidos a `raw/`. Reorganizados: 2 en `raw/documentos/`, 3 SVG en `raw/assets/`.

- **Fuentes creadas (3):** [[fuentes/contexto-proyecto-manta]] (README maestro, 🔒 confidencial),
  [[fuentes/emision-poliza-soat-desarrollo]] (spec v3.0), [[fuentes/diagramas-flujo-reservas]] (3 SVG).
- **Entidades creadas (5):** dian, proyecto-orion, grupo-r5, juan-felipe-restrepo (+ roster de devs en Orión).
- **Conceptos creados (3):** nota-tecnica-soat, parametros-regulados-soat, camara-de-compensacion.
- **Funciones creadas (1):** emision-de-poliza-soat (3 documentos, flujo de 8 pasos, cuentas, brechas E2E).
- **Actualizadas (12):** netsuite, erika-guerrero, columna-contexto, estructura-multi-book, niif-17,
  reservas-tecnicas-soat, lrc-y-lic, soat, transferencias-adres-ansv, marco-normativo, sintesis/libros
  (corregido enlace DIAN), overview, index.
- ⚠️ **Contradicción nueva marcada:** método de transición NIIF 17 — "sin disposiciones de transición" (manual)
  vs. "enfoque retrospectivo completo" (README/spec). Ver [[conceptos/niif-17]].
- **Datos nuevos:** CUIF 10 dígitos ene-2027; ESFA apertura 1-ene-2026; testing SFC 15–30 oct 2026; LatamReady
  terminado → Grupo R5; actuario Juan Felipe Restrepo (NT V14); parámetros GA/CI/θ; cuentas contables de emisión.
- **Fuentes por ingerir (ampliadas):** Nota Técnica SOAT (V12→V14), Hoja de Trabajo SOAT.xlsx, Modelo
  Financiero.xlsx, Estudio de Incidencia/Factibilidad.pdf, Manual SIAR.pdf, "Ajustes al Plan de Cuentas".
