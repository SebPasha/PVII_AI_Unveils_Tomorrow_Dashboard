# Run report - Papua New Guinea

**🔴 Overall: REVIEW NEEDED**  
Generated 2026-08-26 14:26 by run_pipeline.py

| Stage | Ran | Key QA |
|---|---|---|
| validate_stage_schema (L2) | ok | QA FAIL - FAIL 2/8 (papua_new_guinea_mapping_2019.xlsx, papua_new_guinea_strategyclean.xlsx) |
| validate_source_fidelity (L4) | ok | NOT CONFIGURED |
| validate_recall (L4) | ok | NOT CONFIGURED [advisory] |
| validate_refs (L3) | ok | INPUT MISSING (1/1 not on this machine) |
| combine_budget_years | ok | reconcile=FAIL - see MISMATCH rows | data_quality=REVIEW NEEDED - resolve HIGH items before relying on totals for those strategy-years |
| build_final_panel | ok | QA FAIL - ceiling=FAIL - see ceiling sheet | unmatched_codes=155 |
| build_analytics_html | ok | strategies=89 (23 unfunded) | edges=94 |
| audit_checks | FAILED | QA FAIL - 18/19 PASS (A4 1 over ceiling) [advisory] |
| data_issues | FAILED | 6 detected across 1 country(ies): 2 high, 3 medium, 1 low [advisory] |

## Outputs

- Budget layer: `Files/outputs/papua_new_guinea/budget_layer_all_years.xlsx`
- FINAL panel (deliverable): `Files/outputs/papua_new_guinea/FINAL_PANEL.xlsx`
- Dashboard: `Files/outputs/papua_new_guinea/budget_strategy_analytics.html`
- Audit trail: `Files/outputs/union_dashboard.html`, Audit tab, filtered to this country
- Data oddities: `Files/outputs/DATA_ISSUES.xlsx`

## Full stage logs

### validate_stage_schema (L2)
```
--- papua_new_guinea_budget_2014.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/papua_new_guinea/validation/schema_papua_new_guinea_budget_2014.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- papua_new_guinea_budget_2019.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/papua_new_guinea/validation/schema_papua_new_guinea_budget_2019.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- papua_new_guinea_budget_2024.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/papua_new_guinea/validation/schema_papua_new_guinea_budget_2024.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- papua_new_guinea_mapping_2014.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/papua_new_guinea/validation/schema_papua_new_guinea_mapping_2014.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- papua_new_guinea_mapping_2019.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/papua_new_guinea/validation/schema_papua_new_guinea_mapping_2019.xlsx

  RESULT: FAIL - 1 contract violation(s) across 1 file(s).
  The stage output is not accepted; re-run the stage or fix the prompt.

--- papua_new_guinea_mapping_2024.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/papua_new_guinea/validation/schema_papua_new_guinea_mapping_2024.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- papua_new_guinea_strategyclean.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/papua_new_guinea/validation/schema_papua_new_guinea_strategyclean.xlsx

  RESULT: FAIL - 1 contract violation(s) across 1 file(s).
  The stage output is not accepted; re-run the stage or fix the prompt.

--- papua_new_guinea_risk_summary.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/papua_new_guinea/validation/schema_papua_new_guinea_risk_summary.xlsx

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
--- papua_new_guinea references
SKIPPED: input not on this machine: Files/outputs/papua_new_guinea/budget_layer_all_years.xlsx
```

