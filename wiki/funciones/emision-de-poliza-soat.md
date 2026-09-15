---
tipo: funcion
titulo: Emisión de póliza SOAT (PAS → NetSuite → DIAN)
tags: [operativo, contable, desarrollo, proceso]
creado: 2026-09-15
actualizado: 2026-09-15
fuentes: [emision-poliza-soat-desarrollo]
responsable: Proyecto Orión (Grupo R5) / Erika Guerrero (PM)
periodicidad: continua (cron ~30 min)
estado: vigente
---

# Emisión de póliza SOAT (PAS → NetSuite → DIAN)

**Objetivo:** Automatizar, desde la emisión en el PAS, la creación del cliente, la factura, los asientos
contables en los dos marcos y la transmisión a la [[entidades/dian|DIAN]]. Corre en **Sandbox** con **cron
escalonado (~30 min)**. **Fuente de verdad:** PAS (pólizas) / [[entidades/netsuite|NetSuite]] (contable).
**Estado:** v3.0, post sesión E2E 27-jul-2026.

## La estructura de tres documentos

La emisión produce **tres documentos**, porque cada marco exige un asiento distinto y la
[[conceptos/columna-contexto|columna CONTEXTO]] (mapeo cuenta a cuenta) no puede convertir un asiento de 2 líneas
en uno de 4:

| Concepto | Doc 1 (factura) | Doc 3 (reserva) | Neto |
|----------|:---:|:---:|:---:|
| Cuentas por cobrar | + Prima | — | + Prima |
| Ingreso por prima emitida | + Prima | − Prima | **0** |
| Pasivo — reserva de prima no devengada | — | + Prima | + Prima |

**Verificación central:** el **neto de Doc 1 + Doc 3 sobre resultados = 0** (débito a CxC contra crédito al
pasivo). Si no es cero, algo está mal mapeado.

## Flujo del proceso (8 pasos)

| # | Qué ocurre | Sistema |
|---|-----------|---------|
| 1 | Se emite la póliza y se encola el evento | PAS |
| 2 | El cron lee la cola | NetSuite |
| 3 | Se crea/actualiza el cliente (campos de FE) | NetSuite |
| 4 | Se crea el custom record de póliza (encabezado + detalle) | NetSuite |
| 5 | **Doc 1** — factura de venta y transmisión a la DIAN | NetSuite / Dispapeles |
| 6 | **Doc 2** — [[conceptos/camara-de-compensacion|reconocimiento de cámara de compensación]] | NetSuite |
| 7 | **Doc 3** — constitución de reserva de prima no devengada | NetSuite |
| 8 | Devengo diario sobre el pasivo constituido | NetSuite |

## Documentos y cuentas

**Doc 1 — Factura de venta** (fecha = emisión de la póliza):

| Artículo | Cuenta | Movimiento |
|----------|--------|-----------|
| Prima | 4159030201 | Crédito · Ingreso |
| Contribución ADRES | 2990400005 | Crédito · Pasivo (recaudo terceros) |
| Tasa RUNT | 2990400006 | Crédito · Pasivo (recaudo terceros) |
| Contrapartida | 1614100001 | Débito · Cuentas por cobrar |

**Doc 3 — Constitución de reserva** (transacción de venta, valor total **cero**, no se transmite a DIAN):

| Línea | Cuenta | Movimiento |
|-------|--------|-----------|
| Línea 1 (+) | 2601030101 | Crédito · Pasivo — reserva de prima no devengada |
| Línea 2 (−) | 5191101001 | Débito · Gasto — constitución de reserva |

**Devengo:** base 2601030101 → destino 4159030101 (primas asignadas al periodo); **lineal diario, 365 días**,
desde el inicio de vigencia. La liberación **nunca** va a primas emitidas (se reconocería dos veces).
Presentación correcta: *primas emitidas − constitución de reservas + liberación de reservas = primas devengadas*.

## Canales de venta

- **Venta directa:** CxC y reconocimiento inmediato del pago según medio de pago.
- **Intermediario:** CxC → transitoria 1604050007 → se concilia cuando el intermediario paga.
- **Recaudo delegado sin intermediario:** *pendiente de definir*.

## Reglas que no se pueden omitir

1. Idempotencia por número de póliza. 2. Reproceso de cola sin pérdida ni intervención manual (cada registro con
estado). 3. Cron escalonado, sin ejecuciones concurrentes. 4. Doc 3 en cero, no toca CxC. 5. Neto Doc 1+3 sobre
resultado = 0. 6. Devengo a 4159030101, nunca a primas emitidas. 7. External ID cliente = tipo+número, con
actualización. 8. Liquidación de comisiones dentro de la ventana definida.

## Brechas detectadas (E2E 27-jul) y pendientes

- Tarifa y valor RUNT llegan **vacíos** al custom record → poblar desde el PAS (Jefferson Paz).
- Todas las pólizas etiquetadas como **intermediario** por defecto → diferenciar los tres canales (Jefferson Paz).
- Devengo configurado a **12 meses** → ajustar a diario, iniciar en vigencia (Daniel Iriarte).
- Código DANE por defecto (dirección aseguradora) debe quedar **marcado** en listado semanal de excepciones.
- Confirmar que **Advanced Revenue Management** procesa una transacción de valor cero (Ricardo Rojas).
- Definir tratamiento tributario/retenciones (SuiteTax + FE) (Daniel Iriarte).
- Restablecer la conexión de la calculadora actuarial (Khristian Robayo).
- Evaluar **API vs. módulo nativo de Oracle** para FE en volumen (bloquea go-live, no las pruebas).

## Fuera de alcance

Reaseguro (manual, en cierre), anulaciones/notas crédito, reservas de siniestros (Motor Actuarial).

## Referencias

- Relacionado con: [[conceptos/camara-de-compensacion]] · [[conceptos/columna-contexto]] · [[conceptos/transferencias-adres-ansv]] · [[funciones/cierre-contable-mensual]] · [[entidades/proyecto-orion]] · [[entidades/dian]]
- Aparece en: [[fuentes/emision-poliza-soat-desarrollo]]
