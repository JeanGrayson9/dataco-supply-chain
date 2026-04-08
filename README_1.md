# DataCo Supply Chain Analysis

**End-to-end supply chain analysis** using the DataCo SMART SUPPLY CHAIN dataset (Kaggle, ~180K rows). The project covers ABC/XYZ classification, Safety Stock and Reorder Point calculations, and an executive dashboard built in Excel and Power BI.

---

## Objectives

- Classify the SKU portfolio by revenue impact (ABC) and demand variability (XYZ)
- Calculate Safety Stock and Reorder Point per SKU using a dual-variability formula
- Identify systemic delivery and profitability issues in the order data
- Build an interactive executive dashboard to communicate findings

---

## Dataset

**Source:** [DataCo SMART SUPPLY CHAIN FOR BIG DATA ANALYSIS](https://www.kaggle.com/datasets/shashwatwork/dataco-smart-supply-chain-for-big-data-analysis) — Kaggle  
**Size:** ~180,000 order-line records  
**Note:** The dataset is structured at the order-line level, so demand per SKU averages ~1 unit. Safety Stock values are therefore driven primarily by lead time variability, not demand variability. This is documented and expected given the dataset structure.

---

## Methodology

### ABC Classification
SKUs ranked by cumulative revenue contribution:
| Class | SKUs | Criteria |
|-------|------|----------|
| A | 7 | Top 80% of revenue |
| B | 16 | Next 15% of revenue |
| C | 95 | Remaining 5% of revenue |

### XYZ Classification
SKUs ranked by coefficient of variation (CV) of demand:
| Class | Criteria |
|-------|----------|
| X | CV ≤ 0.5 — stable demand |
| Y | 0.5 < CV ≤ 1.0 — variable demand |
| Z | CV > 1.0 — highly irregular demand |

**ABC-XYZ Matrix results:**

| | X | Y | Z |
|---|---|---|---|
| **A** | 7 | 0 | 0 |
| **B** | 2 | 3 | 11 |
| **C** | 0 | 42 | 53 |

### Safety Stock & Reorder Point
Dual-variability formula accounting for both demand and lead time uncertainty:

```
SS = Z × √(LT_avg × σ_demand² + demand_avg² × σ_LT²)
ROP = (demand_avg × LT_avg) + SS
```

Where Z = 1.65 (95% service level).

---

## Key Findings

- **57.28% global late delivery rate** — systemic across all geographies and shipping modes, indicating a structural operations issue rather than a regional one
- **First Class shipping = 100% late deliveries** — the premium shipping mode underperforms every other option
- **~18.71% of orders are unprofitable** — negative margin orders concentrated in specific product categories
- **AX SKUs (7 products)** represent the highest-priority inventory segment: high revenue + stable demand + low safety stock requirements

---

## Tools

| Tool | Use |
|------|-----|
| Microsoft Excel | Data cleaning, ABC/XYZ classification, SS/ROP calculations, dashboard |
| Microsoft Power BI | Interactive executive dashboard with DAX measures |

---

## Repository Structure

```
dataco-supply-chain/
│
├── data/
│   └── (dataset not included — download from Kaggle link above)
│
├── excel/
│   └── DataCoSupplyChainDataset.xlsx   # ABC/XYZ classification + SS/ROP + dashboard
│
├── powerbi/
│   └── DataCoSupply PowerBI.pbix       # Power BI executive dashboard
│
└── README.md
```

---

## Contact

**Julian Suarez**  
Supply Chain Data Analyst  
[GitHub](https://github.com/JeanGrayson9) · [LinkedIn](https://www.linkedin.com/in/julian-suarez-85a5543b6) · Mazatlán, México

---
---

# Análisis de Cadena de Suministro — DataCo

**Análisis end-to-end de cadena de suministro** usando el dataset DataCo SMART SUPPLY CHAIN (Kaggle, ~180K filas). El proyecto cubre clasificación ABC/XYZ, cálculo de Stock de Seguridad y Punto de Reorden, y un dashboard ejecutivo construido en Excel y Power BI.

---

## Objetivos

- Clasificar el portafolio de SKUs por impacto en ingresos (ABC) y variabilidad de demanda (XYZ)
- Calcular Stock de Seguridad y Punto de Reorden por SKU usando fórmula de doble variabilidad
- Identificar problemas sistémicos de entrega y rentabilidad en los datos de órdenes
- Construir un dashboard ejecutivo interactivo para comunicar los hallazgos

---

## Dataset

**Fuente:** [DataCo SMART SUPPLY CHAIN FOR BIG DATA ANALYSIS](https://www.kaggle.com/datasets/shashwatwork/dataco-smart-supply-chain-for-big-data-analysis) — Kaggle  
**Tamaño:** ~180,000 registros a nivel línea de orden  
**Nota:** El dataset está estructurado a nivel línea de orden, por lo que la demanda promedio por SKU es ~1 unidad. Los valores de Stock de Seguridad están impulsados principalmente por la variabilidad del lead time, no de la demanda. Esto está documentado y es esperado dada la estructura del dataset.

---

## Metodología

### Clasificación ABC
SKUs ordenados por contribución acumulada a ingresos:
| Clase | SKUs | Criterio |
|-------|------|----------|
| A | 7 | Top 80% de ingresos |
| B | 16 | Siguiente 15% de ingresos |
| C | 95 | 5% restante de ingresos |

### Clasificación XYZ
SKUs ordenados por coeficiente de variación (CV) de demanda:
| Clase | Criterio |
|-------|----------|
| X | CV ≤ 0.5 — demanda estable |
| Y | 0.5 < CV ≤ 1.0 — demanda variable |
| Z | CV > 1.0 — demanda altamente irregular |

**Matriz ABC-XYZ:**

| | X | Y | Z |
|---|---|---|---|
| **A** | 7 | 0 | 0 |
| **B** | 2 | 3 | 11 |
| **C** | 0 | 42 | 53 |

### Stock de Seguridad y Punto de Reorden
Fórmula de doble variabilidad considerando incertidumbre de demanda y lead time:

```
SS = Z × √(LT_prom × σ_demanda² + demanda_prom² × σ_LT²)
ROP = (demanda_prom × LT_prom) + SS
```

Donde Z = 1.65 (nivel de servicio 95%).

---

## Hallazgos Clave

- **57.28% de tasa global de entregas tardías** — sistémica en todas las geografías y modos de envío, indicando un problema estructural de operaciones y no un problema regional
- **Envío First Class = 100% de entregas tardías** — el modo de envío premium tiene el peor desempeño de todos
- **~18.71% de órdenes son no rentables** — órdenes con margen negativo concentradas en categorías específicas
- **SKUs AX (7 productos)** representan el segmento de inventario de mayor prioridad: alto ingreso + demanda estable + bajos requerimientos de stock de seguridad

---

## Herramientas

| Herramienta | Uso |
|-------------|-----|
| Microsoft Excel | Limpieza de datos, clasificación ABC/XYZ, cálculos SS/ROP, dashboard |
| Microsoft Power BI | Dashboard ejecutivo interactivo con medidas DAX |

---

## Estructura del Repositorio

```
dataco-supply-chain/
│
├── data/
│   └── (dataset no incluido — descargar desde el enlace de Kaggle)
│
├── excel/
│   └── DataCoSupplyChainDataset.xlsx   # Clasificación ABC/XYZ + SS/ROP + dashboard
│
├── powerbi/
│   └── DataCoSupply PowerBI.pbix       # Dashboard ejecutivo Power BI
│
└── README.md
```

---

## Contacto

**Julian Suarez**  
Analista de Datos — Cadena de Suministro  
[GitHub](https://github.com/JeanGrayson9) · [LinkedIn](https://www.linkedin.com/in/julian-suarez-85a5543b6) · Mazatlán, México
