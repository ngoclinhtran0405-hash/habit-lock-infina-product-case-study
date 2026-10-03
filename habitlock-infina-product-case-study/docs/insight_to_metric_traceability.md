# Traceability: survey insight → problem → feature → metric

One chain per insight. Evidence strength is rated honestly: the survey sample size and method are **not stated in the proposal** (the sample size `n` is not given in the deck), and all findings are self-reported attitudes, not observed behaviour.

| # | Survey insight (Project X survey) | Problem | Feature | Behavioural mechanism | Metric (see [`metrics_framework.md`](metrics_framework.md)) | Evidence strength | What would prove it wrong |
|---|---|---|---|---|---|---|---|
| 1 | ~10% actively seek personal-finance info; ~30% understand long-term benefits | Users do not know how to start a plan | Onboarding quiz, savings jar with a goal | Lower the cost of the first step; a personalised starting point | Quiz completion; 7-day activation | Weak: attitude data, n unknown | Quiz completers activate at the same rate as non-completers |
| 2 | ~50% have no clear goal; ~30% have a plan | Saving has no emotional anchor | Goal-based jar with % progress | Goal visibility raises commitment | Deposit rate per jar; jars with goal vs without | Weak | Users with goals deposit no more than users without |
| 3 | >70% name impulsive spending as the biggest barrier | Money leaves savings at the moment of temptation | Pause & Reflect before withdrawal | Add a reflection step at the decision point (friction, not lock) | Impulsive withdrawal rate; Adherence Rate (redefined) | Medium on the problem, weak on the effect | Prompt shows no change in withdrawal rate versus control, or raises uninstalls |
| 4 | >60% find applying theory hard; ~5% find it easy | Knowledge does not turn into daily practice | Streaks and badge levels | Small, repeated rewards build routine | Week-4 streak survival; Lv2 by month 2 | Weak | Streak survival does not differ with or without the bonus (Experiment 1) |
| 5 | 85% want to understand their own financial behaviour | No feedback on own patterns | Dashboard, AI spending nudge | Self-awareness through feedback | Dashboard weekly views; nudge response rate | Weak: stated interest | Low repeat use of the dashboard after week 2 |
| 6 | 88% want a reminder when spending emotionally | Emotional spending goes unnoticed | AI nudge | Timely prompt at risky moments | Nudge → withdrawal cancelled; complaints per 1,000 users | Weak: stated interest | Nudges are muted or dismissed at high rates |
| 7 | Competitor gap: apps earn interest *or* build habit, rarely both | No product combines habit and yield | Habit mechanics on a yield wallet | Differentiation | Share of Habitlock users who choose it over a plain jar | Medium: desk research | Habit features add no retention over plain yield |
| 8 | Saving → investing is the end goal | Savers stay in cash | AI suggestions, auto-invest, Lv5/Lv6 | Habit first, then product step-up | Fund adoption; AI Suggestion Acceptance | Weak | Adoption stays near the 10-20% auto-invest cap |

## How to read this table
- Rows 3 and 4 carry most of the product's value, and both rely on mechanisms (friction and gamified rewards) that the proposal does not test. Experiments 1 and 2 in the metrics framework are designed to test exactly these.
- Stated interest (rows 5, 6, 8) is the weakest kind of evidence: people say they want reminders far more often than they use them.
- The cost of row 4's mechanism (bonus interest) is quantified in [`unit_economics_findings.md`](unit_economics_findings.md).
