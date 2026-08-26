# Run report - Sri Lanka

**🔴 Overall: REVIEW NEEDED**  
Generated 2026-08-26 14:29 by run_pipeline.py

| Stage | Ran | Key QA |
|---|---|---|
| validate_stage_schema (L2) | ok | PASS 3/3 |
| validate_source_fidelity (L4) | ok | NOT CONFIGURED [advisory] |
| validate_recall (L4) | ok | NOT CONFIGURED [advisory] |
| validate_refs (L3) | ok | PASS 1/1 |
| combine_budget_years | ok | reconcile=FAIL - see MISMATCH rows | data_quality=REVIEW NEEDED - resolve HIGH items before relying on totals for those strategy-years |
| build_final_panel | ok | ceiling=PASS - no strategy over-counted in any year | unmatched_codes=0 |
| build_analytics_html | ok | dashboard built, no summary printed |
| audit_checks | FAILED | QA FAIL - 10/11 PASS (A15 2 found) [advisory] |
| data_issues | FAILED | 4 detected across 1 country(ies): 2 high, 2 medium, 0 low [advisory] |

## Outputs

- Budget layer: `Files/outputs/sri_lanka/budget_layer_all_years.xlsx`
- FINAL panel (deliverable): `Files/outputs/sri_lanka/FINAL_PANEL.xlsx`
- Dashboard: `Files/outputs/sri_lanka/budget_strategy_analytics.html`
- Audit trail: `Files/outputs/union_dashboard.html`, Audit tab, filtered to this country
- Data oddities: `Files/outputs/DATA_ISSUES.xlsx`

## Full stage logs

### validate_stage_schema (L2)
```
--- sri_lanka_budget_2024.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/sri_lanka/validation/schema_sri_lanka_budget_2024.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- sri_lanka_strategyclean.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/sri_lanka/validation/schema_sri_lanka_strategyclean.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- sri_lanka_risk_summary.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/sri_lanka/validation/schema_sri_lanka_risk_summary.xlsx

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
--- sri_lanka references
RESULT: PASS - every one of 976 reference(s) resolves
report -> Files/outputs/sri_lanka/validation/refs_sri_lanka_references.xlsx
```

