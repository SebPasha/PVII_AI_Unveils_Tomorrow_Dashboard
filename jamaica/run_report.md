# Run report - Jamaica

**🔴 Overall: REVIEW NEEDED**  
Generated 2026-08-15 10:04 by run_pipeline.py

| Stage | Ran | Key QA |
|---|---|---|
| validate_stage_schema (L2) | ok | PASS 11/11 |
| validate_source_fidelity (L4) | ok | NOT CONFIGURED [advisory] |
| validate_recall (L4) | ok | NOT CONFIGURED [advisory] |
| validate_refs (L3) | ok | QA FAIL - FAIL 1/1 (jamaica references) |
| combine_budget_years | ok | reconcile=FAIL - see MISMATCH rows | data_quality=REVIEW NEEDED - resolve HIGH items before relying on totals for those strategy-years |
| build_final_panel | ok | QA FAIL - ceiling=PASS - no strategy over-counted in any year | unmatched_codes=254 |
| build_analytics_html | ok | QA FAIL - dashboard built, no summary printed |
| audit_checks | ok | QA FAIL - 10/12 PASS (A2 3 disagree, A11 10 dangle) [advisory] |
| data_issues | ok | 7 detected across 1 country(ies): 2 high, 4 medium, 1 low [advisory] |

## Outputs

- Budget layer: `Files/outputs/jamaica/budget_layer_all_years.xlsx`
- FINAL panel (deliverable): `Files/outputs/jamaica/FINAL_PANEL.xlsx`
- Dashboard: `Files/outputs/jamaica/budget_strategy_analytics.html`
- Audit trail: `Files/outputs/union_dashboard.html`, Audit tab, filtered to this country
- Data oddities: `Files/outputs/DATA_ISSUES.xlsx`

## Full stage logs

### validate_stage_schema (L2)
```
--- jamaica_budget_2019.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/jamaica/validation/schema_jamaica_budget_2019.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- jamaica_budget_2022.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/jamaica/validation/schema_jamaica_budget_2022.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- jamaica_budget_2024.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/jamaica/validation/schema_jamaica_budget_2024.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- jamaica_coverage_2019.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/jamaica/validation/schema_jamaica_coverage_2019.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- jamaica_coverage_2022.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/jamaica/validation/schema_jamaica_coverage_2022.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- jamaica_coverage_2024.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/jamaica/validation/schema_jamaica_coverage_2024.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- jamaica_mapping_2019.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/jamaica/validation/schema_jamaica_mapping_2019.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- jamaica_mapping_2022.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/jamaica/validation/schema_jamaica_mapping_2022.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- jamaica_mapping_2024.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/jamaica/validation/schema_jamaica_mapping_2024.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- jamaica_strategyclean.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/jamaica/validation/schema_jamaica_strategyclean.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- jamaica_risk_summary.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/jamaica/validation/schema_jamaica_risk_summary.xlsx

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
--- jamaica references
RESULT: FAIL - 207 dangling reference(s) of 1143
report -> Files/outputs/jamaica/validation/refs_jamaica_references.xlsx
```

