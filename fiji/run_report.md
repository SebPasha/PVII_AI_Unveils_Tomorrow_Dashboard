# Run report - Fiji

**🔴 Overall: REVIEW NEEDED**  
Generated 2026-08-22 21:33 by run_pipeline.py

| Stage | Ran | Key QA |
|---|---|---|
| validate_stage_schema (L2) | ok | PASS 21/21 |
| validate_source_fidelity (L4) | ok | NOT CONFIGURED |
| validate_recall (L4) | ok | NOT CONFIGURED [advisory] |
| validate_refs (L3) | ok | PASS 1/1 |
| combine_budget_years | ok | reconcile=FAIL - see MISMATCH rows | data_quality=REVIEW NEEDED - resolve HIGH items before relying on totals for those strategy-years |
| build_final_panel | ok | ceiling=PASS - no strategy over-counted in any year | unmatched_codes=0 |
| build_analytics_html | ok | strategies=220 (2 unfunded) | edges=2820 |
| audit_checks | FAILED | QA FAIL - 18/19 PASS (A16 3 untraceable) [advisory] |
| data_issues | FAILED | 8 detected across 1 country(ies): 4 high, 2 medium, 2 low [advisory] |

## Outputs

- Budget layer: `Files/outputs/fiji/budget_layer_all_years.xlsx`
- FINAL panel (deliverable): `Files/outputs/fiji/FINAL_PANEL.xlsx`
- Dashboard: `Files/outputs/fiji/budget_strategy_analytics.html`
- Audit trail: `Files/outputs/union_dashboard.html`, Audit tab, filtered to this country
- Data oddities: `Files/outputs/DATA_ISSUES.xlsx`

## Full stage logs

### validate_stage_schema (L2)
```
--- fiji_budget_2012.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/fiji/validation/schema_fiji_budget_2012.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- fiji_budget_2013.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/fiji/validation/schema_fiji_budget_2013.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- fiji_budget_2014.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/fiji/validation/schema_fiji_budget_2014.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- fiji_budget_2015.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/fiji/validation/schema_fiji_budget_2015.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- fiji_budget_2016.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/fiji/validation/schema_fiji_budget_2016.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

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

--- fiji_mapping_2012.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/fiji/validation/schema_fiji_mapping_2012.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- fiji_mapping_2013.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/fiji/validation/schema_fiji_mapping_2013.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- fiji_mapping_2014.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/fiji/validation/schema_fiji_mapping_2014.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- fiji_mapping_2015.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/fiji/validation/schema_fiji_mapping_2015.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- fiji_mapping_2016.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/fiji/validation/schema_fiji_mapping_2016.xlsx

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
RESULT: PASS - every one of 4583 reference(s) resolves
report -> Files/outputs/fiji/validation/refs_fiji_references.xlsx
```

