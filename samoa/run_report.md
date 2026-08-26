# Run report - Samoa

**🔴 Overall: REVIEW NEEDED**  
Generated 2026-08-26 01:44 by run_pipeline.py

| Stage | Ran | Key QA |
|---|---|---|
| validate_stage_schema (L2) | ok | PASS 8/8 |
| validate_source_fidelity (L4) | ok | NOT CONFIGURED |
| validate_recall (L4) | ok | NOT CONFIGURED [advisory] |
| validate_refs (L3) | ok | INPUT MISSING (1/1 not on this machine) |
| combine_budget_years | ok | reconcile=FAIL - see MISMATCH rows | data_quality=REVIEW NEEDED - resolve HIGH items before relying on totals for those strategy-years |
| build_final_panel | ok | ceiling=PASS - no strategy over-counted in any year | unmatched_codes=0 |
| build_analytics_html | ok | strategies=28 (9 unfunded) | edges=29 |
| audit_checks | ok | 19/19 PASS [advisory] |
| data_issues | FAILED | 5 detected across 1 country(ies): 2 high, 2 medium, 1 low [advisory] |

## Outputs

- Budget layer: `Files/outputs/samoa/budget_layer_all_years.xlsx`
- FINAL panel (deliverable): `Files/outputs/samoa/FINAL_PANEL.xlsx`
- Dashboard: `Files/outputs/samoa/budget_strategy_analytics.html`
- Audit trail: `Files/outputs/union_dashboard.html`, Audit tab, filtered to this country
- Data oddities: `Files/outputs/DATA_ISSUES.xlsx`

## Full stage logs

### validate_stage_schema (L2)
```
--- samoa_budget_2023.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/samoa/validation/schema_samoa_budget_2023.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- samoa_budget_2024.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/samoa/validation/schema_samoa_budget_2024.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- samoa_budget_2025.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/samoa/validation/schema_samoa_budget_2025.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- samoa_mapping_2023.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/samoa/validation/schema_samoa_mapping_2023.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- samoa_mapping_2024.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/samoa/validation/schema_samoa_mapping_2024.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- samoa_mapping_2025.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/samoa/validation/schema_samoa_mapping_2025.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- samoa_strategyclean.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/samoa/validation/schema_samoa_strategyclean.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- samoa_risk_summary.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/samoa/validation/schema_samoa_risk_summary.xlsx

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
--- samoa references
SKIPPED: input not on this machine: Files/outputs/samoa/budget_layer_all_years.xlsx
```

