# Self-critique: what a hiring manager would push on

Written after the competition, using the original proposal's own numbers. Listed because spotting these is part of the job.

## Where the proposal is internally inconsistent
| Issue | Evidence | Impact | Fix |
|---|---|---|---|
| Active-Trust Flow Ratio is below 100% at baseline and target | Defined as deposits / withdrawals, 65% → 78% | Implies users withdraw more than they deposit even at target | Redefine (see metrics framework §4) |
| KPIs start before the features exist | AI Suggestion Acceptance has a July value; AI launches in November. Adherence has July-August values; Pause & Reflect launches in September | Baselines and targets look invented | Start each KPI at feature launch |
| Badge timeline does not fit the GTM | Lv4 needs 4 months of habit; streaks launch month 4, so the first Lv4 user is in month 7. Phase 3 (Nov-Dec) relies on Lv4 users | Phase 3 has nobody to target | Re-sequence or lower the gate (live check in the model's Summary tab) |
| Two different conversion numbers | Sizing: 20-30% of 3M. KPI: acquisition rate 30% → 45% | Unclear what is being measured | One definition, one denominator |
| Adherence baseline of 5% | 95% of withdrawals would be impulsive, versus ">70% say impulsive spending is the barrier" | Metric definition is unclear | Operational definition of "impulsive" |
| Market chart | Labels "500M"/"600M" on a USD-billion axis; 25% CAGR does not match 500 → 600 | Looks careless in a slide meant to persuade | Fix or drop; README uses only the McKinsey ~US$600B figure |

## Where the logic is thin
- **Self-reported survey, unknown n.** Stated interest in reminders is not usage.
- **20-30% conversion of the "ready" pool** is aggressive for 6 months and is the proposal's key volume assumption. The financial model uses it as the Aggressive case only.
- **No cost of the bonus interest.** The proposal pays up to +0.40% but never asks who funds it. The model shows it consumes 21-58% of incremental revenue and turns negative at the top badges.
- **No incrementality.** Some Habitlock AUM would have existed anyway.
- **No guardrails.** A mechanism that adds friction to withdrawals needs trust metrics and a stop rule.
- **No evidence the effect sizes are plausible.** Pause & Reflect would need to cancel about 47% of impulsive withdrawals to reach the Dec Adherence target. That is a large effect for a single prompt.

## What I would do next, in order
1. Run the bonus-interest experiment (is the habit coming from the reward or from the streak?).
2. Pull real baseline data from Infina: withdrawal reasons, 60-day retention, average balance, net take rate.
3. Re-run the financial model with those inputs and report the break-even.
4. Fix the KPI definitions and re-publish the targets as ranges tied to feature launch dates.
5. Take legal and compliance questions (see `compliance_notes.md`) to Infina before building anything restrictive.

## What I am still proud of
The problem framing (behaviour, not information), the focus on one persona (Emerging Savers), the decision to put friction at the moment of withdrawal, and the willingness to attach numbers and risks to the idea after the fact.
