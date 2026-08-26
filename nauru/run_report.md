# Run report - Nauru

**🔴 Overall: REVIEW NEEDED**  
Generated 2026-08-26 01:17 by run_pipeline.py

| Stage | Ran | Key QA |
|---|---|---|
| validate_stage_schema (L2) | ok | PASS 3/3 |
| validate_source_fidelity (L4) | ok | NOT CONFIGURED |
| validate_recall (L4) | ok | NOT CONFIGURED [advisory] |
| validate_refs (L3) | ok | INPUT MISSING (1/1 not on this machine) |
| combine_budget_years | ok | reconcile=FAIL - see MISMATCH rows | data_quality=REVIEW NEEDED - resolve HIGH items before relying on totals for those strategy-years |
| build_final_panel | FAILED | QA FAIL - ceiling=? | unmatched_codes=? |
| build_analytics_html | FAILED | QA FAIL - SKIPPED |
| audit_checks | FAILED | SKIPPED [advisory] |
| data_issues | FAILED | SKIPPED [advisory] |

## Outputs

- Budget layer: `Files/outputs/nauru/budget_layer_all_years.xlsx`
- FINAL panel (deliverable): `Files/outputs/nauru/FINAL_PANEL.xlsx`
- Dashboard: `Files/outputs/nauru/budget_strategy_analytics.html`
- Audit trail: `Files/outputs/union_dashboard.html`, Audit tab, filtered to this country
- Data oddities: `Files/outputs/DATA_ISSUES.xlsx`

## Full stage logs

### validate_stage_schema (L2)
```
--- nauru_budget_2024.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/nauru/validation/schema_nauru_budget_2024.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- nauru_strategyclean.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/nauru/validation/schema_nauru_strategyclean.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- nauru_risk_summary.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/nauru/validation/schema_nauru_risk_summary.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.
```

### validate_source_fidelity (L4)
```
no inputs configured for this check
```

### validate_recall (L4)
```
no inputs configured for this check
```

### validate_refs (L3)
```
--- nauru references
SKIPPED: input not on this machine: Files/outputs/nauru/budget_layer_all_years.xlsx
```

