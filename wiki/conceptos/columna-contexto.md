---
tipo: concepto
titulo: Columna CONTEXTO
tags: [contable, plan-de-cuentas, multi-book]
creado: 2026-08-13
actualizado: 2026-08-13
fuentes: [manual-politicas-contables-manta]
estado: vigente
---

# Columna CONTEXTO

**Definición corta:** Columna del plan de cuentas que **traduce cada cuenta entre marcos** — su presentación
[[conceptos/niif-17|NIIF 17]] (libro principal) y su equivalente [[conceptos/cuif|CUIF]]/[[conceptos/niif-4|NIIF 4]]
(libro secundario) — de modo que ambos libros se generan desde un **único registro**.

## Cómo funciona

- Si la cuenta es **idéntica** en ambos marcos → se conserva la misma cuenta en los dos libros (el contexto no se
  deja en blanco, se mantiene la cuenta).
- Si la cuenta **difiere** → cada marco tiene su cuenta y el CONTEXTO porta la equivalente del otro marco.
  Ejemplo: **primas devengadas = 4159 (NIIF 17) ↔ 4121 (NIIF 4)**.
- Contexto **único por cuenta**; la jerarquía del contexto replica la del plan de cuentas; las cuentas
  sumarizadas también requieren contexto.

## Alcance y límite

- **Aplica** a primas y cuentas donde el importe es el mismo entre marcos y solo cambia el código → **posteo único**.
- **No aplica** a las [[conceptos/reservas-tecnicas-soat|reservas de siniestros]], donde los importes NIIF 4
  (nominales) y NIIF 17 (descontados + [[conceptos/ajuste-por-riesgo-no-financiero|ajuste por riesgo]]) son
  distintos → **posteo dual independiente**.

El mapeo cuenta a cuenta vive en la **Plantilla de Contexto Contable** (anexo técnico del manual).

## Referencias

- Relacionado con: [[conceptos/estructura-multi-book]] · [[conceptos/cuif]] · [[conceptos/reservas-tecnicas-soat]]
- Aparece en: [[fuentes/manual-politicas-contables-manta]] (Parte I §3.4; §13.5)
