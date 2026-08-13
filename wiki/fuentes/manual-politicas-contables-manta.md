---
tipo: fuente
titulo: Manual de Políticas Contables y Financieras — Manta Seguros
tags: [contable, legal, operativo, niif, soat]
creado: 2026-08-13
actualizado: 2026-08-13
origen: raw/documentos/manual-politicas-contables-financieras-manta.docx
fecha_fuente: 2026
estado: vigente
---

# Manual de Políticas Contables y Financieras — Manta Seguros

**Qué es:** Manual de políticas contables y financieras de **[[entidades/manta-seguros|Manta Seguros S.A.]]**,
aseguradora del **[[conceptos/soat|ramo SOAT (04)]]** vigilada por la
**[[entidades/superintendencia-financiera|Superintendencia Financiera de Colombia (SFC)]]**.
Portada marcada **V2.0**; la tabla de control de versiones registra V1.0 y V4.0 (ver ⚠️ abajo).
Autora: **[[entidades/erika-guerrero|Erika Guerrero]]** (Controller).

**Origen:** `raw/documentos/manual-politicas-contables-financieras-manta.docx` (48 secciones, 9 partes).

## Estructura del documento

| Parte | Contenido |
|-------|-----------|
| I | Marco normativo y bases de preparación; **[[conceptos/estructura-multi-book|estructura multi-book]]** y catálogo de cuentas |
| II | Contratos de seguro ([[conceptos/niif-17|NIIF 17]] / [[conceptos/paa|PAA]], [[conceptos/lrc-y-lic|LRC/LIC]]) |
| III | [[conceptos/reservas-tecnicas-soat|Reservas técnicas]] (RPND, RIP, RSA, RGIAS, RSONA) y mapeo a NIIF 17 |
| IV | [[conceptos/reaseguro-quota-share|Reaseguro Quota Share 50/50]] |
| V | Ingresos y gastos técnicos; [[conceptos/transferencias-adres-ansv|transferencias ADRES/ANSV]] |
| VI | [[conceptos/instrumentos-financieros-niif-9|Instrumentos financieros (NIIF 9)]] |
| VII | Otras políticas (cuentas por cobrar, PPYE, intangibles, arrendamientos, beneficios, impuestos, provisiones, ME, [[conceptos/patrimonio-y-solvencia|patrimonio/solvencia]]) |
| VIII | Presentación y revelación (formatos SFC) |
| IX | [[funciones/cierre-contable-mensual|Cierre contable mensual]], [[funciones/segregacion-de-funciones|segregación de funciones]], control de versiones |

## Puntos clave

1. **Tres libros contables simultáneos** (multi-book en [[entidades/netsuite|NetSuite]]): **NIIF 17** (principal),
   **NIIF 4 / CUIF** (secundario, reporte SFC 2026–2027) y **Fiscal** (DIAN). Ver [[conceptos/estructura-multi-book]]
   y la síntesis [[sintesis/libros-contables-de-manta]].
2. **PAA** como modelo de medición (contratos ≤ 1 año): sin CSM ni ajuste por riesgo sobre el LRC; descuento y
   ajuste por riesgo (percentil 75) **solo sobre el LIC**.
3. **Columna CONTEXTO** en el plan de cuentas (~2.900 cuentas) traduce entre marcos; las reservas de siniestros
   se postean de forma **dual e independiente** (no por CONTEXTO).
4. **Prima SOAT = 100% ingreso**; ADRES 9,5% y ANSV 3% son **costo**; contribución ADRES 52% y RUNT son
   **recaudo para terceros** (no pasan por resultados).
5. **Convergencia NIIF 17 regulatoria: 1-ene-2028** (Decreto 0217/2026). Por la arquitectura multi-book, el
   alineamiento es directo (el libro NIIF 17 ya opera desde el inicio).
6. Reservas de ley calculadas por el área actuarial; **"Go" humano** del Actuario + Controller en el cierre.

## Impacto en el wiki

**Entidades:** [[entidades/manta-seguros]] · [[entidades/superintendencia-financiera]] · [[entidades/adres]] ·
[[entidades/ansv]] · [[entidades/netsuite]] · [[entidades/erika-guerrero]]

**Conceptos:** [[conceptos/estructura-multi-book]] · [[conceptos/soat]] · [[conceptos/niif-17]] ·
[[conceptos/niif-4]] · [[conceptos/paa]] · [[conceptos/lrc-y-lic]] · [[conceptos/reservas-tecnicas-soat]] ·
[[conceptos/cuif]] · [[conceptos/columna-contexto]] · [[conceptos/reaseguro-quota-share]] ·
[[conceptos/ajuste-por-riesgo-no-financiero]] · [[conceptos/transferencias-adres-ansv]] ·
[[conceptos/instrumentos-financieros-niif-9]] · [[conceptos/patrimonio-y-solvencia]] · [[conceptos/marco-normativo]]

**Funciones:** [[funciones/cierre-contable-mensual]] · [[funciones/segregacion-de-funciones]] ·
[[funciones/calculo-de-reservas-tecnicas]]

**Síntesis:** [[sintesis/libros-contables-de-manta]]

## Comentarios de revisión (Alex Swift) y contradicciones

El `.docx` trae 6 comentarios de revisión pendientes:

1. **Reaseguro:** "Pendiente confirmación condiciones de cesión" (Quota Share 50/50).
2. **Sección 15 faltante:** la numeración salta de la 14 a la 16 en la Parte IV — *"desaparece la sección 15, arreglar"*.
3. **ULAE / factor ρ:** *"¿consistente con valores del estudio de factibilidad?"*.
4. **Control de versiones:** *"saltamos de versión 1 a 4, no tenemos fecha para la v4.0"* — además la portada dice **V2.0**. Inconsistencia interna.
5. **RSONA / factor:** *"revisar consistencia con estudio de factibilidad"*.
6. **⚠️ Contradicción metodológica del Ajuste por Riesgo** (ver bloque abajo).

> ⚠️ **Contradicción:** Este manual mide el **[[conceptos/ajuste-por-riesgo-no-financiero|ajuste por riesgo]]**
> por **nivel de confianza (percentil 75)**. El comentario 6 de la revisión advierte que el **Estudio de
> Factibilidad** cita el **Decreto 1272 de 2024 (art. 2.31.4.1.5)** como el estándar regulatorio en Colombia,
> que exige una fórmula de **Costo de Capital (CoC 5,5%)** — metodología distinta (basada en capital, no en
> percentiles). El manual no menciona el Decreto 1272/2024. **Pendiente de resolver con el humano / responsable
> actuarial** antes de avanzar cualquiera de los dos documentos. (Requiere ingerir el *Estudio de Factibilidad*
> como fuente para completar el cruce.)
