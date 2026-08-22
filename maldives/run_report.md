# Run report - Maldives

**🔴 Overall: REVIEW NEEDED**  
Generated 2026-08-22 10:21 by run_pipeline.py

| Stage | Ran | Key QA |
|---|---|---|
| validate_stage_schema (L2) | ok | QA FAIL - FAIL 4/11 (maldives_mapping_2017.xlsx, maldives_mapping_2018.xlsx, maldives_mapping_2019.xlsx) |
| validate_source_fidelity (L4) | ok | NOT CONFIGURED |
| validate_recall (L4) | ok | NOT CONFIGURED [advisory] |
| validate_refs (L3) | ok | QA FAIL - FAIL 1/1 (maldives references) |
| combine_budget_years | ok | reconcile=FAIL - see MISMATCH rows | data_quality=REVIEW NEEDED - resolve HIGH items before relying on totals for those strategy-years |
| build_final_panel | ok | QA FAIL - ceiling=PASS - no strategy over-counted in any year | unmatched_codes=1 |
| build_analytics_html | ok | strategies=261 (133 unfunded) | edges=246 |
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

  RESULT: FAIL - 1 contract violation(s) across 1 file(s).
  The stage output is not accepted; re-run the stage or fix the prompt.

--- maldives_mapping_2018.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/maldives/validation/schema_maldives_mapping_2018.xlsx

  RESULT: FAIL - 1 contract violation(s) across 1 file(s).
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
RESULT: FAIL - 2 dangling reference(s) of 3011
report -> Files/outputs/maldives/validation/refs_maldives_references.xlsx
```

### combine_budget_years
```
==============================================================================
COMBINED BUDGET LAYER  -  years: 2017, 2019  (3 file(s))
==============================================================================

RECONCILIATION (per year: sum of program rows vs strategy_total)

  FY2017   (national total = 7,988,962,654.0)
    strat 1: total= 270,637,074.0  progsum= 270,637,074.0  OK
    strat 2: total=1,780,849,664.0  progsum=1,780,849,664.0  OK
    strat 3: total= 291,704,544.0  progsum= 291,704,544.0  OK
    strat 4: total= 585,038,849.0  progsum= 585,038,849.0  OK
    strat 5: total= 796,853,288.0  progsum= 796,853,288.0  OK
    strat 6: total=2,294,511,756.0  progsum=2,294,511,756.0  OK
    strat 7: total= 266,705,093.0  progsum= 266,705,093.0  OK
    strat 8: total= 494,853,833.0  progsum= 494,853,833.0  OK
    strat 9: total= 451,821,391.0  progsum= 451,821,391.0  OK
    strat 10: total= 603,169,808.0  progsum= 603,169,808.0  OK
    strat 11: total=  84,903,354.0  progsum=  84,903,354.0  OK
    strat 12: total=  67,914,000.0  progsum=           0.0  ** MISMATCH diff=67,914,000.0

  FY2019   (national total = 7,076,705,474.0)
    strat 1: total=  75,313,347.0  progsum=  75,313,347.0  OK
    strat 2: total= 685,209,227.0  progsum= 685,209,227.0  OK
    strat 3: total= 299,484,547.0  progsum= 299,484,547.0  OK
    strat 4: total= 549,298,857.0  progsum= 549,298,857.0  OK
    strat 5: total=1,360,376,122.0  progsum=1,360,376,122.0  OK
    strat 6: total=2,690,493,443.0  progsum=2,690,493,443.0  OK
    strat 7: total=  55,013,327.0  progsum=  55,013,327.0  OK
    strat 8: total= 396,448,307.0  progsum= 396,448,307.0  OK
    strat 9: total= 201,259,017.0  progsum= 201,259,017.0  OK
    strat 10: total= 677,505,837.0  progsum= 677,505,837.0  OK
    strat 11: total=  59,838,120.0  progsum=  59,838,120.0  OK
    strat 12: total=  26,465,323.0  progsum=           0.0  ** MISMATCH diff=26,465,323.0

RECONCILIATION: FAIL - see MISMATCH rows

NATIONAL TOTAL (the denominator every share is computed against)
    FY2017  heads 7,988,962,654.0  programmes 7,921,048,654.0  gap   0.8%  -> HEADS
    FY2019  heads 7,076,705,474.0  programmes 7,050,240,151.0  gap   0.4%  -> HEADS

READABILITY  0 of 56 programme name(s) unreadable (0%), 0 of 24 head(s) (0%), 0% of the money

PROGRAMME CLASS (share of programme money)
    development        14,971,288,805.0  100.0%  (56 programme-year rows)

