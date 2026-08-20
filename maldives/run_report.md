# Run report - Maldives

**🔴 Overall: REVIEW NEEDED**  
Generated 2026-08-20 14:09 by run_pipeline.py

| Stage | Ran | Key QA |
|---|---|---|
| validate_stage_schema (L2) | ok | QA FAIL - FAIL 4/11 (maldives_budget_2017.xlsx, maldives_budget_2018.xlsx, maldives_mapping_2018.xlsx) |
| validate_source_fidelity (L4) | ok | NOT CONFIGURED |
| validate_recall (L4) | ok | NOT CONFIGURED [advisory] |
| validate_refs (L3) | ok | QA FAIL - FAIL 1/1 (maldives references) |
| combine_budget_years | ok | reconcile=FAIL - see MISMATCH rows | data_quality=REVIEW NEEDED - resolve HIGH items before relying on totals for those strategy-years |
| build_final_panel | ok | QA FAIL - ceiling=FAIL - see ceiling sheet | unmatched_codes=0 |
| build_analytics_html | ok | strategies=261 (251 unfunded) | edges=20 |
| audit_checks | FAILED | QA FAIL - 13/16 PASS (A2 8 disagree, A4 1 over ceiling, A16 2 untraceable) [advisory] |
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

  RESULT: FAIL - 3 contract violation(s) across 1 file(s).
  The stage output is not accepted; re-run the stage or fix the prompt.

--- maldives_budget_2018.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/maldives/validation/schema_maldives_budget_2018.xlsx

  RESULT: FAIL - 160 contract violation(s) across 1 file(s).
  The stage output is not accepted; re-run the stage or fix the prompt.

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

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- maldives_mapping_2018.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/maldives/validation/schema_maldives_mapping_2018.xlsx

  RESULT: FAIL - 1 contract violation(s) across 1 file(s).
  The stage output is not accepted; re-run the stage or fix the prompt.

--- maldives_mapping_2019.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/maldives/validation/schema_maldives_mapping_2019.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

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
RESULT: FAIL - 7 dangling reference(s) of 2783
report -> Files/outputs/maldives/validation/refs_maldives_references.xlsx
```

### combine_budget_years
```
==============================================================================
COMBINED BUDGET LAYER  -  years: 2017, 2018, 2019  (3 file(s))
==============================================================================

