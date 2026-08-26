# Run report - Kiribati

**🔴 Overall: REVIEW NEEDED**  
Generated 2026-08-26 00:51 by run_pipeline.py

| Stage | Ran | Key QA |
|---|---|---|
| validate_stage_schema (L2) | ok | QA FAIL - FAIL 3/10 (kiribati_budget_2023.xlsx, kiribati_budget_2024.xlsx, kiribati_budget_2026.xlsx) |
| validate_source_fidelity (L4) | ok | NOT CONFIGURED |
| validate_recall (L4) | ok | NOT CONFIGURED [advisory] |
| validate_refs (L3) | ok | PASS 1/1 |
| combine_budget_years | ok | reconcile=FAIL - see MISMATCH rows | data_quality=REVIEW NEEDED - resolve HIGH items before relying on totals for those strategy-years |
| build_final_panel | ok | ceiling=PASS - no strategy over-counted in any year | unmatched_codes=0 |
| build_analytics_html | ok | strategies=56 (11 unfunded) | edges=221 |
| audit_checks | FAILED | QA FAIL - 18/19 PASS (A2 1 disagree) [advisory] |
| data_issues | FAILED | 6 detected across 1 country(ies): 2 high, 3 medium, 1 low [advisory] |

## Outputs

- Budget layer: `Files/outputs/kiribati/budget_layer_all_years.xlsx`
- FINAL panel (deliverable): `Files/outputs/kiribati/FINAL_PANEL.xlsx`
- Dashboard: `Files/outputs/kiribati/budget_strategy_analytics.html`
- Audit trail: `Files/outputs/union_dashboard.html`, Audit tab, filtered to this country
- Data oddities: `Files/outputs/DATA_ISSUES.xlsx`

## Full stage logs

### validate_stage_schema (L2)
```
--- kiribati_budget_2023.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/kiribati/validation/schema_kiribati_budget_2023.xlsx

  RESULT: FAIL - 2 contract violation(s) across 1 file(s).
  The stage output is not accepted; re-run the stage or fix the prompt.

--- kiribati_budget_2024.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/kiribati/validation/schema_kiribati_budget_2024.xlsx

  RESULT: FAIL - 14 contract violation(s) across 1 file(s).
  The stage output is not accepted; re-run the stage or fix the prompt.

--- kiribati_budget_2025.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/kiribati/validation/schema_kiribati_budget_2025.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- kiribati_budget_2026.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/kiribati/validation/schema_kiribati_budget_2026.xlsx

  RESULT: FAIL - 1 contract violation(s) across 1 file(s).
  The stage output is not accepted; re-run the stage or fix the prompt.

--- kiribati_mapping_2023.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/kiribati/validation/schema_kiribati_mapping_2023.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- kiribati_mapping_2024.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/kiribati/validation/schema_kiribati_mapping_2024.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- kiribati_mapping_2025.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/kiribati/validation/schema_kiribati_mapping_2025.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- kiribati_mapping_2026.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/kiribati/validation/schema_kiribati_mapping_2026.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- kiribati_strategyclean.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/kiribati/validation/schema_kiribati_strategyclean.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- kiribati_risk_summary.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/kiribati/validation/schema_kiribati_risk_summary.xlsx

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
--- kiribati references
RESULT: PASS - every one of 474 reference(s) resolves
report -> Files/outputs/kiribati/validation/refs_kiribati_references.xlsx
```

