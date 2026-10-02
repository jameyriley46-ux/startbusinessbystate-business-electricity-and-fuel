# Business Electricity Prices, Generation Mix and Diesel and Gas Prices by State, 2026 (startbusinessbystate.com)

Commercial and industrial electricity prices and increases, power plant fuel mix, prices in data center states, and weekly diesel and gasoline prices by state, from EIA data.

Main page: https://startbusinessbystate.com/business-electricity-cost-increase-by-state/

## Summary

What businesses pay for electricity in each state and how fast it is rising, where each state's electricity comes from, how prices compare in states with heavy data center building, and what diesel and gasoline cost this week, with a simple yearly fuel cost for a work truck.

## Files

| File | Rows | What it is |
|---|---|---|
| `data/business_electricity_prices_by_state.csv` | 52 | Commercial and industrial electricity prices and increases by state (U.S. total row included). |
| `data/diesel_gas_prices_by_state.csv` | 51 | Weekly diesel and regular gasoline prices by state, with example truck fuel costs. |
| `data/electricity_generation_mix_by_state.csv` | 52 | Where each state's electricity comes from (U.S. total row included). |
| `data/electricity_prices_by_data_center_tier.csv` | 52 | Residential and commercial prices with each state's data center tier (U.S. total row included). |

All files are UTF-8 CSV with a header row in snake_case. Blank cells mean the value is not available, not applicable, or suppressed by the source.

## Data dictionary

### data/business_electricity_prices_by_state.csv

Commercial and industrial electricity prices and increases by state (U.S. total row included). Rows: 52. Columns: 26.

| Column | Meaning | Units |
|---|---|---|
| `state` | Two-letter code (US = national). | text |
| `state_name` | State name. | text |
| `com_price_12m_jul2019` | Commercial price, 12 months ending July 2019. | cents per kilowatt-hour |
| `com_price_12m_jul2021` | Commercial price, 12 months ending July 2021. | cents per kilowatt-hour |
| `com_price_12m_jul2022` | Commercial price, 12 months ending July 2022. | cents per kilowatt-hour |
| `com_price_12m_jul2025` | Commercial price, 12 months ending July 2025. | cents per kilowatt-hour |
| `com_price_12m_jul2026` | Commercial price, 12 months ending July 2026. | cents per kilowatt-hour |
| `com_chg_1yr_pct` | Change in commercial price, 12 months ending July 2026 vs 2025. | percent |
| `com_chg_1yr_cents` | Same change in cents. | cents per kilowatt-hour |
| `com_chg_since2022_pct` | Change vs 12 months ending July 2022. | percent |
| `com_chg_since2021_pct` | Change vs 12 months ending July 2021. | percent |
| `com_chg_since2019_pct` | Change vs 12 months ending July 2019. | percent |
| `com_price_jul2025_month` | Commercial price, July 2025 only. | cents per kilowatt-hour |
| `com_price_jul2026_month` | Commercial price, July 2026 only. | cents per kilowatt-hour |
| `com_chg_jul_month_pct` | Change July 2026 vs July 2025. | percent |
| `ind_price_12m_jul2021` | Industrial price, 12 months ending July 2021. | cents per kilowatt-hour |
| `ind_price_12m_jul2025` | Industrial price, 12 months ending July 2025. | cents per kilowatt-hour |
| `ind_price_12m_jul2026` | Industrial price, 12 months ending July 2026. | cents per kilowatt-hour |
| `ind_chg_1yr_pct` | Change in industrial price, 2026 vs 2025 (12 months ending July). | percent |
| `ind_chg_since2021_pct` | Change in industrial price vs 2021. | percent |
| `example_5000kwh_monthly_bill_12m_jul2025` | Example monthly bill for 5,000 kWh at the 12-month commercial price ending July 2025. | US dollars per month |
| `example_5000kwh_monthly_bill_12m_jul2026` | Same at the price ending July 2026. | US dollars per month |
| `example_5000kwh_yearly_chg_1yr_dollars` | Yearly cost change of the example bill, 2026 vs 2025. | US dollars per year |
| `example_5000kwh_yearly_chg_since2021_dollars` | Yearly cost change of the example bill vs 2021. | US dollars per year |
| `rank_com_chg_1yr_pct` | Rank of com_chg_1yr_pct among 50 states and DC (1 = largest increase). | rank |
| `rank_com_chg_since2021_pct` | Rank of com_chg_since2021_pct (1 = largest increase). | rank |

