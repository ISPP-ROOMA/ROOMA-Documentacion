# ROOMA
# Matriz RACI de asigncación de responsabilidades del proyecto

## 1. Introducción

La Matriz RACI es una herramienta de gestión de proyectos que se utiliza para asignar y definir el grado de responsabilidad de cada miembro del equipo en las diferentes tareas o entregables. Define los cuatro roles posibles para cada actividad:

* **R - Responsable:** Es la persona encargada de ejecutar la tarea y asegurar que el trabajo se realice.
* **A - Aprobado final:** Es la persona que tiene la autoridad final sobre la tarea y debe validar el resultado. Solo puede haber uno por cada actividad.
* **C - Consultado:** Personas que poseen información o capacidad necesaria para realizar la tarea. Se establece una comunicación bidireccional con ellos.
* **I - Informado:** Personas a las que se les comunica el progreso o el resultado de la tarea, normalmente en una dirección única.


## 2. Matriz RACI

| Actividad | Product Manager | Product Owner | Product Marketer | Analista | Lead Tech | QA/Tester | DevOps | Diseñador UX/UI | Tesorero | Full-Stack Dev |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| Definir funcionalidades / alcance | A | R | C | C | C | I | I | C | C | I |
| Priorizar backlog | A | R | C | C | I | I | I | I | | I |
| Análisis funcional | I | A | | R | C | I | I | C | | I |
| Modelado de datos | | | | R | A | I | I | | | C |
| Diseño UX | I | A | I | C | I | I | | R | | I |
| Diseño UI | I | A | I | I | I | I | | R | | I |
| Arquitectura técnica | | | | C | A/R | I | I | | | C |
| Seguridad | I | | | C | A/R | I | C | | C | C |
| Desarrollo funcionalidades | I | I | | I | A | I | I | | | R |
| Integraciones externas | I | | | I | A | I | C | | C | R |
| Estrategia de testing | I | | | I | C | A/R | I | | | I |
| Validación release | I | A | I | I | C | R | C | I | | I |
| Despliegues / CI/CD | I | | | I | I | I | A/R | | | I |
| Reglas financieras / pagos | C | I | | C | C | I | C | | A/R | I |
| Mensajería / posicionamiento | C | I | A/R | | | | | C | | |

