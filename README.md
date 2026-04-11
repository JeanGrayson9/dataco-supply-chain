# DataCo Supply Chain Analysis | Análisis de Cadena de Suministro

> **EN** | Supply chain inventory analysis using ABC/XYZ classification, Safety Stock, and Reorder Point calculations — built as a portfolio project demonstrating applied supply chain analytics.
>
> **ES** | Análisis de inventario en cadena de suministro mediante clasificación ABC/XYZ, Stock de Seguridad y Punto de Reorden — proyecto de portafolio que demuestra analítica aplicada de supply chain.

---

## 🇺🇸 English

### Project Description

This project applies core supply chain analytics methodologies to the **DataCo Smart Supply Chain** dataset (Kaggle, ~180,000 rows). The goal is to segment inventory by revenue impact and demand behavior, then calculate optimal safety stock and reorder points for each SKU — translating raw transactional data into actionable inventory decisions.

The analysis was built end-to-end: from raw data cleaning in Python/Excel, through statistical calculations, to an interactive Excel dashboard and a Power BI report.

---

### Dataset

- **Source:** [DataCo SMART SUPPLY CHAIN FOR BIG DATA ANALYSIS — Kaggle](https://www.kaggle.com/datasets/shashwatwork/dataco-smart-supply-chain-for-big-data-analysis)
- **Size:** ~180,000 order-line rows
- **Scope:** Multi-category consumer goods — Apparel, Fanshop, Golf, Pet Shop, and more
- **Note:** The dataset is structured at the order-line level. Demand per SKU was derived by aggregating order quantities; lead time variability was sourced from the dataset's shipping fields.

---

### Methodology & Analysis

#### 1. ABC Classification
SKUs were ranked by total revenue contribution and segmented into three tiers:

| Class | SKUs | Criteria |
|-------|------|----------|
| A | 7 | Top revenue contributors (~80% of total) |
| B | 16 | Mid-tier contributors |
| C | 95 | Long-tail SKUs |

#### 2. XYZ Classification
Demand variability per SKU was measured using the **Coefficient of Variation (CV)**:

| Class | Criteria |
|-------|----------|
| X | CV ≤ 0.5 — stable demand |
| Y | 0.5 < CV ≤ 1.0 — moderate variability |
| Z | CV > 1.0 — high variability |

#### 3. ABC-XYZ Matrix
Combined matrix (118 SKUs total):

| | X | Y | Z |
|---|---|---|---|
| **A** | 7 | 0 | 0 |
| **B** | 2 | 3 | 11 |
| **C** | 0 | 42 | 53 |

**Key insight:** All 7 Class A SKUs fall into the AX segment — high revenue, stable demand, lowest safety stock requirements. These are the highest-priority items for inventory management.

#### 4. Safety Stock & Reorder Point
Calculated using the **dual-variability formula**, which accounts for both demand and lead time uncertainty:

```
SS = Z × √(LT_avg × σ_demand² + demand_avg² × σ_LT²)
ROP = (demand_avg × LT_avg) + SS
```

- **Z-score** based on 95% Customer Service Level (CSL) → Z = 1.645
- Lead time variability was the primary SS driver given the order-line dataset structure

---

### Key Findings

- **7 AX SKUs** represent the highest-priority inventory segment: high revenue + stable demand + lowest safety stock requirements → prime candidates for lean replenishment policies
- **11 BZ SKUs** require the most safety stock relative to their revenue contribution — candidates for demand smoothing or supplier renegotiation
- **53 CZ SKUs** (long-tail, high variability) account for the majority of the catalog while contributing minimally to revenue — rationalization opportunity
- Safety stock levels are driven primarily by **lead time variability**, not demand variability, given the dataset's order-line granularity

---

### Tools Used

| Tool | Purpose |
|------|---------|
| Python (pandas) | Data cleaning, ABC/XYZ calculations, SS/ROP computation |
| Microsoft Excel | Dashboard: KPI cards, ABC Pareto chart, SS/ROP summary table |
| Power BI (DAX) | Interactive report with slicers, KPI visuals, and inventory matrix |
| GitHub | Version control and portfolio publishing |

---

### Contact

**Julian Suarez**
Supply Chain Data Analyst | Freelance & Remote
- 📧 [saintjulian9@gmail.com]
- 💼 [www.linkedin.com/in/juliansuarez9]
- 🐙 [github.com/JeanGrayson9](https://github.com/JeanGrayson9)

---
---

## 🇲🇽 Español

### Descripción del Proyecto

Este proyecto aplica metodologías core de analítica de cadena de suministro al dataset **DataCo Smart Supply Chain** (Kaggle, ~180,000 filas). El objetivo es segmentar el inventario por impacto en ingresos y comportamiento de demanda, y calcular el stock de seguridad y punto de reorden óptimos por SKU — traduciendo datos transaccionales en decisiones concretas de inventario.

El análisis fue construido de extremo a extremo: desde la limpieza de datos en Python/Excel, pasando por los cálculos estadísticos, hasta un dashboard interactivo en Excel y un reporte en Power BI.

---

### Dataset

- **Fuente:** [DataCo SMART SUPPLY CHAIN FOR BIG DATA ANALYSIS — Kaggle](https://www.kaggle.com/datasets/shashwatwork/dataco-smart-supply-chain-for-big-data-analysis)
- **Tamaño:** ~180,000 filas a nivel línea de orden
- **Alcance:** Bienes de consumo multicategoría — Apparel, Fanshop, Golf, Pet Shop, entre otros
- **Nota:** El dataset está estructurado a nivel línea de orden. La demanda por SKU se derivó agregando cantidades de orden; la variabilidad de lead time se obtuvo de los campos de envío del dataset.

---

### Metodología y Análisis

#### 1. Clasificación ABC
Los SKUs fueron ordenados por contribución total de ingresos y segmentados en tres niveles:

| Clase | SKUs | Criterio |
|-------|------|----------|
| A | 7 | Principales generadores de ingreso (~80% del total) |
| B | 16 | Contribución media |
| C | 95 | SKUs de cola larga |

#### 2. Clasificación XYZ
La variabilidad de demanda por SKU se midió con el **Coeficiente de Variación (CV)**:

| Clase | Criterio |
|-------|----------|
| X | CV ≤ 0.5 — demanda estable |
| Y | 0.5 < CV ≤ 1.0 — variabilidad moderada |
| Z | CV > 1.0 — alta variabilidad |

#### 3. Matriz ABC-XYZ
Matriz combinada (118 SKUs en total):

| | X | Y | Z |
|---|---|---|---|
| **A** | 7 | 0 | 0 |
| **B** | 2 | 3 | 11 |
| **C** | 0 | 42 | 53 |

**Hallazgo clave:** Los 7 SKUs Clase A caen en el segmento AX — alto ingreso, demanda estable, menores requerimientos de stock de seguridad. Son los ítems de mayor prioridad para la gestión de inventario.

#### 4. Stock de Seguridad y Punto de Reorden
Calculados con la **fórmula de doble variabilidad**, que considera tanto la incertidumbre de demanda como la de lead time:

```
SS = Z × √(LT_prom × σ_demanda² + demanda_prom² × σ_LT²)
ROP = (demanda_prom × LT_prom) + SS
```

- **Z-score** basado en 95% de Nivel de Servicio al Cliente (CSL) → Z = 1.645
- La variabilidad de lead time fue el principal driver del SS, dado que el dataset opera a nivel línea de orden

---

### Hallazgos Clave

- **7 SKUs AX** representan el segmento de inventario de mayor prioridad: alto ingreso + demanda estable + menores requerimientos de stock de seguridad → candidatos prioritarios para políticas de reabastecimiento lean
- **11 SKUs BZ** requieren el mayor stock de seguridad relativo a su contribución de ingresos — candidatos para suavización de demanda o renegociación con proveedores
- **53 SKUs CZ** (cola larga, alta variabilidad) conforman la mayoría del catálogo con contribución mínima a ingresos — oportunidad de racionalización de portafolio
- Los niveles de stock de seguridad están impulsados principalmente por la **variabilidad de lead time**, no por la variabilidad de demanda, dada la granularidad del dataset

---

### Herramientas Utilizadas

| Herramienta | Uso |
|-------------|-----|
| Python (pandas) | Limpieza de datos, cálculos ABC/XYZ, cómputo de SS/ROP |
| Microsoft Excel | Dashboard: tarjetas KPI, gráfico Pareto ABC, tabla resumen SS/ROP |
| Power BI (DAX) | Reporte interactivo con slicers, visuales KPI y matriz de inventario |
| GitHub | Control de versiones y publicación de portafolio |

---

### Contacto

**Julian Suarez**
Analista de Datos — Cadena de Suministro | Freelance & Remoto
- 📧 [saintjulian9@gmail.com]
- 💼 [www.linkedin.com/in/juliansuarez9]
- 🐙 [github.com/JeanGrayson9](https://github.com/JeanGrayson9)
