# Run report - Jamaica

**🔴 Overall: REVIEW NEEDED**  
Generated 2026-08-22 11:55 by run_pipeline.py

| Stage | Ran | Key QA |
|---|---|---|
| validate_stage_schema (L2) | ok | QA FAIL - FAIL 3/11 (jamaica_budget_2019.xlsx, jamaica_budget_2022.xlsx, jamaica_budget_2024.xlsx) |
| validate_source_fidelity (L4) | ok | NOT CONFIGURED [advisory] |
| validate_recall (L4) | ok | NOT CONFIGURED [advisory] |
| validate_refs (L3) | ok | PASS 1/1 |
| combine_budget_years | ok | reconcile=FAIL - see MISMATCH rows | data_quality=REVIEW NEEDED - resolve HIGH items before relying on totals for those strategy-years |
| build_final_panel | ok | ceiling=PASS - no strategy over-counted in any year | unmatched_codes=0 |
| build_analytics_html | ok | strategies=135 (4 unfunded) | edges=572 |
| audit_checks | ok | 19/19 PASS [advisory] |
| data_issues | FAILED | 6 detected across 1 country(ies): 3 high, 2 medium, 1 low [advisory] |

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

  RESULT: FAIL - 108 contract violation(s) across 1 file(s).
  The stage output is not accepted; re-run the stage or fix the prompt.

--- jamaica_budget_2022.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/jamaica/validation/schema_jamaica_budget_2022.xlsx

  RESULT: FAIL - 143 contract violation(s) across 1 file(s).
  The stage output is not accepted; re-run the stage or fix the prompt.

--- jamaica_budget_2024.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/jamaica/validation/schema_jamaica_budget_2024.xlsx

  RESULT: FAIL - 169 contract violation(s) across 1 file(s).
  The stage output is not accepted; re-run the stage or fix the prompt.

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
RESULT: PASS - every one of 1585 reference(s) resolves
report -> Files/outputs/jamaica/validation/refs_jamaica_references.xlsx
```

### combine_budget_years
```
==============================================================================
COMBINED BUDGET LAYER  -  years: 2019, 2022, 2024  (3 file(s))
==============================================================================

