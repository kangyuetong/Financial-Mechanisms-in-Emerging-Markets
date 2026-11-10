# Financial-Mechanisms-in-Emerging-Markets

**Modelling Avelia's Book-and-Claim in SAF Markets**

Model developed for NUS FIN4751: Advanced Independent Study in Finance.

### [Explore the Interactive Financial Dashboard](https://kangyuetong.github.io/Financial-Mechanisms-in-Emerging-Markets/)

An interactive SAF financing dashboard exploring market price premiums, book-and-claim certificate proceeds, public incentives, financing gaps and illustrative project investment returns.

## Repository files

- `index.html` — self-contained interactive dashboard (keep in the repository root).
- `prices.json` — dated market reference read by the dashboard on page load; **keep in the repository root**.
- `data/market_benchmarks.csv` — historical snapshot of the benchmark and its provenance.
- `model_assumptions.csv` — default scenario inputs from the HTML model.
- `methodology.md` — model formulas, implementation details and limitations.
- `sources.md` — benchmark provenance and contextual references.

The dashboard contains a fallback price reference if `prices.json` cannot load; it is not a live market data service. Supporting CSV and Markdown files document the model but are not required for the page to render.

**Disclaimer:** Market benchmarks are dated; all other scenario parameters are illustrative. Not investment advice. The HTML is an independent educational companion rather than a reproduction of an unavailable original FIN4751 workbook.
