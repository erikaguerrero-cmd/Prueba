---
tipo: funcion
titulo: Segregación de funciones (matriz de 7 roles NetSuite)
tags: [operativo, control-interno, gobierno]
creado: 2026-08-13
actualizado: 2026-08-13
fuentes: [manual-politicas-contables-manta]
responsable: Controller
periodicidad: a demanda
estado: vigente
---

# Segregación de funciones (matriz de 7 roles NetSuite)

**Objetivo:** Garantizar el control interno mediante roles con incompatibilidades absolutas en
[[entidades/netsuite|NetSuite]]. **Regla crítica:** el *System Administrator* **no** tiene permisos de aprobación
transaccional (es asunto de roles y permisos, no de línea de reporte). Restricción por subsidiaria.

## Matriz de roles

| Rol | Configurar | Crear/registrar | Aprobar transac. | Ejecutar pagos | Conciliar | Aprobar reservas |
|-----|:---:|:---:|:---:|:---:|:---:|:---:|
| System Administrator | ✓ | ✗ | ✗ | ✗ | ✗ | ✗ |
| Controller | ✗ | ✗ | ✗ | ✗ | ✓ revisión | ✗ |
| Accounting | ✗ | ✓ | ✗ | ✗ | ✓ apoyo | ✗ |
| Treasury – Preparation | ✗ | ✓ | ✗ | ✗ | ✓ | ✗ |
| Treasury – Approval | ✗ | ✗ | ✓ | ✓ | ✗ | ✗ |
| Tax / FEL | ✗ | ✓ (impuestos) | ✗ | ✗ | ✗ | ✗ |
| Read-Only | ✗ | ✗ | ✗ | ✗ | ✗ | ✗ |
| Equipo Actuarial (fuera del ERP) | ✗ | ✗ | ✗ | ✗ | ✗ | ✓ ("Go") |

## Pendientes de verificación

- Verificar roles y subsidiarias en **Sandbox**.
- Confirmar permisos del rol *Administrator* y si la aprobación de *Vendor Payment* es **nativa o SuiteFlow**.

## Referencias

- Relacionado con: [[funciones/cierre-contable-mensual]] · [[entidades/netsuite]] · [[entidades/erika-guerrero]]
- Aparece en: [[fuentes/manual-politicas-contables-manta]] (Parte IX §47)
