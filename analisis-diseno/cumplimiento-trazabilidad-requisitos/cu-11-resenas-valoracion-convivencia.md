# ROOMA

# Trazabilidad y control - CU-11: Reseñas y valoración de convivencia


## Criterio de la columna Testeado
- **Si**: existe evidencia automatizada directa del requisito en al menos una suite (backend unitario/integracion con JUnit-Spring Test o frontend unitario con Vitest o frontend e2e con Playwright).
- **Parcial**: existe cobertura automatizada, pero solo de una parte del flujo o sin cubrir todas las reglas del requisito.
- **No**: no se encontro evidencia automatizada suficiente del requisito en las suites revisadas.
- **Fuentes revisadas**: `backend/src/test` (unitarios e integracion), `frontend/src/__tests__` (unitarios), `frontend/tests` (e2e).
- **Anexo detallado por RF**: desglose-testing-por-cu-rf.md (usar la seccion del CU correspondiente).

## Matriz de Trazabilidad (HU vs Requisitos)
| ID | Historia de Usuario | RF-36 | RF-37 | RF-38 | RF-39 | RF-41 | RF-42 | RF-43 | RF-44 | RF-45 | RNF-14 | RNF-15 | RI-13 |
| :--- | :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **HU-33** | Valoración de la Estancia (Inquilino) | x | x | | | | | | | | | | x |
| **HU-34** | Sistema de Ciego Mutuo | | | x | | | | | | | | x | x |
| **HU-35** | Consulta de Reputación del Casero | | | | | x | | | x | | | | |
| **HU-36** | Valoración del Inquilino (Casero) | x | x | | | | | | | | | | x |
| **HU-37** | Reputación del Candidato | | | | | x | | | x | | | | |
| **HU-38** | Valoración entre Compañeros | | x | x | | | | | | | | | x |
| **HU-39** | Réplica a Valoraciones | | | | x | | x | | | | | | x |
| **HU-40** | Reporte de Reseñas Inadecuadas | | | | | | | x | | | | | x |
| **HU-41** | Moderación Automática | | | | | | x | | | | x | | x |
| **HU-42** | Sistema de Recordatorios e Cierre | x | | | | | | | | x | | | |

---

## Requisitos Funcionales (RF)
| ID | Nombre del Requisito | Estado | Testeado |
| :--- | :--- | :---: | :---: |
| **RF-36** | Tarjeta de Valoración Pendiente |  | Si |
| **RF-37** | Interfaz de Estrellas e Etiquetas |  | Si |
| **RF-38** | Sistema de Ciego Mutuo |  | Si |
| **RF-39** | Hilo de Réplica |  | Si |
| **RF-41** | Visualización de Reseñas en Perfil Público |  | Parcial |
| **RF-42** | Moderación de Contenido |  | No |
| **RF-43** | Reportar Reseña Inadecuada |  | No |
| **RF-44** | Resumen de Reputación en Tarjetas |  | No |
| **RF-45** | Recordatorios de Valoración |  | Parcial |

---

## Requisitos de Información (RI)
| ID | Nombre del Requisito | Estado |
| :--- | :--- | :---: |
| **RI-13** | Reseña | |

---

## Requisitos No Funcionales (RNF)
| ID | Nombre del Requisito | Estado |
| :--- | :--- | :---: |
| **RNF-14** | Anonimización en moderación | |
| **RNF-15** | Inmutabilidad de reseñas | |

---

## Historias de Usuario (HU)
| ID | Título de la Historia | Estado |
| :--- | :--- | :---: |
| **HU-33** | Valoración de la Estancia (Inquilino) | |
| **HU-34** | Sistema de Ciego Mutuo | |
| **HU-35** | Consulta de Reputación del Casero | |
| **HU-36** | Valoración del Inquilino (Casero) | |
| **HU-37** | Reputación del Candidato | |
| **HU-38** | Valoración entre Compañeros | |
| **HU-39** | Réplica a Valoraciones | |
| **HU-40** | Reporte de Reseñas Inadecuadas | |
| **HU-41** | Moderación Automática | |
| **HU-42** | Sistema de Recordatorios e Cierre | |
