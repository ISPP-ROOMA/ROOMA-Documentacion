# ROOMA

# Trazabilidad y control - CU-09: Gestión de facturas y pagos


## Criterio de la columna Testeado
- **Si**: existe evidencia automatizada directa del requisito en al menos una suite (backend unitario/integracion con JUnit-Spring Test o frontend unitario con Vitest o frontend e2e con Playwright).
- **Parcial**: existe cobertura automatizada, pero solo de una parte del flujo o sin cubrir todas las reglas del requisito.
- **No**: no se encontro evidencia automatizada suficiente del requisito en las suites revisadas.
- **Fuentes revisadas**: `backend/src/test` (unitarios e integracion), `frontend/src/__tests__` (unitarios), `frontend/tests` (e2e).
- **Anexo detallado por RF**: desglose-testing-por-cu-rf.md (usar la seccion del CU correspondiente).

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
| **RF-15** | Pantalla de Registro de Gastos |  | Si |
| **RF-16** | Selector Visual de Inquilinos e Modo de Reparto |  | Si |
| **RF-17** | Visualización de Cuotas en Tiempo Real |  | Si |
| **RF-18** | Dashboard de "Mis Pagos" (Vista Inquilino) |  | Si |
| **RF-19** | Pasarela de Pago Integrada |  | Parcial |
| **RF-20** | Indicadores de Estado de Pago |  | Si |
| **RF-21** | Interruptor de Auto-Pago |  | No |
| **RF-22** | Dashboard de Cobros (Vista Casero) |  | Si |
| **RF-23** | Notificaciones de Pagos |  | No |
| **RF-24** | Exportación de Historial Financiero |  | No |
| **RF-25** | Gestión de Métodos de Pago |  | No |
| **RF-26** | Anulación e Edición de Facturas |  | Parcial |

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
