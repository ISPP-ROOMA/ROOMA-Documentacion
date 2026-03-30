# ROOMA

# Trazabilidad y control - CU-08: Filtros avanzados para arrendador


## Criterio de la columna Testeado
- **Si**: existe evidencia automatizada directa del requisito en al menos una suite (backend unitario/integracion con JUnit-Spring Test o frontend unitario con Vitest o frontend e2e con Playwright).
- **Parcial**: existe cobertura automatizada, pero solo de una parte del flujo o sin cubrir todas las reglas del requisito.
- **No**: no se encontro evidencia automatizada suficiente del requisito en las suites revisadas.
- **Fuentes revisadas**: `backend/src/test` (unitarios e integracion), `frontend/src/__tests__` (unitarios), `frontend/tests` (e2e).
- **Anexo detallado por RF**: desglose-testing-por-cu-rf.md (usar la seccion del CU correspondiente).

## Matriz de Trazabilidad (HU vs Requisitos)
| ID | Historia de Usuario | RF-10 | RF-75 | RF-76 | RI-03 | RI-06 | RI-16 |
| :--- | :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| **HU-52** | Definición de Perfil Ideal | x | x | x | x | x | x |


---

## Requisitos Funcionales (RF)
| ID | Nombre del Requisito | Estado | Testeado |
| :--- | :--- | :---: | :---: |
| **RF-10** | Definición de Perfil Ideal |  | Parcial |
| **RF-75** | Filtrado Manual de Solicitudes |  | No |
| **RF-76** | Ordenación de Candidatos |  | No |

---

## Requisitos de Información (RI)
| ID | Nombre del Requisito | Estado |
| :--- | :--- | :---: |
| **RI-03** | Vivienda | |
| **RI-06** | ReglasVivienda | |
| **RI-16** | Usuario | |

---

## Requisitos No Funcionales (RNF)
No se asocian RNF específicos en la documentación para este CU

---

## Historias de Usuario (HU)
| ID | Título de la Historia | Estado |
| :--- | :--- | :---: |
| **HU-52** | Definición de Perfil Ideal | |
