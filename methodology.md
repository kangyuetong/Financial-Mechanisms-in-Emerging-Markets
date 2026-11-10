# Methodology

This document describes the implementation in `index.html` as of 10 November 2026. It is an independent educational research companion; it is **not** a reproduction of an unavailable original FIN4751 workbook.

## Market-premium and financing-gap model

- **SAF premium (USD/t):** `max(0, SAF benchmark - jet fuel benchmark)`. The October 2026 rounded benchmarks give **$822.05/t**; the source reports **$822.06/t**.
- **Effective certificate proceeds (USD/t):** certificate revenue × capture rate / 100.
- **Public support (USD/t):** the user-selected incentive. The funding visual caps allocated support at the benchmark premium and does not treat overfunding as profit.
- **Unfunded premium (USD/t):** `max(0, premium - effective certificate proceeds - public support)`.
- **Annual illustrative financing gap:** unfunded premium × nameplate capacity, **before utilisation**.
- **Certificate break-even price:** `max(0, premium - public support) / (capture rate / 100)`; undefined if capture is zero and the remaining premium is positive.

## Project investment appraisal

The separate investment model applies **capacity utilisation** to nameplate capacity: annual tonnes = nameplate tonnes × utilisation %. It calculates annual fuel revenue using the SAF benchmark × producer fuel-price realisation %, and adds eligible certificate proceeds and public incentives, each capped so that combined support does not exceed the benchmark premium. These are simplified modelling assumptions, not verified commercial contract terms.

- Initial project free cash flow at year 0 = negative CAPEX.
- Annual revenue = annual tonnes × (realised physical fuel price + eligible certificate proceeds + public support).
- Annual operating expense = annual tonnes × operating cost per tonne.
- Straight-line depreciation = CAPEX / project life.
- Project tax = tax rate × `max(0, revenue - operating expense - depreciation)`.
- Annual unlevered free cash flow = revenue − operating expense − project tax.
- Project NPV = sum of project free cash flows discounted at the selected **real** project discount rate.
- Project IRR = discount rate at which project NPV is zero (where a unique numerical root is available).
- Simple payback = time for undiscounted cumulative project cash flow to become non-negative.
- Equity IRR uses initial equity = CAPEX − debt, equal annual debt principal repayments, interest on outstanding debt, and simplified tax after interest.

## Important limitations

This is a constant-price, real-USD illustrative model. It excludes inflation, construction ramp-up, working capital, maintenance capital expenditure, loss carryforwards, terminal value and detailed subsidy or tax eligibility. It does not establish project bankability, certificate additionality, social welfare or emissions savings. The benchmark is **Northwest European**, not an observed emerging-market production cost. Certificate prices and public incentives are user-defined scenarios, not verified Avelia transaction prices.

The dashboard reads a local `prices.json` when deployed, otherwise uses a hardcoded October 2026 fallback. The JSON is **dated, not a live feed**. Update its values only with a verified same-basis publication, and retain historical observations in `data/market_benchmarks.csv`.