RECONCILIATION (per year: sum of program rows vs strategy_total)

  FY2019   (national total = 278,267,320.0)
    strat 01000: total=     290,111.0  progsum=      83,000.0  ** MISMATCH diff=207,111.0
    strat 08000: total=     469,975.0  progsum=     642,858.0  ** MISMATCH diff=-172,883.0
    strat 09000: total=     833,920.0  progsum=     712,147.0  ** MISMATCH diff=121,773.0
    strat 15000: total=   7,952,226.0  progsum=   7,952,226.0  OK
    strat 15010: total=     697,424.0  progsum=           0.0  ** MISMATCH diff=697,424.0
    strat 15020: total=      10,480.0  progsum=     900,480.0  ** MISMATCH diff=-890,000.0
    strat 16049: total=     225,234.0  progsum=     489,234.0  ** MISMATCH diff=-264,000.0
    strat 17000: total=  11,525,361.0  progsum=   6,345,325.0  ** MISMATCH diff=5,180,036.0
    strat 19000: total=  18,424,497.0  progsum=  18,424,497.0  OK
    strat 19046: total=   1,078,318.0  progsum=   1,085,718.0  ** MISMATCH diff=-7,400.0
    strat 20056: total=  10,054,843.0  progsum=  10,054,843.0  OK
    strat 26000: total=  44,836,807.0  progsum=  45,308,512.0  ** MISMATCH diff=-471,705.0
    strat 26022: total=  39,423,260.0  progsum=           0.0  ** MISMATCH diff=39,423,260.0
    strat 26024: total=   7,611,526.0  progsum=   7,621,526.0  ** MISMATCH diff=-10,000.0
    strat 26053: total=      28,811.0  progsum=           0.0  ** MISMATCH diff=28,811.0
    strat 28000: total=   2,061,385.0  progsum=   3,866,946.0  ** MISMATCH diff=-1,805,561.0
    strat 28030: total=     317,177.0  progsum=     542,177.0  ** MISMATCH diff=-225,000.0
    strat 30000: total=   4,811,749.0  progsum=           0.0  ** MISMATCH diff=4,811,749.0
    strat 41000: total= 106,723,489.0  progsum= 107,548,489.0  ** MISMATCH diff=-825,000.0
    strat 50000: total=   9,597,784.0  progsum=           0.0  ** MISMATCH diff=9,597,784.0
    strat 50038: total=      14,019.0  progsum=     483,604.0  ** MISMATCH diff=-469,585.0
    strat 56000: total=      35,872.0  progsum=      35,872.0  OK
    strat 72000: total=  11,243,052.0  progsum=     423,040.0  ** MISMATCH diff=10,820,012.0

  FY2022   (national total = 302,576,866.0)
    strat 01000: total=     407,675.0  progsum=      95,774.0  ** MISMATCH diff=311,901.0
    strat 05000: total=   1,087,007.0  progsum=   1,080,720.0  ** MISMATCH diff=6,287.0
    strat 08000: total=     612,308.0  progsum=     763,809.0  ** MISMATCH diff=-151,501.0
    strat 09000: total=   1,150,532.0  progsum=   1,115,532.0  ** MISMATCH diff=35,000.0
    strat 15000: total=   4,507,458.0  progsum=   4,507,458.0  OK
    strat 15010: total=     680,846.0  progsum=     798,913.0  ** MISMATCH diff=-118,067.0
    strat 15020: total=     659,370.0  progsum=   1,317,383.0  ** MISMATCH diff=-658,013.0
    strat 16049: total=     274,923.0  progsum=     497,725.0  ** MISMATCH diff=-222,802.0
    strat 17000: total=  11,507,204.0  progsum=           0.0  ** MISMATCH diff=11,507,204.0
    strat 19000: total=   8,927,891.0  progsum=  29,765,294.0  ** MISMATCH diff=-20,837,403.0
    strat 19046: total=   1,090,013.0  progsum=   1,100,013.0  ** MISMATCH diff=-10,000.0
    strat 19047: total=     858,517.0  progsum=   3,679,751.0  ** MISMATCH diff=-2,821,234.0
    strat 19050: total=     873,915.0  progsum=   2,268,474.0  ** MISMATCH diff=-1,394,559.0
    strat 20000: total=  49,576,488.0  progsum=  58,653,448.0  ** MISMATCH diff=-9,076,960.0
    strat 26000: total=  34,248,397.0  progsum=  42,338,420.0  ** MISMATCH diff=-8,090,023.0
    strat 26022: total=  46,117,077.0  progsum=  46,517,077.0  ** MISMATCH diff=-400,000.0
    strat 26024: total=   8,903,647.0  progsum=   7,948,845.0  ** MISMATCH diff=954,802.0
    strat 26053: total=   1,121,806.0  progsum=   4,002,887.0  ** MISMATCH diff=-2,881,081.0
    strat 28000: total=   2,567,834.0  progsum=   2,838,834.0  ** MISMATCH diff=-271,000.0
    strat 28030: total=     397,438.0  progsum=     662,438.0  ** MISMATCH diff=-265,000.0
    strat 30000: total=   5,030,141.0  progsum=   5,173,346.0  ** MISMATCH diff=-143,205.0
    strat 41051: total=   3,136,230.0  progsum=   3,138,093.0  ** MISMATCH diff=-1,863.0
    strat 42000: total=  91,011,996.0  progsum=  96,361,130.0  ** MISMATCH diff=-5,349,134.0
    strat 46000: total=   4,407,217.0  progsum=   4,680,006.0  ** MISMATCH diff=-272,789.0
    strat 51000: total=  10,224,964.0  progsum=  16,159,097.0  ** MISMATCH diff=-5,934,133.0
    strat 53000: total=   4,290,996.0  progsum=   4,283,155.0  ** MISMATCH diff=7,841.0
    strat 53038: total=       8,860.0  progsum=     711,596.0  ** MISMATCH diff=-702,736.0
    strat 56000: total=   6,480,924.0  progsum=   7,722,180.0  ** MISMATCH diff=-1,241,256.0
    strat 56039: total=   2,415,192.0  progsum=   2,319,020.0  ** MISMATCH diff=96,172.0

  FY2024   (national total = 458,257,529.0)
    strat 01000: total=     532,852.0  progsum=     153,972.0  ** MISMATCH diff=378,880.0
    strat 05000: total=   1,404,352.0  progsum=   1,385,839.0  ** MISMATCH diff=18,513.0
    strat 08000: total=     837,299.0  progsum=     885,134.0  ** MISMATCH diff=-47,835.0
    strat 15020: total=     516,078.0  progsum=   1,462,358.0  ** MISMATCH diff=-946,280.0
    strat 15039: total=   3,502,373.0  progsum=   4,252,373.0  ** MISMATCH diff=-750,000.0
    strat 16049: total=     274,923.0  progsum=     574,923.0  ** MISMATCH diff=-300,000.0
    strat 19000: total=  12,439,289.0  progsum=  34,051,450.0  ** MISMATCH diff=-21,612,161.0
    strat 19046: total=   1,731,204.0  progsum=   1,766,204.0  ** MISMATCH diff=-35,000.0
    strat 19047: total=   1,568,816.0  progsum=   5,008,264.0  ** MISMATCH diff=-3,439,448.0
    strat 19050: total=   1,288,476.0  progsum=   3,090,257.0  ** MISMATCH diff=-1,801,781.0
    strat 20000: total=  90,947,481.0  progsum= 117,307,933.0  ** MISMATCH diff=-26,360,452.0
    strat 20060: total=   1,461,711.0  progsum=   1,561,711.0  ** MISMATCH diff=-100,000.0
    strat 26000: total=  47,390,535.0  progsum=  51,798,405.0  ** MISMATCH diff=-4,407,870.0
    strat 26022: total=  69,973,343.0  progsum=  70,423,343.0  ** MISMATCH diff=-450,000.0
    strat 26053: total=   1,032,106.0  progsum=   5,080,641.0  ** MISMATCH diff=-4,048,535.0
    strat 26059: total=   2,886,099.0  progsum=   1,033,661.0  ** MISMATCH diff=1,852,438.0
    strat 28000: total=   3,690,999.0  progsum=   4,275,364.0  ** MISMATCH diff=-584,365.0
    strat 28030: total=     438,367.0  progsum=     885,108.0  ** MISMATCH diff=-446,741.0
    strat 30000: total=   6,651,435.0  progsum=   6,751,435.0  ** MISMATCH diff=-100,000.0
    strat 41051: total=   4,756,586.0  progsum=   4,758,206.0  ** MISMATCH diff=-1,620.0
    strat 42000: total= 133,605,851.0  progsum= 145,655,364.0  ** MISMATCH diff=-12,049,513.0
    strat 46000: total=   5,856,463.0  progsum=   6,205,640.0  ** MISMATCH diff=-349,177.0
    strat 51000: total=  14,084,411.0  progsum=  19,608,348.0  ** MISMATCH diff=-5,523,937.0
    strat 53000: total=   6,134,940.0  progsum=   6,974,892.0  ** MISMATCH diff=-839,952.0
    strat 53038: total=     679,042.0  progsum=   1,245,569.0  ** MISMATCH diff=-566,527.0
    strat 69000: total=  23,793,602.0  progsum=  27,873,661.0  ** MISMATCH diff=-4,080,059.0
    strat 72000: total=  20,778,896.0  progsum=  26,555,683.0  ** MISMATCH diff=-5,776,787.0

