# ROOMA

# Trazabilidad y control - CU-01: Descubrimiento de viviendas


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
| **RF-46** | Gestión del Deck | Parcialmente completado | Si |
| **RF-47** | Visualizar Detalles | Completado | Si |
| **RF-48** | Swipe | Completado | Si |
| **RF-49** | Rewind | Fuera del alcance | No |
| **RF-50** | Gestión de Estados |Completado | Si |
| **RF-51** | Persistencia | Completado| Parcial |
| **RF-52** | Sugerencia de Filtros | Por Hacer| Si |

---

## Requisitos de Información (RI)
| ID | Nombre del Requisito | Estado |
| :--- | :--- | :---: |
| **RI-03** | Vivienda (Datos obligatorios) | Parcialmente (Falta el indicador de Nº Máximo de inquilinos en una vivienda)|
| **RI-04** | FotosViviendas (Archivos visuales) | Parcialmente (Nombres en español)|
| **RI-06** | ReglasVivienda (Normas booleanas) | Parcialmente (Los nombres están en español) |

---

## Requisitos No Funcionales (RNF)
| ID | Nombre del Requisito | Estado |
| :--- | :--- | :---: |
| **RNF-08** | Responsividad del Swipe | Completado|
| **RNF-09** | Caché de deck offline | NO |
| **RNF-10** | Estandarización carga Deck | NO |

---

## Historias de Usuario (HU)
| ID | Título de la Historia | Estado |
| :--- | :--- | :---: |
| **HU-01** | Visualización del Deck |  Parcialmente completado |
| **HU-02** | Navegación por Gestos (Swipe) | Completado (Falta la caché offline)|
| **HU-03** | Detalle del Inmueble |  Parcialmente(falta indicador de nº máximo de inquilinos)|
| **HU-04** | Función Rewind |  Fuera del alcance |
