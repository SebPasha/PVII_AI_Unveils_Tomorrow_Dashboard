# Run report - Brunei

**🔴 Overall: REVIEW NEEDED**  
Generated 2026-08-22 11:55 by run_pipeline.py

| Stage | Ran | Key QA |
|---|---|---|
| validate_stage_schema (L2) | ok | PASS 11/11 |
| validate_source_fidelity (L4) | ok | NOT CONFIGURED |
| validate_recall (L4) | ok | NOT CONFIGURED [advisory] |
| validate_refs (L3) | ok | QA FAIL - FAIL 1/1 (brunei references) |
| combine_budget_years | ok | reconcile=FAIL - see MISMATCH rows | data_quality=REVIEW NEEDED - resolve HIGH items before relying on totals for those strategy-years |
| build_final_panel | ok | ceiling=PASS - no strategy over-counted in any year | unmatched_codes=0 |
| build_analytics_html | ok | strategies=83 (10 unfunded) | edges=393 |
| audit_checks | FAILED | QA FAIL - 18/20 PASS (A11 10 dangle, A16 20 untraceable) [advisory] |
| data_issues | FAILED | 7 detected across 1 country(ies): 4 high, 2 medium, 1 low [advisory] |

## Outputs

- Budget layer: `Files/outputs/brunei/budget_layer_all_years.xlsx`
- FINAL panel (deliverable): `Files/outputs/brunei/FINAL_PANEL.xlsx`
- Dashboard: `Files/outputs/brunei/budget_strategy_analytics.html`
- Audit trail: `Files/outputs/union_dashboard.html`, Audit tab, filtered to this country
- Data oddities: `Files/outputs/DATA_ISSUES.xlsx`

## Full stage logs

### validate_stage_schema (L2)
```
--- brunei_budget_2021.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/brunei/validation/schema_brunei_budget_2021.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- brunei_budget_2022.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/brunei/validation/schema_brunei_budget_2022.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- brunei_budget_2025.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/brunei/validation/schema_brunei_budget_2025.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- brunei_budget_2026.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/brunei/validation/schema_brunei_budget_2026.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- brunei_coverage_2025.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/brunei/validation/schema_brunei_coverage_2025.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- brunei_mapping_2021.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/brunei/validation/schema_brunei_mapping_2021.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- brunei_mapping_2022.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/brunei/validation/schema_brunei_mapping_2022.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- brunei_mapping_2025.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/brunei/validation/schema_brunei_mapping_2025.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- brunei_mapping_2026.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/brunei/validation/schema_brunei_mapping_2026.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- brunei_strategyclean.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/brunei/validation/schema_brunei_strategyclean.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- brunei_risk_summary.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/brunei/validation/schema_brunei_risk_summary.xlsx

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
--- brunei references
RESULT: FAIL - 1 dangling reference(s) of 1220
report -> Files/outputs/brunei/validation/refs_brunei_references.xlsx
```

