# Run report - Afghanistan

**🔴 Overall: REVIEW NEEDED**  
Generated 2026-08-26 01:12 by run_pipeline.py

| Stage | Ran | Key QA |
|---|---|---|
| validate_stage_schema (L2) | ok | PASS 4/4 |
| validate_source_fidelity (L4) | ok | NOT CONFIGURED [advisory] |
| validate_recall (L4) | ok | NOT CONFIGURED [advisory] |
| validate_refs (L3) | ok | INPUT MISSING (1/1 not on this machine) |
| combine_budget_years | ok | reconcile=FAIL - see MISMATCH rows | data_quality=REVIEW NEEDED - resolve HIGH items before relying on totals for those strategy-years |
| build_final_panel | ok | ceiling=PASS - no strategy over-counted in any year | unmatched_codes=0 |
| build_analytics_html | ok | strategies=30 (8 unfunded) | edges=52 |
| audit_checks | ok | 19/19 PASS [advisory] |
| data_issues | FAILED | 6 detected across 1 country(ies): 2 high, 3 medium, 1 low [advisory] |

## Outputs

- Budget layer: `Files/outputs/afghanistan/budget_layer_all_years.xlsx`
- FINAL panel (deliverable): `Files/outputs/afghanistan/FINAL_PANEL.xlsx`
- Dashboard: `Files/outputs/afghanistan/budget_strategy_analytics.html`
- Audit trail: `Files/outputs/union_dashboard.html`, Audit tab, filtered to this country
- Data oddities: `Files/outputs/DATA_ISSUES.xlsx`

## Full stage logs

### validate_stage_schema (L2)
```
--- afghanistan_budget_2022.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/afghanistan/validation/schema_afghanistan_budget_2022.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- afghanistan_mapping_2022.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/afghanistan/validation/schema_afghanistan_mapping_2022.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- afghanistan_strategyclean.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/afghanistan/validation/schema_afghanistan_strategyclean.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- afghanistan_risk_summary.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/afghanistan/validation/schema_afghanistan_risk_summary.xlsx

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
--- afghanistan references
SKIPPED: input not on this machine: Files/outputs/afghanistan/budget_layer_all_years.xlsx
```

### combine_budget_years
```
==============================================================================
COMBINED BUDGET LAYER  -  years: 2022  (1 file(s))
==============================================================================

RECONCILIATION (per year: sum of program rows vs strategy_total)

  FY2022   (national total = 473,041,717,900.0)
    strat 1: total=59,153,613,834.0  progsum=83,491,803,650.0  ** MISMATCH diff=-24,338,189,816.0
    strat 2: total=115,478,234,780.0  progsum=230,577,198,938.0  ** MISMATCH diff=-115,098,964,158.0
    strat 3: total=64,831,340,360.0  progsum=132,764,724,983.0  ** MISMATCH diff=-67,933,384,623.0
    strat 4: total=104,985,833,158.0  progsum=143,654,842,474.0  ** MISMATCH diff=-38,669,009,316.0
    strat 5: total=1,509,732,611.0  progsum=21,538,553,134.0  ** MISMATCH diff=-20,028,820,523.0
    strat 6: total=10,250,402,752.0  progsum=42,356,736,212.0  ** MISMATCH diff=-32,106,333,460.0
    strat 7: total=21,201,166,284.0  progsum=55,756,954,644.0  ** MISMATCH diff=-34,555,788,360.0
    strat 8: total=5,635,821,722.0  progsum=37,134,895,582.0  ** MISMATCH diff=-31,499,073,860.0
    strat 9: total=51,467,446,050.0  progsum=108,257,609,026.0  ** MISMATCH diff=-56,790,162,976.0
    strat 10: total=20,338,151,767.0  progsum=41,907,815,185.0  ** MISMATCH diff=-21,569,663,418.0
    strat 99: total=18,189,974,582.0  progsum=18,189,974,582.0  OK

RECONCILIATION: FAIL - see MISMATCH rows

NATIONAL TOTAL (the denominator every share is computed against)
    FY2022  heads 473,041,717,900.0  programmes 915,631,108,410.0  gap  48.3%  -> GRAND_TOTAL
    FY2022  extracted 193.6% of the document's own grand total 473,041,717,901.0

READABILITY  0 of 108 programme name(s) unreadable (0%), 0 of 11 head(s) (0%), 0% of the money

HEAD NAMES: 64 row(s) renamed so a head reads the same in every year

Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/afghanistan/budget_layer_all_years.xlsx
  sheet 'budget_all_years' : 120 rows  (feeds Prompt 6 / build_final_panel - each intervention matches against EVERY year's programs)
  sheet 'programs_wide'    : 108 programs x 1 year(s) (funding-over-time)
  sheet 'reconciliation'   : 11 rows (audit)
  sheet 'data_quality'     : 121 flagged items (see summary below)

==============================================================================
DATA-QUALITY SUMMARY
==============================================================================
  HIGH: 12   MEDIUM: 108   LOW: 0   INFO: 1

  [HIGH] mixed_budget_views  (1)
      - FY2022: rows came from 2 different tables and together made 589,119,556,966.0 against a printed grand total of 473,041,717,901.0, so the same money was present twice. Kept 'Table 17: Budget Based on the Government Functions' (473,041,717,900.0, the closest to the grand total) and dropped 421 row(s) from the others.

  [HIGH] over_extraction  (1)
      - FY2022: the heads extracted sum to 915,631,108,410.0 against a printed grand total of 473,041,717,901.0 (194%), so the same money is being counted more than once.

  [HIGH] reconciliation_mismatch  (10)
      - FY2022 strat 1: programs sum to 83,491,803,650.0 but strategy_total is 59,153,613,834.0 (gap -24,338,189,816.0) - a program line is likely missing or mis-extracted for this strategy-year.
      - FY2022 strat 2: programs sum to 230,577,198,938.0 but strategy_total is 115,478,234,780.0 (gap -115,098,964,158.0) - a program line is likely missing or mis-extracted for this strategy-year.
      - FY2022 strat 3: programs sum to 132,764,724,983.0 but strategy_total is 64,831,340,360.0 (gap -67,933,384,623.0) - a program line is likely missing or mis-extracted for this strategy-year.
      ... and 7 more (see 'data_quality' sheet)

  [MEDIUM] malformed_code_repaired  (108)
      - FY2022 strat 1 1.10: program_code '10' looked malformed and was normalized to '1.10' - verify against source; fix the year file to avoid this.
      - FY2022 strat 1 1.11: program_code '11' looked malformed and was normalized to '1.11' - verify against source; fix the year file to avoid this.
      - FY2022 strat 1 1.12: program_code '12' looked malformed and was normalized to '1.12' - verify against source; fix the year file to avoid this.
      ... and 105 more (see 'data_quality' sheet)
==============================================================================
DATA QUALITY: REVIEW NEEDED - resolve HIGH items before relying on totals for those strategy-years
==============================================================================
```

