# ROOMA

# Trazabilidad y control - CU-02: Gestión de Candidatos y Match


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
| **RF-53** | Gestión de Solicitudes | Completado | Testeado|
| **RF-54** | Visualización Candidato | Completado | Testeado|
| **RF-55** | Gestión de Candidatos | Completado Parcialmente (no hay calendario de citas) | Testeado(sin calendario) |
| **RF-56** | Gestión de Estados del Inmueble | Completado Parcialmente (no se modifica el estado si esta ocupado, pero esto no me parece mal ya que también apuntamos para encontrar compañeros) | Parcialmente( Faltan test por ejemplo en processSwipe) |
| **RF-74** | Match | Completado Parcialmente (el Match no se puede cancelar una vez aceptado) | Parcialmente( Faltan test por ejemplo en processSwipe)|

---

## Requisitos de Información (RI)
| ID | Nombre del Requisito | Estado |
| :--- | :--- | :---: |
| **RI-21** | Match |Completado|

---

## Requisitos No Funcionales (RNF)
| ID | Nombre del Requisito | Estado |Testeado |
| :--- | :--- | :---: | :---: |
| **RNF-19** | Consistencia de Match bilateral | Completado | Parcialmente |
| **RNF-20** | Latencia de aviso de Match | NO | NO|

---

## Historias de Usuario (HU)
| ID | Título de la Historia | Estado |Testeado |
| :--- | :--- | :---: | :---: |
| **HU-05** | Dashboard de Candidatos | Parcialmente| Parcialmente|
| **HU-06** | Ficha Técnica del Candidato | Completado| Testeado|
| **HU-07** | Gestión de Decisiones | Parcialmente | Parcialmente|
