---
tipo: overview
titulo: Visión general del área
tags: [contable, legal, operativo]
creado: 2026-08-13
actualizado: 2026-09-15
fuentes: [manual-politicas-contables-manta, contexto-proyecto-manta, emision-poliza-soat-desarrollo, diagramas-flujo-reservas]
estado: vigente
---

# Visión general del área

> Página de alto nivel del cerebro digital. Es el mapa que conecta todo lo demás.

## ¿Qué es esta área?

El área contable, legal y operativa de **[[entidades/manta-seguros|Manta Seguros S.A.]]**, aseguradora del
**[[conceptos/soat|ramo SOAT (04)]]** de nueva constitución, vigilada por la
**[[entidades/superintendencia-financiera|SFC]]** y con operación 100% digital sobre
**[[entidades/netsuite|NetSuite]]**.

## Alcance del área

- **Contable/financiero:** políticas contables NIIF, medición de contratos de seguro, reservas, instrumentos
  financieros, cierre mensual.
- **Legal/cumplimiento:** [[conceptos/marco-normativo|marco normativo]] (SFC, SOAT, NIIF), reporte regulatorio,
  [[conceptos/patrimonio-y-solvencia|patrimonio y solvencia]], SIAR/SAGRILAFT.
- **Operativo/procesos:** [[funciones/cierre-contable-mensual|cierre]],
  [[funciones/segregacion-de-funciones|segregación de funciones]],
  [[funciones/calculo-de-reservas-tecnicas|cálculo de reservas]].

## La idea central: tres libros contables

Manta opera una **[[conceptos/estructura-multi-book|estructura multi-book]]** — tres libros simultáneos sobre un
único conjunto de transacciones:

1. **[[conceptos/niif-17|NIIF 17]]** — principal (consolidación; regulatorio desde 2028).
2. **[[conceptos/niif-4|NIIF 4]] / [[conceptos/cuif|CUIF]]** — secundario (reporte SFC 2026–2027).
3. **Fiscal** — renta, retenciones, DIAN.

Ver la síntesis: [[sintesis/libros-contables-de-manta]].

## Funciones principales

- [[funciones/cierre-contable-mensual]] — secuencia de 9 pasos, mensual.
- [[funciones/calculo-de-reservas-tecnicas]] — RPND, RIP, RSA, RSONA, RGIAS; posteo dual.
- [[funciones/segregacion-de-funciones]] — matriz de 7 roles en NetSuite.
- [[funciones/emision-de-poliza-soat]] — PAS→NetSuite→DIAN; estructura de 3 documentos contables.

## El proyecto: Orión (implementación NetSuite)

La operación se construye sobre el **[[entidades/proyecto-orion|Proyecto Orión]]** (ERP NetSuite, equipo
[[entidades/grupo-r5|Grupo R5]], PM Erika Guerrero). Hitos: ESFA de apertura 1-ene-2026; testing SFC 15–30 oct
2026; CUIF 10 dígitos en ene-2027; NIIF 17 regulatoria en 2028.

## Entidades clave

- [[entidades/manta-seguros]] · [[entidades/superintendencia-financiera]] · [[entidades/dian]] ·
  [[entidades/adres]] · [[entidades/ansv]] · [[entidades/netsuite]] · [[entidades/proyecto-orion]] ·
  [[entidades/grupo-r5]] · [[entidades/erika-guerrero]] · [[entidades/juan-felipe-restrepo]]

## Temas abiertos / pendientes

- ⚠️ **Contradicción del ajuste por riesgo** (percentil 75 vs. Costo de Capital, Dcto 1272/2024) —
  ver [[conceptos/ajuste-por-riesgo-no-financiero]]. Falta ingerir el **Estudio de Factibilidad**.
- ⚠️ **Método de transición a NIIF 17:** "sin disposiciones de transición" (manual) vs. "enfoque retrospectivo
  completo" (README/spec) — ver [[conceptos/niif-17]].
- Sección 15 faltante en el manual; control de versiones inconsistente (portada V2.0 vs. tabla V1.0/V4.0). Ojo:
  la **Nota Técnica** va en V14, distinta del versionado del manual.
- Confirmar condiciones de cesión del [[conceptos/reaseguro-quota-share|reaseguro]].
- **Brechas de la emisión (E2E 27-jul):** tarifa/RUNT vacíos, canal por defecto, devengo a 12 meses — ver
  [[funciones/emision-de-poliza-soat]].
- **Fuentes por ingerir:** Nota Técnica SOAT (V12→V14), Hoja de Trabajo SOAT.xlsx, Modelo Financiero.xlsx,
  Estudio de Incidencia (Factibilidad).pdf, Manual SIAR.pdf, Plantilla de Contexto Contable, documento "Ajustes
  al Plan de Cuentas".

---

*Este documento lo mantiene el LLM. Corrígeme y guía qué enfatizar.*
