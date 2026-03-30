# ROOMA

# Trazabilidad y control - CU-02: Gestión de Candidatos y Match


## Criterio de la columna Testeado
- **Si**: existe evidencia automatizada directa del requisito en al menos una suite (backend unitario/integracion con JUnit-Spring Test o frontend unitario con Vitest o frontend e2e con Playwright).
- **Parcial**: existe cobertura automatizada, pero solo de una parte del flujo o sin cubrir todas las reglas del requisito.
- **No**: no se encontro evidencia automatizada suficiente del requisito en las suites revisadas.
- **Fuentes revisadas**: `backend/src/test` (unitarios e integracion), `frontend/src/__tests__` (unitarios), `frontend/tests` (e2e).
- **Anexo detallado por RF**: desglose-testing-por-cu-rf.md (usar la seccion del CU correspondiente).

## Matriz de Trazabilidad (HU vs Requisitos)
| ID | Historia de Usuario | RF-53 | RF-54 | RF-55 | RF-56 | RF-74 | RNF-19 | RNF-20 | RI-21 |
| :--- | :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **HU-05** | Dashboard de Candidatos | x | | | x | | | | |
| **HU-06** | Ficha Técnica del Candidato | | x | | | | | | |
| **HU-07** | Gestión de Decisiones | | | x | | x | x | x | x |

---

## Requisitos Funcionales (RF)
| ID | Nombre del Requisito | Estado | Testeado |
| :--- | :--- | :---: | :---: |
| **RF-53** | Gestión de Solicitudes |  | Si |
| **RF-54** | Visualización Candidato |  | Si |
| **RF-55** | Gestión de Candidatos |  | Si |
| **RF-56** | Gestión de Estados del Inmueble |  | Parcial |
| **RF-74** | Match |  | Si |

---

## Requisitos de Información (RI)
| ID | Nombre del Requisito | Estado |
| :--- | :--- | :---: |
| **RI-21** | Match | |

---

## Requisitos No Funcionales (RNF)
| ID | Nombre del Requisito | Estado |
| :--- | :--- | :---: |
| **RNF-19** | Consistencia de Match bilateral | |
| **RNF-20** | Latencia de aviso de Match | |

---

## Historias de Usuario (HU)
| ID | Título de la Historia | Estado |
| :--- | :--- | :---: |
| **HU-05** | Dashboard de Candidatos | |
| **HU-06** | Ficha Técnica del Candidato | |
| **HU-07** | Gestión de Decisiones | |