### data/diesel_gas_prices_by_state.csv

Weekly diesel and regular gasoline prices by state, with example truck fuel costs. Rows: 51. Columns: 18.

| Column | Meaning | Units |
|---|---|---|
| `week_of` | EIA price week (Monday). | date (YYYY-MM-DD) |
| `state` | State name. | text |
| `abbr` | Two-letter USPS state code. | text |
| `eia_region` | EIA PADD region the state belongs to. | text |
| `diesel_price_source_area` | EIA area whose diesel price is used. | text |
| `diesel_latest` | On-highway diesel retail price, latest week. | US dollars per gallon |
| `diesel_year_ago` | Same week a year earlier. | US dollars per gallon |
| `diesel_chg_year` | Change from a year ago. | US dollars per gallon |
| `diesel_avg_2021` | Average diesel price in 2021. | US dollars per gallon |
| `gas_price_source_area` | EIA area whose regular gasoline price is used. | text |
| `gas_is_state_series` | True if EIA publishes a gasoline price for this state itself. | True/False |
| `gas_latest` | Regular gasoline retail price, latest week. | US dollars per gallon |
| `gas_year_ago` | Same week a year earlier. | US dollars per gallon |
| `gas_chg_year` | Change from a year ago. | US dollars per gallon |
| `diesel_truck_cost_latest` | Example yearly fuel cost: diesel work truck, 25,000 miles at 12 mpg, at diesel_latest. | US dollars per year |
| `gas_pickup_cost_latest` | Example yearly fuel cost: gasoline pickup, 20,000 miles at 15 mpg, at gas_latest. | US dollars per year |
| `diesel_series` | EIA series ID for the diesel price. | code |
| `gas_series` | EIA series ID for the gasoline price. | code |

### data/electricity_generation_mix_by_state.csv

Where each state's electricity comes from (U.S. total row included). Rows: 52. Columns: 42.

