# SpaceX Post-IPO Valuation & Aftermarket Analysis

> SpaceX priced its IPO at $135.00 and closed Day 1 at $160.95.
> What do disclosed fundamentals actually support, and how much of
> the pricing rests on expectations rather than current financials?

**Status:** Version 1 complete | **Type:** Valuation / ECM

---

## Objective

Analyse the SpaceX IPO across pricing, aftermarket performance and
intrinsic valuation, testing the offer price against a segment
sum-of-the-parts build, a discounted cash flow and public trading
comparables.

Priced 11 June 2026. First trade 12 June 2026. Nasdaq: SPCX.

---

## Methodology

1. Deal fact sheet reconstructing offering terms and governance
2. Segment sum-of-the-parts using disclosed FY2025 revenue and
   adjusted EBITDA
3. Trading comparables across connectivity, launch and aerospace
   and defence
4. Operating DCF with a five-year forecast and terminal value
5. Aftermarket trading analysis over the first eleven sessions
6. Valuation summary reconciling all methods to IPO and Day-1
   pricing

---

## Offering Terms

| Term | Detail |
|------|--------|
| Offer price | $135.00 |
| Shares offered | 555.6mm |
| Gross proceeds | $75,000mm |
| Greenshoe | 83.3mm shares |
| Total incl. greenshoe | $86,250mm |
| Primary / secondary | 100% / 0% |
| Free float | 4.2% |
| Lead underwriters | Goldman Sachs, Morgan Stanley, BofA, Citigroup, J.P. Morgan |
| Share classes | Class A (1 vote), Class B (10 votes) |
| Founder voting control | 82.3% |
| Lock-up | 366 days |

A 100% primary offering with a 4.2% float — the company raises
all proceeds and existing holders sell nothing.

---

## Financial Profile (FY2025)

| Metric | $mm |
|--------|-----|
| Revenue | 18,674 |
| Revenue growth | 33.2% |
| Adjusted EBITDA | 6,584 |
| Loss from operations | (2,589) |
| Capex | 20,737 |
| Cash and equivalents | 15,852 |
| Debt | 29,111 |
| Pro forma cash incl. proceeds | 90,852 |

**Segment disclosure**

| Segment | Revenue | Adj. EBITDA |
|---------|---------|-------------|
| Connectivity (Starlink) | 11,387 | 7,168 |
| Space / Launch | 4,086 | n/d |
| AI / xAI | 3,201 | (1,237) |
| **Total** | **18,674** | |

Capex of $20,737mm exceeds revenue — the defining feature of the
financial profile and the reason the DCF stays negative through
2028E.

---

## Valuation

**Segment sum-of-the-parts**

| Segment | Revenue | Low | Base | High |
|---------|---------|-----|------|------|
| Connectivity | 11,387 | 3.98x | 6.0x | 8.0x |
| Space / Launch | 4,086 | 6.0x | 11.3x | 15.0x |
| AI / xAI | 3,201 | 3.0x | 5.0x | 7.0x |
| **Segment EV ($mm)** | | **79,439** | **130,499** | **174,793** |
| Less: net debt | | (61,741) | (61,741) | (61,741) |
| **Implied equity value** | | **141,180** | **192,240** | **236,534** |

**Discounted cash flow**

| Assumption | Value |
|-----------|-------|
| Discount rate | 12.0% |
| Terminal growth | 4.0% |
| Revenue growth | 35% tapering to 15% |
| EBITDA margin | 35% expanding to 45% |
| Capex / revenue | 111% tapering to 22.5% |

| | $mm |
|---|---|
| PV of forecast FCF | (25,345) |
| PV of terminal value | 33,543 |
| Implied enterprise value | 8,198 |
| Less: net debt | (61,741) |
| **Implied equity value** | **69,939** |

Free cash flow turns positive in 2029E as capex intensity
normalises. Sensitivity across a 10–14% discount rate and 3–5%
terminal growth gives a range of $59.0bn to $95.2bn.

**Trading comparables**