### combine_budget_years
```
==============================================================================
COMBINED BUDGET LAYER  -  years: 2012, 2013, 2014, 2015, 2016, 2017, 2018, 2019  (8 file(s))
==============================================================================

SCALE: converted 784 row(s) into 'FJD thousand' using the unit each file declared
    FY2012  57 row(s) stated in million, multiplied by 1000
    FY2013  100 row(s) stated in million, multiplied by 1000
    FY2014  218 row(s) stated in million, multiplied by 1000
    FY2015  269 row(s) stated in million, multiplied by 1000
    FY2016  43 row(s) stated in million, multiplied by 1000
    FY2018  53 row(s) stated in million, multiplied by 1000
    FY2019  44 row(s) stated in million, multiplied by 1000

RECONCILIATION (per year: sum of program rows vs strategy_total)

  FY2012   (national total = 2,054,000.0)
    strat 1: total=   1,500,000.0  progsum=     527,984.0  ** MISMATCH diff=972,016.0
    strat 2: total=     554,000.0  progsum=     149,046.0  ** MISMATCH diff=404,954.0

  FY2013   (national total = 2,272,000.0)
    strat 1: total=   1,550,000.0  progsum=     943,390.0  ** MISMATCH diff=606,610.0
    strat 2: total=     722,000.0  progsum=     604,278.0  ** MISMATCH diff=117,722.0

  FY2014   (national total = 2,815,000.0)
    strat 1: total=   1,802,000.0  progsum=   2,291,245.0  ** MISMATCH diff=-489,245.0
    strat 2: total=   1,013,000.0  progsum=     429,794.7  ** MISMATCH diff=583,205.3

  FY2015   (national total = 3,200,000.0)
    strat 1: total=   1,900,000.0  progsum=   2,201,856.0  ** MISMATCH diff=-301,856.0
    strat 2: total=   1,300,000.0  progsum=   1,193,980.0  ** MISMATCH diff=106,020.0

  FY2016   (national total = 3,410,000.0)
    strat 1: total=   2,046,000.0  progsum=   1,134,270.0  ** MISMATCH diff=911,730.0
    strat 2: total=   1,364,000.0  progsum=     107,708.0  ** MISMATCH diff=1,256,292.0

  FY2017   (national total = 5,168,192.1)
    strat 1: total=   2,515,357.4  progsum=           0.0  ** MISMATCH diff=2,515,357.4
    strat 2: total=   1,778,982.6  progsum=           0.0  ** MISMATCH diff=1,778,982.6
    strat 3: total=      62,490.8  progsum=           0.0  ** MISMATCH diff=62,490.8
    strat 21: total=     490,115.7  progsum=     490,115.7  OK
    strat 22: total=     321,245.6  progsum=     321,245.7  ** MISMATCH diff=-0.1

  FY2018   (national total = 4,650,000.0)
    strat 1: total=   3,960,000.0  progsum=           0.0  ** MISMATCH diff=3,960,000.0
    strat 2: total=     690,000.0  progsum=           0.0  ** MISMATCH diff=690,000.0

  FY2019   (national total = 3,786,000.0)
    strat 1: total=   2,534,000.0  progsum=     937,165.0  ** MISMATCH diff=1,596,835.0
    strat 2: total=   1,252,000.0  progsum=     743,255.0  ** MISMATCH diff=508,745.0

RECONCILIATION: FAIL - see MISMATCH rows

NATIONAL TOTAL (the denominator every share is computed against)
    FY2012  heads 2,054,000.0  programmes 677,030.0  gap  67.0%  -> GRAND_TOTAL
    FY2013  heads 2,272,000.0  programmes 1,547,668.0  gap  31.9%  -> GRAND_TOTAL
    FY2014  heads 2,815,000.0  programmes 2,721,039.7  gap   3.3%  -> GRAND_TOTAL
    FY2015  heads 3,200,000.0  programmes 3,395,836.0  gap   5.8%  -> GRAND_TOTAL
    FY2016  heads 3,410,000.0  programmes 1,241,978.0  gap  63.6%  -> GRAND_TOTAL
    FY2017  heads 5,168,192.1  programmes 811,361.4  gap  84.3%  -> GRAND_TOTAL
    FY2018  heads 4,650,000.0  programmes 3,435,750.0  gap  26.1%  -> GRAND_TOTAL
    FY2019  heads 3,786,000.0  programmes 1,680,420.0  gap  55.6%  -> GRAND_TOTAL
    FY2012  extracted 97.8% of the document's own grand total 2,100,000.0
    FY2013  extracted 98.8% of the document's own grand total 2,300,000.0
    FY2014  extracted 100.5% of the document's own grand total 2,800,000.0
    FY2015  extracted 102.9% of the document's own grand total 3,300,000.0
    FY2016  extracted 100.0% of the document's own grand total 3,410,000.0
    FY2017  extracted 118.6% of the document's own grand total 4,356,830.8
    FY2018  extracted 100.0% of the document's own grand total 4,650,000.0
    FY2019  extracted 98.6% of the document's own grand total 3,840,000.0

READABILITY  14 of 776 programme name(s) unreadable (2%), 0 of 19 head(s) (0%), 15% of the money
    e.g. 'None' | 'None' | 'None'

PROGRAMME CLASS (share of programme money)
    development           5,940,094.6   38.3%  (517 programme-year rows)
    standing_function     6,937,147.7   44.7%  (211 programme-year rows)
    overhead              1,956,080.8   12.6%  (30 programme-year rows)
    mixed                   677,760.0    4.4%  (18 programme-year rows)

HEAD NAMES: 368 row(s) renamed so a head reads the same in every year

Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/fiji/budget_layer_all_years.xlsx
  sheet 'budget_all_years' : 803 rows  (feeds Prompt 6 / build_final_panel - each intervention matches against EVERY year's programs)
  sheet 'programs_wide'    : 329 programs x 8 year(s) (funding-over-time)
  sheet 'reconciliation'   : 19 rows (audit)
  sheet 'data_quality'     : 490 flagged items (see summary below)

==============================================================================
DATA-QUALITY SUMMARY
==============================================================================
  HIGH: 20   MEDIUM: 329   LOW: 133   INFO: 8

  [HIGH] granularity_mismatch  (1)
      - the years were not extracted to the same depth: FY2015 has 266 programme rows and FY2017 has 13, a factor of 20.5. Each year's totals may still be right, but a programme cannot be followed across years and any funding-over-time figure is comparing different levels of the same budget.

  [HIGH] over_extraction  (1)
      - FY2017: the heads extracted sum to 5,168,192.1 against a printed grand total of 4,356,830.8 (119%), so the same money is being counted more than once.

  [HIGH] reconciliation_mismatch  (18)
      - FY2012 strat 1: programs sum to 527,984.0 but strategy_total is 1,500,000.0 (gap 972,016.0) - a program line is likely missing or mis-extracted for this strategy-year.
      - FY2012 strat 2: programs sum to 149,046.0 but strategy_total is 554,000.0 (gap 404,954.0) - a program line is likely missing or mis-extracted for this strategy-year.
      - FY2013 strat 1: programs sum to 943,390.0 but strategy_total is 1,550,000.0 (gap 606,610.0) - a program line is likely missing or mis-extracted for this strategy-year.
      ... and 15 more (see 'data_quality' sheet)

  [MEDIUM] program_missing_in_year  (329)
      - FY2017,2018 strat 1 1.1: program '1.1' (Combat drug trafficking) exists in ['2012', '2013', '2014', '2015', '2016', '2019'] but is absent in ['2017', '2018'] - check whether it was dropped during extraction or genuinely did not exist that year.
      - FY2017,2018 strat 1 1.10: program '1.10' (Explore development of centralised bus stands in Nasinu and Nakasi corridors) exists in ['2012', '2013', '2014', '2015', '2016', '2019'] but is absent in ['2017', '2018'] - check whether it was dropped during extraction or genuinely did not exist that year.
      - FY2012,2013,2016,2017,2018,2019 strat 1 1.100: program '1.100' (Freedom of Information Act implementation) exists in ['2014', '2015'] but is absent in ['2012', '2013', '2016', '2017', '2018', '2019'] - check whether it was dropped during extraction or genuinely did not exist that year.
      ... and 326 more (see 'data_quality' sheet)

  [LOW] large_yoy_swing  (133)
      - FY2013->2014 strat 1 1.1: program '1.1' changed +1400% (1,000.0 -> 15,000.0) - verify this is real and not an extraction error.
      - FY2014->2015 strat 1 1.1: program '1.1' changed +3607% (15,000.0 -> 556,000.0) - verify this is real and not an extraction error.
      - FY2013->2014 strat 1 1.10: program '1.10' changed +1344% (1,800.0 -> 26,000.0) - verify this is real and not an extraction error.
      ... and 130 more (see 'data_quality' sheet)
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
  panel               : 220 strategies x 8 years (2012, 2013, 2014, 2015, 2016, 2017, 2018, 2019)
  match_review        : 2822 matches (BOTH names + rationale)
  unmatched_codes     : 0 (codes NOT in that year's budget - REVIEW)
  unfunded_strategies : 2 (strategies with no budget any year)
  funding_by_program  : 619 (per programme x year, amount once - SAFE TO SUM)
  unmapped_programs   : 157 budget programmes with no matched strategy
  risk_panel          : 11 risks | ceiling: PASS
  enrichment          : strategyclean=yes risk_summary=yes
  maturity            : mean=0.835 | financing-weighted=0.855 | {'operational_programme': 179, 'operational_funded': 12, 'partial_operation': 27, 'planned': 1, 'aspirational': 1}
  basket/reverse-pass : 499 shared programmes | reverse-pass edges=76 rows -> 0 new matches
  recall_review       : 32 large programmes matched to only 1 strategy (candidate baskets)
MATURITY: mean=0.835 financing_weighted=0.855
CEILING TEST: PASS - no strategy over-counted in any year
UNMATCHED CODES: 0
QA: PASS - 0 unmatched code(s), ceiling PASS, 0 year warning(s)
```

