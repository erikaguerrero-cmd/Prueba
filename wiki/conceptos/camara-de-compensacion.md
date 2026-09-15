---
tipo: concepto
titulo: Cámara de compensación (Documento 2)
tags: [contable, soat, actuarial, emision]
creado: 2026-09-15
actualizado: 2026-09-15
fuentes: [emision-poliza-soat-desarrollo]
estado: vigente
---

# Cámara de compensación (Documento 2)

**Definición corta:** Segundo de los tres documentos que produce la
[[funciones/emision-de-poliza-soat|emisión de póliza SOAT]]. Reconoce el valor de cámara de compensación que
**devuelve el motor actuarial** al emitirse la póliza. **Manta no lo calcula ni lo estima.**

## Asiento

| Movimiento | Cuenta | Naturaleza |
|-----------|--------|-----------|
| Débito | 1686050001 | Cuenta por cobrar cámara de compensación |
| Crédito | 4159050101 | Ingreso por primas aceptadas en cámara |

## Comportamiento técnico

- Se genera **automáticamente** asociado a la factura (Documento 1).
- El motor responde de forma **asíncrona** respecto de la emisión → el desarrollo debe manejar el caso en que la
  respuesta no llegue o se demore, **sin dejar la factura sin su documento asociado** y sin bloquear el resto de la cola.

## Referencias

- Relacionado con: [[funciones/emision-de-poliza-soat]] · [[funciones/calculo-de-reservas-tecnicas]] · [[conceptos/columna-contexto]]
- Aparece en: [[fuentes/emision-poliza-soat-desarrollo]]
