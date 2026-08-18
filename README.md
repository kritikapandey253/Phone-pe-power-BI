# PhonePe Transactions Analytics Dashboard (Power BI)

An end-to-end Power BI dashboard that analyses digital payment transactions (PhonePe-style UPI data) across users, services, time and payment outcomes — built to turn raw transaction logs into decision-ready insights.



## Dashboard Preview
![PhonePe Dashboard — Executive Summary](assets/phone%20pe%20ss.png)


## Project Overview
The dashboard answers the questions a payments/product team actually asks:
- How many users transact, and how much value flows month over month?
- Which services (recharge, bill payment, money transfer, merchant pay, etc.) drive volume vs value?
- What is the transaction success rate, and where are failures concentrated?
- How does behaviour differ by age segment and by weekday vs weekend?

## Data Model (Star Schema)
| Table | Type | Description |
|---|---|---|
| `All_Transactions` | Fact | Transaction-level records: amount, service, service type, payment status, date, user key |
| `All_Users` | Dimension | User profile attributes incl. name, user ID, age segment |
| `date_Table` | Dimension | Custom DAX calendar (month, weekday/weekend flags) for time intelligence |
| `measure` | Measures table | Centralised DAX measures |

Relationships: one-to-many from `All_Users` and `date_Table` into `All_Transactions`, with a dedicated measures table to keep the model clean.

## Key DAX Measures
- `total user` — distinct transacting users
- `total transction` — total transaction count
- `total transction value` — total value processed (GMV)
- `success rate` — successful transactions / total transactions
- `Total tarns MOM %` — month-over-month growth in transaction volume
- `TRANSCTION VALUEMOM` — month-over-month growth in transaction value

## Report Pages
1. **Executive Summary** — KPI cards (users, transactions, value, success rate) with MoM deltas
2. **Service Performance** — column and 100% stacked charts comparing services and service types
3. **Customer Insights** — donut charts by age segment, weekend vs weekday behaviour
4. **Trend Analysis** — line charts for monthly volume and value trends
5. **Tooltip pages** — custom hover tooltips for drill-level context

Interactivity: slicers for month and service, cross-filtering across all visuals, and custom-tooltip pages.

## Skills Demonstrated
- Data cleaning and shaping in Power Query (M)
- Star-schema data modelling and relationship design
- DAX: `CALCULATE`, `DISTINCTCOUNT`, `DIVIDE`, time intelligence for MoM analysis
- Dashboard design: KPI hierarchy, consistent theme, custom tooltips, UX-first layout

## Key Insights
- Transaction value and volume growth are tracked with MoM % measures to spot momentum and dips early.
- A small set of services accounts for the majority of transaction value, while another set drives raw volume — pricing and marketing focus should differ.
- Success rate monitoring highlights failure-heavy payment paths for operational fixes.
- Weekend and age-segment splits reveal distinct usage patterns useful for campaign timing.



## Author
**Kritika Pandey** — Data Analyst
Power BI · SQL · Excel · DAX · Power Query