RECONCILIATION: FAIL - see MISMATCH rows

NATIONAL TOTAL (the denominator every share is computed against)
    FY2019  heads 278,267,320.0  programmes 239,480,965.0  gap  13.9%  -> PROGRAMMES
    FY2022  heads 302,576,866.0  programmes 404,258,046.0  gap  25.1%  -> PROGRAMMES
    FY2024  heads 458,257,529.0  programmes 639,705,043.0  gap  28.4%  -> PROGRAMMES
    The head totals under-report in 3 year(s); the programme rows are the national budget there.

READABILITY  1 of 341 programme name(s) unreadable (0%), 0 of 79 head(s) (0%), 0% of the money
    e.g. '25'

PROGRAMME CLASS (share of programme money)
    development         182,852,879.0   14.2%  (89 programme-year rows)
    standing_function   727,880,271.0   56.7%  (136 programme-year rows)
    overhead            371,416,346.0   28.9%  (114 programme-year rows)
    mixed                 1,294,558.0    0.1%  (2 programme-year rows)

HEAD NAMES: 107 row(s) renamed so a head reads the same in every year

Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/jamaica/budget_layer_all_years.xlsx
  sheet 'budget_all_years' : 420 rows  (feeds Prompt 6 / build_final_panel - each intervention matches against EVERY year's programs)
  sheet 'programs_wide'    : 222 programs x 3 year(s) (funding-over-time)
  sheet 'reconciliation'   : 79 rows (audit)
  sheet 'data_quality'     : 285 flagged items (see summary below)

==============================================================================
DATA-QUALITY SUMMARY
==============================================================================
  HIGH: 77   MEDIUM: 203   LOW: 2   INFO: 3

  [HIGH] national_basis_programmes  (3)
      - FY2019: head totals sum to 278,267,320.0 but the programmes beneath them sum to 239,480,965.0 (14% apart), so the national total for this year is taken from the PROGRAMME rows. Every share for FY2019 is computed against 239,480,965.0.
      - FY2022: head totals sum to 302,576,866.0 but the programmes beneath them sum to 404,258,046.0 (25% apart), so the national total for this year is taken from the PROGRAMME rows. Every share for FY2022 is computed against 404,258,046.0.
      - FY2024: head totals sum to 458,257,529.0 but the programmes beneath them sum to 639,705,043.0 (28% apart), so the national total for this year is taken from the PROGRAMME rows. Every share for FY2024 is computed against 639,705,043.0.

  [HIGH] reconciliation_mismatch  (74)
      - FY2019 strat 01000: programs sum to 83,000.0 but strategy_total is 290,111.0 (gap 207,111.0) - a program line is likely missing or mis-extracted for this strategy-year.
      - FY2019 strat 08000: programs sum to 642,858.0 but strategy_total is 469,975.0 (gap -172,883.0) - a program line is likely missing or mis-extracted for this strategy-year.
      - FY2019 strat 09000: programs sum to 712,147.0 but strategy_total is 833,920.0 (gap 121,773.0) - a program line is likely missing or mis-extracted for this strategy-year.
      ... and 71 more (see 'data_quality' sheet)

  [MEDIUM] no_grand_total  (3)
      - FY2019: the document printed no grand total that stage 5 could find, so there is nothing to check the extraction's completeness against. Every share for FY2019 rests on the heads being all of them.
      - FY2022: the document printed no grand total that stage 5 could find, so there is nothing to check the extraction's completeness against. Every share for FY2022 rests on the heads being all of them.
      - FY2024: the document printed no grand total that stage 5 could find, so there is nothing to check the extraction's completeness against. Every share for FY2024 rests on the heads being all of them.

  [MEDIUM] program_missing_in_year  (200)
      - FY2024 strat 02000 02000.1.01.001: program '02000.1.01.001' (Executive Direction and Administration) exists in ['2019', '2022'] but is absent in ['2024'] - check whether it was dropped during extraction or genuinely did not exist that year.
      - FY2024 strat 02000 02000.1.01.164: program '02000.1.01.164' (Legislative Services) exists in ['2019', '2022'] but is absent in ['2024'] - check whether it was dropped during extraction or genuinely did not exist that year.
      - FY2024 strat 02000 02000.1.01.165: program '02000.1.01.165' (Political and Electoral Dispute Resolution) exists in ['2019', '2022'] but is absent in ['2024'] - check whether it was dropped during extraction or genuinely did not exist that year.
      ... and 197 more (see 'data_quality' sheet)

  [LOW] large_yoy_swing  (2)
      - FY2022->2024 strat 20000 20000.6.99.137: program '20000.6.99.137' changed +223% (7,603,835.0 -> 24,535,325.0) - verify this is real and not an extraction error.
      - FY2019->2022 strat 26000 26000.1.01.001: program '26000.1.01.001' changed +226% (2,116,532.0 -> 6,902,991.0) - verify this is real and not an extraction error.
==============================================================================
DATA QUALITY: REVIEW NEEDED - resolve HIGH items before relying on totals for those strategy-years
==============================================================================
```

### build_final_panel
```
STALE EDGES DROPPED: 81 edge(s) name a strategy the inventory does not hold (prog=81)
   ! 10700 | Supervision of Education System
   ! 10713 | Supervision of Primary Education
   ! 10715 | Delivery of Instruction
   ! 10772 | Supervision of Tertiary Institutions
   ! 10811 | Training of Nurses
   ! 12829 | In-Service Support
   ! 12835 | Supervision of Technical and Vocational Education
   ! 12836 | Guidance and Counselling Services
   ! 325 | Social Welfare Services
   ! Agricultural Planning and Policy
   Re-run the stage that produced them against the current strategyclean.

Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/jamaica/FINAL_PANEL.xlsx
  panel               : 135 strategies x 3 years (2019, 2022, 2024)
  match_review        : 572 matches (BOTH names + rationale)
  unmatched_codes     : 0 (codes NOT in that year's budget - REVIEW)
  unfunded_strategies : 4 (strategies with no budget any year)
  funding_by_program  : 177 (per programme x year, amount once - SAFE TO SUM)
  unmapped_programs   : 164 budget programmes with no matched strategy
  risk_panel          : 10 risks | ceiling: PASS
  enrichment          : strategyclean=yes risk_summary=yes
  maturity            : mean=0.824 | financing-weighted=0.848 | {'operational_programme': 120, 'partial_operation': 10, 'operational_funded': 1, 'planned': 3, 'aspirational': 1}
  basket/reverse-pass : 128 shared programmes | reverse-pass edges=81 rows -> 0 new matches
  recall_review       : 16 large programmes matched to only 1 strategy (candidate baskets)
MATURITY: mean=0.824 financing_weighted=0.848
CEILING TEST: PASS - no strategy over-counted in any year
UNMATCHED CODES: 0
QA: PASS - 0 unmatched code(s), ceiling PASS, 0 year warning(s)
```

### build_analytics_html
```
dashboard -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/jamaica/budget_strategy_analytics.html
  years        2019, 2022, 2024
  edges        572
  strategies   135 (4 unfunded)
  size         183 KB
```

### audit_checks
```
AUDIT CHECKS: jamaica 19/19 PASS
  ok   A1   Stored programme sums              79 strategy-year(s) / 0 disagree
  ok   A2   Stored strategy totals             79 strategy-year(s) / 0 disagree
  ok   A3   Programme counted once             177 row(s) / 0 duplicate key(s)
  ok   A4   Ceiling holds                      79 strategy-year(s) / 0 over ceiling
  ok   A6   Panel money matches its edges      405 strategy-year figure(s) / 0 disagree
  ok   A8   Edges cite real programmes         572 accepted edge(s) / 0 dangle
  ok   A9   No strategy dropped                135 strategyclean row(s) / 135 panel row(s)
  ok   A10  Unfunded list is complete          4 zero-funded / 4 listed
  ok   A11  Evidence chain resolves            993 distinct id(s) / 0 dangle
  ok   A12  Maturity summary is derivable      8 metric(s) / 0 disagree
  ok   A14  No duplicate edges                 572 edge(s) / 0 duplicate(s)
  ok   A15  One currency                       1 expected / 1 found
  ok   A16  Components are traceable           1086 component(s) / 0 untraceable
  ok   A17  No workbook open in Excel          0 expected / 0 found
  ok   A18  Strategies come from the plan      135 strategy(ies) / 0 with no component
  ok   A19  Funding priority is reproducible   129 distinct (salience, funding) group(s) / 0 split across priorities
  ok   A20  The budget is readable             341 programme(s) / 1 unreadable (0%), carrying 0% of the money
            FY2022 41000.1.22.24: '25'
  ok   A21  Ambiguous codes name their head    0 repeated code(s) / 0 edge(s) do not name a head
  ok   A22  Consolidation keeps every intervention 997 intervention(s) extracted / 4 dropped (0.4%)
            500
            1183
            2655
            3738
  --   A23  The sector layer stayed out of the panel no sector run for this country
```

### data_issues
```
data issues  Files/outputs/DATA_ISSUES.xlsx
  6 detected across 1 country(ies): 3 high, 2 medium, 1 low
  51 hand-written entr(ies) in 04_Docs_and_Planning/data_issues.json
  HIGH  jamaica   D12      An output predates the prompt that produced it
  HIGH  jamaica   D7       Flag raised while combining the budget years
  HIGH  jamaica   D8       A strategy total its own programmes do not add up to
```
