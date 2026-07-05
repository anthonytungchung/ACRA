# ACRA Functional Specification v1.0

**Project:** ACRA — Anthony ChatGPT Racing Assistant  
**Document Type:** Functional Specification  
**Version:** v1.0  
**Created:** 2026-07-05  
**Status:** Active Draft  
**Source of Truth:** GitHub repository `ACRA`

---

## 1. Purpose

ACRA is a disciplined horse-racing betting operating system designed to support repeatable, value-focused betting decisions using Sportily data, independent analysis, structured staking, daily JSON logs, and weekly review.

ACRA is not a tipping service.  
ACRA is a decision framework.

---

## 2. Core Principles

### FS-001 — Process over results
ACRA shall judge each bet by decision quality first, and race result second.

### FS-002 — Value over winner-picking
ACRA shall distinguish between the most likely winner and the best value bet.

### FS-003 — Independent analysis first
ACRA shall form an independent probability estimate before relying on Sportily model percentage.

### FS-004 — No emotional staking
ACRA shall not chase losses, increase stake due to frustration, or change stake based on short-term results.

### FS-005 — Documented system beats assistant memory
If ChatGPT output contradicts the ACRA documentation, the documentation shall take priority.

---

## 3. Daily Workflow Requirements

### FS-006 — Morning scan
Every morning, ACRA shall scan today’s GB and IRE horse races using Sportily unless the user specifies otherwise.

### FS-007 — Morning shortlist
ACRA shall select up to 5 races/horses for the daily shortlist.

### FS-008 — Morning shortlist is not final betting instruction
The morning shortlist shall be treated as watchlist candidates only. Final betting decisions require live review before placing a bet.

### FS-009 — No uncontrolled re-scan
During live review, ACRA shall only review the morning shortlist unless the user explicitly requests a fresh scan.

---

## 4. Race Analysis Requirements

### FS-010 — Race card must be opened
ACRA shall not issue a final betting recommendation unless the full Sportily race card has been opened.

### FS-011 — Non-runner check
ACRA shall check non-runners before any final live recommendation.

### FS-012 — Current odds check
ACRA shall use current available odds where possible and calculate market-implied probability.

### FS-013 — Three-way probability check
For every final recommendation, ACRA shall compare:

- My independent probability estimate
- Sportily model probability
- Market-implied probability

### FS-014 — Probability divergence rule
If My % and Sportily % differ by more than approximately 8 percentage points, ACRA shall downgrade at least one confidence level or pass unless there is a clearly explained reason to override.

### FS-015 — Course model reliability
ACRA shall consider Sportily course model performance. If course model strike rate is below 25%, ACRA shall reduce reliance on the Sportily model.

---

## 5. ACRA Rating Requirements

### FS-016 — Rating system
ACRA shall assign every analysed betting candidate an ACRA rating.

| ACRA Rating | Meaning |
|---|---|
| ⭐⭐⭐⭐⭐+ | Rare, elite confidence and strong value |
| ⭐⭐⭐⭐⭐ | Best bet / NAP-level selection |
| ⭐⭐⭐⭐☆ | Standard value bet |
| ⭐⭐⭐☆☆ | Speculative or conditional |
| ⭐⭐☆☆☆ or below | No bet |

### FS-017 — Rating must match evidence
ACRA shall not assign a high rating purely because Sportily percentage is high. The rating must be justified by independent analysis, Sportily confirmation, market value, and risk context.

---

## 6. ACRA Staking Requirements

### FS-018 — Staking system
ACRA shall use the official ACRA Staking System v1.0:

| ACRA Rating | Stake |
|---|---:|
| ⭐⭐⭐⭐⭐+ | 2 pts (£6) |
| ⭐⭐⭐⭐⭐ | 1.5 pts (£4.50) |
| ⭐⭐⭐⭐☆ | 1 pt (£3) |
| ⭐⭐⭐☆☆ | 0.5–1 pt only with specific reason; otherwise skip |
| ⭐⭐☆☆☆ or below | 0 pt |

### FS-019 — One point value
ACRA shall define 1 point as £3 unless the user later changes the staking unit.

### FS-020 — Stake downgrade rule
If a bet has meaningful uncertainty such as novice race risk, long layoff, class jump, poor liquidity, or model disagreement, ACRA shall downgrade stake even if the price appears attractive.

---

## 7. Bet Structure Requirements

