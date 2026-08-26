# Run report - China

**🔴 Overall: REVIEW NEEDED**  
Generated 2026-08-26 03:03 by run_pipeline.py

| Stage | Ran | Key QA |
|---|---|---|
| validate_stage_schema (L2) | ok | PASS 8/8 |
| validate_source_fidelity (L4) | ok | NOT CONFIGURED [advisory] |
| validate_recall (L4) | ok | NOT CONFIGURED [advisory] |
| validate_refs (L3) | ok | INPUT MISSING (1/1 not on this machine) |
| combine_budget_years | ok | reconcile=FAIL - see MISMATCH rows | data_quality=REVIEW NEEDED - resolve HIGH items before relying on totals for those strategy-years |
| build_final_panel | ok | ceiling=PASS - no strategy over-counted in any year | unmatched_codes=0 |
| build_analytics_html | ok | strategies=168 (98 unfunded) | edges=81 |
| audit_checks | ok | 19/19 PASS [advisory] |
| data_issues | FAILED | 5 detected across 1 country(ies): 2 high, 2 medium, 1 low [advisory] |

## Outputs

- Budget layer: `Files/outputs/china/budget_layer_all_years.xlsx`
- FINAL panel (deliverable): `Files/outputs/china/FINAL_PANEL.xlsx`
- Dashboard: `Files/outputs/china/budget_strategy_analytics.html`
- Audit trail: `Files/outputs/union_dashboard.html`, Audit tab, filtered to this country
- Data oddities: `Files/outputs/DATA_ISSUES.xlsx`

## Full stage logs

### validate_stage_schema (L2)
```
--- china_budget_2022.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/china/validation/schema_china_budget_2022.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- china_budget_2023.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/china/validation/schema_china_budget_2023.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- china_budget_2024.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/china/validation/schema_china_budget_2024.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- china_budget_2025.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/china/validation/schema_china_budget_2025.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- china_budget_2026.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/china/validation/schema_china_budget_2026.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- china_mapping_2026.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/china/validation/schema_china_mapping_2026.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- china_strategyclean.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/china/validation/schema_china_strategyclean.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- china_risk_summary.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/china/validation/schema_china_risk_summary.xlsx

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
--- china references
SKIPPED: input not on this machine: Files/outputs/china/budget_layer_all_years.xlsx
```

### combine_budget_years
```
==============================================================================
COMBINED BUDGET LAYER  -  years: 2026  (5 file(s))
==============================================================================

RECONCILIATION (per year: sum of program rows vs strategy_total)

  FY2026   (national total = 4,779,205,000,000.0)
    strat 1: total=100,000,000,000.0  progsum=1,105,000,000,000.0  ** MISMATCH diff=-1,005,000,000,000.0
    strat 2: total=200,000,000,000.0  progsum=200,000,000,000.0  OK
    strat 3: total=426,400,000,000.0  progsum=426,400,000,000.0  OK
    strat 4: total=1,250,000,000,000.0  progsum=1,509,200,000,724.0  ** MISMATCH diff=-259,200,000,724.0
    strat 5: total=177,000,000,000.0  progsum=177,000,000,000.0  OK
    strat 6: total=202,200,000,000.0  progsum=244,200,000,000.0  ** MISMATCH diff=-42,000,000,000.0
    strat 7: total=184,800,000,000.0  progsum=184,900,000,000.0  ** MISMATCH diff=-100,000,000.0
    strat 8: total=2,238,805,000,000.0  progsum=2,238,805,000,000.0  OK

RECONCILIATION: FAIL - see MISMATCH rows

NATIONAL TOTAL (the denominator every share is computed against)
    FY2026  heads 4,779,205,000,000.0  programmes 6,085,505,000,724.0  gap  21.5%  -> GRAND_TOTAL
    FY2026  extracted 20.3% of the document's own grand total 30,010,000,000,000.0

READABILITY  0 of 17 programme name(s) unreadable (0%), 0 of 8 head(s) (0%), 0% of the money

Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/china/budget_layer_all_years.xlsx
  sheet 'budget_all_years' : 26 rows  (feeds Prompt 6 / build_final_panel - each intervention matches against EVERY year's programs)
  sheet 'programs_wide'    : 17 programs x 1 year(s) (funding-over-time)
  sheet 'reconciliation'   : 8 rows (audit)
  sheet 'data_quality'     : 6 flagged items (see summary below)

==============================================================================
DATA-QUALITY SUMMARY
==============================================================================
  HIGH: 5   MEDIUM: 0   LOW: 0   INFO: 1

  [HIGH] partial_budget  (1)
      - FY2026: the heads extracted sum to 6,085,505,000,724.0 but the document's own grand total is 30,010,000,000,000.0, so only 20% of the budget is here. A section was taken rather than the budget, and every share computed for FY2026 is a share of that section. Re-run stage 5 against the full summary of expenditure.

  [HIGH] reconciliation_mismatch  (4)
      - FY2026 strat 1: programs sum to 1,105,000,000,000.0 but strategy_total is 100,000,000,000.0 (gap -1,005,000,000,000.0) - a program line is likely missing or mis-extracted for this strategy-year.
      - FY2026 strat 4: programs sum to 1,509,200,000,724.0 but strategy_total is 1,250,000,000,000.0 (gap -259,200,000,724.0) - a program line is likely missing or mis-extracted for this strategy-year.
      - FY2026 strat 6: programs sum to 244,200,000,000.0 but strategy_total is 202,200,000,000.0 (gap -42,000,000,000.0) - a program line is likely missing or mis-extracted for this strategy-year.
      ... and 1 more (see 'data_quality' sheet)
==============================================================================
DATA QUALITY: REVIEW NEEDED - resolve HIGH items before relying on totals for those strategy-years
==============================================================================
```

