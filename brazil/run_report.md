# Run report - Brazil

**🟢 Overall: PASS**  
Generated 2026-08-17 07:30 by run_pipeline.py

| Stage | Ran | Key QA |
|---|---|---|
| combine_budget_years | ok | reconcile=PASS - all years reconcile | data_quality=CLEAN |
| build_final_panel | ok | ceiling=PASS - no strategy over-counted in any year | unmatched_codes=0 |
| translate_panel | ok | 1276 cell(s) |
| build_analytics_html | ok | strategies=92 (1 unfunded) | edges=110 |
| audit_checks | FAILED | QA FAIL - 12/15 PASS (A3 13 duplicate key(s), A14 14 duplicate(s), A16 1 untraceable) [advisory] |
| data_issues | FAILED | 8 detected across 1 country(ies): 2 high, 4 medium, 2 low [advisory] |

## Outputs

- Budget layer: `Files/outputs/brazil/budget_layer_all_years.xlsx`
- FINAL panel (deliverable): `Files/outputs/brazil/FINAL_PANEL.xlsx`
- Dashboard: `Files/outputs/brazil/budget_strategy_analytics.html`
- Audit trail: `Files/outputs/union_dashboard.html`, Audit tab, filtered to this country
- Data oddities: `Files/outputs/DATA_ISSUES.xlsx`

## Full stage logs

### combine_budget_years
```
==============================================================================
COMBINED BUDGET LAYER  -  years: 2024  (1 file(s))
==============================================================================

RECONCILIATION (per year: sum of program rows vs strategy_total)

  FY2024   (national total = 5,323,812.2)
    strat 02: total=           0.0  progsum=           0.0  OK
    strat 03: total=         947.5  progsum=         947.5  OK
    strat 04: total=      32,101.8  progsum=      32,101.8  OK
    strat 05: total=      92,730.7  progsum=      92,730.7  OK
    strat 06: total=      16,664.3  progsum=      16,664.3  OK
    strat 07: total=       4,135.5  progsum=       4,135.5  OK
    strat 08: total=     278,581.5  progsum=     278,581.5  OK
    strat 09: total=   1,002,681.6  progsum=   1,002,681.6  OK
    strat 10: total=     219,826.8  progsum=     219,826.8  OK
    strat 11: total=     107,634.1  progsum=     107,634.1  OK
    strat 12: total=     162,614.0  progsum=     162,614.0  OK
    strat 13: total=       2,877.3  progsum=       2,877.3  OK
    strat 14: total=       2,170.6  progsum=       2,170.6  OK
    strat 15: total=      10,239.4  progsum=      10,239.4  OK
    strat 16: total=         682.6  progsum=         682.6  OK
    strat 17: total=       2,937.2  progsum=       2,937.2  OK
    strat 18: total=      15,386.2  progsum=      15,386.2  OK
    strat 19: total=      17,427.2  progsum=      17,427.2  OK
    strat 20: total=      29,160.4  progsum=      29,160.4  OK
    strat 21: total=       3,304.9  progsum=       3,304.9  OK
    strat 22: total=       2,255.6  progsum=       2,255.6  OK
    strat 23: total=       6,197.0  progsum=       6,197.0  OK
    strat 24: total=       3,006.8  progsum=       3,006.8  OK
    strat 25: total=       1,289.5  progsum=       1,289.5  OK
    strat 26: total=      27,266.5  progsum=      27,266.5  OK
    strat 27: total=       2,078.0  progsum=       2,078.0  OK
    strat 28: total=   3,188,051.9  progsum=   3,188,051.9  OK
    strat 99: total=      91,563.5  progsum=      91,563.5  OK

RECONCILIATION: PASS - all years reconcile

Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/brazil/budget_layer_all_years.xlsx
  sheet 'budget_all_years' : 210 rows  (feeds Prompt 6 / build_final_panel - each intervention matches against EVERY year's programs)
  sheet 'programs_wide'    : 182 programs x 1 year(s) (funding-over-time)
  sheet 'reconciliation'   : 28 rows (audit)
  sheet 'data_quality'     : 1 flagged items (see summary below)

==============================================================================
DATA-QUALITY SUMMARY
==============================================================================
  HIGH: 0   MEDIUM: 0   LOW: 0   INFO: 1
  No HIGH/MEDIUM/LOW issues - the combined budget layer looks clean.
==============================================================================
DATA QUALITY: CLEAN
==============================================================================
```