### combine_budget_years
```
==============================================================================
COMBINED BUDGET LAYER  -  years: 2019, 2022, 2024  (3 file(s))
==============================================================================

RECONCILIATION (per year: sum of program rows vs strategy_total)

  FY2019   (national total = 39,096,070.0)
    strat 01: total=   3,738,254.0  progsum=   5,419,260.0  ** MISMATCH diff=-1,681,006.0
    strat 02: total=   7,984,378.0  progsum=   7,984,378.0  OK
    strat 03: total=   6,718,149.0  progsum=   6,718,149.0  OK
    strat 05: total=     273,408.0  progsum=     495,930.0  ** MISMATCH diff=-222,522.0
    strat 06: total=      56,267.0  progsum=     156,267.0  ** MISMATCH diff=-100,000.0
    strat 07: total=   5,615,836.0  progsum=   5,615,836.0  OK
    strat 09: total=     385,563.0  progsum=     385,563.0  OK
    strat 10: total=   3,655,940.0  progsum=   3,655,940.0  OK
    strat 11: total=   2,913,267.0  progsum=   2,913,267.0  OK
    strat 14: total=      93,342.0  progsum=      93,342.0  OK
    strat 15: total=      31,539.0  progsum=      31,539.0  OK
    strat 20: total=      49,739.0  progsum=   2,997,389.0  ** MISMATCH diff=-2,947,650.0
    strat 21: total=      38,768.0  progsum=   2,611,812.0  ** MISMATCH diff=-2,573,044.0
    strat 22: total=     186,121.0  progsum=   6,596,981.0  ** MISMATCH diff=-6,410,860.0
    strat 23: total=      93,664.0  progsum=     435,892.0  ** MISMATCH diff=-342,228.0
    strat 24: total=      71,741.0  progsum=     273,000.0  ** MISMATCH diff=-201,259.0
    strat 25: total=     397,357.0  progsum=  52,348,077.0  ** MISMATCH diff=-51,950,720.0
    strat 26: total=      41,270.0  progsum=      41,270.0  OK
    strat 27: total=     527,179.0  progsum=     552,179.0  ** MISMATCH diff=-25,000.0
    strat 99: total=     660,484.0  progsum=   4,366,710.0  ** MISMATCH diff=-3,706,226.0
    strat 003: total=     295,600.0  progsum=     295,600.0  OK
    strat 105: total=   1,099,839.0  progsum=   1,099,839.0  OK
    strat 110: total=           0.0  progsum=           0.0  OK
    strat 119: total=      10,627.0  progsum=      10,627.0  OK
    strat 120: total=     535,814.0  progsum=     535,814.0  OK
    strat 121: total=      89,387.0  progsum=      89,387.0  OK
    strat 122: total=     267,568.0  progsum=     267,568.0  OK
    strat 123: total=     388,315.0  progsum=     388,315.0  OK
    strat 301: total=     192,436.0  progsum=     192,436.0  OK
    strat 307: total=   2,317,468.0  progsum=   2,317,468.0  OK
    strat 376: total=      93,342.0  progsum=      93,342.0  OK
    strat 500: total=     273,408.0  progsum=     273,408.0  OK

  FY2022   (national total = 52,130,320.0)
    strat 01: total=   1,572,223.0  progsum=   1,572,223.0  OK
    strat 02: total=  36,252,201.0  progsum=  36,421,502.0  ** MISMATCH diff=-169,301.0
    strat 03: total=      38,520.0  progsum=   7,618,777.0  ** MISMATCH diff=-7,580,257.0
    strat 04: total=   1,115,511.0  progsum=   1,115,511.0  OK
    strat 05: total=   4,796,920.0  progsum=   4,796,920.0  OK
    strat 06: total=   1,340,639.0  progsum=   2,268,474.0  ** MISMATCH diff=-927,835.0
    strat 14: total=     149,610.0  progsum=     149,610.0  OK
    strat 20: total=     856,209.0  progsum=   4,209,239.0  ** MISMATCH diff=-3,353,030.0
    strat 21: total=           0.0  progsum=  35,885,181.0  ** MISMATCH diff=-35,885,181.0
    strat 22: total=   1,035,294.0  progsum=  37,583,129.0  ** MISMATCH diff=-36,547,835.0
    strat 23: total=     382,436.0  progsum=   8,490,136.0  ** MISMATCH diff=-8,107,700.0
    strat 26: total=   2,522,023.0  progsum=   2,522,023.0  OK
    strat 28: total=      57,272.0  progsum=   3,353,643.0  ** MISMATCH diff=-3,296,371.0
    strat 31: total=     932,791.0  progsum=     932,791.0  OK
    strat 99: total=   1,078,671.0  progsum=   1,078,671.0  OK

  FY2024   (national total = 17,114,272.0)
    strat 01: total=   1,384,301.0  progsum=   4,907,630.0  ** MISMATCH diff=-3,523,329.0
    strat 02: total=     336,794.0  progsum=     685,101.0  ** MISMATCH diff=-348,307.0
    strat 20: total=      77,492.0  progsum=   9,290,139.0  ** MISMATCH diff=-9,212,647.0
    strat 21: total=      30,810.0  progsum=  46,523,881.0  ** MISMATCH diff=-46,493,071.0
    strat 22: total=     310,355.0  progsum=  63,805,391.0  ** MISMATCH diff=-63,495,036.0
    strat 23: total=     144,182.0  progsum=  13,677,758.0  ** MISMATCH diff=-13,533,576.0
    strat 24: total=     120,125.0  progsum=   3,034,658.0  ** MISMATCH diff=-2,914,533.0
    strat 25: total=           0.0  progsum=  93,208,719.0  ** MISMATCH diff=-93,208,719.0
    strat 26: total=      95,297.0  progsum=     904,052.0  ** MISMATCH diff=-808,755.0
    strat 27: total=     408,005.0  progsum=     408,005.0  OK
    strat 28: total=      66,609.0  progsum=   4,424,598.0  ** MISMATCH diff=-4,357,989.0
    strat 001: total=     739,535.0  progsum=   1,979,822.0  ** MISMATCH diff=-1,240,287.0
    strat 012: total=   1,136,598.0  progsum=   2,273,196.0  ** MISMATCH diff=-1,136,598.0
    strat 148: total=     417,311.0  progsum=     834,622.0  ** MISMATCH diff=-417,311.0
    strat 154: total=   2,427,951.0  progsum=   5,090,267.0  ** MISMATCH diff=-2,662,316.0
    strat 156: total=     438,704.0  progsum=           0.0  ** MISMATCH diff=438,704.0
    strat 161: total=     530,242.0  progsum=   1,060,484.0  ** MISMATCH diff=-530,242.0
    strat 182: total=   2,238,718.0  progsum=           0.0  ** MISMATCH diff=2,238,718.0
    strat 183: total=     805,683.0  progsum=           0.0  ** MISMATCH diff=805,683.0
    strat 184: total=   2,513,354.0  progsum=           0.0  ** MISMATCH diff=2,513,354.0
    strat 188: total=     627,843.0  progsum=   1,030,420.0  ** MISMATCH diff=-402,577.0
    strat 435: total=     411,925.0  progsum=     823,850.0  ** MISMATCH diff=-411,925.0
    strat 439: total=   1,852,438.0  progsum=   3,704,876.0  ** MISMATCH diff=-1,852,438.0

RECONCILIATION: FAIL - see MISMATCH rows

Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/jamaica/budget_layer_all_years.xlsx
  sheet 'budget_all_years' : 481 rows  (feeds Prompt 6 / build_final_panel - each intervention matches against EVERY year's programs)
  sheet 'programs_wide'    : 323 programs x 3 year(s) (funding-over-time)
  sheet 'reconciliation'   : 70 rows (audit)
  sheet 'data_quality'     : 828 flagged items (see summary below)

==============================================================================
DATA-QUALITY SUMMARY
==============================================================================
  HIGH: 41   MEDIUM: 775   LOW: 9   INFO: 3

  [HIGH] reconciliation_mismatch  (41)
      - FY2019 strat 01: programs sum to 5,419,260.0 but strategy_total is 3,738,254.0 (gap -1,681,006.0) - a program line is likely missing or mis-extracted for this strategy-year.
      - FY2019 strat 05: programs sum to 495,930.0 but strategy_total is 273,408.0 (gap -222,522.0) - a program line is likely missing or mis-extracted for this strategy-year.
      - FY2019 strat 06: programs sum to 156,267.0 but strategy_total is 56,267.0 (gap -100,000.0) - a program line is likely missing or mis-extracted for this strategy-year.
      ... and 38 more (see 'data_quality' sheet)

  [MEDIUM] blank_amount  (47)
      - FY2019 strat 01 01.004: amount is blank/unparseable.
      - FY2019 strat 03 03.110: amount is blank/unparseable.
      - FY2019 strat 05 05.578: amount is blank/unparseable.
      ... and 44 more (see 'data_quality' sheet)

  [MEDIUM] malformed_code_repaired  (411)
      - FY2019 strat 01 01.001: program_code '001' looked malformed and was normalized to '01.001' - verify against source; fix the year file to avoid this.
      - FY2019 strat 01 01.004: program_code '004' looked malformed and was normalized to '01.004' - verify against source; fix the year file to avoid this.
      - FY2019 strat 01 01.301: program_code '301' looked malformed and was normalized to '01.301' - verify against source; fix the year file to avoid this.
      ... and 408 more (see 'data_quality' sheet)

  [MEDIUM] program_missing_in_year  (317)
      - FY2019,2022 strat 001 001.01: program '001.01' (Central Administration) exists in ['2024'] but is absent in ['2019', '2022'] - check whether it was dropped during extraction or genuinely did not exist that year.
      - FY2019,2022 strat 001 001.02: program '001.02' (Policy, Planning and Development) exists in ['2024'] but is absent in ['2019', '2022'] - check whether it was dropped during extraction or genuinely did not exist that year.
      - FY2019,2022 strat 001 001.10001: program '001.10001' (Direction and Management) exists in ['2024'] but is absent in ['2019', '2022'] - check whether it was dropped during extraction or genuinely did not exist that year.
      ... and 314 more (see 'data_quality' sheet)

  [LOW] large_yoy_swing  (9)
      - FY2022->2024 strat 02 02.10918: program '02.10918' changed +470% (10,307.0 -> 58,722.0) - verify this is real and not an extraction error.
      - FY2019->2022 strat 20 20.10005: program '20.10005' changed +444% (157,338.0 -> 856,209.0) - verify this is real and not an extraction error.
      - FY2019->2022 strat 21 21.10303: program '21.10303' changed +4616% (103,500.0 -> 4,881,274.0) - verify this is real and not an extraction error.
      ... and 6 more (see 'data_quality' sheet)
==============================================================================
DATA QUALITY: REVIEW NEEDED - resolve HIGH items before relying on totals for those strategy-years
==============================================================================
```