### combine_budget_years
```
==============================================================================
COMBINED BUDGET LAYER  -  years: 2021, 2022, 2025, 2026  (4 file(s))
==============================================================================

RECONCILIATION (per year: sum of program rows vs strategy_total)

  FY2021   (national total = 6,406.4)
    strat 1: total=       1,990.0  progsum=           0.0  ** MISMATCH diff=1,990.0
    strat 2: total=       2,010.0  progsum=       1,190.1  ** MISMATCH diff=819.9
    strat 3: total=         800.0  progsum=         348.7  ** MISMATCH diff=451.3
    strat 4: total=       1,060.0  progsum=           0.0  ** MISMATCH diff=1,060.0
    strat 5: total=           8.0  progsum=           8.0  OK
    strat 6: total=           3.3  progsum=           3.3  OK
    strat 7: total=           1.7  progsum=           1.7  OK
    strat 8: total=           4.5  progsum=           4.5  OK
    strat 9: total=           2.1  progsum=         135.7  ** MISMATCH diff=-133.6
    strat 10: total=           1.5  progsum=           3.4  ** MISMATCH diff=-1.9
    strat 11: total=         507.3  progsum=         356.2  ** MISMATCH diff=151.1
    strat 12: total=          18.0  progsum=          18.0  OK

  FY2022   (national total = 5,860.0)
    strat 1: total=       2,020.0  progsum=           0.0  ** MISMATCH diff=2,020.0
    strat 2: total=       2,180.0  progsum=         703.2  ** MISMATCH diff=1,476.8
    strat 3: total=         600.0  progsum=         752.5  ** MISMATCH diff=-152.5
    strat 4: total=       1,060.0  progsum=           0.0  ** MISMATCH diff=1,060.0

  FY2025   (national total = 6,250.0)
    strat 1: total=       2,290.0  progsum=           0.0  ** MISMATCH diff=2,290.0
    strat 2: total=       2,400.0  progsum=         583.3  ** MISMATCH diff=1,816.7
    strat 3: total=         500.0  progsum=       2,449.7  ** MISMATCH diff=-1,949.7
    strat 4: total=       1,060.0  progsum=           0.0  ** MISMATCH diff=1,060.0

  FY2026   (national total = 1,017.5)
    strat 1: total=         153.0  progsum=         459.0  ** MISMATCH diff=-306.0
    strat 2: total=         146.4  progsum=         146.4  OK
    strat 3: total=         425.2  progsum=       2,126.0  ** MISMATCH diff=-1,700.8
    strat 4: total=          25.0  progsum=          25.0  OK
    strat 5: total=         221.1  progsum=         663.3  ** MISMATCH diff=-442.2
    strat 6: total=          19.2  progsum=          96.1  ** MISMATCH diff=-76.8
    strat 7: total=          27.5  progsum=          27.5  OK

RECONCILIATION: FAIL - see MISMATCH rows

NATIONAL TOTAL (the denominator every share is computed against)
    FY2021  heads 6,406.4  programmes 2,069.5  gap  67.7%  -> GRAND_TOTAL
    FY2022  heads 5,860.0  programmes 1,455.7  gap  75.2%  -> GRAND_TOTAL
    FY2025  heads 6,250.0  programmes 3,033.0  gap  51.5%  -> GRAND_TOTAL
    FY2026  heads 1,017.5  programmes 3,543.3  gap  71.3%  -> GRAND_TOTAL
    FY2021  extracted 109.3% of the document's own grand total 5,860.0
    FY2022  extracted 100.0% of the document's own grand total 5,860.0
    FY2025  extracted 100.0% of the document's own grand total 6,250.0
    FY2026  extracted 55.8% of the document's own grand total 6,350.0

READABILITY  0 of 164 programme name(s) unreadable (0%), 0 of 27 head(s) (0%), 0% of the money

PROGRAMME CLASS (share of programme money)
    development               6,529.8   64.6%  (108 programme-year rows)
    standing_function         3,042.8   30.1%  (48 programme-year rows)
    overhead                    528.8    5.2%  (8 programme-year rows)

HEAD NAMES: 27 row(s) renamed so a head reads the same in every year

Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/brunei/budget_layer_all_years.xlsx
  sheet 'budget_all_years' : 195 rows  (feeds Prompt 6 / build_final_panel - each intervention matches against EVERY year's programs)
  sheet 'programs_wide'    : 95 programs x 4 year(s) (funding-over-time)
  sheet 'reconciliation'   : 27 rows (audit)
  sheet 'data_quality'     : 138 flagged items (see summary below)

==============================================================================
DATA-QUALITY SUMMARY
==============================================================================
  HIGH: 20   MEDIUM: 89   LOW: 25   INFO: 4

  [HIGH] partial_budget  (1)
      - FY2026: the heads extracted sum to 3,543.3 but the document's own grand total is 6,350.0, so only 56% of the budget is here. A section was taken rather than the budget, and every share computed for FY2026 is a share of that section. Re-run stage 5 against the full summary of expenditure.

  [HIGH] reconciliation_mismatch  (19)
      - FY2021 strat 1: programs sum to 0.0 but strategy_total is 1,990.0 (gap 1,990.0) - a program line is likely missing or mis-extracted for this strategy-year.
      - FY2021 strat 2: programs sum to 1,190.1 but strategy_total is 2,010.0 (gap 819.9) - a program line is likely missing or mis-extracted for this strategy-year.
      - FY2021 strat 3: programs sum to 348.7 but strategy_total is 800.0 (gap 451.3) - a program line is likely missing or mis-extracted for this strategy-year.
      ... and 16 more (see 'data_quality' sheet)

  [MEDIUM] program_missing_in_year  (89)
      - FY2021,2022,2025 strat 1 1.1: program '1.1' (Electricity supply reliability and power station operations) exists in ['2026'] but is absent in ['2021', '2022', '2025'] - check whether it was dropped during extraction or genuinely did not exist that year.
      - FY2021,2022,2025 strat 1 1.2: program '1.2' (Clean water access and water supply infrastructure maintenance) exists in ['2026'] but is absent in ['2021', '2022', '2025'] - check whether it was dropped during extraction or genuinely did not exist that year.
      - FY2021,2022,2025 strat 1 1.3: program '1.3' (Road maintenance and upgrading of strategic routes) exists in ['2026'] but is absent in ['2021', '2022', '2025'] - check whether it was dropped during extraction or genuinely did not exist that year.
      ... and 86 more (see 'data_quality' sheet)

  [LOW] large_yoy_swing  (25)
      - FY2022->2025 strat 2 2.1: program '2.1' changed +682% (3.3 -> 25.8) - verify this is real and not an extraction error.
      - FY2025->2026 strat 2 2.1: program '2.1' changed +468% (25.8 -> 146.4) - verify this is real and not an extraction error.
      - FY2022->2025 strat 2 2.10: program '2.10' changed +1972% (1.8 -> 37.3) - verify this is real and not an extraction error.
      ... and 22 more (see 'data_quality' sheet)
==============================================================================
DATA QUALITY: REVIEW NEEDED - resolve HIGH items before relying on totals for those strategy-years
==============================================================================
```

