# Run report - Brunei

**🔴 Overall: REVIEW NEEDED**  
Generated 2026-08-17 06:40 by run_pipeline.py

| Stage | Ran | Key QA |
|---|---|---|
| combine_budget_years | ok | reconcile=FAIL - see MISMATCH rows | data_quality=REVIEW NEEDED - resolve HIGH items before relying on totals for those strategy-years |
| build_final_panel | ok | ceiling=PASS - no strategy over-counted in any year | unmatched_codes=0 |
| build_analytics_html | ok | strategies=68 (25 unfunded) | edges=64 |
| audit_checks | FAILED | QA FAIL - 13/15 PASS (A16 4 untraceable, A18 2 with no component) [advisory] |
| data_issues | FAILED | 10 detected across 1 country(ies): 5 high, 3 medium, 2 low [advisory] |

## Outputs

- Budget layer: `Files/outputs/brunei/budget_layer_all_years.xlsx`
- FINAL panel (deliverable): `Files/outputs/brunei/FINAL_PANEL.xlsx`
- Dashboard: `Files/outputs/brunei/budget_strategy_analytics.html`
- Audit trail: `Files/outputs/union_dashboard.html`, Audit tab, filtered to this country
- Data oddities: `Files/outputs/DATA_ISSUES.xlsx`

## Full stage logs

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
Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/brunei/FINAL_PANEL.xlsx
  panel               : 68 strategies x 1 years (2025)
  match_review        : 79 matches (BOTH names + rationale)
  unmatched_codes     : 0 (codes NOT in that year's budget - REVIEW)
  unfunded_strategies : 25 (strategies with no budget any year)
  funding_by_program  : 39 (per programme x year, amount once - SAFE TO SUM)
  unmapped_programs   : 2 budget programmes with no matched strategy
  risk_panel          : 10 risks | ceiling: PASS
  enrichment          : strategyclean=yes risk_summary=yes
  maturity            : mean=0.651 | financing-weighted=0.87 | {'operational_programme': 39, 'operational_funded': 4, 'planned': 11, 'aspirational': 12, 'planned_specific': 2}
  basket/reverse-pass : 13 shared programmes | reverse-pass edges=29 rows -> 15 new matches
  recall_review       : 9 large programmes matched to only 1 strategy (candidate baskets)
MATURITY: mean=0.651 financing_weighted=0.87
CEILING TEST: PASS - no strategy over-counted in any year
UNMATCHED CODES: 0
QA: PASS - 0 unmatched code(s), ceiling PASS, 0 year warning(s)
```

### build_analytics_html
```
dashboard -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/brunei/budget_strategy_analytics.html
  years        2025
  edges        64
  strategies   68 (25 unfunded)
  size         52 KB
```

### audit_checks
```
AUDIT CHECKS: brunei 13/15 PASS (A16 4 untraceable, A18 2 with no component)
  ok   A1   Stored programme sums              3 strategy-year(s) / 0 disagree
  ok   A2   Stored strategy totals             3 strategy-year(s) / 0 disagree
  ok   A3   Programme counted once             39 row(s) / 0 duplicate key(s)
  ok   A4   Ceiling holds                      3 strategy-year(s) / 0 over ceiling
  ok   A6   Panel money matches its edges      68 strategy-year figure(s) / 0 disagree
  ok   A8   Edges cite real programmes         79 accepted edge(s) / 0 dangle
  ok   A9   No strategy dropped                68 strategyclean row(s) / 68 panel row(s)
  ok   A10  Unfunded list is complete          25 zero-funded / 25 listed
  ok   A11  Evidence chain resolves            574 distinct id(s) / 0 dangle
  ok   A12  Maturity summary is derivable      8 metric(s) / 0 disagree
  ok   A14  No duplicate edges                 64 edge(s) / 0 duplicate(s)
  ok   A15  One currency                       1 expected / 1 found
  FAIL A16  Components are traceable           1022 component(s) / 4 untraceable
            Green Building initiatives under t <- Green Building initiatives under the 12th Na
            Infrastructure provision for enhan <- Preparation and upgrading works for infrastr
            Research and innovation allocation <- Knowledge and Expertise and Innovation Enhan
            Research costs for public higher e <- Research costs for public higher education i
  ok   A17  No workbook open in Excel          0 expected / 0 found
  FAIL A18  Strategies come from the plan      69 strategy(ies) / 2 with no component
            Purchase of medicines, medical consumables and laboratory te
            Payment for medical treatment services at Gleneagles Jerudon
```

### data_issues
```
data issues  Files/outputs/DATA_ISSUES.xlsx
  10 detected across 1 country(ies): 5 high, 3 medium, 2 low
  16 hand-written entr(ies) in 04_Docs_and_Planning/data_issues.json
  HIGH  brunei    D11      Strategy named after the budget line funding it
  HIGH  brunei    D12      An output predates the prompt that produced it
  HIGH  brunei    D3       Strategy with no plan text behind it
  HIGH  brunei    D7       Flag raised while combining the budget years
  HIGH  brunei    D8       A strategy total its own programmes do not add up to
```
