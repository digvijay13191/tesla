# Analyzing Historical Stock/Revenue Data and Building a Dashboard

Final assignment for the Python course. It collects stock and revenue data for **Tesla (TSLA)** and **GameStop (GME)**, analyzes it, and builds an interactive dashboard in Jupyter Notebook.

## What it does

- Downloads historical share prices with `yfinance`.
- Scrapes quarterly revenue tables from HTML pages with `requests` and `BeautifulSoup`.
- Cleans the revenue data (removes `$` and commas, drops empty rows).
- Plots share price and revenue together with `plotly`.

## Files

| File | Contents |
|------|----------|
| `Final_Assignment_Stock_Revenue_Dashboard.ipynb` | Full notebook with all 6 exercises. This is the file to submit. |
| `Q1_Tesla_Stock_Data.ipynb` | Q1: Tesla stock data, `tesla_data.head()` |
| `Q2_Tesla_Revenue.ipynb` | Q2: Tesla revenue scraping, `tesla_revenue.tail()` |
| `Q3_GameStop_Stock_Data.ipynb` | Q3: GameStop stock data, `gme_data.head()` |
| `Q4_GameStop_Revenue.ipynb` | Q4: GameStop revenue scraping, `gme_revenue.tail()` |
| `Q5_Tesla_Dashboard.ipynb` | Q5: Tesla share price and revenue graphs |
| `Q6_GameStop_Dashboard.ipynb` | Q6: GameStop share price and revenue graphs |

Each per-question notebook is self-contained and can be run on its own.

## Requirements

- Python 3.8+
- Internet access (for Yahoo Finance and the course data URLs)
- Packages: `yfinance`, `pandas`, `requests`, `beautifulsoup4`, `lxml`, `plotly`

The first cell of each notebook installs them:

```
!pip install yfinance beautifulsoup4 lxml plotly pandas requests
```

## How to run

1. Open a notebook in Jupyter, JupyterLab, or the course lab environment.
2. Choose **Kernel > Restart & Run All**.
3. Confirm every code cell shows output (tables for the `head()`/`tail()` cells, charts for the dashboard cells).
4. Save the notebook (**Ctrl+S**) so the outputs are stored in the `.ipynb` file.

## Exercises

1. **Tesla stock data:** use `yf.Ticker("TSLA").history(period="max")`, reset the index, show the first 5 rows.
2. **Tesla revenue:** scrape the revenue table, clean the `Revenue` column, show the last 5 rows.
3. **GameStop stock data:** same as Q1 with `GME`.
4. **GameStop revenue:** same as Q2 with the GameStop page.
5. **Tesla dashboard:** `make_graph(tesla_data, tesla_revenue, "Tesla")`.
6. **GameStop dashboard:** `make_graph(gme_data, gme_revenue, "GameStop")`.

## Notes

- `make_graph` limits the stock data to dates up to 2021-06-14 and the revenue data to dates up to 2021-04-30.
- `Date` columns are converted to timezone-naive datetimes so date filtering works with recent `yfinance` versions.
- If `yfinance` returns a rate-limit error or an empty table, wait a minute and rerun, or restart the kernel.
- The notebooks are delivered without saved outputs. Run them before submitting.

## Data sources

- Stock prices: Yahoo Finance via `yfinance`
- Revenue: HTML pages provided by the course (scraped with BeautifulSoup)
