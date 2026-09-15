---
tipo: concepto
titulo: Parámetros regulados del SOAT
tags: [actuarial, regulatorio, reservas, soat]
creado: 2026-09-15
actualizado: 2026-09-15
fuentes: [contexto-proyecto-manta, manual-politicas-contables-manta]
estado: vigente
---

# Parámetros regulados del SOAT

**Definición corta:** Parámetros fijados por la regulación (NT SFC v9.0, sec. 3.5) que alimentan el cálculo de
[[conceptos/reservas-tecnicas-soat|reservas]] y el tratamiento de la prima. **No son decisión interna** de Manta.

## Parámetros regulados

| Parámetro | Valor | Fuente |
|-----------|-------|--------|
| GA — gastos de administración | **10%** | NT SFC v9.0 |
| CI — cargos de intermediación | **8%** | Sentencia C-395-22 |
| T_ADRES — transferencia [[entidades/adres|ADRES]] | **9,5%** | Res. 2709/2022 |
| T_ANSV — transferencia [[entidades/ansv|ANSV]] | **3%** | Ley 1843/2017 |
| θ — factor de seguridad | **{1%, 2,5%, 5%}** | NT SFC v9.0 |

**Factor RSONA** = (1 − GA − CI) × (1 − T_ADRES − T_ANSV) = 0,82 × 0,875 = **0,7175 (71,75%)**.

## Decisiones internas de Manta (no reguladas)

- Cesión de [[conceptos/reaseguro-quota-share|reaseguro]]: **50%**.
- r% (apertura/cierre ULAE): **50%**.
- **Descuentos sobre tarifa: 0%** → Manta cobra la **tarifa máxima SFC** (por eso PCsd = PE en la RPND).
- Tasa de descuento de reservas: curva libre de riesgo SFC (aplica solo a reservas internas, no a la tarifa).

## Distinción a preservar

La **UVB** indexa el manual tarifario de salud pagado a IPS, **no** necesariamente la prima SOAT fijada por la SFC.

## Referencias

- Relacionado con: [[conceptos/reservas-tecnicas-soat]] · [[conceptos/transferencias-adres-ansv]] · [[conceptos/reaseguro-quota-share]]
- Aparece en: [[fuentes/contexto-proyecto-manta]] · [[fuentes/manual-politicas-contables-manta]]
