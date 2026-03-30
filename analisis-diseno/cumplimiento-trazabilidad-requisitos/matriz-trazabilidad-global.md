# ROOMA

# Matriz global de trazabilidad CU-HU-Requisitos

Fecha de actualizacion: 2026-03-30

## Objetivo

Consolidar en una sola vista la trazabilidad entre:

- Casos de uso (CU)
- Historias de usuario (HU)
- Requisitos funcionales (RF)
- Requisitos de informacion (RI)
- Requisitos no funcionales (RNF)

## Matriz consolidada

| CU | Nombre | Estado CU | HU asociadas | RF asociados | RI asociados | RNF asociados | Documento CU |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| CU-01 | Descubrimiento de viviendas | Completado parcialmente | HU-01, HU-02, HU-03, HU-04 | RF-46, RF-47, RF-48, RF-49, RF-50, RF-51, RF-52 | RI-03, RI-04, RI-06 | RNF-08, RNF-09, RNF-10 | cu-01-descubrimiento-viviendas.md |
| CU-02 | Gestion de candidatos y match | Completado parcialmente | HU-05, HU-06, HU-07 | RF-53, RF-54, RF-55, RF-56, RF-74 | RI-21 | RNF-19, RNF-20 | cu-02-gestion-candidatos-match.md |
| CU-03 | Sistema de chats | Pendiente | HU-08, HU-09, HU-10, HU-11 | RF-57, RF-58, RF-59, RF-60, RF-61, RF-62 | RI-12, RI-15 | RNF-18 | cu-03-sistema-chats.md |
| CU-04 | Gestion de notificaciones | Completado parcialmente | HU-43, HU-44, HU-45, HU-46, HU-47 | RF-01, RF-02, RF-03, RF-04, RF-05 | RI-01 | RNF-01, RNF-02 | cu-04-gestion-notificaciones.md |
| CU-05 | Sistema de favoritos | Pendiente | HU-48, HU-49, HU-50 | RF-06, RF-07, RF-08 | RI-02 | RNF-03, RNF-04 | cu-05-sistema-favoritos.md |
| CU-06 | Gestion de inmuebles | Completado parcial (alta), pendiente (edicion) | HU-51, HU-53, HU-54, HU-55, HU-56, HU-65, HU-66, HU-67 | RF-09, RF-11, RF-12, RF-13, RF-14, RF-72, RF-73 | RI-03, RI-04, RI-05, RI-06 | RNF-05, RNF-06, RNF-07 | cu-06-gestion-inmuebles.md |
| CU-07 | Gestion de cuentas y perfil | Pendiente | HU-57, HU-58, HU-59, HU-60, HU-61, HU-62, HU-63, HU-64 | RF-63, RF-64, RF-65, RF-66, RF-67, RF-68, RF-69, RF-70, RF-71 | RI-16, RI-17, RI-18, RI-19, RI-20 | - | cu-07-gestion-cuentas-perfil.md |
| CU-08 | Filtros avanzados para arrendador | Pendiente | HU-52 | RF-10, RF-75, RF-76 | RI-03, RI-06, RI-16 | - | cu-08-filtros-avanzados-arrendador.md |
| CU-09 | Gestion de facturas y pagos | Completado parcialmente | HU-12, HU-13, HU-14, HU-15, HU-16, HU-17, HU-18, HU-19, HU-20, HU-21, HU-22, HU-23 | RF-15, RF-16, RF-17, RF-18, RF-19, RF-20, RF-21, RF-22, RF-23, RF-24, RF-25, RF-26 | RI-07, RI-08, RI-09, RI-10 | RNF-11, RNF-12, RNF-16, RNF-17 | cu-09-gestion-facturas-pagos.md |
| CU-10 | Gestion de incidencias | Pendiente | HU-24, HU-25, HU-26, HU-27, HU-28, HU-29, HU-30, HU-31, HU-32 | RF-27, RF-28, RF-29, RF-30, RF-31, RF-32, RF-33, RF-34, RF-35 | RI-11, RI-12 | RNF-13 | cu-10-gestion-incidencias.md |
| CU-11 | Resenas y valoracion de convivencia | Completado parcialmente | HU-33, HU-34, HU-35, HU-36, HU-37, HU-38, HU-39, HU-40, HU-41, HU-42 | RF-36, RF-37, RF-38, RF-39, RF-41, RF-42, RF-43, RF-44, RF-45 | RI-13 | RNF-14, RNF-15 | cu-11-resenas-valoracion-convivencia.md |

## Control de consistencia

| Validacion | Resultado |
| :--- | :--- |
| Todos los CU tienen archivo de trazabilidad dedicado | OK |
| Todos los CU tienen al menos un RF asociado | OK |
| Todos los CU tienen al menos una HU asociada | OK |
| Todas las filas HU usan IDs HU (no RF) en la matriz CU | OK (corregido en CU-08) |
| Enlaces a matriz global desde documentos principales | OK |

## Notas

- Esta matriz consolida la informacion existente en los documentos por CU y los requisitos base.
- Si se crean nuevas HU o RF, se recomienda actualizar primero el archivo CU correspondiente y despues esta matriz global.
- El desglose detallado por CU/RF (tipos de test existentes, evidencia y faltantes) esta en: desglose-testing-por-cu-rf.md.
