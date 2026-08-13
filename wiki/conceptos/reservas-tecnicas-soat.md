---
tipo: concepto
titulo: Reservas técnicas SOAT
tags: [contable, actuarial, reservas, soat]
creado: 2026-08-13
actualizado: 2026-08-13
fuentes: [manual-politicas-contables-manta]
estado: vigente
---

# Reservas técnicas SOAT

**Definición corta:** Reservas de ley del ramo [[conceptos/soat|SOAT]] que Manta constituye, calcula y reporta
mensualmente (área actuarial, validadas por el Actuario Responsable). Base: Decreto 2555/2010 (Libro 31, mod.
1531/2022), CE 035/2015, CE 025/2017 y la **Nota Técnica SOAT V14**.

## Inventario de reservas

| Reserva | Sigla | Base normativa | Naturaleza |
|---------|-------|----------------|-----------|
| Reserva de Prima No Devengada | **RPND** | Dcto 2555/2010 art. 2.31.4.2.2 | Riesgo en curso |
| Reserva de Insuficiencia de Primas | **RIP** | CE 035/2015; art. 2.31.4.2.3 | Riesgo en curso |
| Reserva de Siniestros Avisados | **RSA** | Dcto 2555/2010 (Libro 31) | Siniestros |
| Reserva de Gastos Indirectos Asociados al Siniestro | **RGIAS** (ULAE/ALAE) | Dcto 2555/2010 | Gastos de gestión |
| Reserva de Siniestros Ocurridos No Avisados | **RSONA** | Dcto 2555/2010 art. 2.31.4.4.7 | Siniestros (IBNR+IBNER) |

Todas se calculan en versión **bruta, cedida (50%) y neta** (cesión = [[conceptos/reaseguro-quota-share|Quota Share]]).

## Notas de cálculo

- **RPND** = Σ máx(PCsd, PE) · FRNC (fracción de riesgo no corrido). Para SOAT, PCsd = PE (no hay descuentos).
  **No** deduce gastos de expedición (coherente con expensar la adquisición al incurrirse).
- **RIP** = máx(0; (Egresos − Ingresos)/PD) · RPND Neta. Arranca al **mes 12** (sin 2 años de historia,
  ventana gradual).
- **RSA:** póliza a póliza, siniestro a siniestro, cobertura a cobertura. Interactúa con **IBNER** (evita
  duplicación con RSONA).
- **RGIAS:** ALAE (3% del gasto directo el primer año) + ULAE (método New York; r%=50%). Factor ρ desde
  Estudio de Factibilidad, recalculado desde el mes 13.
- **RSONA:** Modelo de Siniestralidad Esperada (transitorio) con **Factor RSONA = 0,7175 (71,75%)**; migra a
  **triángulos de desarrollo** desde el mes 13.

## Mapeo a NIIF 17

Se reexpresan en [[conceptos/lrc-y-lic|LRC y LIC]]. En siniestros, las cifras NIIF 4 (nominales) y NIIF 17
(descontadas + [[conceptos/ajuste-por-riesgo-no-financiero|ajuste por riesgo]]) difieren → **posteo dual
independiente** (no [[conceptos/columna-contexto|CONTEXTO]]).

> ⚠️ **Contradicción abierta (Ajuste por Riesgo):** ver [[fuentes/manual-politicas-contables-manta]] — el método
> del RA (percentil 75) podría chocar con el Costo de Capital (CoC 5,5%, Decreto 1272/2024) exigido por el
> Estudio de Factibilidad. Pendiente de resolver.

## Datos que viven fuera de este manual

- Tablas de reserva por cobertura (SMDLV/UVT): **Nota Técnica SOAT V14** (Tablas 5, 6, 7).
- Ejemplos numéricos y hoja ULAE: **Hoja de Trabajo SOAT.xlsx**.

## Referencias

- Relacionado con: [[conceptos/lrc-y-lic]] · [[funciones/calculo-de-reservas-tecnicas]] · [[conceptos/reaseguro-quota-share]]
- Aparece en: [[fuentes/manual-politicas-contables-manta]] (Parte III)
