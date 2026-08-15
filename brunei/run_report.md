# Run report - Brunei

**🔴 Overall: REVIEW NEEDED**  
Generated 2026-08-15 16:28 by run_pipeline.py

| Stage | Ran | Key QA |
|---|---|---|
| validate_stage_schema (L2) | ok | PASS 7/7 |
| validate_source_fidelity (L4) | ok | NOT CONFIGURED |
| validate_recall (L4) | ok | NOT CONFIGURED [advisory] |
| validate_refs (L3) | ok | PASS 1/1 |
| combine_budget_years | ok | reconcile=FAIL - see MISMATCH rows | data_quality=REVIEW NEEDED - resolve HIGH items before relying on totals for those strategy-years |
| build_final_panel | ok | QA FAIL - ceiling=FAIL - see ceiling sheet | unmatched_codes=0 |
| build_analytics_html | ok | strategies=68 (27 unfunded) | edges=49 |
| audit_checks | ok | QA FAIL - 13/15 PASS (A16 4 untraceable, A18 2 with no component) [advisory] |
| data_issues | ok | 10 detected across 1 country(ies): 5 high, 3 medium, 2 low [advisory] |

## Outputs

- Budget layer: `Files/outputs/brunei/budget_layer_all_years.xlsx`
- FINAL panel (deliverable): `Files/outputs/brunei/FINAL_PANEL.xlsx`
- Dashboard: `Files/outputs/brunei/budget_strategy_analytics.html`
- Audit trail: `Files/outputs/union_dashboard.html`, Audit tab, filtered to this country
- Data oddities: `Files/outputs/DATA_ISSUES.xlsx`

## Full stage logs

### validate_stage_schema (L2)
```
--- brunei_budget_2021.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/brunei/validation/schema_brunei_budget_2021.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- brunei_budget_2022.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/brunei/validation/schema_brunei_budget_2022.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- brunei_budget_2025.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/brunei/validation/schema_brunei_budget_2025.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- brunei_budget_2026.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/brunei/validation/schema_brunei_budget_2026.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- brunei_mapping_2025.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/brunei/validation/schema_brunei_mapping_2025.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- brunei_strategyclean.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/brunei/validation/schema_brunei_strategyclean.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- brunei_risk_summary.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/brunei/validation/schema_brunei_risk_summary.xlsx

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
--- brunei references
RESULT: PASS - every one of 925 reference(s) resolves
report -> Files/outputs/brunei/validation/refs_brunei_references.xlsx
```

### combine_budget_years
```
==============================================================================
COMBINED BUDGET LAYER  -  years: 2025  (4 file(s))
==============================================================================

RECONCILIATION (per year: sum of program rows vs strategy_total)

  FY2025   (national total = 3,068.4)
    strat 1: total=       1,949.8  progsum=       1,912.5  ** MISMATCH diff=37.3
    strat 2: total=         493.8  progsum=         493.8  OK
    strat 3: total=         624.9  progsum=         626.7  ** MISMATCH diff=-1.8

RECONCILIATION: FAIL - see MISMATCH rows

Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/brunei/budget_layer_all_years.xlsx
  sheet 'budget_all_years' : 44 rows  (feeds Prompt 6 / build_final_panel - each intervention matches against EVERY year's programs)
  sheet 'programs_wide'    : 41 programs x 1 year(s) (funding-over-time)
  sheet 'reconciliation'   : 3 rows (audit)
  sheet 'data_quality'     : 3 flagged items (see summary below)

==============================================================================
DATA-QUALITY SUMMARY
==============================================================================
  HIGH: 2   MEDIUM: 0   LOW: 0   INFO: 1

  [HIGH] reconciliation_mismatch  (2)
      - FY2025 strat 1: programs sum to 1,912.5 but strategy_total is 1,949.8 (gap 37.3) - a program line is likely missing or mis-extracted for this strategy-year.
      - FY2025 strat 3: programs sum to 626.7 but strategy_total is 624.9 (gap -1.8) - a program line is likely missing or mis-extracted for this strategy-year.
==============================================================================
DATA QUALITY: REVIEW NEEDED - resolve HIGH items before relying on totals for those strategy-years
==============================================================================
```