### combine_budget_years
```
==============================================================================
COMBINED BUDGET LAYER  -  years: 2014, 2019, 2024  (3 file(s))
==============================================================================

RECONCILIATION (per year: sum of program rows vs strategy_total)

  FY2014   (national total = 15,294.5)
    strat 1: total=      15,294.5  progsum=        -252.9  ** MISMATCH diff=15,547.4

  FY2019   (national total = 16,133.5)
    strat 1: total=       4,065.0  progsum=       4,065.0  OK
    strat 2: total=         142.3  progsum=         142.3  OK
    strat 3: total=       1,979.1  progsum=       1,979.1  OK
    strat 4: total=         742.1  progsum=         742.1  OK
    strat 5: total=       1,378.2  progsum=       1,378.2  OK
    strat 6: total=       1,553.1  progsum=       1,553.1  OK
    strat 7: total=       1,298.1  progsum=       1,298.1  OK
    strat 8: total=       3,073.0  progsum=       3,073.0  OK
    strat 9: total=       1,287.4  progsum=       1,287.4  OK
    strat 10: total=         615.2  progsum=         615.2  OK

  FY2024   (national total = 27,377.6)
    strat 1: total=       5,012.4  progsum=      11,326.7  ** MISMATCH diff=-6,314.3
    strat 2: total=         214.0  progsum=       5,039.6  ** MISMATCH diff=-4,825.6
    strat 3: total=       1,608.3  progsum=         415.1  ** MISMATCH diff=1,193.2
    strat 4: total=       4,081.6  progsum=       4,126.5  ** MISMATCH diff=-44.9
    strat 5: total=       2,588.5  progsum=       3,050.8  ** MISMATCH diff=-462.3
    strat 6: total=       2,164.3  progsum=       2,205.0  ** MISMATCH diff=-40.7
    strat 7: total=       1,361.4  progsum=       1,213.8  ** MISMATCH diff=147.6
    strat 8: total=       4,081.8  progsum=           0.0  ** MISMATCH diff=4,081.8
    strat 9: total=       2,013.5  progsum=           0.0  ** MISMATCH diff=2,013.5
    strat 10: total=       1,201.0  progsum=           0.0  ** MISMATCH diff=1,201.0
    strat 11: total=       3,050.8  progsum=           0.0  ** MISMATCH diff=3,050.8

RECONCILIATION: FAIL - see MISMATCH rows

NATIONAL TOTAL (the denominator every share is computed against)
    FY2014  heads 15,294.5  programmes -252.9  gap 101.7%  -> GRAND_TOTAL
    FY2019  heads 16,133.5  programmes 16,133.5  gap   0.0%  -> GRAND_TOTAL
    FY2024  heads 27,377.6  programmes 27,377.5  gap   0.0%  -> GRAND_TOTAL
    FY2014  extracted 100.0% of the document's own grand total 15,294.5
    FY2019  extracted 100.0% of the document's own grand total 16,133.5
    FY2024  extracted 100.0% of the document's own grand total 27,377.5

READABILITY  0 of 48 programme name(s) unreadable (0%), 0 of 22 head(s) (0%), 0% of the money

HEAD NAMES: 33 row(s) renamed so a head reads the same in every year

Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/papua_new_guinea/budget_layer_all_years.xlsx
  sheet 'budget_all_years' : 73 rows  (feeds Prompt 6 / build_final_panel - each intervention matches against EVERY year's programs)
  sheet 'programs_wide'    : 32 programs x 3 year(s) (funding-over-time)
  sheet 'reconciliation'   : 22 rows (audit)
  sheet 'data_quality'     : 58 flagged items (see summary below)

==============================================================================
DATA-QUALITY SUMMARY
==============================================================================
  HIGH: 16   MEDIUM: 33   LOW: 6   INFO: 3

  [HIGH] granularity_mismatch  (1)
      - the years were not extracted to the same depth: FY2024 has 26 programme rows and FY2014 has 2, a factor of 13.0. Each year's totals may still be right, but a programme cannot be followed across years and any funding-over-time figure is comparing different levels of the same budget.

  [HIGH] mixed_budget_views  (1)
      - FY2014: rows came from 6 different tables and together made 22,749.6 against a printed grand total of 15,294.5, so the same money was present twice. Kept 'Table 9a TOTAL EXPENDITURE AND NET LENDING (Kina million)' (15,294.5, the closest to the grand total) and dropped 193 row(s) from the others.

  [HIGH] negative_amount  (2)
      - FY2014 strat 1 1.1: amount is negative (-100.0).
      - FY2014 strat 1 1.2: amount is negative (-152.9).

  [HIGH] reconciliation_mismatch  (12)
      - FY2014 strat 1: programs sum to -252.9 but strategy_total is 15,294.5 (gap 15,547.4) - a program line is likely missing or mis-extracted for this strategy-year.
      - FY2024 strat 1: programs sum to 11,326.7 but strategy_total is 5,012.4 (gap -6,314.3) - a program line is likely missing or mis-extracted for this strategy-year.
      - FY2024 strat 2: programs sum to 5,039.6 but strategy_total is 214.0 (gap -4,825.6) - a program line is likely missing or mis-extracted for this strategy-year.
      ... and 9 more (see 'data_quality' sheet)

  [MEDIUM] malformed_code_repaired  (2)
      - FY2014 strat 1 1.1: program_code '1' looked malformed and was normalized to '1.1' - verify against source; fix the year file to avoid this.
      - FY2014 strat 1 1.2: program_code '2' looked malformed and was normalized to '1.2' - verify against source; fix the year file to avoid this.

  [MEDIUM] program_missing_in_year  (30)
      - FY2014,2019 strat 1 1.3: program '1.3' (Grants) exists in ['2024'] but is absent in ['2014', '2019'] - check whether it was dropped during extraction or genuinely did not exist that year.
      - FY2014,2019 strat 1 1.4: program '1.4' (Other expenses) exists in ['2024'] but is absent in ['2014', '2019'] - check whether it was dropped during extraction or genuinely did not exist that year.
      - FY2014,2019 strat 1 1.5: program '1.5' (Net Aquisition Nonfinancial assets) exists in ['2024'] but is absent in ['2014', '2019'] - check whether it was dropped during extraction or genuinely did not exist that year.
      ... and 27 more (see 'data_quality' sheet)

  [MEDIUM] zero_amount_programme  (1)
      - FY2019 strat 3 3.2: programme carries no money; a strategy matched only to lines like this reads as funded while receiving nothing

  [LOW] large_yoy_swing  (6)
      - FY2019->2024 strat 2 2.1: program '2.1' changed +4877% (43.1 -> 2,145.0) - verify this is real and not an extraction error.
      - FY2019->2024 strat 2 2.2: program '2.2' changed +390% (99.2 -> 486.4) - verify this is real and not an extraction error.
      - FY2019->2024 strat 4 4.1: program '4.1' changed +837% (202.7 -> 1,898.7) - verify this is real and not an extraction error.
      ... and 3 more (see 'data_quality' sheet)
==============================================================================
DATA QUALITY: REVIEW NEEDED - resolve HIGH items before relying on totals for those strategy-years
==============================================================================
```

