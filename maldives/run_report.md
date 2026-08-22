# Run report - Maldives

**🔴 Overall: REVIEW NEEDED**  
Generated 2026-08-22 11:56 by run_pipeline.py

| Stage | Ran | Key QA |
|---|---|---|
| validate_stage_schema (L2) | ok | QA FAIL - FAIL 4/11 (maldives_mapping_2017.xlsx, maldives_mapping_2018.xlsx, maldives_mapping_2019.xlsx) |
| validate_source_fidelity (L4) | ok | NOT CONFIGURED |
| validate_recall (L4) | ok | NOT CONFIGURED [advisory] |
| validate_refs (L3) | ok | QA FAIL - FAIL 1/1 (maldives references) |
| combine_budget_years | ok | reconcile=FAIL - see MISMATCH rows | data_quality=REVIEW NEEDED - resolve HIGH items before relying on totals for those strategy-years |
| build_final_panel | ok | QA FAIL - ceiling=PASS - no strategy over-counted in any year | unmatched_codes=312 |
| build_analytics_html | ok | strategies=261 (153 unfunded) | edges=216 |
| audit_checks | FAILED | QA FAIL - 18/19 PASS (A16 2 untraceable) [advisory] |
| data_issues | FAILED | 7 detected across 1 country(ies): 3 high, 3 medium, 1 low [advisory] |

## Outputs

- Budget layer: `Files/outputs/maldives/budget_layer_all_years.xlsx`
- FINAL panel (deliverable): `Files/outputs/maldives/FINAL_PANEL.xlsx`
- Dashboard: `Files/outputs/maldives/budget_strategy_analytics.html`
- Audit trail: `Files/outputs/union_dashboard.html`, Audit tab, filtered to this country
- Data oddities: `Files/outputs/DATA_ISSUES.xlsx`

## Full stage logs

### validate_stage_schema (L2)
```
--- maldives_budget_2017.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/maldives/validation/schema_maldives_budget_2017.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- maldives_budget_2018.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/maldives/validation/schema_maldives_budget_2018.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- maldives_budget_2019.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/maldives/validation/schema_maldives_budget_2019.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- maldives_coverage_2017.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/maldives/validation/schema_maldives_coverage_2017.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- maldives_coverage_2018.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/maldives/validation/schema_maldives_coverage_2018.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- maldives_coverage_2019.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/maldives/validation/schema_maldives_coverage_2019.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- maldives_mapping_2017.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/maldives/validation/schema_maldives_mapping_2017.xlsx

  RESULT: FAIL - 2 contract violation(s) across 1 file(s).
  The stage output is not accepted; re-run the stage or fix the prompt.

--- maldives_mapping_2018.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/maldives/validation/schema_maldives_mapping_2018.xlsx

  RESULT: FAIL - 4 contract violation(s) across 1 file(s).
  The stage output is not accepted; re-run the stage or fix the prompt.

--- maldives_mapping_2019.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/maldives/validation/schema_maldives_mapping_2019.xlsx

  RESULT: FAIL - 2 contract violation(s) across 1 file(s).
  The stage output is not accepted; re-run the stage or fix the prompt.

--- maldives_strategyclean.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/maldives/validation/schema_maldives_strategyclean.xlsx

  RESULT: FAIL - 5 contract violation(s) across 1 file(s).
  The stage output is not accepted; re-run the stage or fix the prompt.

--- maldives_risk_summary.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/maldives/validation/schema_maldives_risk_summary.xlsx

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
--- maldives references
RESULT: FAIL - 332 dangling reference(s) of 3311
report -> Files/outputs/maldives/validation/refs_maldives_references.xlsx
```

