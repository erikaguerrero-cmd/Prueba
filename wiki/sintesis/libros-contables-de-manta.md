---
tipo: sintesis
titulo: ¿Cuáles son los libros que usa Manta?
tags: [contable, niif, multi-book]
creado: 2026-08-13
actualizado: 2026-08-13
fuentes: [manual-politicas-contables-manta]
estado: vigente
---

# ¿Cuáles son los libros que usa Manta?

**Respuesta corta:** Manta Seguros mantiene **tres libros contables simultáneos** (arquitectura *multi-book*
en [[entidades/netsuite|NetSuite]]) sobre **un único conjunto de transacciones**
(ver [[fuentes/manual-politicas-contables-manta]], Parte I §3).

## Los tres libros

| Libro | Rol | Base normativa | Propósito |
|-------|-----|----------------|-----------|
| **[[conceptos/niif-17|NIIF 17]]** | **Principal** | NIIF 17 (Decreto 2420/2015) | Estados financieros de consolidación y base de decisión; **reporte regulatorio desde 2028**. |
| **[[conceptos/niif-4|NIIF 4]] / [[conceptos/cuif|CUIF]]** | **Secundario** | NIIF 4 + Decreto 2555/2010 (mod. 1531/2022); CBF Parte 3 Cap. 2 | **Reporte y cumplimiento SFC durante 2026–2027**. |
| **Fiscal** | **Tercero** | Estatuto Tributario; Decreto 2420/2015 art. 4 | Impuesto de renta, retenciones, medios magnéticos **[[entidades/adres|DIAN]]**. |

## Cómo conviven los libros

- **Registros genéricos** (facturas, pagos, retenciones): se registran una vez y se reflejan en los tres libros.
- **Registros específicos de libro** (*book-specific*): solo en el libro que corresponde. Ej.: descuento y
  desenrollo del LIC, ajuste por riesgo, componente de pérdida por onerosidad → **solo NIIF 17**; impuesto
  diferido → **solo fiscal**.
- **[[conceptos/columna-contexto|Columna CONTEXTO]]** en el plan de cuentas (~2.900 cuentas): traduce cada
  cuenta entre su presentación NIIF 17 y su equivalente CUIF/NIIF 4, de modo que ambos libros se generan desde
  un único registro (ej.: primas devengadas = 4159 en NIIF 17 ↔ 4121 en NIIF 4).
- **Excepción — reservas de siniestros:** los saldos NIIF 4 (nominales) y NIIF 17 (descontados + ajuste por
  riesgo) son distintos → **posteo dual independiente por libro**, no por CONTEXTO
  (ver [[conceptos/reservas-tecnicas-soat]] y [[conceptos/lrc-y-lic]]).

## Por qué esta arquitectura

La NIIF 17 será el marco **regulatorio obligatorio desde el 1-ene-2028** (Decreto 0217/2026). Como Manta ya
opera el libro NIIF 17 como principal desde su constitución, el alineamiento regulatorio de 2028 es **directo**:
no exige reconstrucción retrospectiva. Durante 2026–2027 el reporte a la SFC sale del libro secundario
(NIIF 4/CUIF).

*Fuente: [[fuentes/manual-politicas-contables-manta]] (Parte I §3; Parte II §11).*
