# Habitlock financial model

`habitlock_financial_model.xlsx`: 18-month unit-economics model for Habitlock, three scenarios side by side. Built after the competition, on top of the proposal's own sizing and badge rules.

**Read this first:** every commercial input (take rate, CAC, churn, balances) is an **illustrative placeholder**, not Infina data. The model is a reasoning tool. Its job is to show *which assumptions the business case depends on*, not to forecast revenue.

## Tabs
| Tab | What it does |
|---|---|
| `Read_me` | How to use, simplifications, colour code |
| `Summary` | Scale, P&L, break-even, cross-checks against the deck, integrity checks |
| `Unit_Economics` | Per-user LTV, CAC, payback, bonus headroom, "what must be true" |
| `Sensitivity` | Bonus vs take-rate spread by badge level; net contribution grid; LTV/CAC grid |
| `Assumptions` | All inputs. Blue = edit. Yellow = needs a real number most |
| `Model_Cons / _Base / _Aggr` | Monthly engine: funnel → cohorts → AUM → revenue → bonus cost → net contribution |

## Logic in one line
Acquired users → activated (first deposit) → cohort survivors (constant churn) → deposits, exits and partial withdrawals (with year-end/Tet seasonality and Pause & Reflect effect) → AUM → revenue on savings vs fund AUM × incrementality → minus badge bonus interest (paid on *all* savings balances) → minus CAC, build and run cost.

## Design choices a reviewer may ask about
- **Bonus interest is not scaled by incrementality, revenue is.** Habitlock pays the bonus to users who would have saved anyway; only the genuinely new AUM earns new revenue.
- **Badge levels follow the deck's unlock rules by tenure** (Lv4 needs 4 months; Lv5/Lv6 need auto-invest adoption after the AI launch). A qualification rate captures that not everyone keeps the streak.
- **A counterfactual block re-runs AUM without Pause & Reflect** to size the AUM it retains.
- **Known simplifications:** constant churn, one average balance for all users, no discounting, no compounding of bonus interest.

## How to make it real
Replace the yellow cells with Infina's numbers, in this order of impact: net take rate on savings, CAC, 90-day retention, average balance, incrementality.