### combine_budget_years
```
==============================================================================
COMBINED BUDGET LAYER  -  years: 2024  (1 file(s))
==============================================================================

RECONCILIATION (per year: sum of program rows vs strategy_total)

  FY2024   (national total = 212,340.0)
    strat 1: total=     133,000.0  progsum=           0.0  ** MISMATCH diff=133,000.0
    strat 2: total=       5,000.0  progsum=           0.0  ** MISMATCH diff=5,000.0
    strat 3: total=       1,000.0  progsum=           0.0  ** MISMATCH diff=1,000.0
    strat 4: total=       2,000.0  progsum=           0.0  ** MISMATCH diff=2,000.0
    strat 5: total=       4,000.0  progsum=           0.0  ** MISMATCH diff=4,000.0
    strat 6: total=         600.0  progsum=           0.0  ** MISMATCH diff=600.0
    strat 7: total=      11,250.0  progsum=           0.0  ** MISMATCH diff=11,250.0
    strat 8: total=      10,000.0  progsum=           0.0  ** MISMATCH diff=10,000.0
    strat 9: total=      10,000.0  progsum=           0.0  ** MISMATCH diff=10,000.0
    strat 10: total=       2,000.0  progsum=           0.0  ** MISMATCH diff=2,000.0
    strat 11: total=       1,000.0  progsum=           0.0  ** MISMATCH diff=1,000.0
    strat 12: total=         500.0  progsum=           0.0  ** MISMATCH diff=500.0
    strat 13: total=          40.0  progsum=           0.0  ** MISMATCH diff=40.0
    strat 14: total=         450.0  progsum=           0.0  ** MISMATCH diff=450.0
    strat 15: total=         750.0  progsum=           0.0  ** MISMATCH diff=750.0
    strat 16: total=         150.0  progsum=           0.0  ** MISMATCH diff=150.0
    strat 17: total=         500.0  progsum=           0.0  ** MISMATCH diff=500.0
    strat 18: total=          75.0  progsum=           0.0  ** MISMATCH diff=75.0
    strat 19: total=          25.0  progsum=           0.0  ** MISMATCH diff=25.0
    strat 20: total=         300.0  progsum=           0.0  ** MISMATCH diff=300.0
    strat 21: total=         100.0  progsum=           0.0  ** MISMATCH diff=100.0
    strat 22: total=       2,500.0  progsum=           0.0  ** MISMATCH diff=2,500.0
    strat 23: total=         500.0  progsum=           0.0  ** MISMATCH diff=500.0
    strat 24: total=         100.0  progsum=           0.0  ** MISMATCH diff=100.0
    strat 25: total=         300.0  progsum=           0.0  ** MISMATCH diff=300.0
    strat 26: total=         500.0  progsum=           0.0  ** MISMATCH diff=500.0
    strat 27: total=         250.0  progsum=           0.0  ** MISMATCH diff=250.0
    strat 28: total=         500.0  progsum=           0.0  ** MISMATCH diff=500.0
    strat 29: total=         500.0  progsum=           0.0  ** MISMATCH diff=500.0
    strat 30: total=         250.0  progsum=           0.0  ** MISMATCH diff=250.0
    strat 31: total=       2,500.0  progsum=           0.0  ** MISMATCH diff=2,500.0
    strat 32: total=         400.0  progsum=           0.0  ** MISMATCH diff=400.0
    strat 33: total=         100.0  progsum=           0.0  ** MISMATCH diff=100.0
    strat 34: total=         200.0  progsum=           0.0  ** MISMATCH diff=200.0
    strat 35: total=       1,500.0  progsum=           0.0  ** MISMATCH diff=1,500.0
    strat 36: total=       1,500.0  progsum=           0.0  ** MISMATCH diff=1,500.0
    strat 37: total=         200.0  progsum=           0.0  ** MISMATCH diff=200.0
    strat 38: total=         700.0  progsum=           0.0  ** MISMATCH diff=700.0
    strat 39: total=       2,000.0  progsum=           0.0  ** MISMATCH diff=2,000.0
    strat 40: total=       1,000.0  progsum=           0.0  ** MISMATCH diff=1,000.0
    strat 41: total=         250.0  progsum=           0.0  ** MISMATCH diff=250.0
    strat 42: total=         250.0  progsum=           0.0  ** MISMATCH diff=250.0
    strat 43: total=         150.0  progsum=           0.0  ** MISMATCH diff=150.0
    strat 44: total=       3,000.0  progsum=           0.0  ** MISMATCH diff=3,000.0
    strat 45: total=       8,000.0  progsum=           0.0  ** MISMATCH diff=8,000.0
    strat 46: total=         250.0  progsum=           0.0  ** MISMATCH diff=250.0
    strat 47: total=         750.0  progsum=           0.0  ** MISMATCH diff=750.0
    strat 48: total=         600.0  progsum=           0.0  ** MISMATCH diff=600.0
    strat 49: total=         750.0  progsum=           0.0  ** MISMATCH diff=750.0
    strat 50: total=         100.0  progsum=           0.0  ** MISMATCH diff=100.0

RECONCILIATION: FAIL - see MISMATCH rows

NATIONAL TOTAL (the denominator every share is computed against)
    FY2024  heads 212,340.0  programmes 0.0  gap 100.0%  -> GRAND_TOTAL
    FY2024  extracted 3043.0% of the document's own grand total 6,978.0

READABILITY  0 of 0 programme name(s) unreadable (0%), 0 of 50 head(s) (0%), 0% of the money

Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/sri_lanka/budget_layer_all_years.xlsx
  sheet 'budget_all_years' : 51 rows  (feeds Prompt 6 / build_final_panel - each intervention matches against EVERY year's programs)
  sheet 'programs_wide'    : 0 programs x 1 year(s) (funding-over-time)
  sheet 'reconciliation'   : 50 rows (audit)
  sheet 'data_quality'     : 52 flagged items (see summary below)

==============================================================================
DATA-QUALITY SUMMARY
==============================================================================
  HIGH: 51   MEDIUM: 0   LOW: 0   INFO: 1

  [HIGH] over_extraction  (1)
      - FY2024: the heads extracted sum to 212,340.0 against a printed grand total of 6,978.0 (3043%), so the same money is being counted more than once.

  [HIGH] reconciliation_mismatch  (50)
      - FY2024 strat 1: programs sum to 0.0 but strategy_total is 133,000.0 (gap 133,000.0) - a program line is likely missing or mis-extracted for this strategy-year.
      - FY2024 strat 2: programs sum to 0.0 but strategy_total is 5,000.0 (gap 5,000.0) - a program line is likely missing or mis-extracted for this strategy-year.
      - FY2024 strat 3: programs sum to 0.0 but strategy_total is 1,000.0 (gap 1,000.0) - a program line is likely missing or mis-extracted for this strategy-year.
      ... and 47 more (see 'data_quality' sheet)
==============================================================================
DATA QUALITY: REVIEW NEEDED - resolve HIGH items before relying on totals for those strategy-years
==============================================================================
```

