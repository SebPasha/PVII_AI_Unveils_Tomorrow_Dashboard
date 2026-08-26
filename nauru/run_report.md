# Run report - Nauru

**🔴 Overall: REVIEW NEEDED**  
Generated 2026-08-26 14:29 by run_pipeline.py

| Stage | Ran | Key QA |
|---|---|---|
| validate_stage_schema (L2) | ok | PASS 3/3 |
| validate_source_fidelity (L4) | ok | NOT CONFIGURED |
| validate_recall (L4) | ok | NOT CONFIGURED [advisory] |
| validate_refs (L3) | ok | PASS 1/1 |
| combine_budget_years | ok | reconcile=FAIL - see MISMATCH rows | data_quality=REVIEW NEEDED - resolve HIGH items before relying on totals for those strategy-years |
| build_final_panel | ok | ceiling=PASS - no strategy over-counted in any year | unmatched_codes=0 |
| build_analytics_html | ok | dashboard built, no summary printed |
| audit_checks | ok | 11/11 PASS [advisory] |
| data_issues | FAILED | 4 detected across 1 country(ies): 2 high, 2 medium, 0 low [advisory] |

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
RESULT: PASS - every one of 60 reference(s) resolves
report -> Files/outputs/nauru/validation/refs_nauru_references.xlsx
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
PLAN ONLY: the budget layer carries 50 strategy total(s) and no programme line, so the mapping stage had nothing to match. The panel carries the plan's 17 strategies with no money against them, which is what the documents held for this country support.

Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/nauru/FINAL_PANEL.xlsx
  panel               : 17 strategies x 0 years ()
  match_review        : 0 matches (BOTH names + rationale)
  unmatched_codes     : 0 (codes NOT in that year's budget - REVIEW)
  unfunded_strategies : 17 (strategies with no budget any year)
  funding_by_program  : 0 (per programme x year, amount once - SAFE TO SUM)
  unmapped_programs   : 0 budget programmes with no matched strategy
  risk_panel          : 5 risks | ceiling: PASS
  enrichment          : strategyclean=yes risk_summary=yes
  maturity            : mean=0.271 | financing-weighted=0.0 | {'planned': 8, 'aspirational': 9}
  basket/reverse-pass : 0 shared programmes | reverse-pass edges=none (run Prompt 6b + --coverage)
  recall_review       : 0 large programmes matched to only 1 strategy (candidate baskets)
MATURITY: mean=0.271 financing_weighted=0.0
CEILING TEST: PASS - no strategy over-counted in any year
UNMATCHED CODES: 0
QA: PASS - 0 unmatched code(s), ceiling PASS, 0 year warning(s)
```

### build_analytics_html
```
PLAN ONLY: no programme line in this country's budget layer, so there is no money for this page to show. The plan's strategies are in FINAL_PANEL.xlsx and on the union dashboard, each with no funding against it.
```

### audit_checks
```
AUDIT CHECKS: nauru 11/11 PASS
  ok   A1   Stored programme sums              50 strategy-year(s) / 0 disagree
  ok   A2   Stored strategy totals             50 strategy-year(s) / 0 disagree
  --   A3   Programme counted once             sheet absent
  --   A4   Ceiling holds                      sheet absent
  --   A6   Panel money matches its edges      sheets absent
  --   A8   Edges cite real programmes         sheets absent
  ok   A9   No strategy dropped                17 strategyclean row(s) / 17 panel row(s)
  ok   A10  Unfunded list is complete          17 zero-funded / 17 listed
  ok   A11  Evidence chain resolves            45 distinct id(s) / 0 dangle
  ok   A12  Maturity summary is derivable      8 metric(s) / 0 disagree
  --   A14  No duplicate edges                 sheet absent
  ok   A15  One currency                       1 expected / 1 found
  ok   A16  Components are traceable           80 component(s) / 0 untraceable
  ok   A17  No workbook open in Excel          0 expected / 0 found
  ok   A18  Strategies come from the plan      17 strategy(ies) / 0 with no component
  --   A19  Funding priority is reproducible   no panel rows or no budget columns
  --   A20  The budget is readable             no programme rows
  --   A21  Ambiguous codes name their head    no budget rows or no accepted edges
  ok   A22  Every intervention is traceable to a strategy 45 intervention(s) extracted / 0 uncited (0.0%)
  --   A23  The sector layer stayed out of the panel no sector run for this country
```

### data_issues
```
data issues  Files/outputs/DATA_ISSUES.xlsx
  4 detected across 1 country(ies): 2 high, 2 medium, 0 low
  70 hand-written entr(ies) in 04_Docs_and_Planning/data_issues.json
  HIGH  nauru     D7       Flag raised while combining the budget years
  HIGH  nauru     D8       A strategy total its own programmes do not add up to
```
