# ROOMA

# Trazabilidad y control - CU-07: Gestión de cuentas y perfil


## Criterio de la columna Testeado
- **Si**: existe evidencia automatizada directa del requisito en al menos una suite (backend unitario/integracion con JUnit-Spring Test o frontend unitario con Vitest o frontend e2e con Playwright).
- **Parcial**: existe cobertura automatizada, pero solo de una parte del flujo o sin cubrir todas las reglas del requisito.
- **No**: no se encontro evidencia automatizada suficiente del requisito en las suites revisadas.
- **Fuentes revisadas**: `backend/src/test` (unitarios e integracion), `frontend/src/__tests__` (unitarios), `frontend/tests` (e2e).
- **Anexo detallado por RF**: desglose-testing-por-cu-rf.md (usar la seccion del CU correspondiente).

## Matriz de Trazabilidad (HU vs Requisitos)
| ID | Historia de Usuario | RF-63 | RF-64 | RF-65 | RF-66 | RF-67 | RF-68 | RF-69 | RF-70 | RF-71 | RI-16 | RI-17 | RI-18 | RI-19 | RI-20 |
| :--- | :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **HU-57** | Registro de Usuario | x | x | | | | | | | | x | x | | | |
| **HU-58** | Inicio de Sesión Social | | | x | | | | | | | x | | x | | |
| **HU-59** | Recuperación de Acceso | | | x | x | | | | | | x | x | | | |
| **HU-60** | Autenticación en Dos Pasos (2FA) | | | | | x | | | | | x | | | x | |
| **HU-61** | Completar Perfil | | | | | | x | | | | x | | | | |
| **HU-62** | Reporte de Usuarios | | | | | | | x | | | x | | | | x |
| **HU-63** | Moderación Administrativa | | | | | | | | x | | x | | | | x |
| **HU-64** | Verificación de Identidad | | | | | | | | | x | x | | | | |

---

## Requisitos Funcionales (RF)
| ID | Nombre del Requisito | Estado | Testeado |
| :--- | :--- | :---: | :---: |
| **RF-63** | Registro con email e contraseña |  | Si |
| **RF-64** | Validación, verificación e reenvío |  | Parcial |
| **RF-65** | Inicio de sesión con proveedores |  | No |
| **RF-66** | Recuperación de contraseña |  | No |
| **RF-67** | Autenticación en dos pasos (2FA TOTP) |  | No |
| **RF-68** | Completar e editar perfil |  | Parcial |
| **RF-69** | Reportes de usuarios |  | No |
| **RF-70** | Sanciones administrativas |  | No |
| **RF-71** | Verificación de identidad delegada |  | No |

---

## Requisitos de Información (RI)
| ID | Nombre del Requisito | Estado |
| :--- | :--- | :---: |
| **RI-16** | Usuario | |
| **RI-17** | Tokens de Seguridad | |
| **RI-18** | ProveedorOAuth | |
| **RI-19** | Seguridad 2FA | |
| **RI-20** | Audit Log | |

---

## Requisitos No Funcionales (RNF)
| ID | Nombre del Requisito | Estado |
| :--- | :--- | :---: |
| *(No se asocian RNF específicos en la documentación para este CU)* | - | |

---

## Historias de Usuario (HU)
| ID | Título de la Historia | Estado |
| :--- | :--- | :---: |
| **HU-57** | Registro de Usuario | |
| **HU-58** | Inicio de Sesión Social | |
| **HU-59** | Recuperación de Acceso | |
| **HU-60** | Autenticación en Dos Pasos (2FA) | |
| **HU-61** | Completar Perfil | |
| **HU-62** | Reporte de Usuarios | |
| **HU-63** | Moderación Administrativa | |
| **HU-64** | Verificación de Identidad | |
