# Run report - Rwanda

**🔴 Overall: REVIEW NEEDED**  
Generated 2026-08-26 09:51 by run_pipeline.py

| Stage | Ran | Key QA |
|---|---|---|
| validate_stage_schema (L2) | ok | PASS 8/8 |
| validate_source_fidelity (L4) | ok | NOT CONFIGURED [advisory] |
| validate_recall (L4) | ok | NOT CONFIGURED [advisory] |
| validate_refs (L3) | ok | INPUT MISSING (1/1 not on this machine) |
| combine_budget_years | ok | reconcile=FAIL - see MISMATCH rows | data_quality=REVIEW NEEDED - resolve HIGH items before relying on totals for those strategy-years |
| build_final_panel | ok | ceiling=PASS - no strategy over-counted in any year | unmatched_codes=0 |
| build_analytics_html | ok | strategies=106 (0 unfunded) | edges=382 |
| audit_checks | ok | 19/19 PASS [advisory] |
| data_issues | FAILED | 4 detected across 1 country(ies): 2 high, 1 medium, 1 low [advisory] |

## Outputs

- Budget layer: `Files/outputs/rwanda/budget_layer_all_years.xlsx`
- FINAL panel (deliverable): `Files/outputs/rwanda/FINAL_PANEL.xlsx`
- Dashboard: `Files/outputs/rwanda/budget_strategy_analytics.html`
- Audit trail: `Files/outputs/union_dashboard.html`, Audit tab, filtered to this country
- Data oddities: `Files/outputs/DATA_ISSUES.xlsx`

## Full stage logs

### validate_stage_schema (L2)
```
--- rwanda_budget_2017.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/rwanda/validation/schema_rwanda_budget_2017.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- rwanda_budget_2020.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/rwanda/validation/schema_rwanda_budget_2020.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- rwanda_budget_2025.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/rwanda/validation/schema_rwanda_budget_2025.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- rwanda_mapping_2017.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/rwanda/validation/schema_rwanda_mapping_2017.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- rwanda_mapping_2020.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/rwanda/validation/schema_rwanda_mapping_2020.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- rwanda_mapping_2025.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/rwanda/validation/schema_rwanda_mapping_2025.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- rwanda_strategyclean.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/rwanda/validation/schema_rwanda_strategyclean.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- rwanda_risk_summary.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/rwanda/validation/schema_rwanda_risk_summary.xlsx

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
--- rwanda references
SKIPPED: input not on this machine: Files/outputs/rwanda/budget_layer_all_years.xlsx
```