### combine_budget_years
```
==============================================================================
COMBINED BUDGET LAYER  -  years: 2023, 2024, 2025  (3 file(s))
==============================================================================

RECONCILIATION (per year: sum of program rows vs strategy_total)

  FY2023   (national total = 737,429,983.0)
    strat 1: total=  19,967,480.0  progsum=  14,812,127.0  ** MISMATCH diff=5,155,353.0
    strat 2: total=   5,815,359.0  progsum=     445,584.0  ** MISMATCH diff=5,369,775.0
    strat 3: total=  18,926,871.0  progsum=  10,676,520.0  ** MISMATCH diff=8,250,351.0
    strat 4: total=   7,171,354.0  progsum=   7,171,354.0  OK
    strat 5: total=  11,596,849.0  progsum=  11,596,849.0  OK
    strat 6: total=   3,782,221.0  progsum=   3,782,220.0  ** MISMATCH diff=1.0
    strat 7: total=         139.0  progsum=  57,621,234.0  ** MISMATCH diff=-57,621,095.0
    strat 8: total=   6,913,566.0  progsum=   6,913,566.0  OK
    strat 9: total=   3,612,717.0  progsum=     721,486.0  ** MISMATCH diff=2,891,231.0
    strat 10: total=  30,856,805.0  progsum=  30,856,805.0  OK
    strat 11: total= 114,471,307.0  progsum= 114,471,307.0  OK
    strat 12: total=  27,205,453.0  progsum=  27,205,453.0  OK
    strat 13: total= 146,544,809.0  progsum= 146,544,809.0  OK
    strat 14: total=  10,875,819.0  progsum=  10,875,855.0  ** MISMATCH diff=-36.0
    strat 15: total=  15,572,666.0  progsum=  15,572,666.0  OK
    strat 16: total=  29,374,460.0  progsum=  29,374,460.0  OK
    strat 17: total=  55,701,690.0  progsum=  55,701,691.0  ** MISMATCH diff=-1.0
    strat 18: total=  13,920,455.0  progsum=  13,920,456.0  ** MISMATCH diff=-1.0
    strat 19: total=   9,583,853.0  progsum=   9,583,853.0  OK
    strat 20: total=  13,441,055.0  progsum=  13,441,055.0  OK
    strat 21: total=  64,755,036.0  progsum=  64,755,036.0  OK
    strat 22: total=  42,779,504.0  progsum=  37,354,790.0  ** MISMATCH diff=5,424,714.0
    strat 23: total=  42,601,827.0  progsum=  42,601,827.0  OK
    strat 24: total=   5,840,075.0  progsum=   5,840,075.0  OK
    strat 25: total=   4,492,999.0  progsum=   4,492,999.0  OK
    strat 26: total=   4,266,735.0  progsum=   4,266,739.0  ** MISMATCH diff=-4.0
    strat 27: total=       8,227.0  progsum=   1,340,991.0  ** MISMATCH diff=-1,332,764.0
    strat 28: total=   1,683,902.0  progsum=   1,683,902.0  OK
    strat 29: total=  10,530,220.0  progsum=  10,530,220.0  OK
    strat 30: total=   5,789,365.0  progsum=   4,495,555.0  ** MISMATCH diff=1,293,810.0
    strat 31: total=   1,506,886.0  progsum=   1,252,973.0  ** MISMATCH diff=253,913.0
    strat 32: total=   7,840,279.0  progsum=   7,840,279.0  OK

  FY2024   (national total = 733,660,623.0)
    strat 1: total=  20,434,017.0  progsum=   7,398,907.0  ** MISMATCH diff=13,035,110.0
    strat 2: total=  20,787,951.0  progsum=  20,787,951.0  OK
    strat 3: total=  10,432,093.0  progsum=  10,432,093.0  OK
    strat 4: total= 135,466,017.0  progsum= 135,466,017.0  OK
    strat 5: total=   8,218,889.0  progsum=   8,218,889.0  OK
    strat 6: total= 117,790,778.0  progsum= 117,790,778.0  OK
    strat 7: total=  30,191,493.0  progsum=  30,191,493.0  OK
    strat 8: total= 156,664,219.0  progsum= 145,029,765.0  ** MISMATCH diff=11,634,454.0
    strat 9: total=  22,632,720.0  progsum=  22,632,720.0  OK
    strat 10: total=  22,722,736.0  progsum=  22,722,736.0  OK
    strat 11: total=   8,538,886.0  progsum=   8,538,886.0  OK
    strat 12: total=      58,333.0  progsum=  44,086,353.0  ** MISMATCH diff=-44,028,020.0
    strat 13: total=      11,008.0  progsum=  11,008,147.0  ** MISMATCH diff=-10,997,139.0
    strat 14: total=  14,436,486.0  progsum=  14,436,486.0  OK
    strat 15: total=  65,665,347.0  progsum=  65,665,347.0  OK
    strat 16: total=  50,762,039.0  progsum=  50,762,039.0  OK
    strat 17: total=   5,642,267.0  progsum=   5,642,267.0  OK
    strat 18: total=   4,431,763.0  progsum=   4,431,763.0  OK
    strat 19: total=   3,392,353.0  progsum=   3,392,354.0  ** MISMATCH diff=-1.0
    strat 20: total=   8,402,796.0  progsum=   8,402,796.0  OK
    strat 21: total=   1,727,923.0  progsum=   1,727,923.0  OK
    strat 22: total=  13,372,015.0  progsum=   5,212,244.0  ** MISMATCH diff=8,159,771.0
    strat 23: total=   5,567,770.0  progsum=   5,567,770.0  OK
    strat 24: total=   1,522,256.0  progsum=   1,522,256.0  OK
    strat 25: total=   4,788,468.0  progsum=   4,788,468.0  OK

  FY2025   (national total = 921,251,557.0)
    strat 1: total=  22,984,980.0  progsum=  22,984,980.0  OK
    strat 2: total=  21,004,417.0  progsum=  21,004,417.0  OK
    strat 3: total=  11,973,261.0  progsum=  11,973,260.0  ** MISMATCH diff=1.0
    strat 4: total= 134,407,987.0  progsum= 134,407,987.0  OK
    strat 5: total=  11,160,668.0  progsum=  11,160,668.0  OK
    strat 6: total= 132,814,395.0  progsum= 132,814,395.0  OK
    strat 7: total=  31,881,708.0  progsum=  31,881,708.0  OK
    strat 8: total= 170,675,414.0  progsum= 170,675,414.4  ** MISMATCH diff=-0.4
    strat 9: total=  20,877,003.0  progsum=  20,877,003.0  OK
    strat 10: total=  37,283,247.0  progsum=  37,283,247.0  OK
    strat 11: total=  13,509,491.0  progsum=  13,509,491.0  OK
    strat 12: total=  63,635,872.0  progsum=  63,635,871.0  ** MISMATCH diff=1.0
    strat 13: total=  11,379,722.0  progsum=  11,379,723.0  ** MISMATCH diff=-1.0
    strat 14: total=   9,817,243.0  progsum=   9,817,243.0  OK
    strat 15: total=   9,136,416.0  progsum=   9,136,416.0  OK
    strat 16: total= 107,167,829.0  progsum= 107,167,829.0  OK
    strat 17: total=  58,220,512.0  progsum=  58,220,512.0  OK
    strat 18: total=   2,952,421.0  progsum=   2,952,421.0  OK
    strat 19: total=   5,840,330.0  progsum=   5,840,330.0  OK
    strat 20: total=   4,349,975.0  progsum=   4,349,975.0  OK
    strat 21: total=   3,907,060.0  progsum=   3,907,060.0  OK
    strat 22: total=   9,171,376.0  progsum=   9,171,376.0  OK
    strat 23: total=   1,870,583.0  progsum=   1,870,583.0  OK
    strat 24: total=  16,926,493.0  progsum=  16,926,493.0  OK
    strat 25: total=   6,795,567.0  progsum=   6,795,567.0  OK
    strat 26: total=   1,507,587.0  progsum=   1,507,587.0  OK

RECONCILIATION: FAIL - see MISMATCH rows

NATIONAL TOTAL (the denominator every share is computed against)
    FY2023  heads 737,429,983.0  programmes 767,744,736.0  gap   4.0%  -> GRAND_TOTAL
    FY2024  heads 733,660,623.0  programmes 755,856,448.0  gap   2.9%  -> GRAND_TOTAL
    FY2025  heads 921,251,557.0  programmes 921,251,556.4  gap   0.0%  -> GRAND_TOTAL
    FY2023  extracted 71.0% of the document's own grand total 1,081,210,959.3
    FY2024  extracted 65.4% of the document's own grand total 1,156,396,212.0
    FY2025  extracted 74.2% of the document's own grand total 1,241,535,754.0

READABILITY  0 of 191 programme name(s) unreadable (0%), 0 of 83 head(s) (0%), 0% of the money

HEAD NAMES: 126 row(s) renamed so a head reads the same in every year

Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/samoa/budget_layer_all_years.xlsx
  sheet 'budget_all_years' : 277 rows  (feeds Prompt 6 / build_final_panel - each intervention matches against EVERY year's programs)
  sheet 'programs_wide'    : 77 programs x 3 year(s) (funding-over-time)
  sheet 'reconciliation'   : 83 rows (audit)
  sheet 'data_quality'     : 76 flagged items (see summary below)

==============================================================================
DATA-QUALITY SUMMARY
==============================================================================
  HIGH: 27   MEDIUM: 24   LOW: 22   INFO: 3

  [HIGH] partial_budget  (3)
      - FY2023: the heads extracted sum to 767,744,736.0 but the document's own grand total is 1,081,210,959.3, so only 71% of the budget is here. A section was taken rather than the budget, and every share computed for FY2023 is a share of that section. Re-run stage 5 against the full summary of expenditure.
      - FY2024: the heads extracted sum to 755,856,448.0 but the document's own grand total is 1,156,396,212.0, so only 65% of the budget is here. A section was taken rather than the budget, and every share computed for FY2024 is a share of that section. Re-run stage 5 against the full summary of expenditure.
      - FY2025: the heads extracted sum to 921,251,557.0 but the document's own grand total is 1,241,535,754.0, so only 74% of the budget is here. A section was taken rather than the budget, and every share computed for FY2025 is a share of that section. Re-run stage 5 against the full summary of expenditure.

  [HIGH] reconciliation_mismatch  (24)
      - FY2023 strat 1: programs sum to 14,812,127.0 but strategy_total is 19,967,480.0 (gap 5,155,353.0) - a program line is likely missing or mis-extracted for this strategy-year.
      - FY2023 strat 2: programs sum to 445,584.0 but strategy_total is 5,815,359.0 (gap 5,369,775.0) - a program line is likely missing or mis-extracted for this strategy-year.
      - FY2023 strat 3: programs sum to 10,676,520.0 but strategy_total is 18,926,871.0 (gap 8,250,351.0) - a program line is likely missing or mis-extracted for this strategy-year.
      ... and 21 more (see 'data_quality' sheet)

  [MEDIUM] program_missing_in_year  (24)
      - FY2023,2024 strat 10 10.3: program '10.3' (Transactions on Behalf of the State) exists in ['2025'] but is absent in ['2023', '2024'] - check whether it was dropped during extraction or genuinely did not exist that year.
      - FY2023 strat 12 12.3: program '12.3' (Transactions on Behalf of the State) exists in ['2024', '2025'] but is absent in ['2023'] - check whether it was dropped during extraction or genuinely did not exist that year.
      - FY2024,2025 strat 13 13.3: program '13.3' (Transactions on Behalf of State) exists in ['2023'] but is absent in ['2024', '2025'] - check whether it was dropped during extraction or genuinely did not exist that year.
      ... and 21 more (see 'data_quality' sheet)

  [LOW] large_yoy_swing  (22)
      - FY2024->2025 strat 1 1.1: program '1.1' changed +104317% (13,048.0 -> 13,624,350.0) - verify this is real and not an extraction error.
      - FY2023->2024 strat 1 1.2: program '1.2' changed +105388420% (5.0 -> 5,269,426.0) - verify this is real and not an extraction error.
      - FY2024->2025 strat 12 12.2: program '12.2' changed +104932% (14,261.0 -> 14,978,547.0) - verify this is real and not an extraction error.
      ... and 19 more (see 'data_quality' sheet)
==============================================================================
DATA QUALITY: REVIEW NEEDED - resolve HIGH items before relying on totals for those strategy-years
==============================================================================
```

