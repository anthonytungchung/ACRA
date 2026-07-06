# ACRA Lessons Learned

This document records practical lessons learned from live ACRA betting decisions.

---

## 2026-07-01 — Do Not Change the System After One Result

Early ACRA test bets showed normal variance.

Lesson:

Do not change the staking system after one win or one loss.

The system should only be reviewed properly after a larger sample size, ideally 50–100 bets.

Status: Active

---

## 2026-07-02 — Morning Scan Is Not Final Bet

Morning scan should only create a watchlist.

Lesson:

A morning candidate must not become a final betting recommendation until the full race card and live market have been reviewed.

Rule update:

Morning scan = watchlist only.

Status: Active

---

## 2026-07-02 — Full Race Card Required

A final betting decision needs complete race context.

Lesson:

No full race card = No final Buy / Stake.

Rule update:

Full Race Card Rule added to ACRA Rulebook.

Status: Active

---

## 2026-07-02 — Long Absence Penalty

Race: Kempton  
Horse: Breakdancer

Breakdancer lost after being considered as a value candidate.

Lesson:

Horses returning after 90+ days may need an extra confidence penalty unless there is strong trainer-pattern support.

Status: Active

---

## 2026-07-03 — 2yo Races Need Caution

Race: Doncaster  
Horse: Sultan Darius

Sultan Darius was a speculative 2yo value candidate and lost.

Lesson:

2yo novice and maiden races are high-uncertainty environments.

Default stake should be 0.5 pt or No Bet unless the full setup is very strong.

Status: Active

---

## 2026-07-03 — Win-Only Was the Wrong Structure

Race: Sandown  
Horse: Glacius

Glacius was backed as a long-price win-only value bet and finished 3rd.

Lesson:

The selection was not necessarily wrong, but the bet structure was wrong.

When a long-price value horse faces a clear class favourite and has strong place appeal, ACRA should consider win/place split.

Rule update:

ACRA Bet Structure Rule v1.1 added.

Status: Active

---

## 2026-07-03 — Visual Race Notes Matter

Race: Newton Abbot  
Horse: Gore Point

Gore Point won easily.

Lesson:

Post-race visual impression is important.

A horse winning easily may deserve watchlist status even if the raw result only says "won".

Action:

Added Gore Point to Horse Watchlist.

Status: Active

---

## 2026-07-03 — Beat-SP Is a Quality Signal

Race: Bellewstown  
Horse: April Mist

April Mist was taken at 3.25 and returned at around 2.38 SP.

Lesson:

Consistently beating SP is a useful sign that ACRA is finding value before the market fully adjusts.

Status: Active

---

## 2026-07-03 — Speculative Value Should Stay Small

Race: Bellewstown  
Horse: Focaccia

Focaccia won at 6.6 as a 0.5 pt speculative value bet.

Lesson:

A speculative value winner does not mean the stake should have been bigger.

If the profile contains risks such as temperament or quick turnaround, the correct stake remains small.

Status: Active

---

## 2026-07-05 — Live Data Must Be Refreshed Before Final Recommendation

Race: 13:50 Sandown  
Horse: Asfoora

Asfoora was considered at around 4.0.

Final check:

- Market implied probability at 4.0: 25.0%
- Sportily model: 20.86%
- My estimate: around 25–27%

Lesson:

Every final recommendation must use refreshed live Sportily data.

Earlier scan data or stale model data must not be used as final confirmation.

Decision:

No Bet at 4.0.

Only reconsider if price drifts to 4.5+.

Rule update:

Live Data Rule added to ACRA Rulebook.

Status: Active

---

## 2026-07-05 — No Edge Means No Bet

Race: 13:50 Sandown  
Horse: Asfoora

Asfoora was a credible horse, but the available price did not provide enough edge.

Lesson:

A good horse is not automatically a good bet.

If the market price already reflects the horse's chance, ACRA must pass.

Discipline reminder:

- Do not force a bet in a high-profile race
- Do not bet because analysis time has already been spent

# ACRA Lessons Learned

## 2026-07-06

### Redline — Win Edge Allocation

Redline won at Ayr after being backed Win @6.6 and Top2 @2.72.

Actual result:

```text
£0.75 Win @6.6 = +£4.20
£0.75 Top2 @2.72 = +£1.29
Total = +£5.49
- Do not bet just because the horse is familiar or attractive
- No edge = No bet

Status: Active

If the full £1.50 had been placed Win-only:

£1.50 Win @6.6 = +£8.40

Difference:

Win-only would have made £2.91 more.

Lesson:

When a runner has a genuine Win profile and Win odds are the main value source, ACRA should use Win-heavy or Win-only instead of automatic 50/50 Win+Place.

Manoir De Mirande — High Place / Low Win Conversion

Manoir De Mirande was not normally unreliable.

Its profile was:

7 runs
0 wins
5 places
Place rate 71.4%
Recent form 2323-3

The correct classification is:

High Place Rate / Low Win Conversion

Lesson:

High place-rate horses can justify Place bets, but Win stake should be reduced when win conversion is poor.

Jumping Incident Penalty

Manoir De Mirande had previous jumping incident history and non-finished at Roscommon.

Lesson:

For hurdles and chases, previous falls / jumping issues must reduce confidence in both Win and short-price Place bets.

Rule change:

Win stake down 0.5 level
Place odds threshold +0.1 to +0.2
Beat SP Is Not Enough

Cloud Summit was backed at 11.5 and returned SP 8.5, but finished 6th.

Lesson:

Good price does not automatically mean good bet.
Selection quality and model alignment must still pass the Review framework.
