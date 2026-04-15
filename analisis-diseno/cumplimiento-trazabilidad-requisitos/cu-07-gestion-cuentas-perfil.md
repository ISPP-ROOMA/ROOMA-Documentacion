# ROOMA

# Trazabilidad y control - CU-07: Gestión de cuentas y perfil


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
| **RF-63** | Registro con email e contraseña | Completado Parcialmente (la vaidación de cuentas no está implementada y la contraseña solo tiene como restriccion min de 4 chars)| Si |
| **RF-64** | Validación, verificación e reenvío | Por Hacer | Parcial |
| **RF-65** | Inicio de sesión con proveedores | Por Hacer | No |
| **RF-66** | Recuperación de contraseña | Por Hacer | No |
| **RF-67** | Autenticación en dos pasos (2FA TOTP) | Por Hacer | No |
| **RF-68** | Completar e editar perfil | Completado | Parcial |
| **RF-69** | Reportes de usuarios | Por Hacer | No |
| **RF-70** | Sanciones administrativas | Por Hacer | No |
| **RF-71** | Verificación de identidad delegada | Por Hacer | No |

---

## Requisitos de Información (RI)
| ID | Nombre del Requisito | Estado |
| :--- | :--- | :---: |
| **RI-16** | Usuario | Completado | 
| **RI-17** | Tokens de Seguridad | Parcialmente Completado (falta incluir el tipo de Token)|
| **RI-18** | ProveedorOAuth | Completado |
| **RI-19** | Seguridad 2FA | Por Hacer |
| **RI-20** | Audit Log | Por Hacer |

---

## Requisitos No Funcionales (RNF)
| ID | Nombre del Requisito | Estado |
| :--- | :--- | :---: |
| *(No se asocian RNF específicos en la documentación para este CU)* | - | |

---

## Historias de Usuario (HU)
| ID | Título de la Historia | Estado |
| :--- | :--- | :---: |
| **HU-57** | Registro de Usuario | Completado Parcialmente|
| **HU-58** | Inicio de Sesión Social | Por Hacer|
| **HU-59** | Recuperación de Acceso | Por Hacer|
| **HU-60** | Autenticación en Dos Pasos (2FA) | Por Hacer|
| **HU-61** | Completar Perfil | Completado|
| **HU-62** | Reporte de Usuarios | Por Hacer|
| **HU-63** | Moderación Administrativa | Por Hacer|
| **HU-64** | Verificación de Identidad | Por Hacer|