### combine_budget_years
```
==============================================================================
COMBINED BUDGET LAYER  -  years: 2023, 2024, 2025, 2026  (4 file(s))
==============================================================================

RECONCILIATION (per year: sum of program rows vs strategy_total)

  FY2023   (national total = 277,562,218.0)
    strat 09: total=   8,765,859.0  progsum=           0.0  ** MISMATCH diff=8,765,859.0
    strat 10: total=   7,932,651.0  progsum=           0.0  ** MISMATCH diff=7,932,651.0
    strat 11: total=           0.0  progsum=           0.0  OK
    strat 12: total=           0.0  progsum=           0.0  OK
    strat 13: total=           0.0  progsum=           0.0  OK
    strat 14: total=     317,118.0  progsum=           0.0  ** MISMATCH diff=317,118.0
    strat 15: total=   1,019,486.0  progsum=           0.0  ** MISMATCH diff=1,019,486.0
    strat 16: total=   4,369,016.0  progsum=           0.0  ** MISMATCH diff=4,369,016.0
    strat 17: total=           0.0  progsum=           0.0  OK
    strat 18: total=   2,845,310.0  progsum=           0.0  ** MISMATCH diff=2,845,310.0
    strat 20: total=           0.0  progsum=           0.0  OK
    strat 21: total=  14,432,381.0  progsum=           0.0  ** MISMATCH diff=14,432,381.0
    strat 22: total=  24,064,736.0  progsum=           0.0  ** MISMATCH diff=24,064,736.0
    strat 23: total=  25,848,062.0  progsum=           0.0  ** MISMATCH diff=25,848,062.0
    strat 24: total=   7,315,647.0  progsum=           0.0  ** MISMATCH diff=7,315,647.0
    strat 25: total=  73,688,332.0  progsum=           0.0  ** MISMATCH diff=73,688,332.0
    strat 26: total=  35,314,890.0  progsum=           0.0  ** MISMATCH diff=35,314,890.0
    strat 27: total=  53,822,725.0  progsum=           0.0  ** MISMATCH diff=53,822,725.0
    strat 28: total=  10,746,833.0  progsum=           0.0  ** MISMATCH diff=10,746,833.0
    strat 29: total=   6,597,172.0  progsum=           0.0  ** MISMATCH diff=6,597,172.0
    strat 37: total=     482,000.0  progsum=           0.0  ** MISMATCH diff=482,000.0

  FY2024   (national total = 315,138,076.0)
    strat 09: total=   9,018,195.0  progsum=  35,283,381.0  ** MISMATCH diff=-26,265,186.0
    strat 10: total=   4,470,130.0  progsum=  29,798,166.0  ** MISMATCH diff=-25,328,036.0
    strat 11: total=   2,541,500.0  progsum=           0.0  ** MISMATCH diff=2,541,500.0
    strat 12: total=     249,000.0  progsum=     834,748.0  ** MISMATCH diff=-585,748.0
    strat 14: total=     131,000.0  progsum=     928,252.0  ** MISMATCH diff=-797,252.0
    strat 15: total=   1,500,000.0  progsum=     108,023.0  ** MISMATCH diff=1,391,977.0
    strat 16: total=   4,698,799.0  progsum=  30,818,502.0  ** MISMATCH diff=-26,119,703.0
    strat 18: total=      65,500.0  progsum=   2,358,038.0  ** MISMATCH diff=-2,292,538.0
    strat 21: total=   7,684,659.0  progsum=  50,720,631.0  ** MISMATCH diff=-43,035,972.0
    strat 22: total=  42,757,940.0  progsum= 112,612,251.0  ** MISMATCH diff=-69,854,311.0
    strat 23: total=  26,071,238.0  progsum=  65,135,477.0  ** MISMATCH diff=-39,064,239.0
    strat 24: total=   5,934,172.0  progsum= 112,064,903.0  ** MISMATCH diff=-106,130,731.0
    strat 25: total=  77,605,428.0  progsum=  53,312,116.0  ** MISMATCH diff=24,293,312.0
    strat 26: total=  31,988,717.0  progsum=   8,853,283.0  ** MISMATCH diff=23,135,434.0
    strat 27: total=  77,441,580.0  progsum= 340,441,654.0  ** MISMATCH diff=-263,000,074.0
    strat 28: total=  13,376,154.0  progsum=  40,760,881.0  ** MISMATCH diff=-27,384,727.0
    strat 29: total=   9,370,064.0  progsum=  21,911,272.0  ** MISMATCH diff=-12,541,208.0
    strat 37: total=     234,000.0  progsum=   1,811,413.0  ** MISMATCH diff=-1,577,413.0

  FY2025   (national total = 353,234,287.0)
    strat 01: total=  13,904,268.0  progsum=           0.0  ** MISMATCH diff=13,904,268.0
    strat 02: total=   6,521,757.0  progsum=           0.0  ** MISMATCH diff=6,521,757.0
    strat 03: total=           0.0  progsum=           0.0  OK
    strat 04: total=      15,000.0  progsum=           0.0  ** MISMATCH diff=15,000.0
    strat 05: total=           0.0  progsum=           0.0  OK
    strat 06: total=     366,003.0  progsum=           0.0  ** MISMATCH diff=366,003.0
    strat 07: total=   1,097,048.0  progsum=           0.0  ** MISMATCH diff=1,097,048.0
    strat 08: total=   3,964,476.0  progsum=           0.0  ** MISMATCH diff=3,964,476.0
    strat 09: total=           0.0  progsum=           0.0  OK
    strat 10: total=     892,092.0  progsum=           0.0  ** MISMATCH diff=892,092.0
    strat 11: total=           0.0  progsum=           0.0  OK
    strat 12: total=           0.0  progsum=           0.0  OK
    strat 13: total=   9,046,978.0  progsum=           0.0  ** MISMATCH diff=9,046,978.0
    strat 14: total=  29,868,199.0  progsum=           0.0  ** MISMATCH diff=29,868,199.0
    strat 15: total=  60,128,726.0  progsum=           0.0  ** MISMATCH diff=60,128,726.0
    strat 16: total=  17,268,632.0  progsum=           0.0  ** MISMATCH diff=17,268,632.0
    strat 17: total=  92,998,701.0  progsum=           0.0  ** MISMATCH diff=92,998,701.0
    strat 18: total=  28,994,089.0  progsum=  27,398,092.0  ** MISMATCH diff=1,595,997.0
    strat 19: total=  69,566,298.0  progsum=  33,290,921.0  ** MISMATCH diff=36,275,377.0
    strat 20: total=  10,271,455.0  progsum=     419,295.0  ** MISMATCH diff=9,852,160.0
    strat 21: total=   7,904,579.0  progsum=   7,904,579.0  OK
    strat 22: total=     425,986.0  progsum=      38,400.0  ** MISMATCH diff=387,586.0

  FY2026   (national total = 358,037,012.0)
    strat 01: total=   6,253,126.0  progsum=           0.0  ** MISMATCH diff=6,253,126.0
    strat 02: total=  10,918,025.0  progsum=           0.0  ** MISMATCH diff=10,918,025.0
    strat 03: total=           0.0  progsum=           0.0  OK
    strat 04: total=      61,980.0  progsum=           0.0  ** MISMATCH diff=61,980.0
    strat 06: total=     181,343.0  progsum=           0.0  ** MISMATCH diff=181,343.0
    strat 07: total=  10,152,582.0  progsum=           0.0  ** MISMATCH diff=10,152,582.0
    strat 08: total=   1,937,120.0  progsum=           0.0  ** MISMATCH diff=1,937,120.0
    strat 09: total=     415,369.0  progsum=           0.0  ** MISMATCH diff=415,369.0
    strat 10: total=     532,604.0  progsum=           0.0  ** MISMATCH diff=532,604.0
    strat 11: total=     182,712.0  progsum=           0.0  ** MISMATCH diff=182,712.0
    strat 13: total=   7,456,948.0  progsum=           0.0  ** MISMATCH diff=7,456,948.0
    strat 14: total=  30,719,333.0  progsum=           0.0  ** MISMATCH diff=30,719,333.0
    strat 15: total=  25,013,703.0  progsum=           0.0  ** MISMATCH diff=25,013,703.0
    strat 16: total=  24,340,453.0  progsum=           0.0  ** MISMATCH diff=24,340,453.0
    strat 17: total=  89,560,247.0  progsum=           0.0  ** MISMATCH diff=89,560,247.0
    strat 18: total=  27,172,934.0  progsum=  24,100,000.0  ** MISMATCH diff=3,072,934.0
    strat 19: total=  99,520,233.0  progsum=  45,860,929.0  ** MISMATCH diff=53,659,304.0
    strat 20: total=  12,725,544.0  progsum=   3,282,942.0  ** MISMATCH diff=9,442,602.0
    strat 21: total=  10,686,548.0  progsum=   1,300,000.0  ** MISMATCH diff=9,386,548.0
    strat 22: total=     206,208.0  progsum=           0.0  ** MISMATCH diff=206,208.0

RECONCILIATION: FAIL - see MISMATCH rows

NATIONAL TOTAL (the denominator every share is computed against)
    FY2023  heads 277,562,218.0  programmes 0.0  gap 100.0%  -> GRAND_TOTAL
    FY2024  heads 315,138,076.0  programmes 907,752,991.0  gap  65.3%  -> GRAND_TOTAL
    FY2025  heads 353,234,287.0  programmes 69,051,287.0  gap  80.5%  -> GRAND_TOTAL
    FY2026  heads 358,037,012.0  programmes 74,543,871.0  gap  79.2%  -> GRAND_TOTAL
    FY2023  extracted 100.0% of the document's own grand total 277,562,217.0
    FY2024  extracted 288.0% of the document's own grand total 315,138,076.0
    FY2025  extracted 100.0% of the document's own grand total 353,234,286.0
    FY2026  extracted 100.0% of the document's own grand total 358,037,012.0

READABILITY  0 of 215 programme name(s) unreadable (0%), 0 of 81 head(s) (0%), 0% of the money

HEAD NAMES: 237 row(s) renamed so a head reads the same in every year

Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/kiribati/budget_layer_all_years.xlsx
  sheet 'budget_all_years' : 300 rows  (feeds Prompt 6 / build_final_panel - each intervention matches against EVERY year's programs)
  sheet 'programs_wide'    : 215 programs x 4 year(s) (funding-over-time)
  sheet 'reconciliation'   : 81 rows (audit)
  sheet 'data_quality'     : 537 flagged items (see summary below)

==============================================================================
DATA-QUALITY SUMMARY
==============================================================================
  HIGH: 71   MEDIUM: 462   LOW: 0   INFO: 4

  [HIGH] granularity_mismatch  (1)
      - the years were not extracted to the same depth: FY2024 has 186 programme rows and FY2023 has 1, a factor of 186.0. Each year's totals may still be right, but a programme cannot be followed across years and any funding-over-time figure is comparing different levels of the same budget.

  [HIGH] over_extraction  (1)
      - FY2024: the heads extracted sum to 907,752,991.0 against a printed grand total of 315,138,076.0 (288%), so the same money is being counted more than once.

  [HIGH] reconciliation_mismatch  (69)
      - FY2023 strat 09: programs sum to 0.0 but strategy_total is 8,765,859.0 (gap 8,765,859.0) - a program line is likely missing or mis-extracted for this strategy-year.
      - FY2023 strat 10: programs sum to 0.0 but strategy_total is 7,932,651.0 (gap 7,932,651.0) - a program line is likely missing or mis-extracted for this strategy-year.
      - FY2023 strat 14: programs sum to 0.0 but strategy_total is 317,118.0 (gap 317,118.0) - a program line is likely missing or mis-extracted for this strategy-year.
      ... and 66 more (see 'data_quality' sheet)

  [MEDIUM] blank_amount  (16)
      - FY2023 strat 9 9.00001: amount is blank/unparseable.
      - FY2024 strat 09 09.00004: amount is blank/unparseable.
      - FY2024 strat 22 22.00186: amount is blank/unparseable.
      ... and 13 more (see 'data_quality' sheet)

  [MEDIUM] malformed_code_repaired  (215)
      - FY2023 strat 9 9.00001: program_code '00001' looked malformed and was normalized to '9.00001' - verify against source; fix the year file to avoid this.
      - FY2024 strat 09 09.00001: program_code '00001' looked malformed and was normalized to '09.00001' - verify against source; fix the year file to avoid this.
      - FY2024 strat 09 09.00002: program_code '00002' looked malformed and was normalized to '09.00002' - verify against source; fix the year file to avoid this.
      ... and 212 more (see 'data_quality' sheet)

  [MEDIUM] program_missing_in_year  (215)
      - FY2023,2025,2026 strat 09 09.00001: program '09.00001' (Climate Security in the Pacific) exists in ['2024'] but is absent in ['2023', '2025', '2026'] - check whether it was dropped during extraction or genuinely did not exist that year.
      - FY2023,2025,2026 strat 09 09.00002: program '09.00002' (Land Reclamation Project Management Design) exists in ['2024'] but is absent in ['2023', '2025', '2026'] - check whether it was dropped during extraction or genuinely did not exist that year.
      - FY2023,2025,2026 strat 09 09.00003: program '09.00003' (Emergency Humanitarian Support - Banaba Crisis) exists in ['2024'] but is absent in ['2023', '2025', '2026'] - check whether it was dropped during extraction or genuinely did not exist that year.
      ... and 212 more (see 'data_quality' sheet)

  [MEDIUM] zero_amount_programme  (16)
      - FY2023 strat 9 9.00001: programme carries no money; a strategy matched only to lines like this reads as funded while receiving nothing
      - FY2024 strat 09 09.00004: programme carries no money; a strategy matched only to lines like this reads as funded while receiving nothing
      - FY2024 strat 22 22.00186: programme carries no money; a strategy matched only to lines like this reads as funded while receiving nothing
      ... and 13 more (see 'data_quality' sheet)
==============================================================================
DATA QUALITY: REVIEW NEEDED - resolve HIGH items before relying on totals for those strategy-years
==============================================================================
```

