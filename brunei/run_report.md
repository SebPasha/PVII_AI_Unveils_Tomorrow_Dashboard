# Run report - Brunei

**🔴 Overall: REVIEW NEEDED**  
Generated 2026-08-17 07:27 by run_pipeline.py

| Stage | Ran | Key QA |
|---|---|---|
| combine_budget_years | ok | reconcile=FAIL - see MISMATCH rows | data_quality=REVIEW NEEDED - resolve HIGH items before relying on totals for those strategy-years |
| build_final_panel | FAILED | QA FAIL - ceiling=? | unmatched_codes=? |
| build_analytics_html | FAILED | QA FAIL - SKIPPED |
| audit_checks | FAILED | SKIPPED [advisory] |
| data_issues | FAILED | SKIPPED [advisory] |

## Outputs

- Budget layer: `Files/outputs/brunei/budget_layer_all_years.xlsx`
- FINAL panel (deliverable): `Files/outputs/brunei/FINAL_PANEL.xlsx`
- Dashboard: `Files/outputs/brunei/budget_strategy_analytics.html`
- Audit trail: `Files/outputs/union_dashboard.html`, Audit tab, filtered to this country
- Data oddities: `Files/outputs/DATA_ISSUES.xlsx`

## Full stage logs

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
Traceback (most recent call last):
  File "/Users/sebastianpasha/Developer/Environment_UNDP/PV2/01_Pipeline/scripts/build_final_panel.py", line 840, in <module>
    sys.exit(main())
             ^^^^^^
  File "/Users/sebastianpasha/Developer/Environment_UNDP/PV2/01_Pipeline/scripts/build_final_panel.py", line 609, in main
    "budget_programme_codes": "; ".join(sorted({c for ys in d["yr_progs"].values() for c in ys})),
                              ^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^
TypeError: sequence item 0: expected str instance, int found
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
