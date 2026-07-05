# ACRA Technical Specification v1.0

## 1. Current Architecture
- GitHub: source of truth for Constitution, Rulebook, schemas, templates, logs.
- Google Sheets: reporting dashboard and manual import destination.
- Apps Script: imports ACRA JSON into Google Sheets.
- Sportily: horse-racing data provider.
- ChatGPT: analysis engine following ACRA documentation.

## 2. GitHub Folder Structure
```text
ACRA/
  README.md
  constitution/
    ACRA_Constitution_v1.md
    ACRA_Rulebook_v1.md
  schemas/
    acra_json_schema_v1.json
  templates/
    daily_delta_template.json
  docs/
    Technical_Specification_v1.md
  logs/
    2026/
      07/
        acra_delta_2026-07-04.json
```

## 3. Google Sheet Import Contract
The Apps Script imports seven top-level JSON arrays:
- bets
- weeklyDashboard
- horseWatchlist
- trainerWatchlist
- jockeyWatchlist
- replayReview
- lessonsLearned

## 4. Future Architecture
- Supabase: operational database.
- Vercel: ACRA web dashboard.
- GitHub: versioned rules and schemas.
