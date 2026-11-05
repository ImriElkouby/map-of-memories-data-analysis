# Map of Memories: Analysis of Terror Attacks Against Israeli Civilians (2000–2023)

A team data-analysis project that explores **when, where and how** terror attacks against Israeli civilians occurred between 2000 and 2023, using victim-level data collected by B'Tselem.

**Team:** Imri Elkouby, Yuval Kirshner, Noa Manor
**Tools:** Python, Pandas, NumPy, Matplotlib, Seaborn, Jupyter Notebook

## Key findings

- **Seasonality:** Attacks are spread fairly evenly across the year (21%–28% per season), but **spring and summer attacks were the deadliest**, with about 2.75 fatalities per attack compared with about 2.1–2.3 in autumn and winter.
- **Geography:** Inside the Green Line, attacks are **concentrated in a few cities**: Jerusalem alone accounts for 40 attacks, followed by Tel Aviv-Yafo (15). In the West Bank, attacks are **spread across many locations**, and no single place has more than 6.
- **Victims by weekday:** Inside the Green Line, the average age of victims **drops towards the weekend**, while on other days it stays stable regardless of region.

![Bar and line chart of attacks and fatalities by season, with a pie chart of each season's share of attacks. Spring has the most attacks (100) and fatalities (275).](seasons-chart.png)

![Three bar charts: attacks by region (West Bank highest, then Israel, then Gaza Strip), top 5 cities in Israel (Jerusalem far ahead), and top 5 locations in the West Bank (5 to 6 attacks each).](regions-chart.png)

## Data

- **Source:** [Kaggle: Israeli–Palestinian Conflict dataset](https://www.kaggle.com/datasets/nada144/israeli-palestinian-conflict), originally collected by B'Tselem
- **Scope:** 881 Israeli civilian victims of attacks by Palestinians, 2000–2023
- Each row in the original data is a **victim**. We grouped victims by date and location to build a second dataset where each row is an **attack** (356 attacks).

## What we did

1. **Data cleaning:** parsed dates, merged duplicate categories (injury types, weapon types, city names such as the different spellings of Jerusalem and Tel Aviv), fixed inconsistent values.
2. **Feature engineering:** day of week, month, season, days from attack to death, and whether the attack happened during Ramadan (using a 2000–2023 Ramadan calendar).
3. **Exploratory analysis:** distributions by gender, weapon, year, region and city, plus a Spearman correlation heatmap.
4. **Visualization and conclusions:** charts that answer each research question, with conclusions written in the notebook.

## Project structure

| File | What it is |
|------|-----------|
| `project.ipynb` | The full analysis notebook: start here |
| `Israeli civilians killed by Palestinians.csv` | Source data (one row per victim) |
| `data_project.csv` | Copy of the data used in the analysis |
| `israeli-palestinian-conflict-metadata.json` | Dataset metadata from Kaggle |

## How to run

```bash
pip install pandas numpy matplotlib seaborn plotly scikit-learn jupyter
jupyter notebook project.ipynb
```
