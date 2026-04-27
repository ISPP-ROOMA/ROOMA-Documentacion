# Informe de costes

Este apartado detalla el capital ya consumido del presupuesto CAPEX original, calculado en función del tiempo transcurrido desde el inicio del proyecto: **$n$** semanas de desarrollo laboral y **$m$** meses de licencias de activos digitales.

## 1. Resumen de Gasto CAPEX Realizado
Se desglosa el gasto ejecutado sobre la inversión inicial, aplicando el prorrateo temporal a las partidas de servicios recurrentes y personal según el cronograma de ejecución.

| Categoría | Cálculo de ejecución | Importe Gastado |
| :--- | :--- | :---: |
| **Equipamiento Informático** | Pago único inicial (100%) | 16.000,00 € |
| **Propiedad Intelectual y Legal** | Liquidación total de registros y constitución (100%) | 7.350,00 € |
| **Licencias y Activos Digitales** | $(1.300 / 4) \times m$ meses | 325 · ${m}$ € |
| **Laboral (Desarrollo)** | (16 trabajadores · 17,82€ la hora · 8 h semanales) $\times n$ semanas | 2280,96 · ${n}$ € |
| **Contingencia Consumida** | 10% sobre el gasto real acumulado | 2.335 + 32,5 · ${m}$ + 228,10 · ${n}$ € |
| **TOTAL GASTADO (CAPEX)** |  | 25.685 + 357,5 · ${m}$ + 2509,06 · ${n}$ € |


### Fórmula de Cálculo del Gasto Ejecutado ($G_e$)
> $$G_e = 25.685 + 357,5 \cdot m + 2.509,06 \cdot n$$


**Ejemplo de verificación (Estado a 16/04/2026):**
> $m = 3$ y $n = 11$:

> $G_e = 25.685 + (357,5 \times 3) + (2.509,06 \times 11) = \mathbf{54.357,16 \text{ €}}$



## 2. Resumen de Gasto OPEX Realizado
Este apartado refleja los costes operativos acumulados durante los **$m$** meses de construcción del producto. Al ser costes fijos mensuales, el cálculo es estrictamente lineal.

| Categoría | Cálculo de ejecución | Importe Gastado |
| :--- | :--- | :---: |
| **Infraestructura Cloud** | 53,72 € $\times m$ meses | 53,72 · ${m}$ € |
| **Herramientas de Desarrollo** | 541,92 € $\times m$ meses | 541,92 · ${m}$ € |
| **Suministros (Luz)** | 19,20 € $\times m$ meses | 19,20 · ${m}$ € |
| **Laboral (Mantenimiento)** | 2.280,96 € $\times m$ meses | 2280,96 · ${m}$ € |
| **Contingencia Operativa** | 10% sobre el gasto operativo acumulado | 289,58 · ${m}$ € |
| **TOTAL GASTADO (OPEX)** | | **3185,38 · ${m}$ €** |


### Fórmula de Cálculo del Gasto Operativo ($O_e$)
> $$O_e = 3.185,38 \cdot m$$


**Ejemplo de verificación ($m = 3$ meses):**
> $O_e = 3.185,38 \times 3 = \mathbf{9.556,14 \text{ €}}$