### build_final_panel
```
Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/papua_new_guinea/FINAL_PANEL.xlsx
  panel               : 89 strategies x 3 years (2014, 2019, 2024)
  match_review        : 249 matches (BOTH names + rationale)
  unmatched_codes     : 155 (codes NOT in that year's budget - REVIEW)  <-- !!
  unfunded_strategies : 23 (strategies with no budget any year)
  funding_by_program  : 21 (per programme x year, amount once - SAFE TO SUM)
  unmapped_programs   : 27 budget programmes with no matched strategy
  risk_panel          : 8 risks | ceiling: FAIL - see 'ceiling' sheet
  enrichment          : strategyclean=yes risk_summary=yes
  maturity            : mean=0.637 | financing-weighted=0.774 | {'operational_programme': 14, 'partial_operation': 52, 'planned_specific': 6, 'planned': 15, 'aspirational': 2}
  basket/reverse-pass : 13 shared programmes | reverse-pass edges=none (run Prompt 6b + --coverage)
  recall_review       : 3 large programmes matched to only 1 strategy (candidate baskets)
MATURITY: mean=0.637 financing_weighted=0.774
CEILING TEST: FAIL - see ceiling sheet
UNMATCHED CODES: 155
QA: FAIL - 155 unmatched code(s), ceiling FAIL, 0 year warning(s)
```

### build_analytics_html
```
dashboard -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/papua_new_guinea/budget_strategy_analytics.html
  years        2019, 2024
  edges        94
  strategies   89 (23 unfunded)
  size         51 KB
```

### audit_checks
```
AUDIT CHECKS: papua_new_guinea 18/19 PASS (A4 1 over ceiling)
  ok   A1   Stored programme sums              22 strategy-year(s) / 0 disagree
  ok   A2   Stored strategy totals             22 strategy-year(s) / 0 disagree
  ok   A3   Programme counted once             21 row(s) / 0 duplicate key(s)
  FAIL A4   Ceiling holds                      22 strategy-year(s) / 1 over ceiling
            FY2024 strategy 4: matched 4,119.0 of 4,081.6
  ok   A6   Panel money matches its edges      267 strategy-year figure(s) / 0 disagree
  ok   A8   Edges cite real programmes         249 accepted edge(s) / 0 dangle
  ok   A9   No strategy dropped                89 strategyclean row(s) / 89 panel row(s)
  ok   A10  Unfunded list is complete          23 zero-funded / 23 listed
  ok   A11  Evidence chain resolves            855 distinct id(s) / 0 dangle
  ok   A12  Maturity summary is derivable      8 metric(s) / 0 disagree
  ok   A14  No duplicate edges                 94 edge(s) / 0 duplicate(s)
  ok   A15  One currency                       1 expected / 1 found
  ok   A16  Components are traceable           613 component(s) / 0 untraceable
  ok   A17  No workbook open in Excel          0 expected / 0 found
  ok   A18  Strategies come from the plan      89 strategy(ies) / 0 with no component
  ok   A19  Funding priority is reproducible   35 distinct (salience, funding) group(s) / 0 split across priorities
  ok   A20  The budget is readable             48 programme(s) / 0 unreadable (0%), carrying 0% of the money
  ok   A21  Ambiguous codes name their head    0 repeated code(s) / 0 edge(s) do not name a head
  ok   A22  Every intervention is traceable to a strategy 867 intervention(s) extracted / 12 uncited (1.4%)
            207
            210
            272
            314
            421
            422
  --   A23  The sector layer stayed out of the panel no sector run for this country
```

### data_issues
```
data issues  Files/outputs/DATA_ISSUES.xlsx
  6 detected across 1 country(ies): 2 high, 3 medium, 1 low
  70 hand-written entr(ies) in 04_Docs_and_Planning/data_issues.json
  HIGH  papua_new_guinea D7       Flag raised while combining the budget years
  HIGH  papua_new_guinea D8       A strategy total its own programmes do not add up to
```