### build_final_panel
```
Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/brunei/FINAL_PANEL.xlsx
  panel               : 68 strategies x 1 years (2025)
  match_review        : 50 matches (BOTH names + rationale)
  unmatched_codes     : 0 (codes NOT in that year's budget - REVIEW)
  unfunded_strategies : 27 (strategies with no budget any year)
  funding_by_program  : 39 (per programme x year, amount once - SAFE TO SUM)
  unmapped_programs   : 2 budget programmes with no matched strategy
  risk_panel          : 10 risks | ceiling: FAIL - see 'ceiling' sheet
  enrichment          : strategyclean=yes risk_summary=yes
  maturity            : mean=0.632 | financing-weighted=0.873 | {'operational_programme': 37, 'operational_funded': 4, 'planned': 11, 'aspirational': 14, 'planned_specific': 2}
  basket/reverse-pass : 10 shared programmes | reverse-pass edges=none (run Prompt 6b + --coverage)
  recall_review       : 10 large programmes matched to only 1 strategy (candidate baskets)
MATURITY: mean=0.632 financing_weighted=0.873
CEILING TEST: FAIL - see ceiling sheet
UNMATCHED CODES: 0
QA: FAIL - 0 unmatched code(s), ceiling FAIL, 0 year warning(s)
```

### build_analytics_html
```
dashboard -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/brunei/budget_strategy_analytics.html
  years        2025
  edges        49
  strategies   68 (27 unfunded)
  size         46 KB
```

### audit_checks
```
AUDIT CHECKS: brunei 13/15 PASS (A16 4 untraceable, A18 2 with no component)
  ok   A1   Stored programme sums              3 strategy-year(s) / 0 disagree
  ok   A2   Stored strategy totals             3 strategy-year(s) / 0 disagree
  ok   A3   Programme counted once             39 row(s) / 0 duplicate key(s)
  ok   A4   Ceiling holds                      3 strategy-year(s) / 0 over ceiling
  ok   A6   Panel money matches its edges      68 strategy-year figure(s) / 0 disagree
  ok   A8   Edges cite real programmes         50 accepted edge(s) / 0 dangle
  ok   A9   No strategy dropped                68 strategyclean row(s) / 68 panel row(s)
  ok   A10  Unfunded list is complete          27 zero-funded / 27 listed
  ok   A11  Evidence chain resolves            574 distinct id(s) / 0 dangle
  ok   A12  Maturity summary is derivable      8 metric(s) / 0 disagree
  ok   A14  No duplicate edges                 49 edge(s) / 0 duplicate(s)
  ok   A15  One currency                       1 expected / 1 found
  FAIL A16  Components are traceable           1022 component(s) / 4 untraceable
            Infrastructure provision for enhan <- Preparation and upgrading works for infrastr
            Research and innovation allocation <- Knowledge and Expertise and Innovation Enhan
            Green Building initiatives under t <- Green Building initiatives under the 12th Na
            Research costs for public higher e <- Research costs for public higher education i
  ok   A17  No workbook open in Excel          0 expected / 0 found
  FAIL A18  Strategies come from the plan      69 strategy(ies) / 2 with no component
            Purchase of medicines, medical consumables and laboratory te
            Payment for medical treatment services at Gleneagles Jerudon
```

### data_issues
```
data issues  Files/outputs/DATA_ISSUES.xlsx
  10 detected across 1 country(ies): 5 high, 3 medium, 2 low
  11 hand-written entr(ies) in 04_Docs_and_Planning/data_issues.json
  HIGH  brunei    D11      Strategy named after the budget line funding it
  HIGH  brunei    D12      An output predates the prompt that produced it
  HIGH  brunei    D3       Strategy with no plan text behind it
  HIGH  brunei    D7       Flag raised while combining the budget years
  HIGH  brunei    D8       A strategy total its own programmes do not add up to
```
