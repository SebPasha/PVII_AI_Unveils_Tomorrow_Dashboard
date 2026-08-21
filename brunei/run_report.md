# Run report - Brunei

**🔴 Overall: REVIEW NEEDED**  
Generated 2026-08-21 08:56 by run_pipeline.py

| Stage | Ran | Key QA |
|---|---|---|
| validate_stage_schema (L2) | ok | PASS 8/8 |
| validate_source_fidelity (L4) | ok | NOT CONFIGURED |
| validate_recall (L4) | ok | NOT CONFIGURED [advisory] |
| validate_refs (L3) | ok | QA FAIL - FAIL 1/1 (brunei references) |
| combine_budget_years | ok | reconcile=FAIL - see MISMATCH rows | data_quality=REVIEW NEEDED - resolve HIGH items before relying on totals for those strategy-years |
| build_final_panel | ok | ceiling=PASS - no strategy over-counted in any year | unmatched_codes=0 |
| build_analytics_html | ok | strategies=83 (37 unfunded) | edges=83 |
| audit_checks | FAILED | QA FAIL - 15/17 PASS (A11 10 dangle, A16 20 untraceable) [advisory] |
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

--- brunei_mapping_2025.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/brunei/validation/schema_brunei_mapping_2025.xlsx

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
RESULT: FAIL - 1 dangling reference(s) of 910
report -> Files/outputs/brunei/validation/refs_brunei_references.xlsx
```

### combine_budget_years
```
==============================================================================
COMBINED BUDGET LAYER  -  years: 2025  (4 file(s))
==============================================================================

RECONCILIATION (per year: sum of program rows vs strategy_total)

  FY2025   (national total = 3,068.4)
    strat 1: total=       1,949.8  progsum=       1,912.5  ** MISMATCH diff=37.3
    strat 2: total=         493.8  progsum=         493.8  OK
    strat 3: total=         624.9  progsum=         626.7  ** MISMATCH diff=-1.8

RECONCILIATION: FAIL - see MISMATCH rows

NATIONAL TOTAL (the denominator every share is computed against)
    FY2025  heads 3,068.4  programmes 3,033.0  gap   1.2%  -> HEADS

READABILITY  0 of 41 programme name(s) unreadable (0%), 0 of 3 head(s) (0%), 0% of the money