### build_final_panel
```
Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/kiribati/FINAL_PANEL.xlsx
  panel               : 56 strategies x 4 years (2023, 2024, 2025, 2026)
  match_review        : 221 matches (BOTH names + rationale)
  unmatched_codes     : 0 (codes NOT in that year's budget - REVIEW)
  unfunded_strategies : 11 (strategies with no budget any year)
  funding_by_program  : 122 (per programme x year, amount once - SAFE TO SUM)
  unmapped_programs   : 93 budget programmes with no matched strategy
  risk_panel          : 0 risks | ceiling: PASS
  enrichment          : strategyclean=yes risk_summary=yes
  maturity            : mean=0.725 | financing-weighted=0.862 | {'operational_programme': 21, 'operational_funded': 9, 'partial_operation': 15, 'planned': 7, 'aspirational': 4}
  basket/reverse-pass : 52 shared programmes | reverse-pass edges=none (run Prompt 6b + --coverage)
  recall_review       : 11 large programmes matched to only 1 strategy (candidate baskets)
MATURITY: mean=0.725 financing_weighted=0.862
CEILING TEST: PASS - no strategy over-counted in any year
UNMATCHED CODES: 0
QA: PASS - 0 unmatched code(s), ceiling PASS, 0 year warning(s)
```

### build_analytics_html
```
dashboard -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/kiribati/budget_strategy_analytics.html
  years        2023, 2024, 2025, 2026
  edges        221
  strategies   56 (11 unfunded)
  size         87 KB
```

