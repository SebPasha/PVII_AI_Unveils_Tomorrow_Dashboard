# Run report - Kiribati

**🔴 Overall: REVIEW NEEDED**  
Generated 2026-08-22 11:55 by run_pipeline.py

| Stage | Ran | Key QA |
|---|---|---|
| validate_stage_schema (L2) | ok | PASS 6/6 |
| validate_source_fidelity (L4) | ok | NOT CONFIGURED |
| validate_recall (L4) | ok | NOT CONFIGURED [advisory] |
| validate_refs (L3) | ok | PASS 1/1 |
| combine_budget_years | ok | reconcile=PASS - all years reconcile | data_quality=CLEAN |
| build_final_panel | FAILED | QA FAIL - ceiling=? | unmatched_codes=? |
| build_analytics_html | FAILED | QA FAIL - SKIPPED |
| audit_checks | FAILED | SKIPPED [advisory] |
| data_issues | FAILED | SKIPPED [advisory] |

## Outputs

- Budget layer: `Files/outputs/kiribati/budget_layer_all_years.xlsx`
- FINAL panel (deliverable): `Files/outputs/kiribati/FINAL_PANEL.xlsx`
- Dashboard: `Files/outputs/kiribati/budget_strategy_analytics.html`
- Audit trail: `Files/outputs/union_dashboard.html`, Audit tab, filtered to this country
- Data oddities: `Files/outputs/DATA_ISSUES.xlsx`

## Full stage logs

### validate_stage_schema (L2)
```
--- kiribati_budget_2023.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/kiribati/validation/schema_kiribati_budget_2023.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- kiribati_budget_2024.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/kiribati/validation/schema_kiribati_budget_2024.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- kiribati_budget_2025.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/kiribati/validation/schema_kiribati_budget_2025.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- kiribati_budget_2026.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/kiribati/validation/schema_kiribati_budget_2026.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- kiribati_strategyclean.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/kiribati/validation/schema_kiribati_strategyclean.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- kiribati_risk_summary.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/kiribati/validation/schema_kiribati_risk_summary.xlsx

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
--- kiribati references
RESULT: PASS - every one of 525 reference(s) resolves
report -> Files/outputs/kiribati/validation/refs_kiribati_references.xlsx
```

### combine_budget_years
```
==============================================================================
COMBINED BUDGET LAYER  -  years:   (4 file(s))
==============================================================================

RECONCILIATION (per year: sum of program rows vs strategy_total)

RECONCILIATION: PASS - all years reconcile

NATIONAL TOTAL (the denominator every share is computed against)

READABILITY  0 of 0 programme name(s) unreadable (0%), 0 of 0 head(s) (0%), 0% of the money

Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/kiribati/budget_layer_all_years.xlsx
  sheet 'budget_all_years' : 0 rows  (feeds Prompt 6 / build_final_panel - each intervention matches against EVERY year's programs)
  sheet 'programs_wide'    : 0 programs x 0 year(s) (funding-over-time)
  sheet 'reconciliation'   : 0 rows (audit)
  sheet 'data_quality'     : 0 flagged items (see summary below)

==============================================================================
DATA-QUALITY SUMMARY
==============================================================================
  HIGH: 0   MEDIUM: 0   LOW: 0   INFO: 0
  No HIGH/MEDIUM/LOW issues - the combined budget layer looks clean.
==============================================================================
DATA QUALITY: CLEAN
==============================================================================
```

### build_final_panel
```
ERROR: no mapping rows. Checked --mapping-dir '/Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/llm/kiribati/mappings' and --mapping None.
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