RECONCILIATION (per year: sum of program rows vs strategy_total)

  FY2017   (national total = 23,007,352,858.0)
    strat 1: total= 101,334,724.0  progsum= 371,971,798.0  ** MISMATCH diff=-270,637,074.0
    strat 2: total= 208,402,975.0  progsum=1,780,849,664.0  ** MISMATCH diff=-1,572,446,689.0
    strat 3: total=  10,854,474.0  progsum= 291,704,544.0  ** MISMATCH diff=-280,850,070.0
    strat 4: total= 367,654,006.0  progsum= 952,692,855.0  ** MISMATCH diff=-585,038,849.0
    strat 5: total=  35,615,361.0  progsum= 796,853,288.0  ** MISMATCH diff=-761,237,927.0
    strat 6: total=  19,009,362.0  progsum=2,294,511,756.0  ** MISMATCH diff=-2,275,502,394.0
    strat 7: total=  22,661,255.0  progsum= 266,705,093.0  ** MISMATCH diff=-244,043,838.0
    strat 8: total=  27,923,748.0  progsum= 494,853,833.0  ** MISMATCH diff=-466,930,085.0
    strat 9: total=  45,000,002.0  progsum= 451,821,391.0  ** MISMATCH diff=-406,821,389.0
    strat 10: total=  35,391,792.0  progsum= 603,169,808.0  ** MISMATCH diff=-567,778,016.0
    strat 11: total=  59,843,651.0  progsum=  84,903,354.0  ** MISMATCH diff=-25,059,703.0
    strat 12: total=   6,993,896.0  progsum=           0.0  ** MISMATCH diff=6,993,896.0
    strat 13: total=   3,626,872.0  progsum=           0.0  ** MISMATCH diff=3,626,872.0
    strat 14: total=   9,198,520.0  progsum=           0.0  ** MISMATCH diff=9,198,520.0
    strat 15: total=   4,223,952.0  progsum=           0.0  ** MISMATCH diff=4,223,952.0
    strat 16: total=  44,828,700.0  progsum=           0.0  ** MISMATCH diff=44,828,700.0
    strat 17: total=   3,834,836.0  progsum=           0.0  ** MISMATCH diff=3,834,836.0
    strat 18: total=   9,410,777.0  progsum=           0.0  ** MISMATCH diff=9,410,777.0
    strat 19: total=8,464,826,356.0  progsum=8,464,826,356.0  OK
    strat 20: total=1,150,675,281.0  progsum=1,150,675,281.0  OK
    strat 21: total=1,955,807,347.0  progsum=1,955,807,347.0  OK
    strat 22: total=2,518,314,582.0  progsum=2,518,314,582.0  OK
    strat 23: total=  30,441,098.0  progsum=           0.0  ** MISMATCH diff=30,441,098.0
    strat 24: total= 142,746,893.0  progsum= 142,746,893.0  OK
    strat 25: total= 186,829,553.0  progsum= 186,829,553.0  OK
    strat 26: total=2,589,886,058.0  progsum=2,589,886,058.0  OK
    strat 27: total= 213,941,310.0  progsum= 213,941,310.0  OK
    strat 28: total= 825,395,191.0  progsum= 825,395,191.0  OK
    strat 29: total= 245,383,805.0  progsum= 245,383,805.0  OK
    strat 30: total=1,519,449,847.0  progsum=1,519,449,847.0  OK
    strat 31: total= 121,190,690.0  progsum=           0.0  ** MISMATCH diff=121,190,690.0
    strat 32: total= 343,336,545.0  progsum= 343,336,545.0  OK
    strat 33: total=1,027,254,755.0  progsum=1,027,254,755.0  OK
    strat 34: total=  23,864,940.0  progsum=           0.0  ** MISMATCH diff=23,864,940.0
    strat 35: total=  71,038,799.0  progsum=  71,038,799.0  OK
    strat 36: total= 561,160,905.0  progsum= 561,160,905.0  OK
    strat 37: total=           0.0  progsum=           0.0  OK
    strat 38: total=           0.0  progsum=           0.0  OK
    strat 39: total=           0.0  progsum=           0.0  OK

  FY2018   (national total = 21,753,879,903.0)
    strat 1: total=     136,000.0  progsum=     136,000.0  OK
    strat 3: total=       9,723.0  progsum=           0.0  ** MISMATCH diff=9,723.0
    strat 4: total=  12,057,704.0  progsum=  12,057,705.0  ** MISMATCH diff=-1.0
    strat 5: total=     362,828.0  progsum=           0.0  ** MISMATCH diff=362,828.0
    strat 6: total=      19,470.0  progsum=           0.0  ** MISMATCH diff=19,470.0
    strat 7: total=      53,545.0  progsum=           0.0  ** MISMATCH diff=53,545.0
    strat 8: total=      66,110.0  progsum=           0.0  ** MISMATCH diff=66,110.0
    strat 9: total=     444,724.0  progsum=           0.0  ** MISMATCH diff=444,724.0
    strat 10: total=     131,985.0  progsum=           0.0  ** MISMATCH diff=131,985.0
    strat 11: total=16,739,705,581.0  progsum=           0.0  ** MISMATCH diff=16,739,705,581.0
    strat 12: total=      33,744.0  progsum=           0.0  ** MISMATCH diff=33,744.0
    strat 13: total=           0.0  progsum=           0.0  OK
    strat 14: total=   8,262,000.0  progsum=           0.0  ** MISMATCH diff=8,262,000.0
    strat 15: total=           0.0  progsum=           0.0  OK
    strat 16: total=           0.0  progsum=           0.0  OK
    strat 17: total=       1,000.0  progsum=           0.0  ** MISMATCH diff=1,000.0
    strat 18: total=      36,000.0  progsum=           0.0  ** MISMATCH diff=36,000.0
    strat 19: total=1,513,867,475.0  progsum=1,513,867,475.0  OK
    strat 20: total=  16,692,428.0  progsum=  16,692,428.0  OK
    strat 21: total= 162,188,162.0  progsum= 162,188,161.0  ** MISMATCH diff=1.0
    strat 22: total=  12,145,452.0  progsum=  12,145,453.0  ** MISMATCH diff=-1.0
    strat 23: total=      92,000.0  progsum=           0.0  ** MISMATCH diff=92,000.0
    strat 24: total=     321,959.0  progsum=     321,959.0  OK
    strat 25: total=      67,467.0  progsum=      67,467.0  OK
    strat 26: total=  44,903,335.0  progsum=  44,903,334.0  ** MISMATCH diff=1.0
    strat 27: total=  68,724,807.0  progsum=  68,724,807.0  OK
    strat 28: total=   3,187,655.0  progsum=   3,187,654.0  ** MISMATCH diff=1.0
    strat 29: total=   1,464,456.0  progsum=   1,464,456.0  OK
    strat 30: total=  15,468,340.0  progsum=  15,468,340.0  OK
    strat 31: total=   8,613,007.0  progsum=           0.0  ** MISMATCH diff=8,613,007.0
    strat 32: total=   1,031,000.0  progsum=   1,031,000.0  OK
    strat 33: total=   6,784,048.0  progsum=   6,784,048.0  OK
    strat 34: total=     175,500.0  progsum=           0.0  ** MISMATCH diff=175,500.0
    strat 35: total=      35,600.0  progsum=      35,600.0  OK
    strat 36: total=           0.0  progsum=           0.0  OK
    strat 37: total=           0.0  progsum=           0.0  OK
    strat 38: total=     487,182.0  progsum=           0.0  ** MISMATCH diff=487,182.0
    strat 39: total=3,095,791,158.0  progsum=           0.0  ** MISMATCH diff=3,095,791,158.0
    strat 40: total=     102,980.0  progsum=           0.0  ** MISMATCH diff=102,980.0
    strat 41: total=  34,682,967.0  progsum=  34,682,967.0  OK
    strat 42: total=   5,732,511.0  progsum=   5,732,511.0  OK

  FY2019   (national total = 121,034,448.3)
    strat 01: total= 121,008,144.0  progsum=           0.0  ** MISMATCH diff=121,008,144.0
    strat 211: total=       4,342.8  progsum=       4,342.9  ** MISMATCH diff=-0.1
    strat 212: total=       3,608.6  progsum=       3,609.8  ** MISMATCH diff=-1.2
    strat 213: total=       1,564.8  progsum=       1,564.8  OK
    strat 221: total=         136.9  progsum=         137.0  ** MISMATCH diff=-0.1
    strat 222: total=         608.0  progsum=         607.9  ** MISMATCH diff=0.1
    strat 223: total=       1,850.9  progsum=       1,850.9  OK
    strat 224: total=         657.2  progsum=         657.2  OK
    strat 225: total=         411.1  progsum=         411.2  ** MISMATCH diff=-0.1
    strat 226: total=         276.0  progsum=         276.0  OK
    strat 227: total=       2,001.5  progsum=       2,001.5  OK
    strat 228: total=       2,772.6  progsum=       2,772.6  OK
    strat 281: total=          50.4  progsum=          50.4  OK
    strat 291: total=           0.8  progsum=           0.8  OK
    strat 292: total=         411.0  progsum=         411.0  OK
    strat 421: total=       1,209.6  progsum=       1,209.5  ** MISMATCH diff=0.1
    strat 422: total=       2,176.0  progsum=       2,176.0  OK
    strat 423: total=         441.8  progsum=         393.7  ** MISMATCH diff=48.1
    strat 440: total=         806.4  progsum=         806.4  OK
    strat 720: total=       2,887.9  progsum=       2,887.9  OK
    strat 730: total=          90.0  progsum=          90.0  OK