### build_final_panel
```
PLAN ONLY: the budget layer carries 50 strategy total(s) and no programme line, so the mapping stage had nothing to match. The panel carries the plan's 143 strategies with no money against them, which is what the documents held for this country support.

Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/sri_lanka/FINAL_PANEL.xlsx
  panel               : 143 strategies x 0 years ()
  match_review        : 0 matches (BOTH names + rationale)
  unmatched_codes     : 0 (codes NOT in that year's budget - REVIEW)
  unfunded_strategies : 143 (strategies with no budget any year)
  funding_by_program  : 0 (per programme x year, amount once - SAFE TO SUM)
  unmapped_programs   : 0 budget programmes with no matched strategy
  risk_panel          : 9 risks | ceiling: PASS
  enrichment          : strategyclean=yes risk_summary=yes
  maturity            : mean=0.349 | financing-weighted=0.0 | {'planned': 119, 'aspirational': 10, 'planned_specific': 14}
  basket/reverse-pass : 0 shared programmes | reverse-pass edges=none (run Prompt 6b + --coverage)
  recall_review       : 0 large programmes matched to only 1 strategy (candidate baskets)
MATURITY: mean=0.349 financing_weighted=0.0
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
AUDIT CHECKS: sri_lanka 10/11 PASS (A15 2 found)
  ok   A1   Stored programme sums              50 strategy-year(s) / 0 disagree
  ok   A2   Stored strategy totals             50 strategy-year(s) / 0 disagree
  --   A3   Programme counted once             sheet absent
  --   A4   Ceiling holds                      sheet absent
  --   A6   Panel money matches its edges      sheets absent
  --   A8   Edges cite real programmes         sheets absent
  ok   A9   No strategy dropped                143 strategyclean row(s) / 143 panel row(s)
  ok   A10  Unfunded list is complete          143 zero-funded / 143 listed
  ok   A11  Evidence chain resolves            957 distinct id(s) / 0 dangle
  ok   A12  Maturity summary is derivable      8 metric(s) / 0 disagree
  --   A14  No duplicate edges                 sheet absent
  FAIL A15  One currency                       1 expected / 2 found
            Rs. Billion
            Rs.Mn
  ok   A16  Components are traceable           1008 component(s) / 0 untraceable
  ok   A17  No workbook open in Excel          0 expected / 0 found
  ok   A18  Strategies come from the plan      143 strategy(ies) / 0 with no component
  --   A19  Funding priority is reproducible   no panel rows or no budget columns
  --   A20  The budget is readable             no programme rows
  --   A21  Ambiguous codes name their head    no budget rows or no accepted edges
  ok   A22  Every intervention is traceable to a strategy 958 intervention(s) extracted / 1 uncited (0.1%)
            2205
  --   A23  The sector layer stayed out of the panel no sector run for this country
```

### data_issues
```
data issues  Files/outputs/DATA_ISSUES.xlsx
  4 detected across 1 country(ies): 2 high, 2 medium, 0 low
  70 hand-written entr(ies) in 04_Docs_and_Planning/data_issues.json
  HIGH  sri_lanka D7       Flag raised while combining the budget years
  HIGH  sri_lanka D8       A strategy total its own programmes do not add up to
```
