# Run report - Thailand

**🟢 Overall: PASS**  
Generated 2026-08-16 13:32 by run_pipeline.py

| Stage | Ran | Key QA |
|---|---|---|
| combine_budget_years | ok | reconcile=PASS - all years reconcile | data_quality=OK with minor flags - review MEDIUM/LOW as needed |
| build_final_panel | ok | ceiling=PASS - no strategy over-counted in any year | unmatched_codes=0 |
| build_analytics_html | ok | strategies=30 (0 unfunded) | edges=145 |
| audit_checks | ok | 15/15 PASS [advisory] |
| data_issues | ok | 4 detected across 1 country(ies): 0 high, 2 medium, 2 low [advisory] |

## Outputs

- Budget layer: `Files/outputs/thailand/budget_layer_all_years.xlsx`
- FINAL panel (deliverable): `Files/outputs/thailand/FINAL_PANEL.xlsx`
- Dashboard: `Files/outputs/thailand/budget_strategy_analytics.html`
- Audit trail: `Files/outputs/union_dashboard.html`, Audit tab, filtered to this country
- Data oddities: `Files/outputs/DATA_ISSUES.xlsx`

## Full stage logs

### combine_budget_years
```
==============================================================================
COMBINED BUDGET LAYER  -  years: 2023, 2024, 2025, 2026  (4 file(s))
==============================================================================

RECONCILIATION (per year: sum of program rows vs strategy_total)

  FY2023   (national total = 3,185,000.0)
    strat 1: total=     296,003.6  progsum=     296,003.6  OK
    strat 2: total=     396,125.5  progsum=     396,125.5  OK
    strat 3: total=     549,514.0  progsum=     549,514.0  OK
    strat 4: total=     759,861.3  progsum=     759,861.3  OK
    strat 5: total=     122,964.9  progsum=     122,964.9  OK
    strat 6: total=     658,012.7  progsum=     658,012.7  OK
    strat 7: total=     402,518.0  progsum=     402,518.0  OK

  FY2024   (national total = 3,480,000.0)
    strat 1: total=     386,149.6  progsum=     386,149.6  OK
    strat 2: total=     392,028.6  progsum=     392,028.6  OK
    strat 3: total=     561,167.1  progsum=     561,167.1  OK
    strat 4: total=     836,382.5  progsum=     836,382.5  OK
    strat 5: total=     131,020.5  progsum=     131,020.5  OK
    strat 6: total=     608,210.5  progsum=     608,210.5  OK
    strat 7: total=     565,041.2  progsum=     565,041.2  OK

  FY2025   (national total = 3,752,700.0)
    strat 1: total=     403,868.0  progsum=     403,868.0  OK
    strat 2: total=     362,199.9  progsum=     362,199.9  OK
    strat 3: total=     582,704.1  progsum=     582,704.1  OK
    strat 4: total=     926,266.8  progsum=     926,266.8  OK
    strat 5: total=     136,851.3  progsum=     136,851.3  OK
    strat 6: total=     645,499.5  progsum=     645,499.5  OK
    strat 7: total=     695,310.4  progsum=     695,310.4  OK

  FY2026   (national total = 3,780,600.0)
    strat 1: total=     413,907.6  progsum=     413,907.6  OK
    strat 2: total=     399,334.9  progsum=     399,334.9  OK
    strat 3: total=     604,805.7  progsum=     604,805.7  OK
    strat 4: total=     941,299.9  progsum=     941,299.9  OK
    strat 5: total=     146,658.0  progsum=     146,658.0  OK
    strat 6: total=     604,228.4  progsum=     604,228.4  OK
    strat 7: total=     670,365.5  progsum=     670,365.5  OK

RECONCILIATION: PASS - all years reconcile

Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/thailand/budget_layer_all_years.xlsx
  sheet 'budget_all_years' : 301 rows  (feeds Prompt 6 / build_final_panel - each intervention matches against EVERY year's programs)
  sheet 'programs_wide'    : 71 programs x 4 year(s) (funding-over-time)
  sheet 'reconciliation'   : 28 rows (audit)
  sheet 'data_quality'     : 24 flagged items (see summary below)

==============================================================================
DATA-QUALITY SUMMARY
==============================================================================
  HIGH: 0   MEDIUM: 6   LOW: 14   INFO: 4

  [MEDIUM] program_missing_in_year  (6)
      - FY2024,2025 strat 1 1.14: program '1.14' (Program on Public Sector Personnel) exists in ['2023', '2026'] but is absent in ['2024', '2025'] - check whether it was dropped during extraction or genuinely did not exist that year.
      - FY2023 strat 2 2.16: program '2.16' (Program on Public Sector Personnel) exists in ['2024', '2025', '2026'] but is absent in ['2023'] - check whether it was dropped during extraction or genuinely did not exist that year.
      - FY2023,2024,2026 strat 2 2.17: program '2.17' (Program on Public Sector Personnel) exists in ['2025'] but is absent in ['2023', '2024', '2026'] - check whether it was dropped during extraction or genuinely did not exist that year.
      ... and 3 more (see 'data_quality' sheet)

  [LOW] large_yoy_swing  (14)
      - FY2023->2024 strat 1 1.12: program '1.12' changed +6462% (536.8 -> 35,226.2) - verify this is real and not an extraction error.
      - FY2023->2024 strat 1 1.13: program '1.13' changed +503% (33,838.4 -> 204,072.1) - verify this is real and not an extraction error.
      - FY2024->2025 strat 2 2.10: program '2.10' changed +966% (446.3 -> 4,758.7) - verify this is real and not an extraction error.
      ... and 11 more (see 'data_quality' sheet)
==============================================================================
DATA QUALITY: OK with minor flags - review MEDIUM/LOW as needed
==============================================================================
```

