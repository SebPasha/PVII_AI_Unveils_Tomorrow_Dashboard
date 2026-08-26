# Run report - Cambodia

**🔴 Overall: REVIEW NEEDED**  
Generated 2026-08-26 16:01 by run_pipeline.py

| Stage | Ran | Key QA |
|---|---|---|
| validate_stage_schema (L2) | ok | PASS 2/2 |
| validate_source_fidelity (L4) | ok | NOT CONFIGURED [advisory] |
| validate_recall (L4) | ok | NOT CONFIGURED [advisory] |
| validate_refs (L3) | ok | INPUT MISSING (1/1 not on this machine) |
| combine_budget_years | ok | reconcile=? | data_quality=? |
| build_final_panel | ok | ceiling=PASS - no strategy over-counted in any year | unmatched_codes=0 |
| build_analytics_html | ok | dashboard built, no summary printed |
| audit_checks | FAILED | QA FAIL - 8/9 PASS (A11 8 dangle) [advisory] |
| data_issues | ok | 2 detected across 1 country(ies): 0 high, 2 medium, 0 low [advisory] |

## Outputs

- Budget layer: `Files/outputs/cambodia/budget_layer_all_years.xlsx`
- FINAL panel (deliverable): `Files/outputs/cambodia/FINAL_PANEL.xlsx`
- Dashboard: `Files/outputs/cambodia/budget_strategy_analytics.html`
- Audit trail: `Files/outputs/union_dashboard.html`, Audit tab, filtered to this country
- Data oddities: `Files/outputs/DATA_ISSUES.xlsx`

## Full stage logs

### validate_stage_schema (L2)
```
--- cambodia_strategyclean.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/cambodia/validation/schema_cambodia_strategyclean.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- cambodia_risk_summary.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/cambodia/validation/schema_cambodia_risk_summary.xlsx

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
--- cambodia references
SKIPPED: input not on this machine: Files/outputs/cambodia/budget_layer_all_years.xlsx
```

### combine_budget_years
```
SKIPPED: this country holds no budget document, so there is no budget layer to build.
```

### build_final_panel
```
PLAN ONLY: the budget layer carries 0 strategy total(s) and no programme line, so the mapping stage had nothing to match. The panel carries the plan's 176 strategies with no money against them, which is what the documents held for this country support.

Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/cambodia/FINAL_PANEL.xlsx
  panel               : 176 strategies x 0 years ()
  match_review        : 0 matches (BOTH names + rationale)
  unmatched_codes     : 0 (codes NOT in that year's budget - REVIEW)
  unfunded_strategies : 176 (strategies with no budget any year)
  funding_by_program  : 0 (per programme x year, amount once - SAFE TO SUM)
  unmapped_programs   : 0 budget programmes with no matched strategy
  risk_panel          : 11 risks | ceiling: PASS
  enrichment          : strategyclean=yes risk_summary=yes
  maturity            : mean=0.286 | financing-weighted=0.0 | {'aspirational': 78, 'planned': 93, 'planned_specific': 5}
  basket/reverse-pass : 0 shared programmes | reverse-pass edges=none (run Prompt 6b + --coverage)
  recall_review       : 0 large programmes matched to only 1 strategy (candidate baskets)
MATURITY: mean=0.286 financing_weighted=0.0
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
AUDIT CHECKS: cambodia 8/9 PASS (A11 8 dangle)
  --   A1   Stored programme sums              budget layer not available
  --   A2   Stored strategy totals             budget layer not available
  --   A3   Programme counted once             sheet absent
  --   A4   Ceiling holds                      sheet absent
  --   A6   Panel money matches its edges      sheets absent
  --   A8   Edges cite real programmes         sheets absent
  ok   A9   No strategy dropped                176 strategyclean row(s) / 176 panel row(s)
  ok   A10  Unfunded list is complete          176 zero-funded / 176 listed
  FAIL A11  Evidence chain resolves            1040 distinct id(s) / 8 dangle
            chunk id 0 has no stage-3 row
            chunk id 1 has no stage-3 row
            chunk id 2 has no stage-3 row
            chunk id 3 has no stage-3 row
            chunk id 4 has no stage-3 row
            chunk id 7 has no stage-3 row
  ok   A12  Maturity summary is derivable      8 metric(s) / 0 disagree
  --   A14  No duplicate edges                 sheet absent
  ok   A15  One currency                       1 expected / 0 found
  ok   A16  Components are traceable           1419 component(s) / 0 untraceable
  ok   A17  No workbook open in Excel          0 expected / 0 found
  ok   A18  Strategies come from the plan      176 strategy(ies) / 0 with no component
  --   A19  Funding priority is reproducible   no panel rows or no budget columns
  --   A20  The budget is readable             no programme rows
  --   A21  Ambiguous codes name their head    no budget rows or no accepted edges
  ok   A22  Every intervention is traceable to a strategy 1033 intervention(s) extracted / 1 uncited (0.1%)
            1103
  --   A23  The sector layer stayed out of the panel no sector run for this country
```

### data_issues
```
data issues  Files/outputs/DATA_ISSUES.xlsx
  2 detected across 1 country(ies): 0 high, 2 medium, 0 low
  70 hand-written entr(ies) in 04_Docs_and_Planning/data_issues.json
```
