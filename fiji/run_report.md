# Run report - Fiji

**🔴 Overall: REVIEW NEEDED**  
Generated 2026-08-22 11:55 by run_pipeline.py

| Stage | Ran | Key QA |
|---|---|---|
| validate_stage_schema (L2) | ok | PASS 11/11 |
| validate_source_fidelity (L4) | ok | NOT CONFIGURED |
| validate_recall (L4) | ok | NOT CONFIGURED [advisory] |
| validate_refs (L3) | ok | PASS 1/1 |
| combine_budget_years | ok | reconcile=FAIL - see MISMATCH rows | data_quality=REVIEW NEEDED - resolve HIGH items before relying on totals for those strategy-years |
| build_final_panel | ok | QA FAIL - ceiling=FAIL - see ceiling sheet | unmatched_codes=0 |
| build_analytics_html | ok | strategies=220 (23 unfunded) | edges=750 |
| audit_checks | FAILED | QA FAIL - 17/19 PASS (A4 3 over ceiling, A16 3 untraceable) [advisory] |
| data_issues | FAILED | 7 detected across 1 country(ies): 3 high, 3 medium, 1 low [advisory] |

## Outputs

- Budget layer: `Files/outputs/fiji/budget_layer_all_years.xlsx`
- FINAL panel (deliverable): `Files/outputs/fiji/FINAL_PANEL.xlsx`
- Dashboard: `Files/outputs/fiji/budget_strategy_analytics.html`
- Audit trail: `Files/outputs/union_dashboard.html`, Audit tab, filtered to this country
- Data oddities: `Files/outputs/DATA_ISSUES.xlsx`

## Full stage logs

### validate_stage_schema (L2)
```
--- fiji_budget_2017.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/fiji/validation/schema_fiji_budget_2017.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- fiji_budget_2018.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/fiji/validation/schema_fiji_budget_2018.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- fiji_budget_2019.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/fiji/validation/schema_fiji_budget_2019.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- fiji_coverage_2017.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/fiji/validation/schema_fiji_coverage_2017.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- fiji_coverage_2018.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/fiji/validation/schema_fiji_coverage_2018.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- fiji_coverage_2019.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/fiji/validation/schema_fiji_coverage_2019.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- fiji_mapping_2017.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/fiji/validation/schema_fiji_mapping_2017.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- fiji_mapping_2018.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/fiji/validation/schema_fiji_mapping_2018.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- fiji_mapping_2019.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/fiji/validation/schema_fiji_mapping_2019.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- fiji_strategyclean.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/fiji/validation/schema_fiji_strategyclean.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- fiji_risk_summary.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/fiji/validation/schema_fiji_risk_summary.xlsx

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
--- fiji references
RESULT: PASS - every one of 2511 reference(s) resolves
report -> Files/outputs/fiji/validation/refs_fiji_references.xlsx
```