### combine_budget_years
```
==============================================================================
COMBINED BUDGET LAYER  -  years: 2017, 2018, 2019  (3 file(s))
==============================================================================

RECONCILIATION (per year: sum of program rows vs strategy_total)

  FY2017   (national total = 26,791,522,461.0)
    strat 1: total=13,881,748,090.0  progsum=23,185,312,192.0  ** MISMATCH diff=-9,303,564,102.0
    strat 2: total=12,541,564,079.0  progsum=8,366,648,627.0  ** MISMATCH diff=4,174,915,452.0
    strat 3: total= 300,000,000.0  progsum= 291,967,033.0  ** MISMATCH diff=8,032,967.0
    strat 4: total=  68,210,292.0  progsum=1,085,020,890.0  ** MISMATCH diff=-1,016,810,598.0

  FY2018   (national total = 24,248,670,940.0)
    strat 1: total= 106,937,119.0  progsum= 106,937,119.0  OK
    strat 2: total= 178,110,976.0  progsum=           0.0  ** MISMATCH diff=178,110,976.0
    strat 3: total=  10,808,542.0  progsum=           0.0  ** MISMATCH diff=10,808,542.0
    strat 4: total= 395,781,981.0  progsum= 395,781,981.0  OK
    strat 5: total= 116,640,968.0  progsum=           0.0  ** MISMATCH diff=116,640,968.0
    strat 6: total=  17,185,357.0  progsum=           0.0  ** MISMATCH diff=17,185,357.0
    strat 7: total=  22,617,101.0  progsum=           0.0  ** MISMATCH diff=22,617,101.0
    strat 8: total=  27,354,797.0  progsum=           0.0  ** MISMATCH diff=27,354,797.0
    strat 9: total=  50,599,993.0  progsum=           0.0  ** MISMATCH diff=50,599,993.0
    strat 10: total=  55,567,565.0  progsum=           0.0  ** MISMATCH diff=55,567,565.0
    strat 11: total=  76,578,436.0  progsum=           0.0  ** MISMATCH diff=76,578,436.0
    strat 12: total=   7,113,960.0  progsum=           0.0  ** MISMATCH diff=7,113,960.0
    strat 13: total=   3,871,575.0  progsum=           0.0  ** MISMATCH diff=3,871,575.0
    strat 14: total=   9,169,865.0  progsum=           0.0  ** MISMATCH diff=9,169,865.0
    strat 15: total=   4,148,333.0  progsum=           0.0  ** MISMATCH diff=4,148,333.0
    strat 16: total=  28,711,608.0  progsum=           0.0  ** MISMATCH diff=28,711,608.0
    strat 17: total=   3,750,412.0  progsum=           0.0  ** MISMATCH diff=3,750,412.0
    strat 18: total=   9,111,740.0  progsum=           0.0  ** MISMATCH diff=9,111,740.0
    strat 19: total= 619,747,281.0  progsum= 619,747,281.0  OK
    strat 20: total=1,240,859,935.0  progsum=1,240,859,935.0  OK
    strat 21: total= 457,853,358.0  progsum= 457,853,358.0  OK
    strat 22: total=2,609,006,595.0  progsum=2,609,006,595.0  OK
    strat 23: total=  33,798,897.0  progsum=           0.0  ** MISMATCH diff=33,798,897.0
    strat 24: total= 151,052,672.0  progsum= 151,052,672.0  OK
    strat 25: total= 220,622,470.0  progsum= 220,622,470.0  OK
    strat 26: total=1,286,241,727.0  progsum=1,286,508,682.0  ** MISMATCH diff=-266,955.0
    strat 27: total= 289,061,638.0  progsum= 289,061,638.0  OK
    strat 28: total= 547,333,257.0  progsum= 547,333,257.0  OK
    strat 29: total= 202,138,264.0  progsum= 202,138,264.0  OK
    strat 30: total=1,460,412,545.0  progsum=1,460,412,545.0  OK
    strat 31: total=  87,929,905.0  progsum=           0.0  ** MISMATCH diff=87,929,905.0
    strat 32: total= 313,772,568.0  progsum= 313,772,568.0  OK
    strat 33: total= 907,119,208.0  progsum= 907,119,208.0  OK
    strat 34: total=  22,362,856.0  progsum=           0.0  ** MISMATCH diff=22,362,856.0
    strat 35: total=  70,323,057.0  progsum=  70,323,057.0  OK
    strat 36: total=7,111,403,554.0  progsum=           0.0  ** MISMATCH diff=7,111,403,554.0
    strat 37: total=1,243,656,717.0  progsum=           0.0  ** MISMATCH diff=1,243,656,717.0
    strat 38: total=1,291,323,207.0  progsum=           0.0  ** MISMATCH diff=1,291,323,207.0
    strat 39: total= 196,905,766.0  progsum=           0.0  ** MISMATCH diff=196,905,766.0
    strat 40: total=1,085,922,672.0  progsum=           0.0  ** MISMATCH diff=1,085,922,672.0
    strat 41: total=1,120,999,134.0  progsum=1,120,999,134.0  OK
    strat 42: total= 554,763,329.0  progsum= 398,633,774.0  ** MISMATCH diff=156,129,555.0

  FY2019   (national total = 29,647.3)
    strat 1: total=       1,613.3  progsum=  75,313,347.0  ** MISMATCH diff=-75,311,733.7
    strat 2: total=       4,889.4  progsum= 685,209,227.0  ** MISMATCH diff=-685,204,337.6
    strat 3: total=       1,258.3  progsum= 299,484,547.0  ** MISMATCH diff=-299,483,288.7
    strat 4: total=       2,472.0  progsum= 549,298,857.0  ** MISMATCH diff=-549,296,385.0
    strat 5: total=       5,278.4  progsum=1,360,376,122.0  ** MISMATCH diff=-1,360,370,843.6
    strat 6: total=       1,588.7  progsum=2,690,493,443.0  ** MISMATCH diff=-2,690,491,854.3
    strat 7: total=       1,609.3  progsum=  55,013,327.0  ** MISMATCH diff=-55,011,717.7
    strat 8: total=       3,059.0  progsum= 396,448,307.0  ** MISMATCH diff=-396,445,248.0
    strat 9: total=         777.7  progsum= 201,259,017.0  ** MISMATCH diff=-201,258,239.3
    strat 10: total=       3,276.9  progsum= 744,903,944.0  ** MISMATCH diff=-744,900,667.1
    strat 11: total=       3,824.3  progsum= 142,620,122.0  ** MISMATCH diff=-142,616,297.7

RECONCILIATION: FAIL - see MISMATCH rows

NATIONAL TOTAL (the denominator every share is computed against)
    FY2017  heads 26,791,522,461.0  programmes 32,928,948,742.0  gap  18.6%  -> GRAND_TOTAL
    FY2018  heads 24,248,670,940.0  programmes 12,398,163,538.0  gap  48.9%  -> GRAND_TOTAL
    FY2019  heads 29,647.3  programmes 7,200,420,260.0  gap 100.0%  -> PROGRAMMES
    The head totals under-report in 1 year(s); the programme rows are the national budget there.
    FY2017  extracted 122.9% of the document's own grand total 26,791,522,461.0
    FY2018  extracted 99.9% of the document's own grand total 24,272,919,611.0

READABILITY  0 of 454 programme name(s) unreadable (0%), 0 of 57 head(s) (0%), 0% of the money

PROGRAMME CLASS (share of programme money)
    development        10,153,728,163.0   19.3%  (32 programme-year rows)
    standing_function  9,761,737,337.0   18.6%  (388 programme-year rows)
    overhead           32,612,067,040.0   62.1%  (34 programme-year rows)

HEAD NAMES: 67 row(s) renamed so a head reads the same in every year

Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/maldives/budget_layer_all_years.xlsx
  sheet 'budget_all_years' : 513 rows  (feeds Prompt 6 / build_final_panel - each intervention matches against EVERY year's programs)
  sheet 'programs_wide'    : 428 programs x 3 year(s) (funding-over-time)
  sheet 'reconciliation'   : 57 rows (audit)
  sheet 'data_quality'     : 611 flagged items (see summary below)

==============================================================================
DATA-QUALITY SUMMARY
==============================================================================
  HIGH: 47   MEDIUM: 561   LOW: 0   INFO: 3

  [HIGH] mixed_budget_views  (3)
      - FY2017: rows came from 3 different tables and together made 50,335,862,440.0 against a printed grand total of 26,791,522,461.0, so the same money was present twice. Kept 'Budget Information (1)' (26,791,522,461.0, the closest to the grand total) and dropped 446 row(s) from the others.
      - FY2018: rows came from 3 different tables and together made 28,667,968,991.0 against a printed grand total of 24,272,919,611.0, so the same money was present twice. Kept '2018 General Budget of Offices - Recurrent and Capital Expen' (24,248,670,940.0, the closest to the grand total) and dropped 57 row(s) from the others.
      - FY2019: rows came from 5 different tables and together made 31,140,233,705.8 against a printed grand total of 29,647.4, so the same money was present twice. Kept 'Table 2: Total expenditure by sector' (29,647.3, the closest to the grand total) and dropped 293 row(s) from the others.

  [HIGH] national_basis_programmes  (1)
      - FY2019: head totals sum to 29,647.3 but the programmes beneath them sum to 7,200,420,260.0 (100% apart), so the national total for this year is taken from the PROGRAMME rows. Every share for FY2019 is computed against 7,200,420,260.0.

  [HIGH] over_extraction  (1)
      - FY2017: the heads extracted sum to 32,928,948,742.0 against a printed grand total of 26,791,522,461.0 (123%), so the same money is being counted more than once.

  [HIGH] reconciliation_mismatch  (41)
      - FY2017 strat 1: programs sum to 23,185,312,192.0 but strategy_total is 13,881,748,090.0 (gap -9,303,564,102.0) - a program line is likely missing or mis-extracted for this strategy-year.
      - FY2017 strat 2: programs sum to 8,366,648,627.0 but strategy_total is 12,541,564,079.0 (gap 4,174,915,452.0) - a program line is likely missing or mis-extracted for this strategy-year.
      - FY2017 strat 3: programs sum to 291,967,033.0 but strategy_total is 300,000,000.0 (gap 8,032,967.0) - a program line is likely missing or mis-extracted for this strategy-year.
      ... and 38 more (see 'data_quality' sheet)

  [HIGH] scale_mismatch  (1)
      - the years are not in the same scale: FY2017 states 26,791,522,461.0 and FY2019 states 29,647.3, a factor of 903675, and both are labelled 'MVR'. A national budget does not change by that much between years, so one extraction is in absolute currency and the other in millions. Every cross-year figure is wrong until they agree.

  [MEDIUM] blank_amount  (63)
      - FY2017 strat 1 1.5: amount is blank/unparseable.
      - FY2018 strat 42 42.017: amount is blank/unparseable.
      - FY2018 strat 42 42.018: amount is blank/unparseable.
      ... and 60 more (see 'data_quality' sheet)

  [MEDIUM] malformed_code_repaired  (6)
      - FY2017 strat 1 1.17: program_code '17' looked malformed and was normalized to '1.17' - verify against source; fix the year file to avoid this.
      - FY2017 strat 2 2.17: program_code '17' looked malformed and was normalized to '2.17' - verify against source; fix the year file to avoid this.
      - FY2017 strat 3 3.17: program_code '17' looked malformed and was normalized to '3.17' - verify against source; fix the year file to avoid this.
      ... and 3 more (see 'data_quality' sheet)

  [MEDIUM] no_grand_total  (1)
      - FY2019: the document printed no grand total that stage 5 could find, so there is nothing to check the extraction's completeness against. Every share for FY2019 rests on the heads being all of them.

  [MEDIUM] program_missing_in_year  (428)
      - FY2019 strat 1 1.001: program '1.001' (President's Office) exists in ['2017', '2018'] but is absent in ['2019'] - check whether it was dropped during extraction or genuinely did not exist that year.
      - FY2019 strat 1 1.002: program '1.002' (Official Residence of the President) exists in ['2017', '2018'] but is absent in ['2019'] - check whether it was dropped during extraction or genuinely did not exist that year.
      - FY2019 strat 1 1.003: program '1.003' (Official Residence of the Vice President) exists in ['2017', '2018'] but is absent in ['2019'] - check whether it was dropped during extraction or genuinely did not exist that year.
      ... and 425 more (see 'data_quality' sheet)

  [MEDIUM] zero_amount_programme  (63)
      - FY2017 strat 1 1.5: programme carries no money; a strategy matched only to lines like this reads as funded while receiving nothing
      - FY2018 strat 42 42.017: programme carries no money; a strategy matched only to lines like this reads as funded while receiving nothing
      - FY2018 strat 42 42.018: programme carries no money; a strategy matched only to lines like this reads as funded while receiving nothing
      ... and 60 more (see 'data_quality' sheet)
==============================================================================
DATA QUALITY: REVIEW NEEDED - resolve HIGH items before relying on totals for those strategy-years
==============================================================================
```

