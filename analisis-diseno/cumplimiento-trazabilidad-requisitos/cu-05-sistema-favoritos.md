# ROOMA

# Trazabilidad y control - CU-05: Sistema de favoritos


## Criterio de la columna Testeado
- **Si**: existe evidencia automatizada directa del requisito en al menos una suite (backend unitario/integracion con JUnit-Spring Test o frontend unitario con Vitest o frontend e2e con Playwright).
- **Parcial**: existe cobertura automatizada, pero solo de una parte del flujo o sin cubrir todas las reglas del requisito.
- **No**: no se encontro evidencia automatizada suficiente del requisito en las suites revisadas.
- **Fuentes revisadas**: `backend/src/test` (unitarios e integracion), `frontend/src/__tests__` (unitarios), `frontend/tests` (e2e).
- **Anexo detallado por RF**: desglose-testing-por-cu-rf.md (usar la seccion del CU correspondiente).

## Matriz de Trazabilidad (HU vs Requisitos)
| ID | Historia de Usuario | RF-06 | RF-07 | RF-08 | RNF-03 | RNF-04 | RI-02 |
| :--- | :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| **HU-48** | Marcar como Favorito | x | | | | x | x |
| **HU-49** | Listado de Favoritos | | x | | x | | x |
| **HU-50** | Control de Disponibilidad en Favoritos | | | x | | x | x |

---

## Requisitos Funcionales (RF)
| ID | Nombre del Requisito | Estado | Testeado |
| :--- | :--- | :---: | :---: |
| **RF-06** | Gestión de Favoritos |  | Si |
| **RF-07** | Visualización del Listado de favoritos |  | Si |
| **RF-08** | Control de Disponibilidad en Favoritos |  | Parcial |

---

## Requisitos de Información (RI)
| ID | Nombre del Requisito | Estado |
| :--- | :--- | :---: |
| **RI-02** | Elemento Guardado | |

---

## Requisitos No Funcionales (RNF)
| ID | Nombre del Requisito | Estado |
| :--- | :--- | :---: |
| **RNF-03** | Privacidad de favoritos | |
| **RNF-04** | Depuración automática favoritos | |

---

## Historias de Usuario (HU)
| ID | Título de la Historia | Estado |
| :--- | :--- | :---: |
| **HU-48** | Marcar como Favorito | |
| **HU-49** | Listado de Favoritos | |
| **HU-50** | Control de Disponibilidad en Favoritos | |