### build_analytics_html
```
dashboard -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/fiji/budget_strategy_analytics.html
  years        2012, 2013, 2014, 2015, 2016, 2017, 2018, 2019
  edges        2820
  strategies   220 (2 unfunded)
  size         877 KB
```

### audit_checks
```
AUDIT CHECKS: fiji 18/19 PASS (A16 3 untraceable)
  ok   A1   Stored programme sums              19 strategy-year(s) / 0 disagree
  ok   A2   Stored strategy totals             19 strategy-year(s) / 0 disagree
  ok   A3   Programme counted once             619 row(s) / 0 duplicate key(s)
  ok   A4   Ceiling holds                      19 strategy-year(s) / 0 over ceiling
  ok   A6   Panel money matches its edges      1760 strategy-year figure(s) / 0 disagree
  ok   A8   Edges cite real programmes         2822 accepted edge(s) / 0 dangle
  ok   A9   No strategy dropped                220 strategyclean row(s) / 220 panel row(s)
  ok   A10  Unfunded list is complete          2 zero-funded / 2 listed
  ok   A11  Evidence chain resolves            1629 distinct id(s) / 0 dangle
  ok   A12  Maturity summary is derivable      8 metric(s) / 0 disagree
  ok   A14  No duplicate edges                 2820 edge(s) / 0 duplicate(s)
  ok   A15  One currency                       1 expected / 1 found
  FAIL A16  Components are traceable           2137 component(s) / 3 untraceable
            Strengthen civil service capabilit <- Civil Service Planning, Implementation, and 
            Expand youth skills, entrepreneurs <- Inclusive Education for Children with Specia
            Promote gender equality, leadershi <- Women’s Equal Access Awareness Campaign
  ok   A17  No workbook open in Excel          0 expected / 0 found
  ok   A18  Strategies come from the plan      220 strategy(ies) / 0 with no component
  ok   A19  Funding priority is reproducible   215 distinct (salience, funding) group(s) / 0 split across priorities
  ok   A20  The budget is readable             776 programme(s) / 14 unreadable (2%), carrying 15% of the money
            FY2018 None: 'None'
            FY2018 None: 'None'
            FY2018 None: 'None'
            FY2018 None: 'None'
            FY2018 None: 'None'
            FY2018 None: 'None'
  ok   A21  Ambiguous codes name their head    1 repeated code(s) / 0 edge(s) do not name a head
  ok   A22  Every intervention is traceable to a strategy 1665 intervention(s) extracted / 36 uncited (2.2%)
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
  8 detected across 1 country(ies): 4 high, 2 medium, 2 low
  54 hand-written entr(ies) in 04_Docs_and_Planning/data_issues.json
  HIGH  fiji      D1       A programme code is not unique within a year
  HIGH  fiji      D12      An output predates the prompt that produced it
  HIGH  fiji      D7       Flag raised while combining the budget years
  HIGH  fiji      D8       A strategy total its own programmes do not add up to
```