### FS-021 — Win bet
ACRA may recommend a win bet when the win edge is clear and the horse has a sufficiently strong profile.

### FS-022 — Place or win/place combination
ACRA shall consider a win/place split when:

- the horse is a big-price value candidate,
- the horse has credible place chance but uncertain win chance,
- the race has a strong favourite,
- previous experience suggests win-only is structurally inefficient.

### FS-023 — Place odds check
ACRA shall compare place market implied probability against estimated place probability before recommending a place bet.

---

## 8. Post-Race Review Requirements

### FS-024 — Daily post-race review
At day end, ACRA shall produce a post-race review covering:

- total stake,
- total P/L,
- points P/L,
- each bet result,
- decision quality,
- what Sportily got right or wrong,
- what independent analysis got right or wrong,
- lessons learned.

### FS-025 — Good decision / bad result distinction
ACRA shall classify losing bets as either acceptable losing decisions or poor decisions where relevant.

### FS-026 — Lessons must be logged
Important lessons shall be added to the Lessons Learned section of the daily JSON delta.

---

## 9. JSON Export Requirements

### FS-027 — Daily JSON delta
Every betting day, ACRA shall generate a daily JSON delta file for import into the master Google Sheet.

### FS-028 — JSON schema compatibility
The daily JSON shall match the Google Apps Script import structure exactly.

### FS-029 — Required top-level JSON keys
Every daily JSON delta shall include:

```json
{
  "bets": [],
  "weeklyDashboard": [],
  "horseWatchlist": [],
  "trainerWatchlist": [],
  "jockeyWatchlist": [],
  "replayReview": [],
  "lessonsLearned": []
}
```

### FS-030 — Betting record fields
Every item in `bets[]` shall contain:

```json
{
  "date": "",
  "time": "",
  "course": "",
  "race": "",
  "horse": "",
  "betType": "",
  "oddsTaken": 0,
  "stakeGBP": 0,
  "stakePoints": 0,
  "result": "",
  "position": "",
  "plGBP": 0,
  "plPoints": 0,
  "acraRating": "",
  "reasonForBet": "",
  "postRaceNote": ""
}
```

### FS-031 — No schema drift
ACRA shall not add, rename, or remove JSON fields without an agreed schema version update.

---

## 10. Weekly Review Requirements

### FS-032 — Sunday weekly review
Every Sunday day end, ACRA shall produce a weekly review.

### FS-033 — Weekly review content
The weekly review shall include:

- total bets,
- total stake,
- total P/L,
- ROI,
- points P/L,
- win rate,
- place rate where available,
- best bet,
- worst bet,
- key mistakes,
- key lessons,
- framework compliance,
- adjustments for next week.

---

## 11. Watchlist Requirements

### FS-034 — Horse watchlist
ACRA shall add horses to the watchlist when a horse produces a notable performance, model blind spot, strong visual impression, or follow-up angle.

### FS-035 — Trainer and jockey watchlists
ACRA shall add trainers and jockeys when repeated patterns or notable performance signals justify future attention.

### FS-036 — Replay review
ACRA shall log replay or visual observations when they materially affect future interpretation.

---

## 12. Versioning Requirements

### FS-037 — Version-controlled rules
Any rule change that affects ACRA behaviour shall be recorded in GitHub.

### FS-038 — Functional specification changes
Changes to this document shall create a new version, such as v1.1, v1.2, etc.

### FS-039 — Rulebook changes
Operational rule changes shall be added to the ACRA Rulebook and referenced in the changelog.

---

## 13. Current Implementation

### Current live tools

- Sportily: race data and model source
- ChatGPT: analysis engine
- Google Sheet: portfolio dashboard
- Apps Script: JSON import and dashboard refresh
- GitHub: source of truth for rules, schema, documentation and logs

### Future tools

- Supabase: structured betting database
- Vercel: web dashboard / ACRA app
- Automated validation: JSON schema checking before import

---

## 14. v1.0 Acceptance Criteria

ACRA v1.0 is considered operational when:

1. GitHub stores the functional specification, rulebook, schema and templates.
2. Daily JSON delta files can be imported into the Google Sheet without manual editing.
3. Morning scan, live review, post-race review and weekly review follow the documented workflow.
4. Every bet has a rating, stake, result, P/L and post-race note.
5. Any future rule change is documented before becoming active.

---

## 15. Change Log

| Version | Date | Change |
|---|---|---|
| v1.0 | 2026-07-05 | Initial functional specification created. |
