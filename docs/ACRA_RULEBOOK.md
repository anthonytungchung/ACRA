# ACRA Rulebook

ACRA = Anthony ChatGPT Racing Analytics

This document records the core betting discipline, staking system, race analysis workflow, and decision rules for ACRA.

---

## 1. Core Principle

ACRA is a disciplined value-betting system.

The objective is not to bet every race.  
The objective is to identify situations where the available market price is higher than the horse's estimated true chance.

No edge = No bet.

---

## 2. Point System

1 point = £3

| Rating | Stake | Meaning |
|---|---:|---|
| ⭐⭐⭐⭐⭐+ | 2 pts / £6 | Ultra-rare, exceptional high-confidence + high-value only |
| ⭐⭐⭐⭐⭐ | 1.5 pts / £4.50 | Premium bet |
| ⭐⭐⭐⭐☆ | 1 pt / £3 | Standard bet |
| ⭐⭐⭐☆☆ | 0.5 pt / £1.50 | Speculative value / small play |
| ⭐⭐☆☆☆ or below | 0 pt | No Bet |

2 pts is allowed but should be extremely rare.

---

## 3. Morning Scan Rule

Morning scan is watchlist only.

A morning scan must not be treated as a final betting recommendation.

No final buy decision should be made until the full race card has been checked.

---

## 4. Full Race Card Rule

No full race card = No final Buy / Stake.

A final recommendation requires complete race context, including:

- Race type
- Field size
- Runner profiles
- Recent form
- Going / ground
- Class level
- Draw / pace context where relevant
- Current market price
- Sportily model data
- My independent estimate

---

## 5. Live Data Rule

Every final betting recommendation must refresh live Sportily data before producing a final Buy / No Bet decision.

A previous morning scan, earlier model output, or stale race-card view must not be treated as final confirmation.

Final decision requires:

- Current market price
- Refreshed Sportily model data
- My independent estimate
- Market implied probability
- Edge assessment after commission / slippage

If live data is not available, the decision must be:

No Bet / Wait.

---

## 6. Three-Way Check

Every final bet must pass the ACRA three-way check:

1. My independent estimate
2. Sportily model probability
3. Market implied probability

Market implied probability formula:

Decimal odds implied probability = 1 / odds

Example:

Odds 4.0 = 25.0% implied probability

A bet is only attractive when our estimated true chance is meaningfully higher than the market implied probability.

---

## 7. No Edge = No Bet

A horse can be credible and still be a No Bet.

If the market price already reflects the horse's true chance, ACRA must pass.

Example:

- Race: 13:50 Sandown
- Horse: Asfoora
- Price: 4.0
- Market implied probability: 25.0%
- Sportily model: 20.86%
- My estimate: around 25–27%

Conclusion:

There was no clear value edge after commission / slippage.

Decision:

No Bet.

Only reconsider if price drifts to 4.5+.

---

## 8. Staking Discipline

Stake size must follow confidence and value.

Do not increase stake because:

- We like the horse
- The race is high-profile
- We have spent time analysing the race
- We want action
- We are chasing losses
- We are trying to hit a daily profit target

The system should not be changed after one or two results.

Proper review should happen after 50–100 bets.

---

## 9. 2yo Novice / Maiden Caution

2yo novice and maiden races carry higher uncertainty.

Default approach:

- 0.5 pt speculative only
- Or No Bet

Only upgrade if form, model, market price, stable intent, and race context all align clearly.

---

## 10. Long-Price Value Structure Rule

Premium long-price value does not always mean win-only.

If a long-price selection faces a clear class favourite, but has strong place appeal, consider win/place split.

Use this when:

1. Selection is long price, usually 8.0+
2. Rating reaches ⭐⭐⭐⭐⭐ / 1.5 pts
3. There is a clear class favourite in the race
4. Our horse has strong place chance but may struggle to beat the favourite

Suggested structures:

- Safer: 0.5 pt win + 1.0 pt place
- Aggressive: 1.0 pt win + 0.5 pt place

Example:

Glacius ran 3rd at Sandown.  
Selection was acceptable, but win-only structure was wrong.

---

## 11. Beat-SP Check

Beat-SP is an important quality-control metric.

If ACRA regularly takes a price bigger than SP, the process may be identifying value before the market fully adjusts.

Example:

April Mist taken at 3.25.  
SP was around 2.38.  
This was a strong beat-SP example.

---

## 12. Post-Race Review Rule

Every bet should be reviewed after the race.

Review should include:

- Result
- Finishing position
- Profit / loss
- Whether the price was good
- Whether the analysis was correct
- Whether the staking was correct
- Whether the horse should enter the watchlist
- Any rule or checklist update

Do not judge the system from result alone.

A losing bet can be a good process.  
A winning bet can still be bad process.

---

## 13. Current ACRA Workflow

1. Morning scan
2. Add candidates to watchlist
3. Wait for full race card / live market
4. Refresh Sportily data
5. Estimate horse's true chance independently
6. Compare with market implied probability
7. Assess edge after commission / slippage
8. Decide: Buy / Wait / No Bet
9. Apply staking rule
10. Log bet in Google Sheet
11. Review result
12. Update lessons and watchlist


# ACRA Rulebook v1.3

Effective from 2026-07-07.

## Live Portfolio Rule

Every confirmed bet slip must be recorded immediately in the daily Live Portfolio with race, horse, bet type, stake, odds and total exposure.

Day End settlement must start from the Live Portfolio, not memory.

## Race-Level vs Bet-Line Accounting

ACRA must report two levels:

Race Level:
- Betting races
- Pass races

Bet-Line Level:
- Win
- Place
- Top2
- Top3

Each bet line must be settled independently.

## Structure Decision Gate

Before recommending any bet structure, ACRA must classify the runner and compare Win edge vs Place edge.

Required block:

```text
Horse Profile:
Win Profile / Place Profile / Speculative Profile

Win Edge:
Strong / Moderate / Thin / None

Place Edge:
Strong / Moderate / Thin / None

Best Structure:
Win-only / Win-heavy / 50-50 / Place-heavy / Pass
