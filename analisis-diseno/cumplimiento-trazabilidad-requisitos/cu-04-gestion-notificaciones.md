# ROOMA

# Trazabilidad y control - CU-04: Gestión de notificaciones


## Criterio de la columna Testeado
- **Si**: existe evidencia automatizada directa del requisito en al menos una suite (backend unitario/integracion con JUnit-Spring Test o frontend unitario con Vitest o frontend e2e con Playwright).
- **Parcial**: existe cobertura automatizada, pero solo de una parte del flujo o sin cubrir todas las reglas del requisito.
- **No**: no se encontro evidencia automatizada suficiente del requisito en las suites revisadas.
- **Fuentes revisadas**: `backend/src/test` (unitarios e integracion), `frontend/src/__tests__` (unitarios), `frontend/tests` (e2e).
- **Anexo detallado por RF**: desglose-testing-por-cu-rf.md (usar la seccion del CU correspondiente).

## Matriz de Trazabilidad (HU vs Requisitos)
| ID | Historia de Usuario | RF-01 | RF-02 | RF-03 | RF-04 | RF-05 | RNF-01 | RNF-02 | RI-01 |
| :--- | :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **HU-43** | Notificaciones Automáticas | x | | | | | | | x |
| **HU-44** | Visualización Cronológica | | x | | | | x | x | x |
| **HU-45** | Indicador de Pendientes | | | x | | | | | x |
| **HU-46** | Navegación desde Notificación | | | | x | | | | x |
| **HU-47** | Gestión de Estado de Lectura | | | | | x | | x | x |

---

## Requisitos Funcionales (RF)
| ID | Nombre del Requisito | Estado | Testeado |
| :--- | :--- | :---: | :---: |
| **RF-01** | Generación de notificaciones por eventos |  | No |
| **RF-02** | Visualización de Listado |  | No |
| **RF-03** | Indicador de nuevas notificaciones |  | No |
| **RF-04** | Navegación Directa desde la notificación |  | No |
| **RF-05** | Actualización de Estado leída |  | No |

---

## Requisitos de Información (RI)
| ID | Nombre del Requisito | Estado |
| :--- | :--- | :---: |
| **RI-01** | Notificación | |

---

## Requisitos No Funcionales (RNF)
| ID | Nombre del Requisito | Estado |
| :--- | :--- | :---: |
| **RNF-01** | Orden descendente notificaciones | |
| **RNF-02** | Autorización de notificaciones | |

---

## Historias de Usuario (HU)
| ID | Título de la Historia | Estado |
| :--- | :--- | :---: |
| **HU-43** | Notificaciones Automáticas | |
| **HU-44** | Visualización Cronológica | |
| **HU-45** | Indicador de Pendientes | |
| **HU-46** | Navegación desde Notificación | |
| **HU-47** | Gestión de Estado de Lectura | |
