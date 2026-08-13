---
tipo: concepto
titulo: Estructura multi-book (tres libros contables)
tags: [contable, niif, multi-book]
creado: 2026-08-13
actualizado: 2026-08-13
fuentes: [manual-politicas-contables-manta]
estado: vigente
---

# Estructura multi-book (tres libros contables)

**Definición corta:** Manta mantiene **tres libros contables simultáneos** en [[entidades/netsuite|NetSuite]]
sobre un **único conjunto de transacciones**. Es la arquitectura central de todo el modelo contable.

## Los tres libros

| Libro | Rol | Base normativa | Propósito |
|-------|-----|----------------|-----------|
| **[[conceptos/niif-17|NIIF 17]]** | Principal | NIIF 17 (Decreto 2420/2015) | Consolidación y decisión; reporte regulatorio desde 2028. |
| **[[conceptos/niif-4|NIIF 4]] / [[conceptos/cuif|CUIF]]** | Secundario | NIIF 4 + Decreto 2555/2010 (mod. 1531/2022) | Reporte y cumplimiento SFC 2026–2027. |
| **Fiscal** | Tercero | Estatuto Tributario; Decreto 2420/2015 art. 4 | Renta, retenciones, medios magnéticos DIAN. |

## Registros genéricos vs. específicos de libro

- **Genéricos** (todos los libros): facturas, pagos, retenciones. Se registran una vez y se reflejan en los tres.
- **Específicos de libro** (*book-specific*): solo en el libro que corresponde —
  - Descuento del LIC y su desenrollo, [[conceptos/ajuste-por-riesgo-no-financiero|ajuste por riesgo]] sobre el
    LIC, componente de pérdida por onerosidad → **solo NIIF 17**.
  - Impuesto diferido → **solo fiscal**.
  - Reservas de siniestros bajo cada marco → **posteo dual independiente** (ver [[conceptos/reservas-tecnicas-soat]]).
- **No hay CSM** (bajo [[conceptos/paa|PAA]] no existe).

## Mecanismos de traducción entre marcos

- **[[conceptos/columna-contexto|Columna CONTEXTO]]**: para cuentas de igual monto entre marcos (posteo único).
- **Posteo dual independiente**: para reservas de siniestros, donde los importes NIIF 4 (nominales) y NIIF 17
  (descontados + ajuste por riesgo) son distintos.

## Por qué importa

Permite que Manta cumpla el reporte SFC bajo NIIF 4 (2026–2027) **y** consolide bajo NIIF 17 desde el inicio, de
modo que la **convergencia regulatoria de 2028** (Decreto 0217/2026) sea directa, sin reconstrucción retrospectiva.

## Referencias

- Síntesis: [[sintesis/libros-contables-de-manta]]
- Relacionado con: [[conceptos/columna-contexto]] · [[conceptos/cuif]] · [[conceptos/niif-17]] · [[conceptos/niif-4]]
- Aparece en: [[fuentes/manual-politicas-contables-manta]] (Parte I §3)
