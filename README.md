# Forecast for VELTRAXA: Is $180M in 2029 Reachable?

Brand forecast for **VELTRAXA**, a fictional once-daily oral BTK degrader launching in July 2027 for relapsed/refractory mantle cell lymphoma (2L+). The goal is a monthly budget, a low/base/high long-range plan to 2035, and a clear answer to whether the plan of record ($180M net revenue in 2029) is reachable and what would have to be true. All data are synthetic.

**Author:** Michael Chen

Built for *Applied Data Science and AI in Pharma Commercial* (Columbia University, Fall 2026)****

## What's here

```
data/
  mcl_epi_inputs.csv                   New MCL cases by year and age band
  mcl_treatment_funnel.csv             Diagnosed, treated and progression rates, with ranges
  mcl_market_monthly.csv               Observed 2L and 3L+ starts (used to check the funnel)
  mcl_market_by_region.csv             Regional starts for the top-down split
  mcl_analog_launches_monthly.csv      Six analog launches, 36 months each
  mcl_analog_launches_attributes.csv   Analog drug class, line, order of entry
  veltraxa_assumptions.csv             Starter assumption book
deliverables/
  HW2_mwc2150.ipynb                    Full analysis, executed: tasks 1-5
  HW2_mwc2150_assumptions.csv          Assumption book (27 rows)
  HW2_mwc2150_memo.pdf                 Two-page memo to the brand forecaster
  img/                                 Charts used in the notebook and memo
```

## Approach

| Task | Topic |
|---|---|
| 1 | Assumption book: every model input is a row with low / base / high, source type, source and rationale. Funnel rates are population-weighted from the funnel file; peak share and uptake come from the analogs and an order-of-entry fit |
| 2 | Funnel and brand forecast, 2023-2035: cases, 1L, 2L and 3L+ starts, new VELTRAXA patients, patients on therapy, net revenue. Incidence-based flow model with a one-year lag between lines. Funnel checked against 2025 observed starts |
| 3 | Low, base and high scenarios, plus a one-at-a-time tornado on 2029 net revenue |
| 4 | Checks: linear trend of 2L+ starts vs the funnel for 2027-28, and a regional split of 2028 new patients that sums to the national total |
| 5 | Memo: forecast and range in one chart, three key assumptions, the $180M verdict, monthly budget and annual plan with the phasing assumption |

Revenue is a chain of multiplications: line starts x brand share (peak share x uptake x coverage) x months on therapy x compliance x list price x gross-to-net. Share is applied to line starts, not to all patients, and all of a patient's revenue is booked in the start year (recorded as an assumption).

## Headline results

- 2029 net revenue is **$15M (low), $62M (base), $177M (high)** against the $180M plan of record. $180M is not reachable on current evidence; it takes every assumption at its best value at once, and even then lands just short in 2029 ($182M in 2030).
- The three assumptions that matter most are **months on therapy (D1)**, **peak share in 3L+ (B3)** and **peak share in 2L (B4)**.
- The funnel matches the 2025 market: 2L starts +3% and 3L+ starts -5% against observed. The simple trend of 2L+ starts is within +4% of the funnel for 2027-28.
- Monthly budget, base case: about $2.0M in 2027 (linear ramp Jul-Dec) and $36.6M in 2028 (flat, about $3.0M a month).
- The least certain number is months on therapy: it is a judgment, since the data have no duration information, and it drives the most revenue.

See the memo for the full reasoning and the 90-day research plan.

## Running it

Open `deliverables/HW2_mwc2150.ipynb` in Jupyter or VS Code and run it from the `deliverables/` folder. The notebook finds `data/` one level up, and writes the charts to `deliverables/img/` and the assumption book to `deliverables/HW2_mwc2150_assumptions.csv`. It uses numpy, pandas and matplotlib.

## AI usage

Claude (Claude Code in VS Code) was used to review the deliverables before publishing and to set up this repository and README. The notebook was re-executed from a clean copy and reproduced the saved outputs and assumption book exactly.
