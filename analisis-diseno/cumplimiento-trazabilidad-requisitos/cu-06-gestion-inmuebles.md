# ROOMA

# Trazabilidad y control - CU-06: Gestión de inmuebles


## Criterio de la columna Testeado
- **Si**: existe evidencia automatizada directa del requisito en al menos una suite (backend unitario/integracion con JUnit-Spring Test o frontend unitario con Vitest o frontend e2e con Playwright).
- **Parcial**: existe cobertura automatizada, pero solo de una parte del flujo o sin cubrir todas las reglas del requisito.
- **No**: no se encontro evidencia automatizada suficiente del requisito en las suites revisadas.
- **Fuentes revisadas**: `backend/src/test` (unitarios e integracion), `frontend/src/__tests__` (unitarios), `frontend/tests` (e2e).
- **Anexo detallado por RF**: desglose-testing-por-cu-rf.md (usar la seccion del CU correspondiente).

## Matriz de Trazabilidad (HU vs Requisitos)
| ID | Historia de Usuario | RF-09 | RF-11 | RF-12 | RF-13 | RF-14 | RF-72 | RF-73 | RNF-05 | RNF-06 | RNF-07 | RI-03 | RI-04 | RI-05 | RI-06 |
| :--- | :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **HU-51** | Registro de Inmueble | x | | | | | | | | x | x | x | x | | x |
| **HU-53** | Control de Disponibilidad | | x | | | | | | | | | x | | | |
| **HU-54** | Previsualización de Anuncio | | | x | | | | | | | | x | x | | x |
| **HU-55** | Eliminación Protegida | | | | x | | | | x | | | x | | x | |
| **HU-56** | Visualización de Convivientes | | | | | x | | | | | x | | | x | |
| **HU-65** | Edición de Información | | | | | | x | | | | | | | | |
| **HU-66** | Pausa de Anuncio | | | | | | | x | | | | | | | |
| **HU-67** | Reactivación de Anuncio | | | | | | | x | | | | | | | |

---

## Requisitos Funcionales (RF)
| ID | Nombre del Requisito | Estado | Testeado |
| :--- | :--- | :---: | :---: |
| **RF-09** | Formulario de Alta Guiado |  | Si |
| **RF-11** | Gestión de Estado del Anuncio de la vivienda |  | Si |
| **RF-12** | Previsualización del Anuncio de la vivienda |  | No |
| **RF-13** | Restricción de eliminación de vivienda |  | Parcial |
| **RF-14** | Consulta de miembros de la vivienda |  | Si |
| **RF-72** | Gestión de anuncios |  | Parcial |
| **RF-73** | Pausar y reactivar anuncio |  | Si |

---

## Requisitos de Información (RI)
| ID | Nombre del Requisito | Estado |
| :--- | :--- | :---: |
| **RI-03** | Vivienda | |
| **RI-04** | FotosViviendas | |
| **RI-05** | MiembrosViviendas | |
| **RI-06** | ReglasVivienda | |

---

## Requisitos No Funcionales (RNF)
| ID | Nombre del Requisito | Estado |
| :--- | :--- | :---: |
| **RNF-05** | Confirmación de borrado inmueble | |
| **RNF-06** | Moderación previa publicación | |
| **RNF-07** | Acceso restringido a datos sensibles | |

---

## Historias de Usuario (HU)
| ID | Título de la Historia | Estado |
| :--- | :--- | :---: |
| **HU-51** | Registro de Inmueble | |
| **HU-53** | Control de Disponibilidad | |
| **HU-54** | Previsualización de Anuncio | |
| **HU-55** | Eliminación Protegida | |
| **HU-56** | Visualización de Convivientes | |
| **HU-65** | Edición de Información | |
| **HU-66** | Pausa de Anuncio | |
| **HU-67** | Reactivación de Anuncio | |