### combine_budget_years
```
==============================================================================
COMBINED BUDGET LAYER  -  years: 2017, 2018, 2019  (3 file(s))
==============================================================================

RECONCILIATION (per year: sum of program rows vs strategy_total)

  FY2017   (national total = 4,403,368.1)
    strat 1: total=       2,144.6  progsum=       2,144.6  OK
    strat 2: total=      23,980.0  progsum=      23,980.0  OK
    strat 3: total=      22,314.5  progsum=      22,314.5  OK
    strat 4: total=     117,275.4  progsum=     116,220.2  ** MISMATCH diff=1,055.2
    strat 5: total=      13,214.4  progsum=      13,214.3  ** MISMATCH diff=0.1
    strat 6: total=       5,236.7  progsum=       5,236.7  OK
    strat 7: total=      16,487.0  progsum=      16,487.0  OK
    strat 8: total=      43,885.0  progsum=      43,885.0  OK
    strat 9: total=      98,447.6  progsum=      98,447.6  OK
    strat 13: total=      27,040.5  progsum=      27,040.6  ** MISMATCH diff=-0.1
    strat 14: total=      15,178.5  progsum=      15,178.5  OK
    strat 15: total=      46,722.0  progsum=      46,722.0  OK
    strat 16: total=      55,363.6  progsum=      55,363.6  OK
    strat 17: total=      69,032.6  progsum=      69,032.6  OK
    strat 18: total=      20,480.3  progsum=      20,480.3  OK
    strat 19: total=      96,688.5  progsum=      96,688.5  OK
    strat 20: total=     148,798.8  progsum=     148,798.8  OK
    strat 21: total=     490,115.7  progsum=     490,115.7  OK
    strat 22: total=     321,245.6  progsum=     321,245.4  ** MISMATCH diff=0.2
    strat 23: total=      34,637.2  progsum=      34,637.2  OK
    strat 24: total=     113,354.1  progsum=     113,354.0  ** MISMATCH diff=0.1
    strat 25: total=      23,096.6  progsum=      23,096.7  ** MISMATCH diff=-0.1
    strat 26: total=     106,499.6  progsum=     106,499.6  OK
    strat 30: total=      86,339.0  progsum=      86,339.0  OK
    strat 31: total=      18,809.2  progsum=      18,809.2  OK
    strat 32: total=      16,020.9  progsum=      16,020.9  OK
    strat 33: total=      42,329.9  progsum=      28,538.8  ** MISMATCH diff=13,791.1
    strat 34: total=     108,382.8  progsum=     107,606.0  ** MISMATCH diff=776.8
    strat 35: total=      60,021.0  progsum=      60,021.0  OK
    strat 36: total=      17,939.8  progsum=      17,939.8  OK
    strat 37: total=      33,927.8  progsum=       9,439.7  ** MISMATCH diff=24,488.1
    strat 38: total=       7,336.1  progsum=       7,336.1  OK
    strat 40: total=     134,178.0  progsum=      91,462.8  ** MISMATCH diff=42,715.2
    strat 41: total=     306,942.7  progsum=     306,942.7  OK
    strat 42: total=      24,200.0  progsum=      21,809.9  ** MISMATCH diff=2,390.1
    strat 43: total=     527,548.6  progsum=     527,548.6  OK
    strat 49: total=      79,207.7  progsum=      79,207.7  OK
    strat 50: total=     628,116.8  progsum=     615,572.2  ** MISMATCH diff=12,544.6
    strat 51: total=      46,221.1  progsum=      46,221.1  OK
    strat 52: total=     354,607.9  progsum=     364,701.0  ** MISMATCH diff=-10,093.1

  FY2018   (national total = 4,529,133.6)
    strat 1: total=       3,127.2  progsum=       3,127.2  OK
    strat 2: total=      14,262.3  progsum=      23,891.3  ** MISMATCH diff=-9,629.0
    strat 3: total=      13,708.4  progsum=      17,708.4  ** MISMATCH diff=-4,000.0
    strat 4: total=     109,562.1  progsum=      94,269.6  ** MISMATCH diff=15,292.5
    strat 5: total=      15,069.1  progsum=      14,241.8  ** MISMATCH diff=827.3
    strat 6: total=       4,599.0  progsum=       4,599.0  OK
    strat 7: total=      15,989.0  progsum=      15,989.0  OK
    strat 8: total=      46,964.9  progsum=      46,964.9  OK
    strat 14: total=      15,525.6  progsum=      15,525.6  OK
    strat 15: total=      49,265.0  progsum=      49,265.0  OK
    strat 16: total=      64,951.2  progsum=      64,951.2  OK
    strat 17: total=      51,994.4  progsum=      51,994.4  OK
    strat 18: total=      21,678.3  progsum=      21,678.3  OK
    strat 19: total=     103,252.1  progsum=     103,252.1  OK
    strat 20: total=     193,509.9  progsum=     193,509.9  OK
    strat 21: total=     535,365.7  progsum=     558,619.6  ** MISMATCH diff=-23,253.9
    strat 22: total=     334,960.2  progsum=     334,960.2  OK
    strat 23: total=      41,422.6  progsum=      41,422.6  OK
    strat 24: total=     132,997.2  progsum=     132,997.2  OK
    strat 25: total=      24,095.9  progsum=      23,095.8  ** MISMATCH diff=1,000.1
    strat 26: total=     123,789.1  progsum=     123,789.1  OK
    strat 30: total=      96,837.1  progsum=      96,837.0  ** MISMATCH diff=0.1
    strat 31: total=      20,533.8  progsum=      20,533.8  OK
    strat 32: total=      17,065.6  progsum=      17,065.6  OK
    strat 33: total=      37,487.7  progsum=      37,487.7  OK
    strat 34: total=      99,258.7  progsum=      99,258.9  ** MISMATCH diff=-0.2
    strat 35: total=      62,331.9  progsum=      62,331.9  OK
    strat 36: total=      15,844.4  progsum=      15,844.4  OK
    strat 37: total=      30,126.1  progsum=      30,126.0  ** MISMATCH diff=0.1
    strat 40: total=     165,226.9  progsum=     165,226.4  ** MISMATCH diff=0.5
    strat 41: total=     349,264.2  progsum=     349,264.2  OK
    strat 42: total=      69,955.7  progsum=      69,955.7  OK
    strat 43: total=     563,056.9  progsum=     563,056.9  OK
    strat 49: total=      80,696.0  progsum=      80,696.0  OK
    strat 50: total=     567,864.0  progsum=           0.0  ** MISMATCH diff=567,864.0
    strat 51: total=      46,221.1  progsum=           0.0  ** MISMATCH diff=46,221.1
    strat 52: total=     391,274.3  progsum=     400,474.3  ** MISMATCH diff=-9,200.0

  FY2019   (national total = 3,268,563.2)
    strat 1: total=       3,064.2  progsum=       3,064.2  OK
    strat 2: total=      17,082.7  progsum=      17,082.7  OK
    strat 3: total=      10,659.4  progsum=      10,659.4  OK
    strat 4: total=      86,087.8  progsum=      86,087.8  OK
    strat 5: total=      14,546.3  progsum=      14,546.3  OK
    strat 6: total=      16,181.5  progsum=      16,181.5  OK
    strat 7: total=      13,383.6  progsum=      13,383.6  OK
    strat 8: total=      43,261.0  progsum=      43,261.0  OK
    strat 14: total=      12,785.1  progsum=      12,784.9  ** MISMATCH diff=0.2
    strat 15: total=      41,889.0  progsum=      41,889.0  OK
    strat 16: total=      74,611.4  progsum=      74,611.3  ** MISMATCH diff=0.1
    strat 17: total=       3,271.3  progsum=       3,271.3  OK
    strat 18: total=      18,692.2  progsum=      18,692.2  OK
    strat 19: total=      95,922.9  progsum=      95,922.9  OK
    strat 20: total=     177,789.4  progsum=     177,789.4  OK
    strat 21: total=     467,653.9  progsum=     467,653.9  OK
    strat 22: total=     349,774.2  progsum=     349,774.1  ** MISMATCH diff=0.1
    strat 23: total=      17,176.0  progsum=      17,176.0  OK
    strat 24: total=     127,684.0  progsum=     127,684.0  OK
    strat 25: total=      19,898.7  progsum=      19,696.7  ** MISMATCH diff=202.0
    strat 26: total=     115,587.2  progsum=     115,587.2  OK
    strat 30: total=      78,715.9  progsum=      78,715.8  ** MISMATCH diff=0.1
    strat 31: total=      17,177.7  progsum=      17,177.7  OK
    strat 32: total=      16,522.7  progsum=      16,522.7  OK
    strat 33: total=      29,627.9  progsum=      29,627.9  OK
    strat 34: total=      67,086.7  progsum=      84,250.3  ** MISMATCH diff=-17,163.6
    strat 35: total=      70,395.4  progsum=      70,395.4  OK
    strat 37: total=      28,447.3  progsum=      28,447.3  OK
    strat 40: total=      89,627.4  progsum=      89,627.3  ** MISMATCH diff=0.1
    strat 41: total=     258,715.7  progsum=     258,715.7  OK
    strat 42: total=      33,928.4  progsum=      33,928.4  OK
    strat 43: total=     419,426.6  progsum=     419,426.6  OK
    strat 49: total=      77,526.8  progsum=      77,526.8  OK
    strat 52: total=     354,362.9  progsum=     363,562.9  ** MISMATCH diff=-9,200.0

RECONCILIATION: FAIL - see MISMATCH rows

NATIONAL TOTAL (the denominator every share is computed against)
    FY2017  heads 4,403,368.1  programmes 4,315,699.9  gap   2.0%  -> GRAND_TOTAL
    FY2018  heads 4,529,133.6  programmes 3,944,011.0  gap  12.9%  -> PROGRAMMES
    FY2019  heads 3,268,563.2  programmes 3,413,014.2  gap   4.2%  -> HEADS
    The head totals under-report in 1 year(s); the programme rows are the national budget there.
    FY2017  extracted 101.1% of the document's own grand total 4,356,830.8

READABILITY  0 of 271 programme name(s) unreadable (0%), 0 of 111 head(s) (0%), 0% of the money

PROGRAMME CLASS (share of programme money)
    development           1,949,964.1   16.7%  (37 programme-year rows)
    standing_function     6,017,887.9   51.6%  (119 programme-year rows)
    overhead              3,289,987.6   28.2%  (87 programme-year rows)
    (unclassified)          414,885.5    3.6%  (0 programme-year rows)

HEAD NAMES: 21 row(s) renamed so a head reads the same in every year

Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/fiji/budget_layer_all_years.xlsx
  sheet 'budget_all_years' : 383 rows  (feeds Prompt 6 / build_final_panel - each intervention matches against EVERY year's programs)
  sheet 'programs_wide'    : 108 programs x 3 year(s) (funding-over-time)
  sheet 'reconciliation'   : 111 rows (audit)
  sheet 'data_quality'     : 76 flagged items (see summary below)

==============================================================================
DATA-QUALITY SUMMARY
==============================================================================
  HIGH: 35   MEDIUM: 32   LOW: 6   INFO: 3

  [HIGH] national_basis_programmes  (1)
      - FY2018: head totals sum to 4,529,133.6 but the programmes beneath them sum to 3,944,011.0 (13% apart), so the national total for this year is taken from the PROGRAMME rows. Every share for FY2018 is computed against 3,944,011.0.

  [HIGH] reconciliation_mismatch  (34)
      - FY2017 strat 4: programs sum to 116,220.2 but strategy_total is 117,275.4 (gap 1,055.2) - a program line is likely missing or mis-extracted for this strategy-year.
      - FY2017 strat 5: programs sum to 13,214.3 but strategy_total is 13,214.4 (gap 0.1) - a program line is likely missing or mis-extracted for this strategy-year.
      - FY2017 strat 13: programs sum to 27,040.6 but strategy_total is 27,040.5 (gap -0.1) - a program line is likely missing or mis-extracted for this strategy-year.
      ... and 31 more (see 'data_quality' sheet)

  [MEDIUM] no_grand_total  (2)
      - FY2018: the document printed no grand total that stage 5 could find, so there is nothing to check the extraction's completeness against. Every share for FY2018 rests on the heads being all of them.
      - FY2019: the document printed no grand total that stage 5 could find, so there is nothing to check the extraction's completeness against. Every share for FY2019 rests on the heads being all of them.

  [MEDIUM] program_missing_in_year  (29)
      - FY2018 strat 13 13.1: program '13.1' (Policy and Administration) exists in ['2017', '2019'] but is absent in ['2018'] - check whether it was dropped during extraction or genuinely did not exist that year.
      - FY2018,2019 strat 13 13.2: program '13.2' (Accountability and Transparency) exists in ['2017'] but is absent in ['2018', '2019'] - check whether it was dropped during extraction or genuinely did not exist that year.
      - FY2018,2019 strat 13 13.3: program '13.3' (Constitutional Offices Commission) exists in ['2017'] but is absent in ['2018', '2019'] - check whether it was dropped during extraction or genuinely did not exist that year.
      ... and 26 more (see 'data_quality' sheet)

  [MEDIUM] zero_amount_programme  (1)
      - FY2017 strat 30 30.5: programme carries no money; a strategy matched only to lines like this reads as funded while receiving nothing

  [LOW] large_yoy_swing  (6)
      - FY2018->2019 strat 34 34.1: program '34.1' changed +846% (1,828.0 -> 17,291.2) - verify this is real and not an extraction error.
      - FY2017->2018 strat 34 34.4: program '34.4' changed +217% (431.6 -> 1,370.0) - verify this is real and not an extraction error.
      - FY2017->2018 strat 37 37.1: program '37.1' changed +1629% (1,350.5 -> 23,355.8) - verify this is real and not an extraction error.
      ... and 3 more (see 'data_quality' sheet)
==============================================================================
DATA QUALITY: REVIEW NEEDED - resolve HIGH items before relying on totals for those strategy-years
==============================================================================
```

