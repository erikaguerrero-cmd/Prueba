---
tipo: concepto
titulo: LRC y LIC — pasivos de seguro NIIF 17
tags: [contable, niif, seguro]
creado: 2026-08-13
actualizado: 2026-08-13
fuentes: [manual-politicas-contables-manta]
estado: vigente
---

# LRC y LIC — pasivos de seguro NIIF 17

**Definición corta:** Los dos pasivos de seguro bajo [[conceptos/niif-17|NIIF 17]]:

- **LRC** — Pasivo por **Cobertura Remanente** (*Liability for Remaining Coverage*): prima aún no devengada.
- **LIC** — Pasivo por **Siniestros Incurridos** (*Liability for Incurred Claims*): siniestros ya ocurridos.

## LRC (desde la RPND)

- Bajo [[conceptos/paa|PAA]]: **LRC inicial = primas recibidas**; se reduce por el ingreso devengado (lineal
  diario) y se incrementa por primas nuevas.
- **No se descuenta** ni lleva ajuste por riesgo. Contenido económico ≈ **RPND** (prima no devengada pro-rata) →
  conciliación inmaterial.
- **Componente de pérdida** si el grupo es oneroso (NIIF 17.57-58).

## LIC (siniestros incurridos)

- Mejor estimación de flujos de cumplimiento de siniestros ya ocurridos, **descontada + con
  [[conceptos/ajuste-por-riesgo-no-financiero|ajuste por riesgo]]** (percentil 75). Calculado por el Motor Actuarial.
- Componentes conceptuales (no traducción de saldos): RSA ↔ RBNS (avisados); RSONA ↔ IBNR+IBNER;
  RGIAS/ULAE ↔ flujos de gastos de gestión. Ver [[conceptos/reservas-tecnicas-soat]].
- El **desenrollo del descuento** (*unwinding*) se reconoce como resultado financiero de seguros.

## Mapeo con las reservas de ley

| Reserva de ley (NIIF 4) | Componente NIIF 17 | Overlay |
|-------------------------|--------------------|---------|
| RPND | LRC | Sin descuento ni RA (PAA) |
| RIP | Análogo al componente de pérdida | — |
| RSA | LIC — RBNS | Descuento + RA |
| RSONA | LIC — IBNR/IBNER | Descuento + RA |
| RGIAS (ULAE/ALAE) | LIC — gastos de gestión | Descuento + RA |
| Componente cedido 50% | Activo por reaseguro | Descuento + RA + riesgo incumplimiento |

**La correspondencia en siniestros es conceptual, no de saldos** → posteo dual independiente.

## Referencias

- Relacionado con: [[conceptos/paa]] · [[conceptos/reservas-tecnicas-soat]] · [[conceptos/ajuste-por-riesgo-no-financiero]]
- Aparece en: [[fuentes/manual-politicas-contables-manta]] (Parte II §6; Parte III §13-14)