### build_final_panel
```
Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/samoa/FINAL_PANEL.xlsx
  panel               : 28 strategies x 3 years (2023, 2024, 2025)
  match_review        : 29 matches (BOTH names + rationale)
  unmatched_codes     : 0 (codes NOT in that year's budget - REVIEW)
  unfunded_strategies : 9 (strategies with no budget any year)
  funding_by_program  : 20 (per programme x year, amount once - SAFE TO SUM)
  unmapped_programs   : 171 budget programmes with no matched strategy
  risk_panel          : 8 risks | ceiling: PASS
  enrichment          : strategyclean=yes risk_summary=yes
  maturity            : mean=0.623 | financing-weighted=0.815 | {'operational_programme': 7, 'partial_operation': 12, 'planned': 7, 'aspirational': 1, 'planned_specific': 1}
  basket/reverse-pass : 7 shared programmes | reverse-pass edges=none (run Prompt 6b + --coverage)
  recall_review       : 4 large programmes matched to only 1 strategy (candidate baskets)
MATURITY: mean=0.623 financing_weighted=0.815
CEILING TEST: PASS - no strategy over-counted in any year
UNMATCHED CODES: 0
QA: PASS - 0 unmatched code(s), ceiling PASS, 0 year warning(s)
```

### build_analytics_html
```
dashboard -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/samoa/budget_strategy_analytics.html
  years        2023, 2024, 2025
  edges        29
  strategies   28 (9 unfunded)
  size         36 KB
```