### build_final_panel
```
STALE EDGES DROPPED: 76 edge(s) name a strategy the inventory does not hold (prog=76)
   ! 14.1 | Disaster Management
   ! 14.2 | Meteorological Services
   ! 16.3 | Department of Communication
   ! 18.2 | Rural Development Services
   ! 18.3 | Rural Infrastructure
   ! 18.4 | Rehabilitation and Rural Housing
   ! 20.1 | Fiji Police
   ! 21.2 | Primary Education
   ! 21.3 | Secondary Education
   ! 21.4 | Curriculum Development
   Re-run the stage that produced them against the current strategyclean.

Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/fiji/FINAL_PANEL.xlsx
  panel               : 220 strategies x 3 years (2017, 2018, 2019)
  match_review        : 750 matches (BOTH names + rationale)
  unmatched_codes     : 0 (codes NOT in that year's budget - REVIEW)
  unfunded_strategies : 23 (strategies with no budget any year)
  funding_by_program  : 167 (per programme x year, amount once - SAFE TO SUM)
  unmapped_programs   : 104 budget programmes with no matched strategy
  risk_panel          : 11 risks | ceiling: FAIL - see 'ceiling' sheet
  enrichment          : strategyclean=yes risk_summary=yes
  maturity            : mean=0.78 | financing-weighted=0.853 | {'operational_programme': 155, 'operational_funded': 12, 'partial_operation': 30, 'planned': 12, 'aspirational': 9, 'planned_specific': 2}
  basket/reverse-pass : 129 shared programmes | reverse-pass edges=76 rows -> 0 new matches
  recall_review       : 11 large programmes matched to only 1 strategy (candidate baskets)
MATURITY: mean=0.78 financing_weighted=0.853
CEILING TEST: FAIL - see ceiling sheet
UNMATCHED CODES: 0
QA: FAIL - 0 unmatched code(s), ceiling FAIL, 0 year warning(s)
```

