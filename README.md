# DataCo Supply Chain — Análisis de Entregas Tardías
### Late Delivery Analysis | Supply Chain Data Analytics Project

---

## 🇲🇽 Español

### Descripción
Análisis exploratorio de un dataset real de operaciones de supply chain con 180,519 órdenes de venta distribuidas en múltiples mercados globales (LATAM, Europa, Pacific Asia, USCA, África).

El objetivo fue identificar patrones en las entregas tardías, su distribución por modo de envío, mercado y categoría de producto, y cuantificar el impacto financiero de las órdenes con pérdida.

### Hallazgos principales

- **Tasa global de entregas tardías: 57.28%** — problema sistémico presente en todos los mercados y categorías de forma uniforme.
- **First Class: 100% de entregas tardías** — el modo de envío más costoso para el cliente tiene la peor ejecución operativa. Los clientes que pagan más por velocidad son los más afectados.
- **Second Class: 79.73% de tardanzas** — muy por encima del promedio global.
- **Standard Class es el modo más confiable (39.77%)** — paradoja operativa: el modo más lento es el más predecible.
- **18.71% de órdenes generan pérdida** — equivalente a $3.88 millones en déficit acumulado.
- **El problema no es geográfico:** todos los mercados presentan tasas entre 56.81% y 57.69%, lo que apunta a un fallo en el proceso de promesa de fecha de entrega, no en la logística regional.

### Recomendaciones
1. Revisar el proceso de asignación de fechas prometidas en First Class y Second Class.
2. Investigar si el problema de First Class es de capacidad, rutas o configuración del sistema.
3. Auditar las 33,784 órdenes con pérdida para identificar patrones de descuento excesivo.

### Herramientas utilizadas
- **Python** — Pandas para manipulación y análisis de datos
- **Matplotlib** — visualizaciones
- **Excel** — análisis exploratorio inicial con tablas dinámicas (Pivot Tables)
- **VS Code + Jupyter Notebook** — entorno de desarrollo
- **GitHub** — control de versiones y portafolio

### Estructura del proyecto
```
dataco-supply-chain/
├── data/                        # Dataset original (.xlsx)
├── notebooks/
│   └── 01_exploracion_inicial.ipynb   # Análisis completo
├── outputs/
│   └── analisis_entregas.png    # Visualizaciones generadas
└── README.md
```

### Dataset
DataCo Smart Supply Chain for Big Data Analysis — disponible públicamente en [Kaggle](https://www.kaggle.com/datasets/shashwatwork/dataco-smart-supply-chain-for-big-data-analysis).

---

## 🇺🇸 English

### Description
Exploratory analysis of a real supply chain operations dataset containing 180,519 sales orders across multiple global markets (LATAM, Europe, Pacific Asia, USCA, Africa).

The goal was to identify late delivery patterns by shipping mode, market, and product category, and to quantify the financial impact of loss-generating orders.

### Key Findings

- **Global late delivery rate: 57.28%** — a systemic issue present uniformly across all markets and product categories.
- **First Class: 100% late deliveries** — the most expensive shipping mode has the worst operational performance. Customers paying a premium for speed are the most affected.
- **Second Class: 79.73% late** — well above the global average.
- **Standard Class is the most reliable mode (39.77%)** — an operational paradox: the slowest mode is the most predictable.
- **18.71% of orders generate a loss** — equivalent to $3.88M in accumulated deficit.
- **The problem is not geographic:** all markets show rates between 56.81% and 57.69%, pointing to a failure in the delivery date promise process rather than regional logistics.

### Recommendations
1. Review the delivery date assignment process for First Class and Second Class shipments.
2. Investigate whether the First Class issue stems from capacity constraints, routing, or system configuration.
3. Audit the 33,784 loss-generating orders to identify excessive discount patterns.

### Tools Used
- **Python** — Pandas for data manipulation and analysis
- **Matplotlib** — data visualizations
- **Excel** — initial exploratory analysis using Pivot Tables
- **VS Code + Jupyter Notebook** — development environment
- **GitHub** — version control and portfolio

### Project Structure
```
dataco-supply-chain/
├── data/                        # Original dataset (.xlsx)
├── notebooks/
│   └── 01_exploracion_inicial.ipynb   # Full analysis
├── outputs/
│   └── analisis_entregas.png    # Generated visualizations
└── README.md
```

### Dataset
DataCo Smart Supply Chain for Big Data Analysis — publicly available on [Kaggle](https://www.kaggle.com/datasets/shashwatwork/dataco-smart-supply-chain-for-big-data-analysis).

---

*Análisis realizado por Julian Suarez | Supply Chain Data Analyst*
*Analysis by Julian Suarez | Supply Chain Data Analyst* 