| Column | Meaning | Units |
|---|---|---|
| `state` | State name (U.S. total row included). | text |
| `abbr` | Two-letter code (US = national). | text |
| `period_latest12` | Months covered by the latest 12-month window. | text |
| `data_center_tier` | Data center tier from the startbusinessbystate-data-center-boom dataset (Hot, Warm, Watch). | category |
| `top_source_latest12` | Largest generation source in the latest 12 months. | category |
| `total_gwh_latest12` | Total net generation, latest 12 months. | gigawatt-hours |
| `total_gwh_y2019` | Total net generation, 2019. | gigawatt-hours |
| `total_gwh_y2022` | Total net generation, 2022. | gigawatt-hours |
| `total_pct_chg_vs2019` | Change in total generation vs 2019. | percent |
| `total_pct_chg_vs2022` | Change vs 2022. | percent |
| `total_pct_chg_vs_prior12` | Change vs the 12 months before. | percent |
| `natural_gas_share_latest12` | Natural gas share of net generation, latest 12 months (period_latest12). | percent |
| `natural_gas_share_y2019` | Natural gas share of net generation, calendar 2019. | percent |
| `natural_gas_share_y2022` | Natural gas share of net generation, calendar 2022. | percent |
| `natural_gas_share_chg_pts_vs2019` | Change in natural gas share, latest 12 months vs 2019. | percentage points |
| `coal_share_latest12` | Coal share of net generation, latest 12 months (period_latest12). | percent |
| `coal_share_y2019` | Coal share of net generation, calendar 2019. | percent |
| `coal_share_y2022` | Coal share of net generation, calendar 2022. | percent |
| `coal_share_chg_pts_vs2019` | Change in coal share, latest 12 months vs 2019. | percentage points |
| `nuclear_share_latest12` | Nuclear share of net generation, latest 12 months (period_latest12). | percent |
| `nuclear_share_y2019` | Nuclear share of net generation, calendar 2019. | percent |
| `nuclear_share_y2022` | Nuclear share of net generation, calendar 2022. | percent |
| `nuclear_share_chg_pts_vs2019` | Change in nuclear share, latest 12 months vs 2019. | percentage points |
| `wind_share_latest12` | Wind share of net generation, latest 12 months (period_latest12). | percent |
| `wind_share_y2019` | Wind share of net generation, calendar 2019. | percent |
| `wind_share_y2022` | Wind share of net generation, calendar 2022. | percent |
| `wind_share_chg_pts_vs2019` | Change in wind share, latest 12 months vs 2019. | percentage points |
| `solar_share_latest12` | Solar share of net generation, latest 12 months (period_latest12). | percent |
| `solar_share_y2019` | Solar share of net generation, calendar 2019. | percent |
| `solar_share_y2022` | Solar share of net generation, calendar 2022. | percent |
| `solar_share_chg_pts_vs2019` | Change in solar share, latest 12 months vs 2019. | percentage points |
| `hydro_share_latest12` | Hydroelectric share of net generation, latest 12 months (period_latest12). | percent |
| `hydro_share_y2019` | Hydroelectric share of net generation, calendar 2019. | percent |
| `hydro_share_y2022` | Hydroelectric share of net generation, calendar 2022. | percent |
| `hydro_share_chg_pts_vs2019` | Change in hydroelectric share, latest 12 months vs 2019. | percentage points |
| `other_share_latest12` | Other sources share of net generation, latest 12 months (period_latest12). | percent |
| `other_share_y2019` | Other sources share of net generation, calendar 2019. | percent |
| `other_share_y2022` | Other sources share of net generation, calendar 2022. | percent |
| `other_share_chg_pts_vs2019` | Change in other sources share, latest 12 months vs 2019. | percentage points |
| `petroleum_share_latest12` | Petroleum share of net generation, latest 12 months. | percent |
| `wind_solar_share_latest12` | Wind plus solar share, latest 12 months. | percent |
| `wind_solar_chg_pts_vs2019` | Change in wind plus solar share vs 2019. | percentage points |

### data/electricity_prices_by_data_center_tier.csv

Residential and commercial prices with each state's data center tier (U.S. total row included). Rows: 52. Columns: 22.

| Column | Meaning | Units |
|---|---|---|
| `state` | Two-letter code (US = national). | text |
| `state_name` | State name. | text |
| `dc_tier` | Data center group from the boom page: Hot, Warm or Little or none. | category |
| `res_price_12m_jul2019` | Residential price, 12 months ending July 2019. | cents per kilowatt-hour |
| `res_price_12m_jul2022` | Residential price, 12 months ending July 2022. | cents per kilowatt-hour |
| `res_price_12m_jul2025` | Residential price, 12 months ending July 2025. | cents per kilowatt-hour |
| `res_price_12m_jul2026` | Residential price, 12 months ending July 2026. | cents per kilowatt-hour |
| `res_chg_1yr_pct` | Residential change, 2026 vs 2025. | percent |
| `res_chg_since2022_pct` | Residential change vs 2022. | percent |
| `res_chg_since2019_pct` | Residential change vs 2019. | percent |
| `res_bill_monthly_12m_jul2022` | Average monthly residential bill (revenue / customers / 12), 12 months ending July 2022. | US dollars per month |
| `res_bill_monthly_12m_jul2026` | Same, 12 months ending July 2026. | US dollars per month |
| `com_price_12m_jul2019` | Commercial price, 12 months ending July 2019. | cents per kilowatt-hour |
| `com_price_12m_jul2022` | Commercial price, 12 months ending July 2022. | cents per kilowatt-hour |
| `com_price_12m_jul2025` | Commercial price, 12 months ending July 2025. | cents per kilowatt-hour |
| `com_price_12m_jul2026` | Commercial price, 12 months ending July 2026. | cents per kilowatt-hour |
| `com_chg_1yr_pct` | Commercial change, 2026 vs 2025. | percent |
| `com_chg_since2022_pct` | Commercial change vs 2022. | percent |
| `com_chg_since2019_pct` | Commercial change vs 2019. | percent |
| `com_sales_12m_jul2019_gwh` | Commercial electricity sales, 12 months ending July 2019. | gigawatt-hours |
| `com_sales_12m_jul2026_gwh` | Commercial sales, 12 months ending July 2026. | gigawatt-hours |
| `com_sales_chg_since2019_pct` | Change in commercial sales vs 2019. | percent |

