# ROOMA

# Trazabilidad y control - CU-01: Descubrimiento de viviendas


## Criterio de la columna Testeado
- **Si**: existe evidencia automatizada directa del requisito en al menos una suite (backend unitario/integracion con JUnit-Spring Test o frontend unitario con Vitest o frontend e2e con Playwright).
- **Parcial**: existe cobertura automatizada, pero solo de una parte del flujo o sin cubrir todas las reglas del requisito.
- **No**: no se encontro evidencia automatizada suficiente del requisito en las suites revisadas.
- **Fuentes revisadas**: `backend/src/test` (unitarios e integracion), `frontend/src/__tests__` (unitarios), `frontend/tests` (e2e).
- **Anexo detallado por RF**: desglose-testing-por-cu-rf.md (usar la seccion del CU correspondiente).

## Matriz de Trazabilidad (HU vs Requisitos)
| ID | Historia de Usuario | RF-46 | RF-47 | RF-48 | RF-49 | RF-50 | RF-51 | RF-52 | RNF-08 | RNF-09 | RNF-10 | RI-03 | RI-04 | RI-06 |
| :--- | :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **HU-01** | Visualización del Deck | x | | x | | | x | x | | x | x | x | x | x |
| **HU-02** | Navegación (Swipe) | | | x | x | x | | | x | | | | | |
| **HU-03** | Detalle del Inmueble | | x | | | | | | | | | x | x | x |
| **HU-04** | Función Rewind | | | | x | x | | | | | | | | |

---

## Requisitos Funcionales (RF)
| ID | Nombre del Requisito | Estado | Testeado |
| :--- | :--- | :---: | :---: |
| **RF-46** | Gestión del Deck |  | Si |
| **RF-47** | Visualizar Detalles |  | Si |
| **RF-48** | Swipe |  | Si |
| **RF-49** | Rewind |  | No |
| **RF-50** | Gestión de Estados |  | Si |
| **RF-51** | Persistencia |  | Parcial |
| **RF-52** | Sugerencia de Filtros |  | Si |

---

## Requisitos de Información (RI)
| ID | Nombre del Requisito | Estado |
| :--- | :--- | :---: |
| **RI-03** | Vivienda (Datos obligatorios) |  |
| **RI-04** | FotosViviendas (Archivos visuales) |  |
| **RI-06** | ReglasVivienda (Normas booleanas) |  |

---

## Requisitos No Funcionales (RNF)
| ID | Nombre del Requisito | Estado |
| :--- | :--- | :---: |
| **RNF-08** | Responsividad del Swipe |  |
| **RNF-09** | Caché de deck offline | |
| **RNF-10** | Estandarización carga Deck |  |

---

## Historias de Usuario (HU)
| ID | Título de la Historia | Estado |
| :--- | :--- | :---: |
| **HU-01** | Visualización del Deck |  |
| **HU-02** | Navegación por Gestos (Swipe) |  |
| **HU-03** | Detalle del Inmueble |  |
| **HU-04** | Función Rewind (Premium) |  |
