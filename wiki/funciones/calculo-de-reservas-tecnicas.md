---
tipo: funcion
titulo: Cálculo de reservas técnicas
tags: [actuarial, contable, proceso, reservas]
creado: 2026-08-13
actualizado: 2026-08-13
fuentes: [manual-politicas-contables-manta]
responsable: Área actuarial / Actuario Responsable
periodicidad: mensual
estado: vigente
---

# Cálculo de reservas técnicas

**Objetivo:** Calcular, constituir y reportar mensualmente las [[conceptos/reservas-tecnicas-soat|reservas
técnicas SOAT]], en versión bruta, cedida (50%) y neta, y **postearlas de forma dual** en los libros NIIF 4 y
NIIF 17.
**Responsable:** área actuarial, validado por el **Actuario Responsable**; presentación al Comité de Riesgos y
Junta Directiva (Manual SIAR).

## Alcance

- Reservas de riesgo en curso: **RPND**, **RIP**.
- Reservas de siniestros: **RSA**, **RSONA** (IBNR+IBNER), **RGIAS** (ULAE/ALAE).
- Motor Actuarial calcula el [[conceptos/lrc-y-lic|LIC NIIF 17]] (descontado + ajuste por riesgo) y las reservas
  de ley NIIF 4 **por separado** → posteo independiente por libro.

## Entradas y salidas

- **Entradas:** experiencia siniestral, Nota Técnica SOAT V14 (Tablas 5–7), Hoja de Trabajo SOAT.xlsx, tasa de
  descuento (curva TES + iliquidez), parámetros regulados (GA, CI, T_ADRES, T_ANSV).
- **Salidas:** saldos de reservas por libro, conciliación NIIF 4 ↔ NIIF 17, insumo del paso 3 del
  [[funciones/cierre-contable-mensual|cierre mensual]] (con "Go" humano del Actuario + Controller).

## Transición metodológica

- **RSONA:** Modelo de Siniestralidad Esperada (transitorio, Factor 0,7175) → **triángulos de desarrollo** desde
  el mes 13.
- **RIP:** arranca al mes 12; ventana de 2 años gradual.
- **ULAE (ρ):** aproximado con Estudio de Factibilidad al inicio; recalculado desde el mes 13.

> ⚠️ **Pendiente:** consistencia con el Estudio de Factibilidad (ULAE/RSONA) y la **contradicción del método del
> ajuste por riesgo** — ver [[conceptos/ajuste-por-riesgo-no-financiero]].

## Referencias

- Relacionado con: [[conceptos/reservas-tecnicas-soat]] · [[conceptos/lrc-y-lic]] · [[conceptos/reaseguro-quota-share]]
- Aparece en: [[fuentes/manual-politicas-contables-manta]] (Parte III)
