# Run report - Thailand (one-page test)

**🔴 Overall: REVIEW NEEDED**  
Generated 2026-08-22 21:35 by run_pipeline.py

| Stage | Ran | Key QA |
|---|---|---|
| validate_stage_schema (L2) | ok | PASS 5/5 |
| validate_source_fidelity (L4) | ok | PASS 1/1 |
| validate_recall (L4) | ok | PASS 1/1 [advisory] |
| validate_refs (L3) | ok | PASS 1/1 |
| combine_budget_years | ok | reconcile=FAIL - see MISMATCH rows | data_quality=REVIEW NEEDED - resolve HIGH items before relying on totals for those strategy-years |
| build_final_panel | ok | ceiling=PASS - no strategy over-counted in any year | unmatched_codes=0 |
| build_analytics_html | ok | strategies=6 (2 unfunded) | edges=4 |
| audit_checks | ok | 19/19 PASS [advisory] |
| data_issues | ok | 0 detected across 0 country(ies): 0 high, 0 medium, 0 low [advisory] |

## Outputs

- Budget layer: `Files/outputs/thailand_test/budget_layer_all_years.xlsx`
- FINAL panel (deliverable): `Files/outputs/thailand_test/FINAL_PANEL.xlsx`
- Dashboard: `Files/outputs/thailand_test/budget_strategy_analytics.html`
- Audit trail: `Files/outputs/union_dashboard.html`, Audit tab, filtered to this country
- Data oddities: `Files/outputs/DATA_ISSUES.xlsx`

## Full stage logs

### validate_stage_schema (L2)
```
--- thailand_test_budget_2026.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/thailand_test/validation/schema_thailand_test_budget_2026.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- thailand_test_coverage_2026.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/thailand_test/validation/schema_thailand_test_coverage_2026.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- thailand_test_mapping_2026.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/thailand_test/validation/schema_thailand_test_mapping_2026.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- thailand_test_strategyclean.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/thailand_test/validation/schema_thailand_test_strategyclean.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- thailand_test_risk_summary.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/thailand_test/validation/schema_thailand_test_risk_summary.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.
```

### validate_source_fidelity (L4)
```
--- thailand_test_budget_2026.xlsx
==============================================================================
SOURCE FIDELITY  -  thailand_test_budget_2026.xlsx
  verified against: Thai Budget Test Page.pdf (independent text extraction, 1,726 chars)
==============================================================================
  rows                 19
  amounts traced       19/19
  codes traced         19/19
  names matched        19/19

  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/thailand_test/validation/fidelity_thailand_test_budget_2026.xlsx

  RESULT: PASS - every figure traces back to the source document.
Ignoring wrong pointing object 5 0 (offset 0)
Ignoring wrong pointing object 7 0 (offset 0)
Ignoring wrong pointing object 9 0 (offset 0)
Ignoring wrong pointing object 11 0 (offset 0)
```

### validate_recall (L4)
```
--- thailand_test_budget_2026.xlsx
RESULT: PASS - 17 programme code(s) extracted, none missed
report -> Files/outputs/thailand_test/validation/recall_thailand_test_budget_2026.xlsx
```

### validate_refs (L3)
```
--- thailand_test references
RESULT: PASS - every one of 11 reference(s) resolves
report -> Files/outputs/thailand_test/validation/refs_thailand_test_references.xlsx
```

### combine_budget_years
```
==============================================================================
COMBINED BUDGET LAYER  -  years: 2026  (1 file(s))
==============================================================================

RECONCILIATION (per year: sum of program rows vs strategy_total)

  FY2026   (national total = 813,242.5)
    strat 1: total=     413,907.6  progsum=     413,907.6  OK
    strat 2: total=     399,334.9  progsum=      43,335.7  ** MISMATCH diff=355,999.2

RECONCILIATION: FAIL - see MISMATCH rows

NATIONAL TOTAL (the denominator every share is computed against)
    FY2026  heads 813,242.5  programmes 457,243.3  gap  43.8%  -> PROGRAMMES
    The head totals under-report in 1 year(s); the programme rows are the national budget there.

READABILITY  0 of 17 programme name(s) unreadable (0%), 0 of 2 head(s) (0%), 0% of the money

Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/thailand_test/budget_layer_all_years.xlsx
  sheet 'budget_all_years' : 19 rows  (feeds Prompt 6 / build_final_panel - each intervention matches against EVERY year's programs)
  sheet 'programs_wide'    : 17 programs x 1 year(s) (funding-over-time)
  sheet 'reconciliation'   : 2 rows (audit)
  sheet 'data_quality'     : 4 flagged items (see summary below)

==============================================================================
DATA-QUALITY SUMMARY
==============================================================================
  HIGH: 2   MEDIUM: 1   LOW: 0   INFO: 1

  [HIGH] national_basis_programmes  (1)
      - FY2026: head totals sum to 813,242.5 but the programmes beneath them sum to 457,243.3 (44% apart), so the national total for this year is taken from the PROGRAMME rows. Every share for FY2026 is computed against 457,243.3.

  [HIGH] reconciliation_mismatch  (1)
      - FY2026 strat 2: programs sum to 43,335.7 but strategy_total is 399,334.9 (gap 355,999.2) - a program line is likely missing or mis-extracted for this strategy-year.

  [MEDIUM] no_grand_total  (1)
      - FY2026: the document printed no grand total that stage 5 could find, so there is nothing to check the extraction's completeness against. Every share for FY2026 rests on the heads being all of them.
==============================================================================
DATA QUALITY: REVIEW NEEDED - resolve HIGH items before relying on totals for those strategy-years
==============================================================================
```