## Sources

| Source | Link | License or status |
|---|---|---|
| EIA API v2, electricity retail sales (revenue, sales, customers, price) | https://www.eia.gov/opendata/ | Public domain (U.S. government work) |
| EIA API v2, electric power operational data (net generation by fuel) | https://www.eia.gov/opendata/ | Public domain (U.S. government work) |
| EIA Weekly Retail Gasoline and On-Highway Diesel Prices | https://www.eia.gov/petroleum/gasdiesel/ | Public domain (U.S. government work) |
| Data center tiers from startbusinessbystate.com Data Center Boom by State (uses Epoch AI data, CC BY 4.0) | https://startbusinessbystate.com/data-center-boom-by-state/ | Our own compilation |

## Methodology

- Prices are 12-month averages: total revenue / total kilowatt-hours sold over the 12 months ending in July of each year. This smooths out seasons. Single-month July prices are also shown for the business table.
- Example bill = 5,000 kWh per month at the 12-month average commercial price. It is an illustration, not a typical bill.
- Generation shares are each fuel's share of total net generation (all sectors) in the window.
- Fuel: EIA publishes weekly diesel prices only by region (PADD) and gasoline prices for regions plus 9 states. Each state gets its own series where EIA publishes one, otherwise its region's. The source area columns say which.
- Truck costs are examples chosen by us, not EIA data: a diesel work truck at 25,000 miles a year and 12 mpg, and a gasoline work pickup at 20,000 miles a year and 15 mpg.
- A few missing monthly cells in EIA state data were filled from neighboring months for 12-month totals (logged in our build files).

## Limitations

- EIA monthly state data are preliminary and revised.
- Average price is not the rate on any one tariff. Demand charges and contract rates vary.
- Regional fuel prices can differ a lot from local pump prices.
- Data center tiers are a descriptive grouping. A price difference between groups does not show that data centers caused it.

## As-of date

Electricity data through July 2026 (EIA, pages updated September 28, 2026). Fuel prices for the week of September 28, 2026 (page updated September 30, 2026).

Version 1.0.0, released 2026-10-02.

## How to cite

StartBusinessByState. (2026). *Business Electricity Prices, Generation Mix and Diesel and Gas Prices by State, 2026 (startbusinessbystate.com)* (Version 1.0.0) [Data set]. startbusinessbystate.com. https://github.com/jameyriley46-ux/startbusinessbystate-business-electricity-and-fuel

Please also credit the original sources listed above. When you use the data, a link back to https://startbusinessbystate.com/business-electricity-cost-increase-by-state/ is appreciated.

## Related pages on startbusinessbystate.com

- https://startbusinessbystate.com/business-electricity-cost-increase-by-state/
- https://startbusinessbystate.com/electricity-sources-by-state/
- https://startbusinessbystate.com/data-center-electricity-prices-by-state/
- https://startbusinessbystate.com/diesel-gas-prices-by-state/

## License

This dataset is released under the Creative Commons Attribution 4.0 International license (CC BY 4.0). See `LICENSE`. You may share and adapt it, including for commercial use, as long as you give credit.
Underlying public domain data from U.S. government agencies stays public domain. Data from CC BY sources (such as LegiScan, PatentsView, Epoch AI or the Anthropic Economic Index, where used) also requires credit to those sources.

## Contact

StartBusinessByState (startbusinessbystate.com) (https://startbusinessbystate.com/)
