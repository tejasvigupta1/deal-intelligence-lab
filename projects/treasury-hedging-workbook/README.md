# Automated Treasury Hedging Workbook

> Can a duration-ratio short-futures hedge hold a $100M Treasury
> portfolio's market value stable through a rate-moving period,
> and where does the construction fall short of a clean hedge?

**Status:** Version 1 complete | **Type:** Risk Management

---

## Objective

Build and evaluate a duration-neutral hedge of a simulated $100.0mm
U.S. Treasury portfolio using CBOT 10-Year Treasury Note futures,
tested over a defined management period against a mandate to
minimize deviation from the portfolio's starting value.

Prepared as a Boston University AD713 (Derivative Securities and
Markets) course assignment and for portfolio purposes.

---

## Methodology

1. Construct a four-note Treasury portfolio (5Y, 7Y, 10Y, 20Y) and
   compute weighted-average modified duration and DV01
2. Size the initial short futures position by the duration-ratio
   method: portfolio dollar duration divided by futures dollar
   duration
3. Track daily mark-to-market on both the bond portfolio and the
   futures margin account over 31 trading sessions
4. Re-solve the hedge ratio and rebalance the futures position as
   rates move
5. Compute stability statistics (mean, standard deviation, range)
   on daily deviation from the starting portfolio value
6. Attribute the period result between bond price change, accrued
   interest, and futures margin P&L

---

## Key Assumptions

| Assumption | Value | Basis |
|-----------|-------|-------|
| Portfolio face value | $100.0mm | Assignment parameter |
| Starting market value | $101,378,688 | Priced above par at inception |
| Weighted-average modified duration | 9.29 years | Derived from four-note portfolio |
| Portfolio DV01 | $92,887 per bp | Derived |
| Hedge instrument | CBOT 10Y Treasury Note futures (TYM6) | Assignment parameter |
| Futures modified duration | 6.50 | Held constant throughout |
| Futures contract size | $100,000 face | CBOT contract specification |
| Margin financing rate | 5.0% | Assumption |
| Management period | 24 Feb – 7 Apr 2026 | 31 trading sessions |
| Sizing method | Duration ratio, re-solved at each adjustment | Standard futures hedge convention |

---

## Portfolio Composition

| Note | Face ($mm) | Coupon | Yield | Mod. duration | Duration contribution |
|------|-----------|--------|-------|--------------|----------------------|
| 5Y | 15.0 | 3.750% | 3.63% | 4.557 | 0.68 yrs (7.4%) |
| 7Y | 17.0 | 4.000% | 3.82% | 6.130 | 1.04 yrs (11.2%) |
| 10Y | 25.0 | 4.625% | 4.05% | 7.906 | 1.98 yrs (21.3%) |
| 20Y | 43.0 | 4.625% | 4.63% | 12.992 | 5.59 yrs (60.1%) |
| **Total** | **100.0** | — | — | **9.29** | **9.29 yrs (100.0%)** |

The duration profile is concentrated: the 20-year note is 43.0% of
face but contributes 60.1% of portfolio duration. This is the
origin of the curve-risk limitation noted below — the portfolio's
risk sits materially further out the curve than the single
instrument used to hedge it.

---

## Execution

Eight transactions were executed over the period: one initial
hedge and seven subsequent adjustments, all priced at end-of-day
marks.

| Date | Action | Contracts | Price | Running short |
|------|--------|-----------|-------|---------------|
| 27 Feb 2026 | Sell | 1,261 | 113.641 | 1,261 |
| 27 Feb 2026 | Buy | 3 | 113.641 | 1,258 |
| 2 Mar 2026 | Sell | 3 | 113.344 | 1,261 |
| 4 Mar 2026 | Sell | 6 | 112.781 | 1,267 |
| 11 Mar 2026 | Sell | 8 | 112.063 | 1,275 |
| 25 Mar 2026 | Sell | 14 | 110.859 | 1,289 |
| 1 Apr 2026 | Buy | 2 | 111.000 | 1,287 |
| 3 Apr 2026 | Sell | 3 | 110.750 | 1,290 |

