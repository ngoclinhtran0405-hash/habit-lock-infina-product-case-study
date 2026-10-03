# What the financial model says (and what it does not)

Source: [`model/habitlock_financial_model.xlsx`](../model/habitlock_financial_model.xlsx). All commercial inputs are illustrative; the *structure* of the findings matters more than the exact numbers.

## Headline: on these assumptions, Habitlock does not pay for itself as a stand-alone acquisition product

| 18 months from launch | Conservative | Base | Aggressive |
|---|---|---|---|
| Users acquired (% of the 3M "ready" pool) | 150K (5%) | 300K (10%) | 600K (20%) |
| Active users, M18 | 31K | 97K | 282K |
| AUM, M18 (VND bn) | 49 | 299 | 1,585 |
| Bonus interest as % of incremental revenue | 58% | 32% | 21% |
| LTV / CAC | 0.00x | 0.06x | 0.61x |
| AUM needed to cover run cost vs AUM reached | 0.02x | 0.49x | 5.8x |
| Cumulative net contribution, M18 (VND bn) | (18.6) | (24.8) | (32.2) |

Three things stand out:

1. **Growth makes the loss bigger, not smaller.** The Aggressive case loses the most because LTV/CAC is below 1: every extra paid user destroys value. The deck's headline (600K-900K new users) is a *cost* line unless acquisition is close to free.
2. **The bonus interest is not the main problem; revenue per user is.** A 20-25-year-old with an average balance of a few million VND earns Infina very little per year at any plausible take rate. Bonus cost matters mostly at the top badges: at the Base take rate, Lv6 (+0.40%) already costs more than it earns; in the Conservative case Lv4 onwards is negative (Sensitivity, Table 1).
3. **The product only closes if acquisition is near-organic or the value is elsewhere.** At Base, the CAC that gives LTV/CAC = 3 is about VND 2.5K per user. That is not a marketing budget, it is a signal that the case must rest on something other than paid acquisition.

## What this implies for the product case

- **Reframe the value.** Habitlock is better argued as a *retention and AUM-defence feature for users Infina already has* (and a cross-sell path into funds) than as a new-user acquisition engine. The model's Pause & Reflect block shows the mechanism: in the Base case it retains roughly VND 7.9bn of AUM at M18 (about 2.6% of AUM). Small, but it costs almost nothing to run once built, unlike acquisition.
- **Test whether the bonus is needed at all.** If streaks and goals produce the habit, the bonus interest is pure cost. This is the first experiment in [`metrics_framework.md`](metrics_framework.md).
- **Cap the top badges** or fund them only for users who also adopt auto-invest, where take rate is higher.
- **Validate the deck's KPI targets against the same logic.** The Dec 2025 Adherence target of 50% implies Pause & Reflect cancels about 47% of impulsive withdrawals. The Base case assumes 20%. That gap is the single most important claim to test.

## What would change the conclusion
Higher net take rate (check Sensitivity, Table 2), much lower CAC (Table 3), balances several times larger than modelled, or strong cross-sell into higher-margin products. None of these is evidenced in the proposal; each is a question for Infina's data.

## Limits of this model
Constant churn and one average balance for all users; no discounting; no cross-sell revenue; no cannibalisation of Infina's existing products beyond the incrementality factor; take rates and CAC are placeholders.