### build_final_panel
```
STALE EDGES DROPPED: 29 edge(s) name a strategy the inventory does not hold (prog=29)
   ! Aquaculture industry site development and basic infrastructure projects
   ! Bru-HIMS 2.0 system project
   ! Capacity enhancement programme for irrigation systems in agricultural development areas 
   ! Development of school and higher education institution infrastructure under the 12th Nat
   ! Education digital infrastructure and smart systems under the 12th National Development P
   ! Education information and data management systems under the 12th National Development Pl
   ! Flood prevention projects under the 12th National Development Plan
   ! Green Building initiatives under the 12th National Development Plan
   ! High-technology vegetable production enhancement programme under the 12th National Devel
   ! Human capital funds and private participation in education services
   Re-run the stage that produced them against the current strategyclean.

Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/brunei/FINAL_PANEL.xlsx
  panel               : 83 strategies x 4 years (2021, 2022, 2025, 2026)
  match_review        : 393 matches (BOTH names + rationale)
  unmatched_codes     : 0 (codes NOT in that year's budget - REVIEW)
  unfunded_strategies : 10 (strategies with no budget any year)
  funding_by_program  : 138 (per programme x year, amount once - SAFE TO SUM)
  unmapped_programs   : 26 budget programmes with no matched strategy
  risk_panel          : 9 risks | ceiling: PASS
  enrichment          : strategyclean=yes risk_summary=yes
  maturity            : mean=0.78 | financing-weighted=0.849 | {'operational_programme': 61, 'partial_operation': 8, 'operational_funded': 4, 'planned': 7, 'planned_specific': 1, 'aspirational': 2}
  basket/reverse-pass : 104 shared programmes | reverse-pass edges=29 rows -> 0 new matches
  recall_review       : 14 large programmes matched to only 1 strategy (candidate baskets)
MATURITY: mean=0.78 financing_weighted=0.849
CEILING TEST: PASS - no strategy over-counted in any year
UNMATCHED CODES: 0
QA: PASS - 0 unmatched code(s), ceiling PASS, 0 year warning(s)
```