### build_final_panel
```
Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/brazil/FINAL_PANEL.xlsx
  panel               : 92 strategies x 1 years (2024)
  match_review        : 169 matches (BOTH names + rationale)
  unmatched_codes     : 0 (codes NOT in that year's budget - REVIEW)
  unfunded_strategies : 1 (strategies with no budget any year)
  funding_by_program  : 97 (per programme x year, amount once - SAFE TO SUM)
  unmapped_programs   : 85 budget programmes with no matched strategy
  risk_panel          : 10 risks | ceiling: PASS
  enrichment          : strategyclean=yes risk_summary=yes
  maturity            : mean=0.843 | financing-weighted=0.85 | {'operational_programme': 91, 'aspirational': 1}
  basket/reverse-pass : 21 shared programmes | reverse-pass edges=45 rows -> 21 new matches
  recall_review       : 18 large programmes matched to only 1 strategy (candidate baskets)
MATURITY: mean=0.843 financing_weighted=0.85
CEILING TEST: PASS - no strategy over-counted in any year
UNMATCHED CODES: 0
QA: PASS - 0 unmatched code(s), ceiling PASS, 0 year warning(s)
```

### translate_panel
```
country    brazil
workbooks  FINAL_PANEL.xlsx, budget_layer_all_years.xlsx
strings    0 new, 127 already cached
translated 1276 cell(s); originals kept in <column>_source
cache      Files/llm/brazil/translations.json - edit it to correct a translation, then re-run
```

### build_analytics_html
```
dashboard -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/brazil/budget_strategy_analytics.html
  years        2024
  edges        110
  strategies   92 (1 unfunded)
  size         60 KB
```

### audit_checks
```
AUDIT CHECKS: brazil 12/15 PASS (A3 13 duplicate key(s), A14 14 duplicate(s), A16 1 untraceable)
  ok   A1   Stored programme sums              28 strategy-year(s) / 0 disagree
  ok   A2   Stored strategy totals             28 strategy-year(s) / 0 disagree
  FAIL A3   Programme counted once             97 row(s) / 13 duplicate key(s)
            FY2024 programme 1144 appears 2 times
            FY2024 programme 1158 appears 2 times
            FY2024 programme 1191 appears 2 times
            FY2024 programme 2317 appears 2 times
            FY2024 programme 2320 appears 2 times
            FY2024 programme 2321 appears 3 times
  ok   A4   Ceiling holds                      28 strategy-year(s) / 0 over ceiling
  ok   A6   Panel money matches its edges      92 strategy-year figure(s) / 0 disagree
  ok   A8   Edges cite real programmes         169 accepted edge(s) / 0 dangle
  ok   A9   No strategy dropped                92 strategyclean row(s) / 92 panel row(s)
  ok   A10  Unfunded list is complete          1 zero-funded / 1 listed
  ok   A11  Evidence chain resolves            669 distinct id(s) / 0 dangle
  ok   A12  Maturity summary is derivable      8 metric(s) / 0 disagree
  FAIL A14  No duplicate edges                 125 edge(s) / 14 duplicate(s)
            FY2024 family farming and agroecology -> 1191 x2
            FY2024 water resources: water in quantity and q -> 2321 x3
            FY2024 1158 | climate emergency response -> 1158 x2
            FY2024 2801 | neo-industrialization, business e -> 2801 x2
            FY2024 2317 | regional development and territor -> 2317 x2
            FY2024 1144 | sustainable agriculture -> 1144 x2
  ok   A15  One currency                       1 expected / 1 found
  FAIL A16  Components are traceable           561 component(s) / 1 untraceable
            State Transformation for Citizensh <- Public Service Capacity Expansion and Improv
  ok   A17  No workbook open in Excel          0 expected / 0 found
  ok   A18  Strategies come from the plan      93 strategy(ies) / 0 with no component
```

### data_issues
```
data issues  Files/outputs/DATA_ISSUES.xlsx
  8 detected across 1 country(ies): 2 high, 4 medium, 2 low
  16 hand-written entr(ies) in 04_Docs_and_Planning/data_issues.json
  HIGH  brazil    D1       A programme code is not unique within a year
  HIGH  brazil    D12      An output predates the prompt that produced it
```
