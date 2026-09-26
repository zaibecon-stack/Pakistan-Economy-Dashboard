# Pakistan Economic Indicators Dashboard (2016–2026)

A Power BI dashboard tracking three key Pakistani macroeconomic indicators — CPI inflation, the PKR/USD exchange rate, and SBP's policy rate — over a 10-year period, built to visualize how they moved together through Pakistan's 2022–23 economic crisis.

<img width="1171" height="666" alt="image" src="https://github.com/user-attachments/assets/ac042458-e1e8-462b-92da-8abdd9cb444d" />


## Data Source

All data was sourced from the [State Bank of Pakistan's EasyData portal](https://easydata.sbp.org.pk):
- CPI National Inflation (Year-over-Year %)
- Bank Floating Average Exchange Rate (PKR per USD)
- SBP Policy (Target) Rate

## Key Findings

Inflation and the exchange rate both spiked sharply during Pakistan's 2022–23 economic crisis — inflation peaked near 35–38% while the rupee depreciated from roughly 150 to 280 against the dollar. In response, SBP raised its policy rate to a high of 22%, holding it there before gradually cutting rates as inflation eased through 2024–2026.

## Methodology Notes

- Inflation and exchange rate data are reported monthly and were merged directly by date.
- The policy rate is only recorded when SBP's Monetary Policy Committee changes it, so it does not have a value for every month. A **forward-fill** technique (`MAXIFS` + `VLOOKUP` in Excel) was used to carry the last known rate forward until the next rate change, correctly reflecting that the rate stays constant between policy decisions.
- All three series were combined into a single monthly master table before being loaded into Power BI.

## Tools Used

- **Excel** — data cleaning, date standardization (`EOMONTH`), and forward-fill merging (`MAXIFS` + `VLOOKUP`)
- **Power BI Desktop** — dashboard visualization

## Files

- `dashboard-screenshot.png` — exported view of the final dashboard
- `master-data.xlsx` — cleaned, merged dataset (Date, Inflation, Exchange Rate, Policy Rate)
- `raw-data/` — original CSV exports from SBP EasyData

## About

Built by [Aurang Zaib] as a portfolio project. [Aurang Zaib] is an economics graduate learning data analytics, focused on projects that connect economic theory with real data.