Total transaction cost across the period was $14,766, of which
$14,330 (97.0%) was incurred on the initial hedge. As futures
prices fell, the DV01 per contract declined and the required
position rose from 1,261 to 1,290 contracts to remain
duration-neutral — the hedge ratio is not static even when
portfolio duration is unchanged, since the denominator moves with
the market.

---

## Results

| Metric | Value |
|--------|-------|
| Trading sessions evaluated | 31 |
| Mean deviation from starting market value | $233,707 |
| Standard deviation of deviation | $463,570 |
| Standard deviation as % of starting value | 0.46% |
| Minimum deviation | ($644,196) |
| Maximum deviation | $906,062 |
| Deviation range | $1,550,258 |

**Period attribution**

| Component | $ |
|-----------|---|
| Bond portfolio market value, 24 February | 101,378,688 |
| Change in bond market value | (2,548,316) |
| Accrued interest | 504,863 |
| Futures margin account balance | 2,946,296 |
| **Total portfolio value, 7 April** | **102,281,531** |
| **Deviation from starting market value** | **902,843** |

The bond portfolio lost $2,548,316 in market value as rates rose
over the period; the short futures position generated $2,946,296
in the margin account, more than offsetting that loss. Expressed
as a capture ratio, the hedge recovered 115.6% of the underlying
loss — directionally correct and modestly over-sized.

**Conclusion:** The stability mandate was met. A 0.46% standard
deviation of portfolio value against a $100mm base, over a period
that saw meaningful rate movement, reflects an effective
duration-neutral hedge. The hedge is modestly over-sized (a 115.6%
capture ratio) and carries unhedged curve risk from concentrating
the hedge in a single 10-year instrument against a 5-to-20-year
ladder — both addressed below.

---

## Limitations

- The hedge uses a single 10-year futures contract against a
  ladder spanning 5 to 20 years. The 20-year note contributes
  60.1% of portfolio duration but is hedged with an instrument of
  6.50 modified duration; the sizing embeds a parallel-shift
  assumption, and any curve steepening or flattening passes
  through unhedged. A two-point hedge (for example, FV plus US
  futures) with front- and long-end DV01 matched separately would
  address this.
- Futures modified duration is held constant at 6.50 throughout.
  In practice the cheapest-to-deliver bond and its conversion
  factor shift as the curve moves, so the true contract DV01
  drifts; holding it fixed means the position departs from
  genuine DV01-neutrality between re-solves.
- The rebalancing trigger is not documented in the workbook. Seven
  adjustments over 31 sessions is consistent with a threshold
  policy, but the threshold itself is not stated, so the
  rebalancing record cannot be independently reviewed or
  replicated.
- Margin financing is modeled one-directional. The margin balance
  ran positive for most of the period and earned interest at the
  assumed 5% rate; a sustained adverse move would invert this into
  a funding cost, which is not stress-tested.
- The hedge is first-order only. Duration-ratio sizing neutralizes
  linear rate exposure; convexity is unhedged, which is a real,
  if second-order, residual for a portfolio with a 20-year
  component under large rate moves.
- The portfolio, its marks and the hedging record are simulated.
  No independent term-structure model or yield-curve fitting
  underlies the marks; yields, prices and durations are taken as
  given at inception.

---

## Deliverables

| File | Description |
|------|-------------|
| [`models/`](models) | Treasury hedging workbook, macro-free copy, rate scenario engine |
| [`outputs/`](outputs) | Hedge effectiveness summary, rate scenario results |
| [`screenshots/`](screenshots) | Hedged vs. unhedged P&L, rate scenario matrix, hedge ratio calculation |

---

## Technology Stack

- Microsoft Excel
- VBA
- Fixed income analytics

---

## Skills Demonstrated

- Fixed income analysis and duration management
- Treasury futures hedge construction and sizing
- Interest rate risk management
- Portfolio hedging and rebalancing mechanics
- Performance attribution

---

*Prepared for portfolio and educational purposes only. Figures are
illustrative, derived from a simulated portfolio and hedging
model, and do not constitute investment advice.*

[Back to Deal Intelligence Lab](../../README.md)