### build_final_panel
```
Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/thailand_test/FINAL_PANEL.xlsx
  panel               : 6 strategies x 1 years (2026)
  match_review        : 4 matches (BOTH names + rationale)
  unmatched_codes     : 0 (codes NOT in that year's budget - REVIEW)
  unfunded_strategies : 2 (strategies with no budget any year)
  funding_by_program  : 4 (per programme x year, amount once - SAFE TO SUM)
  unmapped_programs   : 13 budget programmes with no matched strategy
  risk_panel          : 7 risks | ceiling: PASS
  enrichment          : strategyclean=yes risk_summary=yes
  maturity            : mean=0.675 | financing-weighted=0.85 | {'operational_programme': 4, 'aspirational': 1, 'planned_specific': 1}
  basket/reverse-pass : 0 shared programmes | reverse-pass edges=none (run Prompt 6b + --coverage)
  recall_review       : 2 large programmes matched to only 1 strategy (candidate baskets)
MATURITY: mean=0.675 financing_weighted=0.85
CEILING TEST: PASS - no strategy over-counted in any year
UNMATCHED CODES: 0
QA: PASS - 0 unmatched code(s), ceiling PASS, 0 year warning(s)
```

### build_analytics_html
```
dashboard -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/thailand_test/budget_strategy_analytics.html
  years        2026
  edges        4
  strategies   6 (2 unfunded)
  size         29 KB
```

### audit_checks
```
AUDIT CHECKS: thailand_test 19/19 PASS
  ok   A1   Stored programme sums              2 strategy-year(s) / 0 disagree
  ok   A2   Stored strategy totals             2 strategy-year(s) / 0 disagree
  ok   A3   Programme counted once             4 row(s) / 0 duplicate key(s)
  ok   A4   Ceiling holds                      2 strategy-year(s) / 0 over ceiling
  ok   A6   Panel money matches its edges      6 strategy-year figure(s) / 0 disagree
  ok   A8   Edges cite real programmes         4 accepted edge(s) / 0 dangle
  ok   A9   No strategy dropped                6 strategyclean row(s) / 6 panel row(s)
  ok   A10  Unfunded list is complete          2 zero-funded / 2 listed
  ok   A11  Evidence chain resolves            4 distinct id(s) / 0 dangle
  ok   A12  Maturity summary is derivable      8 metric(s) / 0 disagree
  ok   A14  No duplicate edges                 4 edge(s) / 0 duplicate(s)
  ok   A15  One currency                       1 expected / 1 found
  ok   A16  Components are traceable           9 component(s) / 0 untraceable
  ok   A17  No workbook open in Excel          0 expected / 0 found
  ok   A18  Strategies come from the plan      6 strategy(ies) / 0 with no component
  ok   A19  Funding priority is reproducible   6 distinct (salience, funding) group(s) / 0 split across priorities
  ok   A20  The budget is readable             17 programme(s) / 0 unreadable (0%), carrying 0% of the money
  ok   A21  Ambiguous codes name their head    0 repeated code(s) / 0 edge(s) do not name a head
  ok   A22  Every intervention is traceable to a strategy 4 intervention(s) extracted / 0 uncited (0.0%)
  --   A23  The sector layer stayed out of the panel no sector run for this country
```

### data_issues
```
data issues  Files/outputs/DATA_ISSUES.xlsx
  0 detected across 0 country(ies): 0 high, 0 medium, 0 low
  54 hand-written entr(ies) in 04_Docs_and_Planning/data_issues.json
```