| Segment | Median EV / Revenue | Median EV / EBITDA |
|---------|--------------------|--------------------|
| Connectivity | 3.98x | 10.5x |
| Launch / space infrastructure | 11.29x | n/m |
| Aerospace and defence | 2.92x | 19.2x |

AST SpaceMobile excluded from the connectivity median as an
outlier. Launch EV/EBITDA is not meaningful — most comparables
have negative EBITDA.

---

## Pricing and Aftermarket

| Metric | IPO | Day 1 |
|--------|-----|-------|
| Price | $135.00 | $160.95 |
| Equity value ($mm) | 1,776,492 | 2,117,973 |
| Enterprise value ($mm) | 1,714,751 | 2,056,232 |
| EV / Revenue | 91.8x | 110.1x |

Day-1 pop of 19.2%. Money left on the table: $14,417mm,
calculated as shares offered times the difference between the
Day-1 close and the offer price.

**First eleven sessions**

| Session | Close | vs IPO |
|---------|-------|--------|
| Day 1 | $160.95 | +19.2% |
| Day 3 (peak) | $201.80 | +49.5% |
| Day 5 | $185.00 | +37.0% |
| Day 7 | $154.60 | +14.5% |
| Day 11 | $153.23 | +13.5% |

The stock held above the offer price throughout, peaking at
+49.5% on Day 3 before retracing. The pattern suggests genuine
demand at pricing followed by the market recalibrating around
capex intensity and segment economics.

---

## Valuation Summary

| Method | Equity value ($mm) | vs IPO |
|--------|-------------------|--------|
| DCF (base) | 69,939 | (96.1%) |
| Segment SOTP (base) | 192,240 | (89.2%) |
| IPO pricing | 1,776,492 | — |
| Day-1 trading | 2,117,973 | +19.2% |

**Conclusion.** Every fundamentals-based method lands far below
the offer price. The SOTP, built on disclosed FY2025 segment
revenue, supports $141bn to $237bn. The DCF, constrained by capex
exceeding revenue, supports $59bn to $95bn. The IPO priced at
91.8x revenue and traded to 110.1x on Day 1.

The gap is not explained by current financials. It reflects
whatever the market assigns to Starlink terminal scale, Starship
economics, defence and government programmes, AI infrastructure
and scarcity value — none of which the disclosed segment data
captures. The analysis is best read as sizing that gap rather than
as a fair-value estimate.

---

## Deliverables

| File | Description |
|------|-------------|
| [`models/`](models) | DCF model, trading comparables, SOTP build, IPO pricing analysis |
| [`outputs/`](outputs) | Valuation summary, football field chart |
| [`screenshots/`](screenshots) | Football field range, DCF sensitivity, comparables set |

---

## Technology Stack

- Microsoft Excel
- PitchBook market data
- SEC EDGAR (S-1, 424B4)
- DCF and comparable company analysis

---

## Skills Demonstrated

- IPO pricing and aftermarket performance analysis
- Sum-of-the-parts valuation across disclosed segments
- Discounted cash flow modelling
- Trading comparables selection and outlier treatment
- Equity capital markets analysis
- Multi-method valuation reconciliation

---

## Limitations

- The implied multiples at pricing — 91.8x revenue and 260.4x
  EBITDA — sit far outside any observable comparable range. The
  diluted share count driving equity value should be verified
  against the final 424B4 before these figures are relied upon.
- Space and Launch segment EBITDA is not disclosed, so all three
  segments are valued on revenue multiples. This understates
  Connectivity, which carries a 63% segment EBITDA margin.
- The DCF applies a simplified tax on EBITDA rather than a full
  tax build, and does not model stock-based compensation, working
  capital seasonality or segment-level capex allocation.
- Terminal value represents more than 100% of DCF enterprise value
  because forecast-period free cash flow is negative. The DCF is
  therefore highly sensitive to terminal assumptions.
- Comparable companies span connectivity, launch and aerospace
  with materially different growth and margin profiles. No single
  set is a clean read.
- Aftermarket data covers eleven sessions only, well inside the
  lock-up and index-inclusion windows.

---

*Prepared for educational and portfolio purposes. Figures are
illustrative and do not constitute investment advice.*

[Back to Deal Intelligence Lab](../../README.md)