### build_final_panel
```
Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/afghanistan/FINAL_PANEL.xlsx
  panel               : 30 strategies x 1 years (2022)
  match_review        : 52 matches (BOTH names + rationale)
  unmatched_codes     : 0 (codes NOT in that year's budget - REVIEW)
  unfunded_strategies : 8 (strategies with no budget any year)
  funding_by_program  : 29 (per programme x year, amount once - SAFE TO SUM)
  unmapped_programs   : 79 budget programmes with no matched strategy
  risk_panel          : 10 risks | ceiling: PASS
  enrichment          : strategyclean=yes risk_summary=yes
  maturity            : mean=0.702 | financing-weighted=0.85 | {'operational_programme': 22, 'planned': 5, 'aspirational': 3}
  basket/reverse-pass : 11 shared programmes | reverse-pass edges=none (run Prompt 6b + --coverage)
  recall_review       : 7 large programmes matched to only 1 strategy (candidate baskets)
MATURITY: mean=0.702 financing_weighted=0.85
CEILING TEST: PASS - no strategy over-counted in any year
UNMATCHED CODES: 0
QA: PASS - 0 unmatched code(s), ceiling PASS, 0 year warning(s)
```

### build_analytics_html
```
dashboard -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/afghanistan/budget_strategy_analytics.html
  years        2022
  edges        52
  strategies   30 (8 unfunded)
  size         42 KB
```

### audit_checks
```
AUDIT CHECKS: afghanistan 19/19 PASS
  ok   A1   Stored programme sums              11 strategy-year(s) / 0 disagree
  ok   A2   Stored strategy totals             11 strategy-year(s) / 0 disagree
  ok   A3   Programme counted once             29 row(s) / 0 duplicate key(s)
  ok   A4   Ceiling holds                      11 strategy-year(s) / 0 over ceiling
  ok   A6   Panel money matches its edges      30 strategy-year figure(s) / 0 disagree
  ok   A8   Edges cite real programmes         52 accepted edge(s) / 0 dangle
  ok   A9   No strategy dropped                30 strategyclean row(s) / 30 panel row(s)
  ok   A10  Unfunded list is complete          8 zero-funded / 8 listed
  ok   A11  Evidence chain resolves            133 distinct id(s) / 0 dangle
  ok   A12  Maturity summary is derivable      8 metric(s) / 0 disagree
  ok   A14  No duplicate edges                 52 edge(s) / 0 duplicate(s)
  ok   A15  One currency                       1 expected / 1 found
  ok   A16  Components are traceable           271 component(s) / 0 untraceable
  ok   A17  No workbook open in Excel          0 expected / 0 found
  ok   A18  Strategies come from the plan      30 strategy(ies) / 0 with no component
  ok   A19  Funding priority is reproducible   24 distinct (salience, funding) group(s) / 0 split across priorities
  ok   A20  The budget is readable             108 programme(s) / 0 unreadable (0%), carrying 0% of the money
  ok   A21  Ambiguous codes name their head    0 repeated code(s) / 0 edge(s) do not name a head
  ok   A22  Every intervention is traceable to a strategy 133 intervention(s) extracted / 0 uncited (0.0%)
  --   A23  The sector layer stayed out of the panel no sector run for this country
```

### data_issues
```
data issues  Files/outputs/DATA_ISSUES.xlsx
  6 detected across 1 country(ies): 2 high, 3 medium, 1 low
  70 hand-written entr(ies) in 04_Docs_and_Planning/data_issues.json
  HIGH  afghanistan D7       Flag raised while combining the budget years
  HIGH  afghanistan D8       A strategy total its own programmes do not add up to
```