### combine_budget_years
```
==============================================================================
COMBINED BUDGET LAYER  -  years: 2017, 2020, 2025  (3 file(s))
==============================================================================

SCALE: converted 37 row(s) into 'RWF million' using the unit each file declared
    FY2017  37 row(s) stated in billion, multiplied by 1000

RECONCILIATION (per year: sum of program rows vs strategy_total)

  FY2017   (national total = 1,949,381,651,743,000.0)
    strat 1: total=517,563,532,040,000.0  progsum=517,563,532,040,000.0  OK
    strat 2: total=262,134,568,724,000.0  progsum=262,150,844,724,000.0  ** MISMATCH diff=-16,276,000,000.0
    strat 3: total=107,893,010,186,000.0  progsum=107,893,010,186,000.0  OK
    strat 4: total=190,255,872,771,000.0  progsum=190,255,872,771,000.0  OK
    strat 5: total=871,534,668,022,000.0  progsum=871,534,668,022,000.0  OK

  FY2020   (national total = 2,876,916,340,789.0)
    strat 01: total=1,637,340,557,226.0  progsum=1,637,039,671,826.0  ** MISMATCH diff=300,885,400.0
    strat 02: total=781,798,407,013.0  progsum=781,798,407,013.0  OK
    strat 03: total=457,777,376,550.0  progsum=457,777,376,550.0  OK

  FY2025   (national total = 5,690,144,278,196.0)
    strat 01: total=3,399,415,790,257.0  progsum=3,399,415,790,258.0  ** MISMATCH diff=-1.0
    strat 02: total=1,509,822,372,705.0  progsum=1,509,822,372,705.0  OK
    strat 03: total=780,906,115,234.0  progsum=780,906,115,234.0  OK

RECONCILIATION: FAIL - see MISMATCH rows

NATIONAL TOTAL (the denominator every share is computed against)
    FY2017  heads 1,949,381,651,743,000.0  programmes 1,949,397,927,743,000.0  gap   0.0%  -> GRAND_TOTAL
    FY2020  heads 2,876,916,340,789.0  programmes 2,876,615,455,389.0  gap   0.0%  -> GRAND_TOTAL
    FY2025  heads 5,690,144,278,196.0  programmes 5,690,144,278,197.0  gap   0.0%  -> GRAND_TOTAL
    FY2017  extracted 100.0% of the document's own grand total 1,949,381,651,743,000.0
    FY2020  extracted 100.0% of the document's own grand total 2,876,916,340,789.0
    FY2025  extracted 100.0% of the document's own grand total 5,690,144,278,196.0

READABILITY  0 of 74 programme name(s) unreadable (0%), 0 of 11 head(s) (0%), 0% of the money

Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/rwanda/budget_layer_all_years.xlsx
  sheet 'budget_all_years' : 88 rows  (feeds Prompt 6 / build_final_panel - each intervention matches against EVERY year's programs)
  sheet 'programs_wide'    : 55 programs x 3 year(s) (funding-over-time)
  sheet 'reconciliation'   : 11 rows (audit)
  sheet 'data_quality'     : 106 flagged items (see summary below)

==============================================================================
DATA-QUALITY SUMMARY
==============================================================================
  HIGH: 4   MEDIUM: 98   LOW: 1   INFO: 3

  [HIGH] reconciliation_mismatch  (3)
      - FY2017 strat 2: programs sum to 262,150,844,724,000.0 but strategy_total is 262,134,568,724,000.0 (gap -16,276,000,000.0) - a program line is likely missing or mis-extracted for this strategy-year.
      - FY2020 strat 01: programs sum to 1,637,039,671,826.0 but strategy_total is 1,637,340,557,226.0 (gap 300,885,400.0) - a program line is likely missing or mis-extracted for this strategy-year.
      - FY2025 strat 01: programs sum to 3,399,415,790,258.0 but strategy_total is 3,399,415,790,257.0 (gap -1.0) - a program line is likely missing or mis-extracted for this strategy-year.

  [HIGH] scale_mismatch  (1)
      - the years are not in the same scale: FY2017 states 1,949,381,651,743,000.0 and FY2020 states 2,876,916,340,789.0, a factor of 678, and both are labelled 'RWF million'. A national budget does not change by that much between years, so one extraction is in absolute currency and the other in millions. Every cross-year figure is wrong until they agree.

  [MEDIUM] malformed_code_repaired  (43)
      - FY2020 strat 01 01.01: program_code '01' looked malformed and was normalized to '01.01' - verify against source; fix the year file to avoid this.
      - FY2020 strat 01 01.02: program_code '02' looked malformed and was normalized to '01.02' - verify against source; fix the year file to avoid this.
      - FY2020 strat 01 01.03: program_code '03' looked malformed and was normalized to '01.03' - verify against source; fix the year file to avoid this.
      ... and 40 more (see 'data_quality' sheet)

  [MEDIUM] program_missing_in_year  (55)
      - FY2017 strat 01 01.01: program '01.01' (Agriculture) exists in ['2020', '2025'] but is absent in ['2017'] - check whether it was dropped during extraction or genuinely did not exist that year.
      - FY2017 strat 01 01.02: program '01.02' (Private sector Development & Youth Employment) exists in ['2020', '2025'] but is absent in ['2017'] - check whether it was dropped during extraction or genuinely did not exist that year.
      - FY2017 strat 01 01.03: program '01.03' (Transport) exists in ['2020', '2025'] but is absent in ['2017'] - check whether it was dropped during extraction or genuinely did not exist that year.
      ... and 52 more (see 'data_quality' sheet)

  [LOW] large_yoy_swing  (1)
      - FY2020->2025 strat 02 02.14: program '02.14' changed +11201% (621,941,520.0 -> 70,286,830,287.0) - verify this is real and not an extraction error.
==============================================================================
DATA QUALITY: REVIEW NEEDED - resolve HIGH items before relying on totals for those strategy-years
==============================================================================
```

