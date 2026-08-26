# Run report - India

**🔴 Overall: REVIEW NEEDED**  
Generated 2026-08-26 08:16 by run_pipeline.py

| Stage | Ran | Key QA |
|---|---|---|
| validate_stage_schema (L2) | ok | QA FAIL - FAIL 1/6 (india_strategyclean.xlsx) |
| validate_source_fidelity (L4) | ok | NOT CONFIGURED |
| validate_recall (L4) | ok | NOT CONFIGURED [advisory] |
| validate_refs (L3) | ok | INPUT MISSING (1/1 not on this machine) |
| combine_budget_years | ok | reconcile=PASS - all years reconcile | data_quality=OK with minor flags - review MEDIUM/LOW as needed |
| build_final_panel | FAILED | QA FAIL - ceiling=? | unmatched_codes=? |
| build_analytics_html | FAILED | QA FAIL - SKIPPED |
| audit_checks | FAILED | SKIPPED [advisory] |
| data_issues | FAILED | SKIPPED [advisory] |

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
SKIPPED: input not on this machine: Files/outputs/india/budget_layer_all_years.xlsx
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
ERROR: no mapping rows. Checked --mapping-dir '/Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/llm/india/mappings' and --mapping None.
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