RECONCILIATION: FAIL - see MISMATCH rows

PROGRAMME CLASS (share of programme money)
    development         939,353,088.0    2.9%  (8 programme-year rows)
    standing_function  2,158,845,140.5    6.7%  (495 programme-year rows)
    overhead            403,103,665.0    1.3%  (3 programme-year rows)
    mixed              28,604,300,340.0   89.1%  (346 programme-year rows)

HEAD NAMES: 452 row(s) renamed so a head reads the same in every year

Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/maldives/budget_layer_all_years.xlsx
  sheet 'budget_all_years' : 953 rows  (feeds Prompt 6 / build_final_panel - each intervention matches against EVERY year's programs)
  sheet 'programs_wide'    : 680 programs x 3 year(s) (funding-over-time)
  sheet 'reconciliation'   : 101 rows (audit)
  sheet 'data_quality'     : 1019 flagged items (see summary below)

==============================================================================
DATA-QUALITY SUMMARY
==============================================================================
  HIGH: 52   MEDIUM: 962   LOW: 2   INFO: 3

  [HIGH] reconciliation_mismatch  (52)
      - FY2017 strat 1: programs sum to 371,971,798.0 but strategy_total is 101,334,724.0 (gap -270,637,074.0) - a program line is likely missing or mis-extracted for this strategy-year.
      - FY2017 strat 2: programs sum to 1,780,849,664.0 but strategy_total is 208,402,975.0 (gap -1,572,446,689.0) - a program line is likely missing or mis-extracted for this strategy-year.
      - FY2017 strat 3: programs sum to 291,704,544.0 but strategy_total is 10,854,474.0 (gap -280,850,070.0) - a program line is likely missing or mis-extracted for this strategy-year.
      ... and 49 more (see 'data_quality' sheet)

  [MEDIUM] blank_amount  (106)
      - FY2017 strat 1 1.5: amount is blank/unparseable.
      - FY2017 strat 20 20.003: amount is blank/unparseable.
      - FY2017 strat 26 26.009: amount is blank/unparseable.
      ... and 103 more (see 'data_quality' sheet)

  [MEDIUM] malformed_code_repaired  (176)
      - FY2019 strat 211 211.211001: program_code '211001' looked malformed and was normalized to '211.211001' - verify against source; fix the year file to avoid this.
      - FY2019 strat 211 211.211002: program_code '211002' looked malformed and was normalized to '211.211002' - verify against source; fix the year file to avoid this.
      - FY2019 strat 212 212.212002: program_code '212002' looked malformed and was normalized to '212.212002' - verify against source; fix the year file to avoid this.
      ... and 173 more (see 'data_quality' sheet)

  [MEDIUM] program_missing_in_year  (680)
      - FY2019 strat 1 1.001: program '1.001' (+3) exists in ['2017', '2018'] but is absent in ['2019'] - check whether it was dropped during extraction or genuinely did not exist that year.
      - FY2019 strat 1 1.002: program '1.002' (Se Hará) exists in ['2017', '2018'] but is absent in ['2019'] - check whether it was dropped during extraction or genuinely did not exist that year.
      - FY2019 strat 1 1.003: program '1.003' (Sp 322 9892) exists in ['2017', '2018'] but is absent in ['2019'] - check whether it was dropped during extraction or genuinely did not exist that year.
      ... and 677 more (see 'data_quality' sheet)

  [LOW] large_yoy_swing  (2)
      - FY2017->2018 strat 19 19.001: program '19.001' changed +726% (182,168,767.0 -> 1,504,471,755.0) - verify this is real and not an extraction error.
      - FY2017->2018 strat 27 27.004: program '27.004' changed +961% (4,686,782.0 -> 49,731,428.0) - verify this is real and not an extraction error.
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
  match_review        : 20 matches (BOTH names + rationale)
  unmatched_codes     : 0 (codes NOT in that year's budget - REVIEW)
  unfunded_strategies : 251 (strategies with no budget any year)
  funding_by_program  : 16 (per programme x year, amount once - SAFE TO SUM)
  unmapped_programs   : 836 budget programmes with no matched strategy
  risk_panel          : 10 risks | ceiling: FAIL - see 'ceiling' sheet
  enrichment          : strategyclean=yes risk_summary=yes
  maturity            : mean=0.369 | financing-weighted=0.7 | {'partial_operation': 10, 'aspirational': 12, 'planned_specific': 33, 'planned': 206}
  basket/reverse-pass : 4 shared programmes | reverse-pass edges=1 rows -> 0 new matches
  recall_review       : 4 large programmes matched to only 1 strategy (candidate baskets)
MATURITY: mean=0.369 financing_weighted=0.7
CEILING TEST: FAIL - see ceiling sheet
UNMATCHED CODES: 0
QA: FAIL - 0 unmatched code(s), ceiling FAIL, 0 year warning(s)
```

### build_analytics_html
```
dashboard -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/maldives/budget_strategy_analytics.html
  years        2017, 2018, 2019
  edges        20
  strategies   261 (251 unfunded)
  size         33 KB
```

### audit_checks
```
AUDIT CHECKS: maldives 13/16 PASS (A2 8 disagree, A4 1 over ceiling, A16 2 untraceable)
  ok   A1   Stored programme sums              101 strategy-year(s) / 0 disagree
  FAIL A2   Stored strategy totals             101 strategy-year(s) / 8 disagree
            FY2017 strategy 37: stored 0.0, layer -
            FY2017 strategy 38: stored 0.0, layer -
            FY2017 strategy 39: stored 0.0, layer -
            FY2018 strategy 13: stored 0.0, layer -
            FY2018 strategy 15: stored 0.0, layer -
            FY2018 strategy 16: stored 0.0, layer -
  ok   A3   Programme counted once             16 row(s) / 0 duplicate key(s)
  FAIL A4   Ceiling holds                      101 strategy-year(s) / 1 over ceiling
            FY2017 strategy 5: matched 431,283,126.0 of 35,615,361.0
  ok   A6   Panel money matches its edges      783 strategy-year figure(s) / 0 disagree
  ok   A8   Edges cite real programmes         20 accepted edge(s) / 0 dangle
  ok   A9   No strategy dropped                261 strategyclean row(s) / 261 panel row(s)
  ok   A10  Unfunded list is complete          251 zero-funded / 251 listed
  ok   A11  Evidence chain resolves            2705 distinct id(s) / 0 dangle
  ok   A12  Maturity summary is derivable      8 metric(s) / 0 disagree
  ok   A14  No duplicate edges                 20 edge(s) / 0 duplicate(s)
  ok   A15  One currency                       1 expected / 1 found
  FAIL A16  Components are traceable           2803 component(s) / 2 untraceable
            Gender equality law and institutio <- Women's Political Participation and Decision
            Women's economic empowerment, entr <- Women's Economic Participation and Shared Ca
  ok   A17  No workbook open in Excel          0 expected / 0 found
  ok   A18  Strategies come from the plan      261 strategy(ies) / 0 with no component
  ok   A19  Funding priority is reproducible   12 distinct (salience, funding) group(s) / 0 split across priorities
```

### data_issues
```
data issues  Files/outputs/DATA_ISSUES.xlsx
  7 detected across 1 country(ies): 3 high, 3 medium, 1 low
  31 hand-written entr(ies) in 04_Docs_and_Planning/data_issues.json
  HIGH  maldives  D12      An output predates the prompt that produced it
  HIGH  maldives  D7       Flag raised while combining the budget years
  HIGH  maldives  D8       A strategy total its own programmes do not add up to
```
