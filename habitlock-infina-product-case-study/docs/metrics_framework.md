# Metrics framework for Habitlock

Replaces "four KPIs with monthly targets" with a structure a product team could run: one North Star, input metrics, guardrails, and experiments. Original targets stay in [`metrics_roadmap_gtm.md`](metrics_roadmap_gtm.md) and `data/kpi_targets.csv`.

## 1. North Star
**Consistent Savers**: users who made a qualifying deposit (>= VND 100K, the Lv1/Lv2 floor) in each of the last 2 consecutive months **and** had net flow >= 0 over the period.

Why this and not AUM: AUM can be raised by one large depositor and says nothing about habit. Why not "streak length": streaks are the intervention, not the outcome. Consistent Savers measures the behaviour the proposal claims to change.

## 2. Input metrics (what moves the North Star)
| Stage | Metric | Definition | Feature that moves it |
|---|---|---|---|
| Acquire | Quiz completion rate | Quiz completed / quiz started | Onboarding quiz |
| Activate | 7-day activation | First deposit within 7 days of signup | Savings jar with goal |
| Habit | Week-4 streak survival | Users with an unbroken streak at week 4 / users who started one | Streaks, nudges |
| Habit | Badge progression | Share of active users reaching Lv2 by month 2 | Badge system |
| Retain | 60-day retention | Active (deposit or open) at day 60 / activated | All |
| Friction | Pause & Reflect completion | Withdrawals completed after the prompt / prompts shown | Pause & Reflect |
| Monetise | Fund adoption | Users with fund AUM > 0 / active users | AI suggestions, auto-invest |

## 3. Guardrail metrics (what must not get worse)
A product that restricts withdrawals can raise "habit" metrics by making people feel trapped. These guardrails are the main thing missing from the deck.
| Guardrail | Trigger to pause a test |
|---|---|
| Withdrawal-related support tickets / 1,000 users | > 1.5x control |
| Uninstall or account closure within 7 days of a Pause & Reflect prompt | > +20% relative to control |
| Time-to-withdraw after the user decides to proceed | Median > 60 seconds added |
| Withdrawal failure or abandonment rate | > +2 pts vs control |
| Bonus interest cost / incremental revenue | > 40% (see financial model) |
| AI suggestion complaints or "not suitable" flags | Any pattern of one product type |
| Net Promoter Score among users who saw Pause & Reflect | Drop > 5 pts |

Principle: Pause & Reflect is **friction, never a lock**. The user can always proceed in two taps.

## 4. Fixes the original KPI definitions need
| Deck metric | Problem | Proposed fix |
|---|---|---|
| Active-Trust Flow Ratio = deposits / withdrawals to bank, 65% → 78% | A ratio below 100% means users withdraw more than they deposit. Even the Dec target is a net outflow, so AUM would shrink | Redefine as deposits / (deposits + withdrawals) with a >50% target, or use net flow per active user |
| Adherence Rate = 1 − impulsive / savings withdrawals, baseline 5% | Baseline 5% means 95% of withdrawals are impulsive, which sits oddly with the survey (>70% *say* impulsive spending is the main barrier) and no rule classifies "impulsive" | Define impulsive operationally: withdrawal within 48h of a deposit, or reason picked in Pause & Reflect. Report the baseline from data before setting targets |
| AI Suggestion Acceptance from Jul 2025 (12%) | AI suggestions launch in Nov on the roadmap | Start tracking at launch; no baseline before it exists |
| TA Acquisition Rate 30% → 45% | Sizing converts 20-30% of the 3M pool by year end; a 30% baseline in July contradicts that | Pick one definition (share of reachable TA vs share of new signups) and one denominator |
| Badge-dependent targets in Phase 3 | Lv4 needs 4 months of habit; streaks launch in month 4, so the first Lv4 user appears in month 7 | Move the "invest within 7 days of Lv4" target to month 7+ or lower the level gate |

## 5. Experiment design

### Experiment 1: Does the bonus interest do anything? (highest priority)
- **Hypothesis:** Streaks and goals alone produce most of the habit lift; bonus interest adds little.
- **Arms (randomised by user):** A control; B streaks + badges, no bonus; C streaks + badges + bonus.
- **Primary metric:** Consistent Savers at day 90. **Secondary:** 60-day retention, AUM per user.
- **Decision rule:** if C does not beat B by a margin larger than the bonus cost per user, drop the bonus.
- **Why it matters:** the financial model shows the bonus is a recurring cost on all balances.

### Experiment 2: Does Pause & Reflect reduce impulsive withdrawals without harming trust?
- **Hypothesis:** A reflection prompt cancels a meaningful share of impulsive withdrawals.
- **Arms:** control (no prompt) vs prompt, with a second prompt variant later.
- **Primary metric:** impulsive withdrawal rate (operational definition above). **Guardrails:** section 3.
- **Sample size (illustrative):** for a baseline impulsive rate p = 30% and a detectable drop of 5 points, n per arm ≈ 16 × p(1−p) / δ² = 16 × 0.21 / 0.0025 ≈ 1,350 (80% power, 5% significance).
- **Duration:** at least 4 weeks so that salary or allowance cycles are covered.
- **Stop rule:** any guardrail trigger in section 3, or 2 pts worse on withdrawal abandonment at the interim check.
- **Threshold to scale:** the financial model needs roughly 20% of impulsive withdrawals cancelled to matter; the deck's Dec target implies about 47%.

### Experiment 3 (cheap, pre-build): fake-door test
Landing page or in-app banner for Habitlock with a "Join the waitlist" button, to measure intent among Infina's existing users before building anything.