### build_final_panel
```
Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/china/FINAL_PANEL.xlsx
  panel               : 168 strategies x 1 years (2026)
  match_review        : 81 matches (BOTH names + rationale)
  unmatched_codes     : 0 (codes NOT in that year's budget - REVIEW)
  unfunded_strategies : 98 (strategies with no budget any year)
  funding_by_program  : 15 (per programme x year, amount once - SAFE TO SUM)
  unmapped_programs   : 2 budget programmes with no matched strategy
  risk_panel          : 9 risks | ceiling: PASS
  enrichment          : strategyclean=yes risk_summary=yes
  maturity            : mean=0.548 | financing-weighted=0.85 | {'operational_programme': 70, 'planned': 85, 'aspirational': 12, 'planned_specific': 1}
  basket/reverse-pass : 13 shared programmes | reverse-pass edges=none (run Prompt 6b + --coverage)
  recall_review       : 0 large programmes matched to only 1 strategy (candidate baskets)
MATURITY: mean=0.548 financing_weighted=0.85
CEILING TEST: PASS - no strategy over-counted in any year
UNMATCHED CODES: 0
QA: PASS - 0 unmatched code(s), ceiling PASS, 0 year warning(s)
```

### build_analytics_html
```
dashboard -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/china/budget_strategy_analytics.html
  years        2026
  edges        81
  strategies   168 (98 unfunded)
  size         53 KB
```

### audit_checks
```
AUDIT CHECKS: china 19/19 PASS
  ok   A1   Stored programme sums              8 strategy-year(s) / 0 disagree
  ok   A2   Stored strategy totals             8 strategy-year(s) / 0 disagree
  ok   A3   Programme counted once             15 row(s) / 0 duplicate key(s)
  ok   A4   Ceiling holds                      8 strategy-year(s) / 0 over ceiling
  ok   A6   Panel money matches its edges      168 strategy-year figure(s) / 0 disagree
  ok   A8   Edges cite real programmes         81 accepted edge(s) / 0 dangle
  ok   A9   No strategy dropped                168 strategyclean row(s) / 168 panel row(s)
  ok   A10  Unfunded list is complete          98 zero-funded / 98 listed
  ok   A11  Evidence chain resolves            481 distinct id(s) / 0 dangle
  ok   A12  Maturity summary is derivable      8 metric(s) / 0 disagree
  ok   A14  No duplicate edges                 81 edge(s) / 0 duplicate(s)
  ok   A15  One currency                       1 expected / 1 found
  ok   A16  Components are traceable           1550 component(s) / 0 untraceable
  ok   A17  No workbook open in Excel          0 expected / 0 found
  ok   A18  Strategies come from the plan      168 strategy(ies) / 0 with no component
  ok   A19  Funding priority is reproducible   32 distinct (salience, funding) group(s) / 0 split across priorities
  ok   A20  The budget is readable             17 programme(s) / 0 unreadable (0%), carrying 0% of the money
  ok   A21  Ambiguous codes name their head    0 repeated code(s) / 0 edge(s) do not name a head
  ok   A22  Every intervention is traceable to a strategy 481 intervention(s) extracted / 0 uncited (0.0%)
  --   A23  The sector layer stayed out of the panel no sector run for this country
```

### data_issues
```
data issues  Files/outputs/DATA_ISSUES.xlsx
  5 detected across 1 country(ies): 2 high, 2 medium, 1 low
  70 hand-written entr(ies) in 04_Docs_and_Planning/data_issues.json
  HIGH  china     D7       Flag raised while combining the budget years
  HIGH  china     D8       A strategy total its own programmes do not add up to
```
