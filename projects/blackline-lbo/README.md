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
4. Debt schedule with mandatory amortization and a cash flow
   sweep above a minimum liquidity balance
5. Levered tax build capturing the interest tax shield
6. Exit valuation at entry multiple held flat
7. Returns via IRR and MOIC, decomposed in an equity value
   creation bridge
8. Two-way sensitivity across exit multiple and exit EBITDA
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
| Sponsor equity | $1,446.0mm | Balancing plug |
| Debt / equity split | 39.0% / 61.0% | Of total sources |
| Cash interest rate | 9.5% | SOFR plus spread |
| Transaction fees | 2.0% of EV | Sponsor assumption |
| Financing fees | 2.0% of debt | LevFin market data |
| Cash tax rate | 25.0% | Applied to EBT |
| Minimum cash balance | $25.0mm | Credit agreement liquidity floor |
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
| Rule of 40 | n/a | 35.0% | 37.0% | 39.0% | 39.0% | 39.0% |

Revenue compounds at 8.1% over the hold, with EBITDA margin
expanding 620 basis points from 25.8% to 32.0%.

---

## Results

| Metric | Value |
|--------|-------|
| Entry enterprise value | $2,282.5mm |
| Total uses | $2,371.7mm |
| Sponsor equity at entry | $1,446.0mm |
| Exit EBITDA (2031E) | $338.5mm |
| Exit enterprise value | $4,173.0mm |
| Less: net debt at exit | $325.0mm |
| **Exit equity value** | **$3,848.0mm** |
| **Gross IRR** | **21.6%** |
| **MOIC** | **2.66x** |

**Credit profile over the hold**

| | 2026E | 2028E | 2031E |
|---|---|---|---|
| Total debt / EBITDA | 4.8x | 3.2x | 1.0x |
| Interest coverage | 2.1x | 3.0x | 6.9x |

Debt falls from $925.7mm at close to $350.0mm at exit, a 62
percent reduction driven by the cash sweep and $108.7mm of
cumulative interest tax shield. The sweep retains a $25.0mm
minimum cash balance each year rather than sweeping to zero.
Interest coverage troughs at 2.1x in the first year, the tightest
point in the capital structure.

**Equity value creation bridge**

| Lever | $mm | % of gain |
|-------|-----|-----------|
| Revenue growth | 1,086.5 | 45.2% |
| Margin expansion | 804.0 | 33.5% |
| Deleveraging | 575.7 | 24.0% |
| Multiple expansion | 0.0 | 0.0% |
| Transaction and financing fees | (64.2) | (2.7%) |
| **Total equity gain** | **2,402.0** | **100.0%** |

**Conclusion:** The transaction clears a 20 percent hurdle at
21.6% IRR and 2.66x MOIC with the exit multiple held flat at
entry. Returns are earned entirely through operating performance
and deleveraging rather than multiple expansion, which makes the
case less dependent on exit market conditions than a typical
software LBO. Two constraints bind: first-year interest coverage
of 2.1x leaves limited headroom if FY2027 growth disappoints, and
the margin over the hurdle is thin enough that roughly half a turn
of exit multiple contraction would break the case.

---

## Sensitivities

IRR across exit multiple and exit EBITDA margin:

| Exit multiple ↓ / margin → | 28% | 30% | 32% | 34% | 36% |
|---|---|---|---|---|---|
| 10.0x | 12.8% | 14.5% | 16.2% | 17.7% | 19.2% |
| 11.0x | 15.2% | 17.0% | 18.6% | 20.2% | 21.7% |
| 12.0x | 17.4% | 19.2% | 20.9% | 22.5% | 24.0% |
| 13.0x | 19.5% | 21.3% | 23.0% | 24.6% | 26.2% |
| 14.0x | 21.5% | 23.3% | 25.0% | 26.6% | 28.2% |

Returns range from 12.8% to 28.2% across the grid. At the base
case margin of 32%, the deal clears a 20 percent hurdle only above
roughly 11.7x — meaning it tolerates about 0.6 turns of multiple
contraction from the 12.3x entry before failing. Exit multiple is
the dominant driver: a one-turn move shifts IRR by roughly 210 to
230 basis points, against roughly 170 basis points for a 200 basis
point margin change.

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
- Levered tax build and interest tax shield
- Capital structure analysis
- Sponsor returns analysis and value creation attribution
- Private equity investment evaluation

---

## Limitations

- The model runs a single operating case. Downside returns are
  inferred from the sensitivity grid rather than from a
  separately built recession case with distinct growth, margin
  and working capital assumptions.
- Entry valuation is derived from an EV/Revenue multiple applied
  to forward revenue. No offer price per share or premium to the
  unaffected trading price is modeled, so the analysis does not
  test whether the implied premium would clear a board.
- The capital structure is modeled as a single debt tranche at a
  blended 9.5% rate, rather than a revolver, Term Loan A and Term
  Loan B with distinct pricing and amortization.
- Interest is deducted before tax at a flat 25% rate. NOL
  carryforwards and the Section 163(j) interest deductibility
  limitation are not modeled.
- The sensitivity grid holds the base-case debt schedule constant
  while flexing exit margin, so it isolates valuation effects and
  does not capture the additional deleveraging a higher margin
  would fund.
- Operating assumptions are derived from public filings and
  market data. No management projections were used.
- The exit assumes a single sale at a fixed multiple. Dividend
  recapitalizations, bolt-on acquisitions and IPO exit routes are
  not modeled.

---

*Prepared for portfolio purposes. Figures are illustrative and do
not constitute investment advice.*

[Back to Deal Intelligence Lab](../../README.md)