### build_final_panel
```
Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/rwanda/FINAL_PANEL.xlsx
  panel               : 106 strategies x 3 years (2017, 2020, 2025)
  match_review        : 382 matches (BOTH names + rationale)
  unmatched_codes     : 0 (codes NOT in that year's budget - REVIEW)
  unfunded_strategies : 0 (strategies with no budget any year)
  funding_by_program  : 68 (per programme x year, amount once - SAFE TO SUM)
  unmapped_programs   : 6 budget programmes with no matched strategy
  risk_panel          : 10 risks | ceiling: PASS
  enrichment          : strategyclean=yes risk_summary=yes
  maturity            : mean=0.854 | financing-weighted=0.855 | {'operational_programme': 103, 'operational_funded': 3}
  basket/reverse-pass : 61 shared programmes | reverse-pass edges=none (run Prompt 6b + --coverage)
  recall_review       : 0 large programmes matched to only 1 strategy (candidate baskets)
MATURITY: mean=0.854 financing_weighted=0.855
CEILING TEST: PASS - no strategy over-counted in any year
UNMATCHED CODES: 0
QA: PASS - 0 unmatched code(s), ceiling PASS, 0 year warning(s)
```

### build_analytics_html
```
dashboard -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/rwanda/budget_strategy_analytics.html
  years        2017, 2020, 2025
  edges        382
  strategies   106 (0 unfunded)
  size         125 KB
```

### audit_checks
```
AUDIT CHECKS: rwanda 19/19 PASS
  ok   A1   Stored programme sums              11 strategy-year(s) / 0 disagree
  ok   A2   Stored strategy totals             11 strategy-year(s) / 0 disagree
  ok   A3   Programme counted once             68 row(s) / 0 duplicate key(s)
  ok   A4   Ceiling holds                      11 strategy-year(s) / 0 over ceiling
  ok   A6   Panel money matches its edges      318 strategy-year figure(s) / 0 disagree
  ok   A8   Edges cite real programmes         382 accepted edge(s) / 0 dangle
  ok   A9   No strategy dropped                106 strategyclean row(s) / 106 panel row(s)
  ok   A10  Unfunded list is complete          0 zero-funded / 0 listed
  ok   A11  Evidence chain resolves            617 distinct id(s) / 0 dangle
  ok   A12  Maturity summary is derivable      8 metric(s) / 0 disagree
  ok   A14  No duplicate edges                 382 edge(s) / 0 duplicate(s)
  ok   A15  One currency                       1 expected / 1 found
  ok   A16  Components are traceable           1052 component(s) / 0 untraceable
  ok   A17  No workbook open in Excel          0 expected / 0 found
  ok   A18  Strategies come from the plan      106 strategy(ies) / 0 with no component
  ok   A19  Funding priority is reproducible   66 distinct (salience, funding) group(s) / 0 split across priorities
  ok   A20  The budget is readable             74 programme(s) / 0 unreadable (0%), carrying 0% of the money
  ok   A21  Ambiguous codes name their head    0 repeated code(s) / 0 edge(s) do not name a head
  ok   A22  Every intervention is traceable to a strategy 617 intervention(s) extracted / 0 uncited (0.0%)
  --   A23  The sector layer stayed out of the panel no sector run for this country
```

### data_issues
```
data issues  Files/outputs/DATA_ISSUES.xlsx
  4 detected across 1 country(ies): 2 high, 1 medium, 1 low
  70 hand-written entr(ies) in 04_Docs_and_Planning/data_issues.json
  HIGH  rwanda    D7       Flag raised while combining the budget years
  HIGH  rwanda    D8       A strategy total its own programmes do not add up to
```
