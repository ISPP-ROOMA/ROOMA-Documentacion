# ROOMA

# Trazabilidad y control - CU-09: Gestión de facturas y pagos


## Matriz de Trazabilidad (HU vs Requisitos)
| ID | Historia de Usuario | RF-15 | RF-16 | RF-17 | RF-18 | RF-19 | RF-20 | RF-21 | RF-22 | RF-23 | RF-24 | RF-25 | RF-26 | RNF-11 | RNF-12 | RNF-16 | RNF-17 | RI-07 | RI-08 | RI-09 | RI-10 |
| :--- | :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **HU-12** | Registro de Facturas | x | x | | | | | | | | | | | | x | | | x | | | |
| **HU-13** | Selección de Participantes e Reparto | | x | x | | | | | | | | | | | | | | x | x | | |
| **HU-14** | Dashboard de Cobros (Vista Casero) | | | | | | | | x | x | | | | | | | | x | x | | |
| **HU-15** | Edición e Anulación de Facturas | | | | | | | | | | | | x | | | | | x | x | | |
| **HU-16** | Exportación Contable (Casero) | | | | | | | | | | x | | | | | | | x | x | | |
| **HU-17** | Dashboard "Mis Pagos" (Inquilino) | | | | x | | x | | | | | | | | | | | | x | | |
| **HU-18** | Historial de Pagos (Inquilino) | | | | x | | | | | | | | | | | | | | x | x | |
| **HU-19** | Pago con un Clic | | | | | x | | | | | | | | x | x | x | x | | x | x | x |
| **HU-20** | Activación de Auto-Pago | | | | | | | x | | | | | | x | | | | | x | x | x |
| **HU-21** | Gestión de Métodos de Pago | | | | | | | | | | | x | | x | x | | | | | | x |
| **HU-22** | Exportación de Justificantes (Inquilino) | | | | | | | | | | x | | | | | | | | x | x | |
| **HU-23** | Sistema de Alertas de Pago | | | | x | | | | | x | | | | | | | | | x | | |

---

## Requisitos Funcionales (RF)
| ID | Nombre del Requisito | Estado | Testeado |
| :--- | :--- | :---: | :---: |
| **RF-15** | Pantalla de Registro de Gastos | | |
| **RF-16** | Selector Visual de Inquilinos e Modo de Reparto | | |
| **RF-17** | Visualización de Cuotas en Tiempo Real | | |
| **RF-18** | Dashboard de "Mis Pagos" (Vista Inquilino) | | |
| **RF-19** | Pasarela de Pago Integrada | | |
| **RF-20** | Indicadores de Estado de Pago | | |
| **RF-21** | Interruptor de Auto-Pago | | |
| **RF-22** | Dashboard de Cobros (Vista Casero) | | |
| **RF-23** | Notificaciones de Pagos | | |
| **RF-24** | Exportación de Historial Financiero | | |
| **RF-25** | Gestión de Métodos de Pago | | |
| **RF-26** | Anulación e Edición de Facturas | | |

---

## Requisitos de Información (RI)
| ID | Nombre del Requisito | Estado |
| :--- | :--- | :---: |
| **RI-07** | FacturaGasto | |
| **RI-08** | DeudaInquilino | |
| **RI-09** | TransaccionPago | |
| **RI-10** | MetodoPago | |

---

## Requisitos No Funcionales (RNF)
| ID | Nombre del Requisito | Estado |
| :--- | :--- | :---: |
| **RNF-11** | Cumplimiento PCI-DSS | |
| **RNF-12** | Cifrado AES-256 e TLS 1.2+ | |
| **RNF-16** | Uptime del 99.00% en pagos | |
| **RNF-17** | Claves de Idempotencia | |

---

## Historias de Usuario (HU)
| ID | Título de la Historia | Estado |
| :--- | :--- | :---: |
| **HU-12** | Registro de Facturas | |
| **HU-13** | Selección de Participantes e Reparto | |
| **HU-14** | Dashboard de Cobros (Vista Casero) | |
| **HU-15** | Edición e Anulación de Facturas | |
| **HU-16** | Exportación Contable (Casero) | |
| **HU-17** | Dashboard "Mis Pagos" (Inquilino) | |
| **HU-18** | Historial de Pagos (Inquilino) | |
| **HU-19** | Pago con un Clic | |
| **HU-20** | Activación de Auto-Pago | |
| **HU-21** | Gestión de Métodos de Pago | |
| **HU-22** | Exportación de Justificantes (Inquilino) | |
| **HU-23** | Sistema de Alertas de Pago | |