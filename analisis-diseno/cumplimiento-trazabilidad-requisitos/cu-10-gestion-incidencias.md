# ROOMA

# Trazabilidad y control - CU-10: Gestión de incidencias


## Criterio de la columna Testeado
- **Si**: existe evidencia automatizada directa del requisito en al menos una suite (backend unitario/integracion con JUnit-Spring Test o frontend unitario con Vitest o frontend e2e con Playwright).
- **Parcial**: existe cobertura automatizada, pero solo de una parte del flujo o sin cubrir todas las reglas del requisito.
- **No**: no se encontro evidencia automatizada suficiente del requisito en las suites revisadas.
- **Fuentes revisadas**: `backend/src/test` (unitarios e integracion), `frontend/src/__tests__` (unitarios), `frontend/tests` (e2e).
- **Anexo detallado por RF**: desglose-testing-por-cu-rf.md (usar la seccion del CU correspondiente).

## Matriz de Trazabilidad (HU vs Requisitos)
| ID | Historia de Usuario | RF-27 | RF-28 | RF-29 | RF-30 | RF-31 | RF-32 | RF-33 | RF-34 | RF-35 | RNF-13 | RI-11 | RI-12 |
| :--- | :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **HU-24** | Reporte de Avería | x | | | | | | x | | | | x | |
| **HU-25** | Listado de Incidencias (Inquilino) | | | | | x | | | | | | x | |
| **HU-26** | Seguimiento por Línea de Tiempo | | x | | | | | x | | | x | x | |
| **HU-27** | Validación de Solución | | | | x | | | x | | | | x | |
| **HU-28** | Chat Técnico de Incidencia | | | x | | | | x | | | x | | x |
| **HU-29** | Panel Kanban (Vista Casero) | | | | | | x | | | | | x | |
| **HU-30** | Actualización de Estado (Casero) | | x | | | | | x | | | | x | |
| **HU-31** | Gestión de Presupuestos | | | | | | | | | x | | x | |
| **HU-32** | Historial de Mantenimiento | | | | | | | x | x | | | x | |

---

## Requisitos Funcionales (RF)
| ID | Nombre del Requisito | Estado | Testeado |
| :--- | :--- | :---: | :---: |
| **RF-27** | Formulario de Nueva Incidencia |  | No |
| **RF-28** | Línea de Tiempo de Estado |  | No |
| **RF-29** | Pestaña de Chat Técnico |  | No |
| **RF-30** | Botonera de Validación del Inquilino |  | No |
| **RF-31** | Listado de Incidencias (Vista Inquilino) |  | No |
| **RF-32** | Panel de Incidencias (Vista Casero) |  | No |
| **RF-33** | Notificaciones de Incidencias |  | No |
| **RF-34** | Historial de Incidencias por Vivienda |  | No |
| **RF-35** | Adjuntar Presupuesto de Reparación |  | No |

---

## Requisitos de Información (RI)
| ID | Nombre del Requisito | Estado |
| :--- | :--- | :---: |
| **RI-11** | Incidencia | |
| **RI-12** | Mensaje | |

---

## Requisitos No Funcionales (RNF)
| ID | Nombre del Requisito | Estado |
| :--- | :--- | :---: |
| **RNF-13** | Visibilidad según zona incidencia | |

---

## Historias de Usuario (HU)
| ID | Título de la Historia | Estado |
| :--- | :--- | :---: |
| **HU-24** | Reporte de Avería | |
| **HU-25** | Listado de Incidencias (Inquilino) | |
| **HU-26** | Seguimiento por Línea de Tiempo | |
| **HU-27** | Validación de Solución | |
| **HU-28** | Chat Técnico de Incidencia | |
| **HU-29** | Panel Kanban (Vista Casero) | |
| **HU-30** | Actualización de Estado (Casero) | |
| **HU-31** | Gestión de Presupuestos | |
| **HU-32** | Historial de Mantenimiento | |