### build_final_panel
```
STALE EDGES DROPPED: 1 edge(s) name a strategy the inventory does not hold (prog=1)
   ! Agricultural production, markets, and value chain development
   Re-run the stage that produced them against the current strategyclean.

Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/maldives/FINAL_PANEL.xlsx
  panel               : 261 strategies x 3 years (2017, 2018, 2019)
  match_review        : 528 matches (BOTH names + rationale)
  unmatched_codes     : 312 (codes NOT in that year's budget - REVIEW)  <-- !!
  unfunded_strategies : 153 (strategies with no budget any year)
  funding_by_program  : 97 (per programme x year, amount once - SAFE TO SUM)
  unmapped_programs   : 357 budget programmes with no matched strategy
  risk_panel          : 10 risks | ceiling: PASS
  enrichment          : strategyclean=yes risk_summary=yes
  maturity            : mean=0.509 | financing-weighted=0.754 | {'operational_programme': 9, 'partial_operation': 96, 'operational_funded': 3, 'planned': 128, 'planned_specific': 21, 'aspirational': 4}
  basket/reverse-pass : 46 shared programmes | reverse-pass edges=1 rows -> 0 new matches
  recall_review       : 11 large programmes matched to only 1 strategy (candidate baskets)
MATURITY: mean=0.509 financing_weighted=0.754
CEILING TEST: PASS - no strategy over-counted in any year
UNMATCHED CODES: 312
QA: FAIL - 312 unmatched code(s), ceiling PASS, 0 year warning(s)
```

