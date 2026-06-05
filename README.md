# VISUAL_CODES

A collection of Python data-visualization recipes built around a small set of
sales/store datasets. The notebook walks through the main chart families —
proportion, trend, correlation, distribution, and multi-dimensional analysis —
using `matplotlib`, `seaborn`, `pandas`, and `statsmodels`.

Each cell is self-contained: it loads the data it needs, builds one figure, and
shows it. You can run any cell on its own.

## Requirements

```bash
pip install pandas numpy matplotlib seaborn statsmodels
```

Python 3.8+ and a Jupyter environment (JupyterLab, classic Notebook, or the
VS Code notebook editor).

## Data

All datasets are read directly from public URLs, so **an internet connection is
required** to run the cells. No local files are needed.

| Group   | Files |
|---------|-------|
| Product | `DailySales`, `MarketingPerProduct`, `PricePerUnit`, `ProfitPerUnit` |
| Store   | `StoreDailyCustomers`, `StoreMarketing`, `StoreOverheads`, `StoreSize`, `StoreStaff` |

Most cells use `DailySales` (daily units sold per product, indexed by date) and
derive a `summary_data` table (Price, Profit, Sales, Marketing per product) for
the multi-dimensional sections.

## Contents

The notebook is organized into sections (L2–L6), each focused on a question and
the chart types that answer it.

| Section | Theme | Techniques |
|---------|-------|-----------|
| **L2** | Proportion | Bar charts (grouped, sorted, volume-segmented, small items rolled into "Others"); pie charts with percentages and `explode` |
| **L3** | Trend over time | Line charts and stacked area (`stackplot`) for time series |
| **L4** | Correlation | Scatter plots and pairwise scatter grids; seaborn correlation heatmap; rolling-mean trend overlays |
| **L5** | Distribution | Histograms (with dynamic bin sizing and subplot grids); boxplots by volume segment; autocorrelation; seasonal decomposition (`seasonal_decompose`) |
| **L6** | Multiple dimensions | Bubble charts, seaborn `pairplot`, and OLS regression with `statsmodels` over the summary table |

## Running

Open the notebook and run the cells top to bottom, or run any single cell —
each one re-imports its libraries and reloads its data.

### Notes

- A couple of cells require `statsmodels` (one cell even runs `pip install
  statsmodels`); make sure it is installed if you skip ahead to L5/L6.
- The seaborn heatmap cell includes a comment about a known clipping bug in
  `matplotlib 3.1.1`. If the heatmap edges get cut off, reinstall a different
  matplotlib version as noted in that cell.