### build_final_panel
```
Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/jamaica/FINAL_PANEL.xlsx
  panel               : 117 strategies x 3 years (2019, 2022, 2024)
  match_review        : 254 matches (BOTH names + rationale)
  unmatched_codes     : 254 (codes NOT in that year's budget - REVIEW)  <-- !!
  unfunded_strategies : 117 (strategies with no budget any year)
  funding_by_program  : 0 (per programme x year, amount once - SAFE TO SUM)
  unmapped_programs   : 411 budget programmes with no matched strategy
  risk_panel          : 10 risks | ceiling: PASS
  enrichment          : strategyclean=yes risk_summary=yes
  maturity            : mean=0.318 | financing-weighted=0.0 | {'planned': 84, 'aspirational': 28, 'planned_specific': 5}
  basket/reverse-pass : 0 shared programmes | reverse-pass edges=54 rows -> 0 new matches
  recall_review       : 0 large programmes matched to only 1 strategy (candidate baskets)
MATURITY: mean=0.318 financing_weighted=0.0
CEILING TEST: PASS - no strategy over-counted in any year
UNMATCHED CODES: 254
QA: FAIL - 254 unmatched code(s), ceiling PASS, 0 year warning(s)
```

### build_analytics_html
```
FAILED: /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/jamaica/FINAL_PANEL.xlsx has no funding_by_program / matches sheet
```