PROGRAMME CLASS (share of programme money)
    development               2,569.3   84.7%  (34 programme-year rows)
    standing_function           293.2    9.7%  (5 programme-year rows)
    overhead                    144.7    4.8%  (1 programme-year rows)
    mixed                        25.8    0.9%  (1 programme-year rows)

Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/brunei/budget_layer_all_years.xlsx
  sheet 'budget_all_years' : 44 rows  (feeds Prompt 6 / build_final_panel - each intervention matches against EVERY year's programs)
  sheet 'programs_wide'    : 41 programs x 1 year(s) (funding-over-time)
  sheet 'reconciliation'   : 3 rows (audit)
  sheet 'data_quality'     : 3 flagged items (see summary below)

==============================================================================
DATA-QUALITY SUMMARY
==============================================================================
  HIGH: 2   MEDIUM: 0   LOW: 0   INFO: 1

  [HIGH] reconciliation_mismatch  (2)
      - FY2025 strat 1: programs sum to 1,912.5 but strategy_total is 1,949.8 (gap 37.3) - a program line is likely missing or mis-extracted for this strategy-year.
      - FY2025 strat 3: programs sum to 626.7 but strategy_total is 624.9 (gap -1.8) - a program line is likely missing or mis-extracted for this strategy-year.
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
  panel               : 83 strategies x 1 years (2025)
  match_review        : 83 matches (BOTH names + rationale)
  unmatched_codes     : 0 (codes NOT in that year's budget - REVIEW)
  unfunded_strategies : 37 (strategies with no budget any year)
  funding_by_program  : 34 (per programme x year, amount once - SAFE TO SUM)
  unmapped_programs   : 7 budget programmes with no matched strategy
  risk_panel          : 9 risks | ceiling: PASS
  enrichment          : strategyclean=yes risk_summary=yes
  maturity            : mean=0.605 | financing-weighted=0.852 | {'operational_programme': 45, 'operational_funded': 1, 'aspirational': 14, 'planned': 22, 'planned_specific': 1}
  basket/reverse-pass : 26 shared programmes | reverse-pass edges=29 rows -> 0 new matches
  recall_review       : 2 large programmes matched to only 1 strategy (candidate baskets)
MATURITY: mean=0.605 financing_weighted=0.852
CEILING TEST: PASS - no strategy over-counted in any year
UNMATCHED CODES: 0
QA: PASS - 0 unmatched code(s), ceiling PASS, 0 year warning(s)
```

### build_analytics_html
```
dashboard -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/brunei/budget_strategy_analytics.html
  years        2025
  edges        83
  strategies   83 (37 unfunded)
  size         55 KB
```

### audit_checks
```
AUDIT CHECKS: brunei 15/17 PASS (A11 10 dangle, A16 20 untraceable)
  ok   A1   Stored programme sums              3 strategy-year(s) / 0 disagree
  ok   A2   Stored strategy totals             3 strategy-year(s) / 0 disagree
  ok   A3   Programme counted once             34 row(s) / 0 duplicate key(s)
  ok   A4   Ceiling holds                      3 strategy-year(s) / 0 over ceiling
  ok   A6   Panel money matches its edges      83 strategy-year figure(s) / 0 disagree
  ok   A8   Edges cite real programmes         83 accepted edge(s) / 0 dangle
  ok   A9   No strategy dropped                83 strategyclean row(s) / 83 panel row(s)
  ok   A10  Unfunded list is complete          37 zero-funded / 37 listed
  FAIL A11  Evidence chain resolves            573 distinct id(s) / 10 dangle
            chunk id 0 has no stage-3 row
            chunk id 1 has no stage-3 row
            chunk id 2 has no stage-3 row
            chunk id 3 has no stage-3 row
            chunk id 4 has no stage-3 row
            chunk id 5 has no stage-3 row
  ok   A12  Maturity summary is derivable      8 metric(s) / 0 disagree
  ok   A14  No duplicate edges                 83 edge(s) / 0 duplicate(s)
  ok   A15  One currency                       1 expected / 1 found
  FAIL A16  Components are traceable           1032 component(s) / 20 untraceable
            Electricity generation, transmissi <- Electricity supply projects under the 12th N
            Agricultural development area infr <- Capacity enhancement programme for irrigatio
            Agricultural development area infr <- Infrastructure provision for enhancement of 
            Agricultural development area infr <- Preparation and upgrading works for infrastr
            Airport infrastructure modernisati <- Airport infrastructure modernisation project
            Climate policy, emissions reductio <- Green Building initiatives under the 12th Na
  ok   A17  No workbook open in Excel          0 expected / 0 found
  ok   A18  Strategies come from the plan      83 strategy(ies) / 0 with no component
  ok   A19  Funding priority is reproducible   46 distinct (salience, funding) group(s) / 0 split across priorities
  ok   A20  The budget is readable             41 programme(s) / 0 unreadable (0%), carrying 0% of the money
```

### data_issues
```
data issues  Files/outputs/DATA_ISSUES.xlsx
  7 detected across 1 country(ies): 4 high, 2 medium, 1 low
  36 hand-written entr(ies) in 04_Docs_and_Planning/data_issues.json
  HIGH  brunei    D11      Strategy named after the budget line funding it
  HIGH  brunei    D12      An output predates the prompt that produced it
  HIGH  brunei    D7       Flag raised while combining the budget years
  HIGH  brunei    D8       A strategy total its own programmes do not add up to
```