### build_analytics_html
```
dashboard -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/brunei/budget_strategy_analytics.html
  years        2021, 2022, 2025, 2026
  edges        393
  strategies   83 (10 unfunded)
  size         146 KB
```

### audit_checks
```
AUDIT CHECKS: brunei 18/20 PASS (A11 10 dangle, A16 20 untraceable)
  ok   A1   Stored programme sums              27 strategy-year(s) / 0 disagree
  ok   A2   Stored strategy totals             27 strategy-year(s) / 0 disagree
  ok   A3   Programme counted once             138 row(s) / 0 duplicate key(s)
  ok   A4   Ceiling holds                      27 strategy-year(s) / 0 over ceiling
  ok   A6   Panel money matches its edges      332 strategy-year figure(s) / 0 disagree
  ok   A8   Edges cite real programmes         393 accepted edge(s) / 0 dangle
  ok   A9   No strategy dropped                83 strategyclean row(s) / 83 panel row(s)
  ok   A10  Unfunded list is complete          10 zero-funded / 10 listed
  FAIL A11  Evidence chain resolves            573 distinct id(s) / 10 dangle
            chunk id 0 has no stage-3 row
            chunk id 1 has no stage-3 row
            chunk id 2 has no stage-3 row
            chunk id 3 has no stage-3 row
            chunk id 4 has no stage-3 row
            chunk id 5 has no stage-3 row
  ok   A12  Maturity summary is derivable      8 metric(s) / 0 disagree
  ok   A14  No duplicate edges                 393 edge(s) / 0 duplicate(s)
  ok   A15  One currency                       1 expected / 1 found
  FAIL A16  Components are traceable           1032 component(s) / 20 untraceable
            Electricity generation, transmissi <- Electricity supply projects under the 12th N
            Research, innovation and commercia <- Research and innovation allocations under th
            Research, innovation and commercia <- Research costs for public higher education i
            Research, innovation and commercia <- Knowledge and Expertise and Innovation Enhan
            Scholarships and human resource fu <- Scholarships through the Ministry of Educati
            Sewerage system upgrading and sani <- Construction programme for sewerage and wast
  ok   A17  No workbook open in Excel          0 expected / 0 found
  ok   A18  Strategies come from the plan      83 strategy(ies) / 0 with no component
  ok   A19  Funding priority is reproducible   75 distinct (salience, funding) group(s) / 0 split across priorities
  ok   A20  The budget is readable             164 programme(s) / 0 unreadable (0%), carrying 0% of the money
  ok   A21  Ambiguous codes name their head    0 repeated code(s) / 0 edge(s) do not name a head
  ok   A22  Consolidation keeps every intervention 581 intervention(s) extracted / 18 dropped (3.1%)
            147
            341
            365
            370
            426
            475
  ok   A23  The sector layer stayed out of the panel 198 sector intervention(s) not in the plan / 0 of them present in the panel
```

### data_issues
```
data issues  Files/outputs/DATA_ISSUES.xlsx
  7 detected across 1 country(ies): 4 high, 2 medium, 1 low
  51 hand-written entr(ies) in 04_Docs_and_Planning/data_issues.json
  HIGH  brunei    D11      Strategy named after the budget line funding it
  HIGH  brunei    D12      An output predates the prompt that produced it
  HIGH  brunei    D7       Flag raised while combining the budget years
  HIGH  brunei    D8       A strategy total its own programmes do not add up to
```