### build_final_panel
```
Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/thailand/FINAL_PANEL.xlsx
  panel               : 30 strategies x 4 years (2023, 2024, 2025, 2026)
  match_review        : 172 matches (BOTH names + rationale)
  unmatched_codes     : 0 (codes NOT in that year's budget - REVIEW)
  unfunded_strategies : 0 (strategies with no budget any year)
  funding_by_program  : 126 (per programme x year, amount once - SAFE TO SUM)
  unmapped_programs   : 147 budget programmes with no matched strategy
  risk_panel          : 11 risks | ceiling: PASS
  enrichment          : strategyclean=yes risk_summary=yes
  maturity            : mean=0.85 | financing-weighted=0.85 | {'operational_programme': 30}
  basket/reverse-pass : 10 shared programmes | reverse-pass edges=52 rows -> 25 new matches
  recall_review       : 32 large programmes matched to only 1 strategy (candidate baskets)
MATURITY: mean=0.85 financing_weighted=0.85
CEILING TEST: PASS - no strategy over-counted in any year
UNMATCHED CODES: 0
QA: PASS - 0 unmatched code(s), ceiling PASS, 0 year warning(s)
```

### build_analytics_html
```
dashboard -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/thailand/budget_strategy_analytics.html
  years        2023, 2024, 2025, 2026
  edges        145
  strategies   30 (0 unfunded)
  size         86 KB
```

### audit_checks
```
AUDIT CHECKS: thailand 15/15 PASS
  ok   A1   Stored programme sums              28 strategy-year(s) / 0 disagree
  ok   A2   Stored strategy totals             28 strategy-year(s) / 0 disagree
  ok   A3   Programme counted once             126 row(s) / 0 duplicate key(s)
  ok   A4   Ceiling holds                      28 strategy-year(s) / 0 over ceiling
  ok   A6   Panel money matches its edges      120 strategy-year figure(s) / 0 disagree
  ok   A8   Edges cite real programmes         172 accepted edge(s) / 0 dangle
  ok   A9   No strategy dropped                30 strategyclean row(s) / 30 panel row(s)
  ok   A10  Unfunded list is complete          0 zero-funded / 0 listed
  ok   A11  Evidence chain resolves            528 distinct id(s) / 0 dangle
  ok   A12  Maturity summary is derivable      8 metric(s) / 0 disagree
  ok   A14  No duplicate edges                 145 edge(s) / 0 duplicate(s)
  ok   A15  One currency                       1 expected / 1 found
  ok   A16  Components are traceable           882 component(s) / 0 untraceable
  ok   A17  No workbook open in Excel          0 expected / 0 found
  ok   A18  Strategies come from the plan      30 strategy(ies) / 0 with no component
```

### data_issues
```
data issues  Files/outputs/DATA_ISSUES.xlsx
  4 detected across 1 country(ies): 0 high, 2 medium, 2 low
  16 hand-written entr(ies) in 04_Docs_and_Planning/data_issues.json
```