HEAD NAMES: 21 row(s) renamed so a head reads the same in every year

Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/maldives/budget_layer_all_years.xlsx
  sheet 'budget_all_years' : 80 rows  (feeds Prompt 6 / build_final_panel - each intervention matches against EVERY year's programs)
  sheet 'programs_wide'    : 29 programs x 2 year(s) (funding-over-time)
  sheet 'reconciliation'   : 24 rows (audit)
  sheet 'data_quality'     : 12 flagged items (see summary below)

==============================================================================
DATA-QUALITY SUMMARY
==============================================================================
  HIGH: 2   MEDIUM: 6   LOW: 2   INFO: 2

  [HIGH] reconciliation_mismatch  (2)
      - FY2017 strat 12: programs sum to 0.0 but strategy_total is 67,914,000.0 (gap 67,914,000.0) - a program line is likely missing or mis-extracted for this strategy-year.
      - FY2019 strat 12: programs sum to 0.0 but strategy_total is 26,465,323.0 (gap 26,465,323.0) - a program line is likely missing or mis-extracted for this strategy-year.

  [MEDIUM] blank_amount  (1)
      - FY2017 strat 1 1.5: amount is blank/unparseable.

  [MEDIUM] no_grand_total  (2)
      - FY2017: the document printed no grand total that stage 5 could find, so there is nothing to check the extraction's completeness against. Every share for FY2017 rests on the heads being all of them.
      - FY2019: the document printed no grand total that stage 5 could find, so there is nothing to check the extraction's completeness against. Every share for FY2019 rests on the heads being all of them.

  [MEDIUM] program_missing_in_year  (2)
      - FY2019 strat 7 7.3: program '7.3' (Customs) exists in ['2017'] but is absent in ['2019'] - check whether it was dropped during extraction or genuinely did not exist that year.
      - FY2019 strat 8 8.2: program '8.2' (Electricity System) exists in ['2017'] but is absent in ['2019'] - check whether it was dropped during extraction or genuinely did not exist that year.

  [MEDIUM] zero_amount_programme  (1)
      - FY2017 strat 1 1.5: programme carries no money; a strategy matched only to lines like this reads as funded while receiving nothing

  [LOW] large_yoy_swing  (2)
      - FY2017->2019 strat 3 3.1: program '3.1' changed +241% (15,262,397.0 -> 52,102,041.0) - verify this is real and not an extraction error.
      - FY2017->2019 strat 5 5.2: program '5.2' changed +246% (240,531,117.0 -> 833,099,145.0) - verify this is real and not an extraction error.
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
  panel               : 261 strategies x 2 years (2017, 2019)
  match_review        : 247 matches (BOTH names + rationale)
  unmatched_codes     : 1 (codes NOT in that year's budget - REVIEW)  <-- !!
  unfunded_strategies : 133 (strategies with no budget any year)
  funding_by_program  : 48 (per programme x year, amount once - SAFE TO SUM)
  unmapped_programs   : 8 budget programmes with no matched strategy
  risk_panel          : 10 risks | ceiling: PASS
  enrichment          : strategyclean=yes risk_summary=yes
  maturity            : mean=0.599 | financing-weighted=0.85 | {'operational_programme': 126, 'operational_funded': 2, 'aspirational': 6, 'planned': 111, 'planned_specific': 16}
  basket/reverse-pass : 40 shared programmes | reverse-pass edges=1 rows -> 0 new matches
  recall_review       : 3 large programmes matched to only 1 strategy (candidate baskets)
MATURITY: mean=0.599 financing_weighted=0.85
CEILING TEST: PASS - no strategy over-counted in any year
UNMATCHED CODES: 1
QA: FAIL - 1 unmatched code(s), ceiling PASS, 0 year warning(s)
```

### build_analytics_html
```
dashboard -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/maldives/budget_strategy_analytics.html
  years        2017, 2019
  edges        246
  strategies   261 (133 unfunded)
  size         89 KB
```

### audit_checks
```
AUDIT CHECKS: maldives 18/19 PASS (A16 2 untraceable)
  ok   A1   Stored programme sums              24 strategy-year(s) / 0 disagree
  ok   A2   Stored strategy totals             24 strategy-year(s) / 0 disagree
  ok   A3   Programme counted once             48 row(s) / 0 duplicate key(s)
  ok   A4   Ceiling holds                      24 strategy-year(s) / 0 over ceiling
  ok   A6   Panel money matches its edges      522 strategy-year figure(s) / 0 disagree
  ok   A8   Edges cite real programmes         247 accepted edge(s) / 0 dangle
  ok   A9   No strategy dropped                261 strategyclean row(s) / 261 panel row(s)
  ok   A10  Unfunded list is complete          133 zero-funded / 133 listed
  ok   A11  Evidence chain resolves            2705 distinct id(s) / 0 dangle
  ok   A12  Maturity summary is derivable      8 metric(s) / 0 disagree
  ok   A14  No duplicate edges                 246 edge(s) / 0 duplicate(s)
  ok   A15  One currency                       1 expected / 1 found
  FAIL A16  Components are traceable           2803 component(s) / 2 untraceable
            Gender equality law and institutio <- Women's Political Participation and Decision
            Women's economic empowerment, entr <- Women's Economic Participation and Shared Ca
  ok   A17  No workbook open in Excel          0 expected / 0 found
  ok   A18  Strategies come from the plan      261 strategy(ies) / 0 with no component
  ok   A19  Funding priority is reproducible   78 distinct (salience, funding) group(s) / 0 split across priorities
  ok   A20  The budget is readable             56 programme(s) / 0 unreadable (0%), carrying 0% of the money
  ok   A21  Ambiguous codes name their head    0 repeated code(s) / 0 edge(s) do not name a head
  ok   A22  Consolidation keeps every intervention 2727 intervention(s) extracted / 22 dropped (0.8%)
            149
            154
            282
            346
            469
            712
```

### data_issues
```
data issues  Files/outputs/DATA_ISSUES.xlsx
  7 detected across 1 country(ies): 3 high, 3 medium, 1 low
  38 hand-written entr(ies) in 04_Docs_and_Planning/data_issues.json
  HIGH  maldives  D12      An output predates the prompt that produced it
  HIGH  maldives  D7       Flag raised while combining the budget years
  HIGH  maldives  D8       A strategy total its own programmes do not add up to
```
