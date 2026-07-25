# BlackLine Take-Private LBO

> Can a financial sponsor take BlackLine private at 12.3x EBITDA
> and clear a 20% return hurdle through deleveraging and margin
> expansion alone, without relying on multiple expansion?

**Status:** Version 1 complete | **Type:** LBO

---

## Objective

Evaluate the feasibility of a sponsor-led take-private
transaction for BlackLine Inc. (NASDAQ: BL) using a leveraged
buyout framework over a five-year hold.

---

## Methodology

1. Sources and uses of funds, sized from an EV/Revenue entry
   multiple against FY2026E revenue
2. Capital structure sized at 5.0x EBITDA, with the sponsor
   equity check as the balancing plug
3. Six-year operating model with revenue growth and margin
   expansion assumptions, tested against Rule of 40
4. Debt schedule with mandatory amortization and a 100 percent
   cash flow sweep
5. Exit valuation at entry multiple held flat
6. Returns via IRR and MOIC, decomposed in an equity value
   creation bridge
7. Two-way sensitivity across exit multiple and exit EBITDA
   margin

---

## Key Assumptions

| Assumption | Value | Basis |
|-----------|-------|-------|
| Entry revenue (FY2026E) | $716.7mm | PitchBook / company filings |
| Entry EBITDA | $185.1mm | Adjusted EBITDA proxy |
| Entry EBITDA margin | 25.8% | Derived |
| Entry EV / Revenue | 3.19x | SaaS transaction comparables |
| Entry EV / EBITDA | 12.3x | Derived |
| Purchase enterprise value | $2,282.5mm | Derived |
| Leverage at close | 5.0x EBITDA | PitchBook LBO comparables |
| New debt raised | $925.7mm | Derived |
| Sponsor equity | $1,421.0mm | Balancing plug |
| Debt / equity split | 39.4% / 60.6% | Of total sources |
| Cash interest rate | 9.5% | SOFR plus spread |
| Transaction fees | 2.0% of EV | Sponsor assumption |
| Financing fees | 2.0% of debt | LevFin market data |
| Cash tax rate | 25.0% | Model convention |
| Capex / revenue | 3.0% | Held flat |
| Exit multiple | 12.3x | Entry multiple held flat |
| Hold period | 5 years | Standard sponsor hold |

---

## Operating Case

| | 2026E | 2027E | 2028E | 2029E | 2030E | 2031E |
|---|---|---|---|---|---|---|
| Revenue ($mm) | 716.7 | 774.0 | 839.8 | 915.4 | 988.6 | 1,057.8 |
| Growth | — | 8.0% | 8.5% | 9.0% | 8.0% | 7.0% |
| EBITDA margin | 25.8% | 27.0% | 28.5% | 30.0% | 31.0% | 32.0% |
| EBITDA ($mm) | 185.1 | 209.0 | 239.3 | 274.6 | 306.5 | 338.5 |
| Rule of 40 | 25.8% | 35.0% | 37.0% | 39.0% | 39.0% | 39.0% |

Revenue compounds at 8.1% over the hold, with EBITDA margin
expanding 620 basis points from 25.8% to 32.0%.

---

## Results

| Metric | Value |
|--------|-------|
| Entry enterprise value | $2,282.5mm |
| Sponsor equity at entry | $1,421.0mm |
| Exit EBITDA (2031E) | $338.5mm |
| Exit enterprise value | $4,173.0mm |
| Less: ending debt | $302.2mm |
| **Exit equity value** | **$3,870.8mm** |
| **Gross IRR** | **22.2%** |
| **MOIC** | **2.72x** |

**Credit profile over the hold**

| | 2026E | 2028E | 2031E |
|---|---|---|---|
| Net debt / EBITDA | 4.8x | 3.1x | 0.9x |
| Interest coverage | 2.1x | 3.0x | 7.4x |

Debt falls from $925.7mm at close to $302.2mm at exit, a 67
percent reduction driven by the cash sweep. Interest coverage
troughs at 2.1x in the first year, the tightest point in the
capital structure.

**Equity value creation bridge**

| Lever | $mm | % of gain |
|-------|-----|-----------|
| Revenue growth | 1,086.5 | 44.4% |
| Margin expansion | 804.0 | 32.8% |
| Deleveraging | 623.5 | 25.5% |
| Multiple expansion | 0.0 | 0.0% |
| Transaction and financing fees | (64.2) | (2.6%) |
| **Total equity gain** | **2,449.8** | **100.0%** |

**Conclusion:** The transaction clears a 20 percent hurdle at
22.2% IRR and 2.72x MOIC without any multiple expansion — the
exit multiple is held flat at entry. Returns are earned
entirely through operating performance and deleveraging, which
makes the case less dependent on exit market conditions than a
typical software LBO. The binding constraint is first-year
interest coverage at 2.1x, which leaves limited headroom if
FY2027 growth disappoints.

---

## Sensitivities

IRR across exit multiple and exit EBITDA margin:

| Exit multiple ↓ / margin → | 28% | 30% | 32% | 34% | 36% |
|---|---|---|---|---|---|
| 10.0x | 13.4% | 15.1% | 16.8% | 18.3% | 19.8% |
| 11.0x | 15.8% | 17.5% | 19.2% | 20.8% | 22.3% |
| 12.0x | 18.0% | 19.8% | 21.5% | 23.1% | 24.6% |
| 13.0x | 20.1% | 21.9% | 23.6% | 25.2% | 26.7% |
| 14.0x | 22.0% | 23.8% | 25.6% | 27.2% | 28.8% |

Returns range from 13.4% to 28.8% across the grid. Exit
multiple is the dominant driver: a one-turn move shifts IRR by
roughly 200 to 240 basis points, against roughly 170 basis
points for a 200 basis point margin change. At the base case
margin of 32%, the deal breaks the 20 percent hurdle at an
exit multiple of 11.4x or above — meaning it tolerates roughly
one turn of multiple contraction before failing.

---

## Deliverables

| File | Description |
|------|-------------|
| [`models/`](models) | LBO model workbook, debt schedule, operating model |
| [`outputs/`](outputs) | Returns summary, sensitivity tables, sources and uses |
| [`screenshots/`](screenshots) | Returns grid, capital structure, debt paydown |

---

## Technology Stack

- Microsoft Excel
- LBO modeling
- Sensitivity and scenario analysis

---

## Skills Demonstrated

- Leveraged buyout modeling
- Debt schedule construction and cash sweep mechanics
- Capital structure analysis
- Sponsor returns analysis and value creation attribution
- Private equity investment evaluation

---

## Limitations

- The model runs a single operating case. Downside returns are
  inferred from the sensitivity grid rather than from a
  separately built recession case with distinct growth,
  margin and working capital assumptions.
- Entry valuation is derived from an EV/Revenue multiple
  applied to forward revenue. No offer price per share or
  premium to the unaffected trading price is modeled, so the
  analysis does not test whether the implied premium would
  clear a board.
- The capital structure is modeled as a single debt tranche at
  a blended 9.5% rate, rather than a revolver, Term Loan A and
  Term Loan B with distinct pricing and amortization.
- Operating assumptions are derived from public filings and
  market data. No management projections were used.
- The exit assumes a single sale at a fixed multiple. Dividend
  recapitalizations, bolt-on acquisitions and IPO exit routes
  are not modeled.
- Tax attributes such as NOL carryforwards and the interest
  deductibility limitation under Section 163(j) are not
  modeled; a flat 25% cash tax rate is applied.

---

*Prepared for portfolio purposes. Figures are illustrative and
do not constitute investment advice.*

[Back to Deal Intelligence Lab](../../README.md)
