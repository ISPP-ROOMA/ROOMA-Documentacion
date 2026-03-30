# ROOMA

# Trazabilidad y control - CU-03: Sistema de Chats


## Criterio de la columna Testeado
- **Si**: existe evidencia automatizada directa del requisito en al menos una suite (backend unitario/integracion con JUnit-Spring Test o frontend unitario con Vitest o frontend e2e con Playwright).
- **Parcial**: existe cobertura automatizada, pero solo de una parte del flujo o sin cubrir todas las reglas del requisito.
- **No**: no se encontro evidencia automatizada suficiente del requisito en las suites revisadas.
- **Fuentes revisadas**: `backend/src/test` (unitarios e integracion), `frontend/src/__tests__` (unitarios), `frontend/tests` (e2e).
- **Anexo detallado por RF**: desglose-testing-por-cu-rf.md (usar la seccion del CU correspondiente).

## Matriz de Trazabilidad (HU vs Requisitos)
| ID | Historia de Usuario | RF-57 | RF-58 | RF-59 | RF-60 | RF-61 | RF-62 | RNF-18 | RI-12 | RI-15 |
| :--- | :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **HU-08** | Mensajería Multimedia | x | x | x | | | | x | x | |
| **HU-09** | Proponer Visitas | | | | x | | | | | x |
| **HU-10** | Cancelación de Citas | | | | | x | | | | x |
| **HU-11** | Cierre de Chats | | | | | | x | | x | |

---

## Requisitos Funcionales (RF)
| ID | Nombre del Requisito | Estado | Testeado |
| :--- | :--- | :---: | :---: |
| **RF-57** | Gestión de Chats entre Usuarios |  | Si |
| **RF-58** | Mensajería Multimedia en Tiempo Real |  | Parcial |
| **RF-59** | Indicadores de Estado |  | Parcial |
| **RF-60** | Gestión de Citas |  | No |
| **RF-61** | Cancelación de Citas |  | No |
| **RF-62** | Cierre de Chats |  | No |

---

## Requisitos de Información (RI)
| ID | Nombre del Requisito | Estado |
| :--- | :--- | :---: |
| **RI-12** | Mensaje | |
| **RI-15** | Citas | Visitas | |

---

## Requisitos No Funcionales (RNF)
| ID | Nombre del Requisito | Estado |
| :--- | :--- | :---: |
| **RNF-18** | Latencia de Mensajes | |

---

## Historias de Usuario (HU)
| ID | Título de la Historia | Estado |
| :--- | :--- | :---: |
| **HU-08** | Mensajería Multimedia | |
| **HU-09** | Proponer Visitas | |
| **HU-10** | Cancelación de Citas | |
| **HU-11** | Cierre de Chats | |
