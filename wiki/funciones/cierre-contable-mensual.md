---
tipo: funcion
titulo: Cierre contable mensual
tags: [operativo, contable, proceso]
creado: 2026-08-13
actualizado: 2026-08-13
fuentes: [manual-politicas-contables-manta]
responsable: Controller
periodicidad: mensual
estado: vigente
---

# Cierre contable mensual

**Objetivo:** Ejecutar el cierre del período con una secuencia de **orden estricto**, generando los reportes por
cada libro de la [[conceptos/estructura-multi-book|estructura multi-book]].
**Responsable general:** [[entidades/erika-guerrero|Controller]]. **Periodicidad:** mensual.

## Secuencia (orden estricto)

| # | Proceso | Responsable |
|---|---------|-------------|
| 1 | Procesar anulaciones pendientes (antes del devengo) | Key User O2C |
| 2 | Revenue Recognition — devengo de prima (ARM) | Sistema (ARM) |
| 3 | Reservas actuariales — Motor Actuarial (**posteo dual** NIIF 4 / NIIF 17), con **"Go" humano** | Actuario + Controller |
| 4 | Ajustes ADRES (transferencias como costo; recaudos como pasivo con terceros) | Contabilidad |
| 5 | Reclasificación de reaseguro (**manual**) | Contabilidad |
| 6 | Revaluación de saldos en moneda extranjera (TRM cierre) | Contabilidad |
| 7 | Conciliación bancaria | Tesorería + Controller |
| 8 | Cuadre **CONTEXTO / CUIF** y generación de reportes por libro | Controller |
| 9 | Cierre y bloqueo del período | Controller |

## Dependencias

- Paso 3 → [[conceptos/reservas-tecnicas-soat]] y [[funciones/calculo-de-reservas-tecnicas]].
- Paso 4 → [[conceptos/transferencias-adres-ansv]].
- Paso 5 → [[conceptos/reaseguro-quota-share]] (contabilización manual).
- Paso 8 → [[conceptos/columna-contexto]] / [[conceptos/cuif]].

## Referencias

- Relacionado con: [[funciones/segregacion-de-funciones]] · [[entidades/netsuite]]
- Aparece en: [[fuentes/manual-politicas-contables-manta]] (Parte IX §46)
