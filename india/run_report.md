# Run report - India

**🔴 Overall: REVIEW NEEDED**  
Generated 2026-08-26 14:31 by run_pipeline.py

| Stage | Ran | Key QA |
|---|---|---|
| validate_stage_schema (L2) | ok | QA FAIL - FAIL 1/6 (india_strategyclean.xlsx) |
| validate_source_fidelity (L4) | ok | NOT CONFIGURED |
| validate_recall (L4) | ok | NOT CONFIGURED [advisory] |
| validate_refs (L3) | ok | PASS 1/1 |
| combine_budget_years | ok | reconcile=PASS - all years reconcile | data_quality=OK with minor flags - review MEDIUM/LOW as needed |
| build_final_panel | ok | ceiling=PASS - no strategy over-counted in any year | unmatched_codes=0 |
| build_analytics_html | ok | dashboard built, no summary printed |
| audit_checks | ok | 14/14 PASS [advisory] |
| data_issues | ok | 4 detected across 1 country(ies): 0 high, 3 medium, 1 low [advisory] |

## Outputs

- Budget layer: `Files/outputs/india/budget_layer_all_years.xlsx`
- FINAL panel (deliverable): `Files/outputs/india/FINAL_PANEL.xlsx`
- Dashboard: `Files/outputs/india/budget_strategy_analytics.html`
- Audit trail: `Files/outputs/union_dashboard.html`, Audit tab, filtered to this country
- Data oddities: `Files/outputs/DATA_ISSUES.xlsx`

## Full stage logs

### validate_stage_schema (L2)
```
--- india_budget_2003.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/india/validation/schema_india_budget_2003.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- india_budget_2025.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/india/validation/schema_india_budget_2025.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- india_budget_2026.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/india/validation/schema_india_budget_2026.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- india_mapping_2026.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/india/validation/schema_india_mapping_2026.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- india_strategyclean.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/india/validation/schema_india_strategyclean.xlsx

  RESULT: FAIL - 1 contract violation(s) across 1 file(s).
  The stage output is not accepted; re-run the stage or fix the prompt.

--- india_risk_summary.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/india/validation/schema_india_risk_summary.xlsx

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
--- india references
RESULT: PASS - every one of 2883 reference(s) resolves
report -> Files/outputs/india/validation/refs_india_references.xlsx
```

### combine_budget_years
```
==============================================================================
COMBINED BUDGET LAYER  -  years: 2026  (3 file(s))
==============================================================================

RECONCILIATION (per year: sum of program rows vs strategy_total)

  FY2026   (national total = 802,990.2)
    strat 6: total=     802,990.2  progsum=     802,990.2  OK

RECONCILIATION: PASS - all years reconcile

NATIONAL TOTAL (the denominator every share is computed against)
    FY2026  heads 802,990.2  programmes 802,990.2  gap   0.0%  -> GRAND_TOTAL
    FY2026  extracted 100.0% of the document's own grand total 802,990.2

READABILITY  0 of 13 programme name(s) unreadable (0%), 0 of 1 head(s) (0%), 0% of the money

Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/india/budget_layer_all_years.xlsx
  sheet 'budget_all_years' : 15 rows  (feeds Prompt 6 / build_final_panel - each intervention matches against EVERY year's programs)
  sheet 'programs_wide'    : 13 programs x 1 year(s) (funding-over-time)
  sheet 'reconciliation'   : 1 rows (audit)
  sheet 'data_quality'     : 14 flagged items (see summary below)

==============================================================================
DATA-QUALITY SUMMARY
==============================================================================
  HIGH: 0   MEDIUM: 13   LOW: 0   INFO: 1

  [MEDIUM] malformed_code_repaired  (13)
      - FY2026 strat 6 6.1: program_code '1' looked malformed and was normalized to '6.1' - verify against source; fix the year file to avoid this.
      - FY2026 strat 6 6.2: program_code '2' looked malformed and was normalized to '6.2' - verify against source; fix the year file to avoid this.
      - FY2026 strat 6 6.3: program_code '3' looked malformed and was normalized to '6.3' - verify against source; fix the year file to avoid this.
      ... and 10 more (see 'data_quality' sheet)
==============================================================================
DATA QUALITY: OK with minor flags - review MEDIUM/LOW as needed
==============================================================================
```

### build_final_panel
```
MATCHED NOTHING: 1 mapping workbook(s) were read and not one edge came out of them, against 13 programme line(s) in the budget layer. The panel carries the plan's 359 strategies unfunded and the programme lines unclaimed. Stage 6 ran; check whether the budget documents are the country's expenditure budget before re-running it.

Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/india/FINAL_PANEL.xlsx
  panel               : 359 strategies x 1 years (2026)
  match_review        : 0 matches (BOTH names + rationale)
  unmatched_codes     : 0 (codes NOT in that year's budget - REVIEW)
  unfunded_strategies : 359 (strategies with no budget any year)
  funding_by_program  : 0 (per programme x year, amount once - SAFE TO SUM)
  unmapped_programs   : 13 budget programmes with no matched strategy
  risk_panel          : 10 risks | ceiling: PASS
  enrichment          : strategyclean=yes risk_summary=yes
  maturity            : mean=0.32 | financing-weighted=0.0 | {'planned': 180, 'aspirational': 115, 'planned_specific': 64}
  basket/reverse-pass : 0 shared programmes | reverse-pass edges=none (run Prompt 6b + --coverage)
  recall_review       : 0 large programmes matched to only 1 strategy (candidate baskets)
MATURITY: mean=0.32 financing_weighted=0.0
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
AUDIT CHECKS: india 14/14 PASS
  ok   A1   Stored programme sums              1 strategy-year(s) / 0 disagree
  ok   A2   Stored strategy totals             1 strategy-year(s) / 0 disagree
  --   A3   Programme counted once             sheet absent
  ok   A4   Ceiling holds                      1 strategy-year(s) / 0 over ceiling
  --   A6   Panel money matches its edges      sheets absent
  --   A8   Edges cite real programmes         sheets absent
  ok   A9   No strategy dropped                359 strategyclean row(s) / 359 panel row(s)
  ok   A10  Unfunded list is complete          359 zero-funded / 359 listed
  ok   A11  Evidence chain resolves            2347 distinct id(s) / 0 dangle
  ok   A12  Maturity summary is derivable      8 metric(s) / 0 disagree
  --   A14  No duplicate edges                 sheet absent
  ok   A15  One currency                       1 expected / 1 found
  ok   A16  Components are traceable           3689 component(s) / 0 untraceable
  ok   A17  No workbook open in Excel          0 expected / 0 found
  ok   A18  Strategies come from the plan      360 strategy(ies) / 0 with no component
  ok   A19  Funding priority is reproducible   2 distinct (salience, funding) group(s) / 0 split across priorities
  ok   A20  The budget is readable             13 programme(s) / 0 unreadable (0%), carrying 0% of the money
  --   A21  Ambiguous codes name their head    no budget rows or no accepted edges
  ok   A22  Every intervention is traceable to a strategy 2349 intervention(s) extracted / 2 uncited (0.1%)
            436
            648
  --   A23  The sector layer stayed out of the panel no sector run for this country
```

### data_issues
```
data issues  Files/outputs/DATA_ISSUES.xlsx
  4 detected across 1 country(ies): 0 high, 3 medium, 1 low
  70 hand-written entr(ies) in 04_Docs_and_Planning/data_issues.json
```
