---
tipo: fuente
titulo: Diagramas de flujo de reservas (avisado vs. IBNR)
tags: [actuarial, reservas, diagramas]
creado: 2026-09-15
actualizado: 2026-09-15
origen: raw/assets/flujo-reserva-siniestro-avisado-lic.svg; raw/assets/flujo-reserva-ibnr-agregada.svg; raw/assets/flujo-comparativo-avisado-vs-ibnr.svg
estado: vigente
---

# Diagramas de flujo de reservas (avisado vs. IBNR)

**Qué es:** Tres diagramas de flujo (SVG) que ilustran cómo nacen las
[[conceptos/reservas-tecnicas-soat|reservas de siniestros]]: la **avisada (RSA / LIC reportados)** frente a la
**IBNR agregada (RSONA)**. Material de apoyo conceptual.

## 1. Reserva de siniestro avisado (LIC) — `flujo-reserva-siniestro-avisado-lic.svg`

Póliza emitida (vigente) → ocurre el siniestro (real, sin avisar) → **siniestro reportado** (evento disparador) →
se crea el expediente (caso identificable) → se estima el valor a pagar (por ajustador/caso) → **reserva de
siniestro avisado** (registro individual: póliza + siniestro).

## 2. Reserva IBNR agregada — `flujo-reserva-ibnr-agregada.svg`

Cartera expuesta al riesgo (pólizas vigentes) → sin siniestro reportado (ningún aviso individual) → **el motor
actuarial analiza** → estima ocurridos no avisados (cálculo estadístico) → **reserva IBNR** (monto estimado
agregado) → reconocimiento contable (registro por período / cohorte).

## 3. Comparativo avisado vs. IBNR — `flujo-comparativo-avisado-vs-ibnr.svg`

Árbol de decisión: **¿hay siniestro reportado?**
- **Sí →** reserva avisada (LIC reportados) → registro individual (póliza + siniestro).
- **No →** ¿cartera expuesta? → motor actuarial (cálculo periódico) → reserva IBNR (monto agregado) → registro
  agregado (período / cohorte).

## Conexión con el wiki

- **Avisado (RSA)** ↔ [[conceptos/reservas-tecnicas-soat|RSA]] / componente RBNS del [[conceptos/lrc-y-lic|LIC]].
- **IBNR** ↔ [[conceptos/reservas-tecnicas-soat|RSONA]] (IBNR + IBNER), calculada por el
  [[funciones/calculo-de-reservas-tecnicas|Motor Actuarial]].
- Registro **individual** (póliza + siniestro) vs. **agregado** (período / cohorte).

## Referencias

- Relacionado con: [[conceptos/reservas-tecnicas-soat]] · [[conceptos/lrc-y-lic]] · [[funciones/calculo-de-reservas-tecnicas]]
