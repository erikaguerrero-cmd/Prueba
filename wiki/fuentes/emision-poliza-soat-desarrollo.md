---
tipo: fuente
titulo: Emisión de póliza SOAT — Especificación de desarrollo
tags: [operativo, contable, desarrollo, netsuite, dian]
creado: 2026-09-15
actualizado: 2026-09-15
origen: raw/documentos/emision-poliza-soat-desarrollo.docx
fecha_fuente: 2026-07-27
estado: vigente
---

# Emisión de póliza SOAT — Especificación de desarrollo

**Qué es:** Especificación técnica del proceso de **emisión de póliza SOAT** (PAS → [[entidades/netsuite|NetSuite]]
→ [[entidades/dian|DIAN]]), **versión 3.0** (post sesión E2E 27-jul). De [[entidades/erika-guerrero|Erika Guerrero]]
(Controller y PM) para **Ricardo Rojas**. Describe el comportamiento objetivo y las **brechas** detectadas en la
sesión E2E.

**Origen:** `raw/documentos/emision-poliza-soat-desarrollo.docx`. Detalle completo en
[[funciones/emision-de-poliza-soat]].

## Puntos clave

1. **Ambiente:** Sandbox. **Ejecución:** cron escalonado (~30 min). **Fuente de verdad:** PAS (pólizas) /
   NetSuite (contable).
2. **La emisión produce TRES documentos**, no uno: Doc 1 factura de venta, Doc 2 cámara de compensación, Doc 3
   constitución de reserva. La razón: cada marco necesita un asiento distinto y la
   [[conceptos/columna-contexto|columna CONTEXTO]] no puede convertir un asiento de 2 líneas en uno de 4.
   Ver [[conceptos/camara-de-compensacion]] y [[funciones/emision-de-poliza-soat]].
3. **Verificación central:** el efecto **neto de Doc 1 + Doc 3 sobre resultados = 0** (débito a CxC contra
   crédito al pasivo, sin efecto en resultado). Si no es cero, algo está mal mapeado.
4. **Devengo diario** a 365 días desde la fecha de **inicio de vigencia** de la póliza (no la fecha de factura).
5. **Costos de adquisición → gasto inmediato**; la comisión no se difiere ni se neta contra la reserva.
6. **Brechas E2E (27-jul):** tarifa y RUNT vacíos en el custom record; todas las pólizas etiquetadas como
   intermediario por defecto; devengo configurado a 12 meses (debe ser diario).

## Cuentas contables citadas (Documento 1 — factura)

| Artículo | Cuenta | Movimiento |
|----------|--------|-----------|
| Prima | 4159030201 | Crédito · Ingreso |
| Contribución ADRES | 2990400005 | Crédito · Pasivo |
| Tasa RUNT | 2990400006 | Crédito · Pasivo |
| Contrapartida (CxC) | 1614100001 | Débito · Cuentas por cobrar |

Ver más cuentas en [[funciones/emision-de-poliza-soat]] y [[conceptos/transferencias-adres-ansv]].

## Impacto en el wiki

**Entidades:** [[entidades/dian]] · [[entidades/proyecto-orion]] (actualiza [[entidades/netsuite]],
[[entidades/erika-guerrero]])

**Conceptos:** [[conceptos/camara-de-compensacion]] (actualiza [[conceptos/columna-contexto]],
[[conceptos/transferencias-adres-ansv]], [[conceptos/paa]])

**Funciones:** [[funciones/emision-de-poliza-soat]] (nueva)

## Fuera de alcance (declarado)

Reaseguro (manual, en cierre), anulaciones/notas crédito, y reservas de siniestros (provienen del Motor Actuarial).