### build_analytics_html
```
dashboard -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/maldives/budget_strategy_analytics.html
  years        2017, 2018, 2019
  edges        216
  strategies   261 (153 unfunded)
  size         83 KB
```

### audit_checks
```
AUDIT CHECKS: maldives 18/19 PASS (A16 2 untraceable)
  ok   A1   Stored programme sums              57 strategy-year(s) / 0 disagree
  ok   A2   Stored strategy totals             57 strategy-year(s) / 0 disagree
  ok   A3   Programme counted once             97 row(s) / 0 duplicate key(s)
  ok   A4   Ceiling holds                      57 strategy-year(s) / 0 over ceiling
  ok   A6   Panel money matches its edges      783 strategy-year figure(s) / 0 disagree
  ok   A8   Edges cite real programmes         528 accepted edge(s) / 0 dangle
  ok   A9   No strategy dropped                261 strategyclean row(s) / 261 panel row(s)
  ok   A10  Unfunded list is complete          153 zero-funded / 153 listed
  ok   A11  Evidence chain resolves            2705 distinct id(s) / 0 dangle
  ok   A12  Maturity summary is derivable      8 metric(s) / 0 disagree
  ok   A14  No duplicate edges                 216 edge(s) / 0 duplicate(s)
  ok   A15  One currency                       1 expected / 1 found
  FAIL A16  Components are traceable           2803 component(s) / 2 untraceable
            Gender equality law and institutio <- Women's Political Participation and Decision
            Women's economic empowerment, entr <- Women's Economic Participation and Shared Ca
  ok   A17  No workbook open in Excel          0 expected / 0 found
  ok   A18  Strategies come from the plan      261 strategy(ies) / 0 with no component
  ok   A19  Funding priority is reproducible   71 distinct (salience, funding) group(s) / 0 split across priorities
  ok   A20  The budget is readable             454 programme(s) / 0 unreadable (0%), carrying 0% of the money
  ok   A21  Ambiguous codes name their head    0 repeated code(s) / 0 edge(s) do not name a head
  ok   A22  Consolidation keeps every intervention 2727 intervention(s) extracted / 22 dropped (0.8%)
            149
            154
            282
            346
            469
            712
  --   A23  The sector layer stayed out of the panel no sector run for this country
```

### data_issues
```
data issues  Files/outputs/DATA_ISSUES.xlsx
  7 detected across 1 country(ies): 3 high, 3 medium, 1 low
  51 hand-written entr(ies) in 04_Docs_and_Planning/data_issues.json
  HIGH  maldives  D12      An output predates the prompt that produced it
  HIGH  maldives  D7       Flag raised while combining the budget years
  HIGH  maldives  D8       A strategy total its own programmes do not add up to
```