### combine_budget_years
```
==============================================================================
COMBINED BUDGET LAYER  -  years: 2024  (1 file(s))
==============================================================================

RECONCILIATION (per year: sum of program rows vs strategy_total)

  FY2024   (national total = 348,734,249.0)
    strat 01: total=  10,199,552.0  progsum=           0.0  ** MISMATCH diff=10,199,552.0
    strat 02: total=  20,140,565.0  progsum=           0.0  ** MISMATCH diff=20,140,565.0
    strat 03: total=  25,238,229.0  progsum=           0.0  ** MISMATCH diff=25,238,229.0
    strat 05: total=     414,462.0  progsum=           0.0  ** MISMATCH diff=414,462.0
    strat 08: total=   2,956,112.0  progsum=           0.0  ** MISMATCH diff=2,956,112.0
    strat 09: total=     418,444.0  progsum=           0.0  ** MISMATCH diff=418,444.0
    strat 11: total=   4,684,961.0  progsum=           0.0  ** MISMATCH diff=4,684,961.0
    strat 12: total=           0.0  progsum=           0.0  OK
    strat 13: total=     235,220.0  progsum=           0.0  ** MISMATCH diff=235,220.0
    strat 15: total=     614,751.0  progsum=           0.0  ** MISMATCH diff=614,751.0
    strat 16: total= 114,284,642.0  progsum=           0.0  ** MISMATCH diff=114,284,642.0
    strat 17: total=     803,679.0  progsum=           0.0  ** MISMATCH diff=803,679.0
    strat 18: total=     936,227.0  progsum=           0.0  ** MISMATCH diff=936,227.0
    strat 21: total=   1,065,769.0  progsum=           0.0  ** MISMATCH diff=1,065,769.0
    strat 22: total=     664,602.0  progsum=           0.0  ** MISMATCH diff=664,602.0
    strat 31: total=   3,162,933.0  progsum=           0.0  ** MISMATCH diff=3,162,933.0
    strat 41: total=   6,881,465.0  progsum=           0.0  ** MISMATCH diff=6,881,465.0
    strat 42: total=  59,901,640.0  progsum=           0.0  ** MISMATCH diff=59,901,640.0
    strat 43: total=   3,408,657.0  progsum=           0.0  ** MISMATCH diff=3,408,657.0
    strat 44: total=   1,954,599.0  progsum=           0.0  ** MISMATCH diff=1,954,599.0
    strat 45: total=   1,108,692.0  progsum=           0.0  ** MISMATCH diff=1,108,692.0
    strat 46: total=   1,307,566.0  progsum=           0.0  ** MISMATCH diff=1,307,566.0
    strat 50: total=   1,927,683.0  progsum=           0.0  ** MISMATCH diff=1,927,683.0
    strat 51: total=  23,184,433.0  progsum=           0.0  ** MISMATCH diff=23,184,433.0
    strat 52: total=     316,367.0  progsum=           0.0  ** MISMATCH diff=316,367.0
    strat 59: total=   6,460,961.0  progsum=           0.0  ** MISMATCH diff=6,460,961.0
    strat 60: total=           0.0  progsum=           0.0  OK
    strat 61: total=  15,800,540.0  progsum=           0.0  ** MISMATCH diff=15,800,540.0
    strat 62: total=   1,252,963.0  progsum=           0.0  ** MISMATCH diff=1,252,963.0
    strat 63: total=   4,016,473.0  progsum=           0.0  ** MISMATCH diff=4,016,473.0
    strat 71: total=   1,456,815.0  progsum=           0.0  ** MISMATCH diff=1,456,815.0
    strat 72: total=   1,538,229.0  progsum=           0.0  ** MISMATCH diff=1,538,229.0
    strat 73: total=     760,381.0  progsum=           0.0  ** MISMATCH diff=760,381.0
    strat 74: total=   2,604,367.0  progsum=           0.0  ** MISMATCH diff=2,604,367.0
    strat 75: total=           0.0  progsum=           0.0  OK
    strat 76: total=   1,218,947.0  progsum=           0.0  ** MISMATCH diff=1,218,947.0
    strat 77: total=     846,835.0  progsum=           0.0  ** MISMATCH diff=846,835.0
    strat 78: total=   3,901,609.0  progsum=           0.0  ** MISMATCH diff=3,901,609.0
    strat 79: total=     874,900.0  progsum=           0.0  ** MISMATCH diff=874,900.0
    strat 81: total=   3,507,984.0  progsum=           0.0  ** MISMATCH diff=3,507,984.0
    strat 82: total=   1,027,490.0  progsum=           0.0  ** MISMATCH diff=1,027,490.0
    strat 83: total=     752,540.0  progsum=           0.0  ** MISMATCH diff=752,540.0
    strat 84: total=   6,988,107.0  progsum=           0.0  ** MISMATCH diff=6,988,107.0
    strat 85: total=     436,926.0  progsum=           0.0  ** MISMATCH diff=436,926.0
    strat 86: total=     133,495.0  progsum=           0.0  ** MISMATCH diff=133,495.0
    strat 87: total=     684,983.0  progsum=           0.0  ** MISMATCH diff=684,983.0
    strat 88: total=   1,910,735.0  progsum=           0.0  ** MISMATCH diff=1,910,735.0
    strat 91: total=   3,761,531.0  progsum=           0.0  ** MISMATCH diff=3,761,531.0
    strat 95: total=   2,817,553.0  progsum=           0.0  ** MISMATCH diff=2,817,553.0
    strat 97: total=     168,635.0  progsum=           0.0  ** MISMATCH diff=168,635.0

RECONCILIATION: FAIL - see MISMATCH rows

NATIONAL TOTAL (the denominator every share is computed against)
    FY2024  heads 348,734,249.0  programmes 0.0  gap 100.0%  -> GRAND_TOTAL
    FY2024  extracted 100.0% of the document's own grand total 348,734,244.0

READABILITY  0 of 0 programme name(s) unreadable (0%), 0 of 50 head(s) (0%), 0% of the money

Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/nauru/budget_layer_all_years.xlsx
  sheet 'budget_all_years' : 51 rows  (feeds Prompt 6 / build_final_panel - each intervention matches against EVERY year's programs)
  sheet 'programs_wide'    : 0 programs x 1 year(s) (funding-over-time)
  sheet 'reconciliation'   : 50 rows (audit)
  sheet 'data_quality'     : 48 flagged items (see summary below)

==============================================================================
DATA-QUALITY SUMMARY
==============================================================================
  HIGH: 47   MEDIUM: 0   LOW: 0   INFO: 1

  [HIGH] reconciliation_mismatch  (47)
      - FY2024 strat 01: programs sum to 0.0 but strategy_total is 10,199,552.0 (gap 10,199,552.0) - a program line is likely missing or mis-extracted for this strategy-year.
      - FY2024 strat 02: programs sum to 0.0 but strategy_total is 20,140,565.0 (gap 20,140,565.0) - a program line is likely missing or mis-extracted for this strategy-year.
      - FY2024 strat 03: programs sum to 0.0 but strategy_total is 25,238,229.0 (gap 25,238,229.0) - a program line is likely missing or mis-extracted for this strategy-year.
      ... and 44 more (see 'data_quality' sheet)
==============================================================================
DATA QUALITY: REVIEW NEEDED - resolve HIGH items before relying on totals for those strategy-years
==============================================================================
```

### build_final_panel
```
ERROR: no mapping rows. Checked --mapping-dir '/Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/llm/nauru/mappings' and --mapping None.
       Run Prompt 6 (and optionally 6b) before assembling the panel.
```

### build_analytics_html
```
SKIPPED (panel not produced)
```

### audit_checks
```
SKIPPED (panel not produced)
```

### data_issues
```
SKIPPED (panel not produced)
```