### audit_checks
```
AUDIT CHECKS: samoa 19/19 PASS
  ok   A1   Stored programme sums              83 strategy-year(s) / 0 disagree
  ok   A2   Stored strategy totals             83 strategy-year(s) / 0 disagree
  ok   A3   Programme counted once             20 row(s) / 0 duplicate key(s)
  ok   A4   Ceiling holds                      83 strategy-year(s) / 0 over ceiling
  ok   A6   Panel money matches its edges      84 strategy-year figure(s) / 0 disagree
  ok   A8   Edges cite real programmes         29 accepted edge(s) / 0 dangle
  ok   A9   No strategy dropped                28 strategyclean row(s) / 28 panel row(s)
  ok   A10  Unfunded list is complete          9 zero-funded / 9 listed
  ok   A11  Evidence chain resolves            140 distinct id(s) / 0 dangle
  ok   A12  Maturity summary is derivable      8 metric(s) / 0 disagree
  ok   A14  No duplicate edges                 29 edge(s) / 0 duplicate(s)
  ok   A15  One currency                       1 expected / 1 found
  ok   A16  Components are traceable           276 component(s) / 0 untraceable
  ok   A17  No workbook open in Excel          0 expected / 0 found
  ok   A18  Strategies come from the plan      28 strategy(ies) / 0 with no component
  ok   A19  Funding priority is reproducible   21 distinct (salience, funding) group(s) / 0 split across priorities
  ok   A20  The budget is readable             191 programme(s) / 0 unreadable (0%), carrying 0% of the money
  ok   A21  Ambiguous codes name their head    0 repeated code(s) / 0 edge(s) do not name a head
  ok   A22  Every intervention is traceable to a strategy 140 intervention(s) extracted / 0 uncited (0.0%)
  --   A23  The sector layer stayed out of the panel no sector run for this country
```

### data_issues
```
data issues  Files/outputs/DATA_ISSUES.xlsx
  5 detected across 1 country(ies): 2 high, 2 medium, 1 low
  70 hand-written entr(ies) in 04_Docs_and_Planning/data_issues.json
  HIGH  samoa     D7       Flag raised while combining the budget years
  HIGH  samoa     D8       A strategy total its own programmes do not add up to
```