### build_analytics_html
```
dashboard -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/fiji/budget_strategy_analytics.html
  years        2017, 2018, 2019
  edges        750
  strategies   220 (23 unfunded)
  size         241 KB
```

### audit_checks
```
AUDIT CHECKS: fiji 17/19 PASS (A4 3 over ceiling, A16 3 untraceable)
  ok   A1   Stored programme sums              111 strategy-year(s) / 0 disagree
  ok   A2   Stored strategy totals             111 strategy-year(s) / 0 disagree
  ok   A3   Programme counted once             167 row(s) / 0 duplicate key(s)
  FAIL A4   Ceiling holds                      111 strategy-year(s) / 3 over ceiling
            FY2017 strategy 52: matched 364,701.0 of 354,607.9
            FY2018 strategy 52: matched 400,474.3 of 391,274.3
            FY2019 strategy 52: matched 363,562.9 of 354,362.9
  ok   A6   Panel money matches its edges      660 strategy-year figure(s) / 0 disagree
  ok   A8   Edges cite real programmes         750 accepted edge(s) / 0 dangle
  ok   A9   No strategy dropped                220 strategyclean row(s) / 220 panel row(s)
  ok   A10  Unfunded list is complete          23 zero-funded / 23 listed
  ok   A11  Evidence chain resolves            1629 distinct id(s) / 0 dangle
  ok   A12  Maturity summary is derivable      8 metric(s) / 0 disagree
  ok   A14  No duplicate edges                 750 edge(s) / 0 duplicate(s)
  ok   A15  One currency                       1 expected / 1 found
  FAIL A16  Components are traceable           2137 component(s) / 3 untraceable
            Strengthen civil service capabilit <- Civil Service Planning, Implementation, and 
            Expand youth skills, entrepreneurs <- Inclusive Education for Children with Specia
            Promote gender equality, leadershi <- Women’s Equal Access Awareness Campaign
  ok   A17  No workbook open in Excel          0 expected / 0 found
  ok   A18  Strategies come from the plan      220 strategy(ies) / 0 with no component
  ok   A19  Funding priority is reproducible   155 distinct (salience, funding) group(s) / 0 split across priorities
  ok   A20  The budget is readable             271 programme(s) / 0 unreadable (0%), carrying 0% of the money
  ok   A21  Ambiguous codes name their head    0 repeated code(s) / 0 edge(s) do not name a head
  ok   A22  Consolidation keeps every intervention 1665 intervention(s) extracted / 36 dropped (2.2%)
            169
            226
            268
            324
            326
            333
  --   A23  The sector layer stayed out of the panel no sector run for this country
```

### data_issues
```
data issues  Files/outputs/DATA_ISSUES.xlsx
  7 detected across 1 country(ies): 3 high, 3 medium, 1 low
  51 hand-written entr(ies) in 04_Docs_and_Planning/data_issues.json
  HIGH  fiji      D12      An output predates the prompt that produced it
  HIGH  fiji      D7       Flag raised while combining the budget years
  HIGH  fiji      D8       A strategy total its own programmes do not add up to
```