### audit_checks
```
AUDIT CHECKS: jamaica 10/12 PASS (A2 3 disagree, A11 10 dangle)
  ok   A1   Stored programme sums              70 strategy-year(s) / 0 disagree
  FAIL A2   Stored strategy totals             70 strategy-year(s) / 3 disagree
            FY2019 strategy 110: stored 0.0, layer -
            FY2022 strategy 21: stored 0.0, layer -
            FY2024 strategy 25: stored 0.0, layer -
  --   A3   Programme counted once             sheet absent
  ok   A4   Ceiling holds                      70 strategy-year(s) / 0 over ceiling
  --   A6   Panel money matches its edges      sheets absent
  ok   A8   Edges cite real programmes         254 accepted edge(s) / 0 dangle
  ok   A9   No strategy dropped                117 strategyclean row(s) / 117 panel row(s)
  ok   A10  Unfunded list is complete          117 zero-funded / 117 listed
  FAIL A11  Evidence chain resolves            830 distinct id(s) / 10 dangle
            chunk id 0 has no stage-3 row
            chunk id 1 has no stage-3 row
            chunk id 2 has no stage-3 row
            chunk id 3 has no stage-3 row
            chunk id 4 has no stage-3 row
            chunk id 5 has no stage-3 row
  ok   A12  Maturity summary is derivable      8 metric(s) / 0 disagree
  --   A14  No duplicate edges                 sheet absent
  ok   A15  One currency                       1 expected / 1 found
  ok   A16  Components are traceable           1067 component(s) / 0 untraceable
  ok   A17  No workbook open in Excel          0 expected / 0 found
  ok   A18  Strategies come from the plan      117 strategy(ies) / 0 with no component
```

### data_issues
```
data issues  Files/outputs/DATA_ISSUES.xlsx
  7 detected across 1 country(ies): 2 high, 4 medium, 1 low
  10 hand-written entr(ies) in 04_Docs_and_Planning/data_issues.json
  HIGH  jamaica   D7       Flag raised while combining the budget years
  HIGH  jamaica   D8       A strategy total its own programmes do not add up to
```
