# Simulated S&P 500 Options Portfolio

> A short index strangle collects premium betting the market stays
> range-bound. What happens when a single headline breaks that
> range, and does active risk management save the trade — or just
> delay the loss?

**Status:** Version 1 complete | **Type:** Derivatives

---

## Objective

Construct and monitor a short S&P 500 Index (SPX) strangle
designed to monetize elevated implied volatility, then evaluate
whether the realized result was earned by the market thesis or by
active position management once that thesis was invalidated.

---

## Methodology

1. Price a short strangle (put and call, single expiry) using
   Black-Scholes-Merton for European index options
2. Set an explicit ex-ante hedge policy: delta band, roll
   triggers, and a breach-tightening rule into expiry
3. Track daily portfolio delta, theta and P&L against posted
   end-of-day marks and implied volatilities
4. Execute rolls and closes per the stated policy as the position
   moves
5. Attribute realized P&L by leg
6. Reconstruct a counterfactual (holding the position unadjusted)
   to isolate the value of active management from the value of
   the original thesis

---

## Key Assumptions

| Assumption | Value | Basis |
|-----------|-------|-------|
| Underlying | S&P 500 Index (SPX) | Assignment parameter |
| Expiry | 16 May 2026 | Assignment parameter |
| Initial structure | Short 6385 put / short 6595 call | Strangle, single expiry |
| Net premium collected | $453.70 | Both legs, per one-contract unit |
| Risk-free rate | 4.30% (continuously compounded) | Black-Scholes-Merton input |
| Dividend yield | 1.30% (continuous) | Black-Scholes-Merton input |
| Volatility input | Posted end-of-day implied volatility per leg | No fitted surface |
| Delta policy | Evaluate adjustment if \|delta\| exceeds 0.20 | Stated ex-ante |
| Delta policy, final two weeks | Tighten to ±0.10 | Stated ex-ante, not reached in review period |
| Review period | 26 Mar – 24 Apr 2026 | 21 trading sessions |

Premiums and P&L are stated per one-contract unit without the SPX
$100 index multiplier; scaling to a traded contract multiplies
every figure by 100.

---

## Execution

Five option executions across three trade events: the strangle
entry, a call roll, and a risk-reducing close.

| Date | Action | Strike | Price | S&P ref | Realized P&L |
|------|--------|--------|-------|---------|--------------|
| 27 Mar | Open put | 6,385 | 226.20 | 6,368.85 | — |
| 27 Mar | Open call | 6,595 | 227.50 | 6,368.85 | — |
| 6 Apr | Roll — close call | 6,595 | 189.66 | 6,611.83 | +37.84 |
| 6 Apr | Roll — open call | 6,625 | 174.46 | 6,611.83 | — |
| 9 Apr | Close call | 6,625 | 298.59 | 6,824.66 | (124.13) |

The 6 April roll lifted the call strike 30 points for a net cost
of $15.20 and improved portfolio delta from −0.18 to −0.16. The 9
April close crystallized a loss on the call side but, as the
counterfactual below shows, preserved the profitability of the
book.

---

## Results

| Metric | Value |
|--------|-------|
| Net premium collected | $453.70 |
| Final portfolio P&L | $135.31 |
| Return on premium collected | 29.8% |
| Trading sessions | 21 |
| Executions | 5 |
| Peak P&L (7 Apr) | $154.60 |
| Trough P&L (9 Apr) | $84.47 |
| Peak-to-trough drawdown | $70.13 (15.5% of premium) |
| Index move over period | +12.50% |

**Attribution by leg**

| Leg | Premium ($) | P&L ($) | Capture |
|-----|------------|---------|---------|
| Short put 6385 (retained, marked $4.60) | 226.20 | +221.60 | 98.0% |
| Short call 6595 (rolled 6 April) | 227.50 | +37.84 | 16.6% |
| Short call 6625 (closed 9 April) | 174.46 | (124.13) | (71.2%) |
| **Total portfolio** | **453.70** | **135.31** | **29.8%** |

**The counterfactual that matters:** the index closed the review
period at 7,165.08, above the strangle's upper break-even of
7,048.70. Had the position been left unadjusted, the 6595 call
alone would have carried at least 570 points of intrinsic value at
period end, putting the book at roughly negative $121 or worse
before any time value. Revaluing the actual 6625 call at
period-end marks instead of the 9 April close price:

| | Closed 9 April (actual) | Held to 24 April (counterfactual) |
|---|---|---|
| Short call 6625 — leg P&L | (124.13) | (383.63) |
| Short call 6595 — realized on roll | +37.84 | +37.84 |
| Short put 6385 — unrealized | +221.60 | +221.60 |
| **Portfolio P&L** | **135.31** | **(124.19)** |

**Conclusion:** The 29.8% return is real, but it was not earned by
the market thesis. The index finished well above the range the
strangle was structured to profit from, so the position as
originally sized was a loss-maker. The gain of $135.31 is
attributable to the 9 April decision to close the losing call leg
— worth $259.50 relative to holding it — not to the original view
that the market would stay range-bound.

---

## Limitations

- Premiums and P&L are stated per one-contract unit without the
  SPX $100 index multiplier; scaling to a traded position
  multiplies every figure in this analysis by 100.
- Marks and implied volatilities are posted end-of-day inputs, not
  independently sourced. No volatility surface is fitted, so skew
  and term structure are not modeled — adequate for monitoring at
  posted marks, but understates risk on a book with strike
  dispersion.
- No transaction costs, bid-offer spread, market impact or
  slippage are applied to any execution.
- Margin requirements and the financing cost of posted collateral
  are not modeled. An undefined-risk short strangle carries
  material margin in practice, which return-on-premium figures
  here do not capture.
- The position was not held to expiry. The short put is marked at
  $4.60 with 22 days remaining, so the final result is a
  mark-to-market figure, not a settled outcome.
- The structure itself — an undefined-risk strangle — was poorly
  matched to a binary-headline regime in which a single
  announcement moved the index 2.5% in one session. A defined-risk
  structure (an iron condor, or a credit put spread if directional
  risk was judged asymmetric) would have capped the tail while
  retaining most of the theta capture; this is treated as the
  primary structural lesson, not a footnote.

---

## Deliverables

| File | Description |
|------|-------------|
| [`models/`](models) | Options portfolio workbook, position log, Black-Scholes and Greeks calculations |
| [`outputs/`](outputs) | Performance summary, risk metrics summary |
| [`screenshots/`](screenshots) | Cumulative P&L chart, position-level Greeks, payoff diagram at expiry |

---

## Technology Stack

- Microsoft Excel
- Black-Scholes-Merton option pricing
- Options analytics and Greeks management

---

## Skills Demonstrated

- Derivatives structuring and options pricing
- Delta hedging and position risk management
- Performance attribution and counterfactual analysis
- Risk governance and post-trade review

---

*Prepared for portfolio and educational purposes only. Figures are
illustrative, derived from a simulated options portfolio, and do
not constitute investment advice.*

[Back to Deal Intelligence Lab](../../README.md)