### audit_checks
```
AUDIT CHECKS: kiribati 18/19 PASS (A2 1 disagree)
  ok   A1   Stored programme sums              81 strategy-year(s) / 0 disagree
  FAIL A2   Stored strategy totals             81 strategy-year(s) / 1 disagree
            FY2026 strategy 03: stored 0.0, layer -
  ok   A3   Programme counted once             122 row(s) / 0 duplicate key(s)
  ok   A4   Ceiling holds                      81 strategy-year(s) / 0 over ceiling
  ok   A6   Panel money matches its edges      224 strategy-year figure(s) / 0 disagree
  ok   A8   Edges cite real programmes         221 accepted edge(s) / 0 dangle
  ok   A9   No strategy dropped                56 strategyclean row(s) / 56 panel row(s)
  ok   A10  Unfunded list is complete          11 zero-funded / 11 listed
  ok   A11  Evidence chain resolves            461 distinct id(s) / 0 dangle
  ok   A12  Maturity summary is derivable      8 metric(s) / 0 disagree
  ok   A14  No duplicate edges                 221 edge(s) / 0 duplicate(s)
  ok   A15  One currency                       1 expected / 1 found
  ok   A16  Components are traceable           607 component(s) / 0 untraceable
  ok   A17  No workbook open in Excel          0 expected / 0 found
  ok   A18  Strategies come from the plan      56 strategy(ies) / 0 with no component
  ok   A19  Funding priority is reproducible   44 distinct (salience, funding) group(s) / 0 split across priorities
  ok   A20  The budget is readable             215 programme(s) / 0 unreadable (0%), carrying 0% of the money
  ok   A21  Ambiguous codes name their head    0 repeated code(s) / 0 edge(s) do not name a head
  ok   A22  Every intervention is traceable to a strategy 462 intervention(s) extracted / 1 uncited (0.2%)
            1102
  --   A23  The sector layer stayed out of the panel no sector run for this country
```

### data_issues
```
data issues  Files/outputs/DATA_ISSUES.xlsx
  6 detected across 1 country(ies): 2 high, 3 medium, 1 low
  70 hand-written entr(ies) in 04_Docs_and_Planning/data_issues.json
  HIGH  kiribati  D7       Flag raised while combining the budget years
  HIGH  kiribati  D8       A strategy total its own programmes do not add up to
```
