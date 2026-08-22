# Run report - Thailand

**🔴 Overall: REVIEW NEEDED**  
Generated 2026-08-22 11:57 by run_pipeline.py

| Stage | Ran | Key QA |
|---|---|---|
| validate_stage_schema (L2) | ok | PASS 14/14 |
| validate_source_fidelity (L4) | ok | QA FAIL - FAIL 4/4 (thailand_budget_2023.xlsx, thailand_budget_2024.xlsx, thailand_budget_2025.xlsx) |
| validate_recall (L4) | ok | PASS 4/4 |
| validate_totals (L4) | ok | PASS 1/1 |
| validate_refs (L3) | ok | PASS 1/1 |
| combine_budget_years | ok | reconcile=PASS - all years reconcile | data_quality=REVIEW NEEDED - resolve HIGH items before relying on totals for those strategy-years |
| build_final_panel | ok | ceiling=PASS - no strategy over-counted in any year | unmatched_codes=0 |
| build_analytics_html | ok | strategies=99 (3 unfunded) | edges=732 |
| audit_checks | FAILED | QA FAIL - 18/19 PASS (A16 1 untraceable) [advisory] |
| data_issues | FAILED | 5 detected across 1 country(ies): 2 high, 2 medium, 1 low [advisory] |

## Outputs

- Budget layer: `Files/outputs/thailand/budget_layer_all_years.xlsx`
- FINAL panel (deliverable): `Files/outputs/thailand/FINAL_PANEL.xlsx`
- Dashboard: `Files/outputs/thailand/budget_strategy_analytics.html`
- Audit trail: `Files/outputs/union_dashboard.html`, Audit tab, filtered to this country
- Data oddities: `Files/outputs/DATA_ISSUES.xlsx`

## Full stage logs

### validate_stage_schema (L2)
```
--- thailand_budget_2023.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/thailand/validation/schema_thailand_budget_2023.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- thailand_budget_2024.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/thailand/validation/schema_thailand_budget_2024.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- thailand_budget_2025.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/thailand/validation/schema_thailand_budget_2025.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- thailand_budget_2026.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/thailand/validation/schema_thailand_budget_2026.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- thailand_coverage_2023.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/thailand/validation/schema_thailand_coverage_2023.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- thailand_coverage_2024.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/thailand/validation/schema_thailand_coverage_2024.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- thailand_coverage_2025.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/thailand/validation/schema_thailand_coverage_2025.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- thailand_coverage_2026.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/thailand/validation/schema_thailand_coverage_2026.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- thailand_mapping_2023.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/thailand/validation/schema_thailand_mapping_2023.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- thailand_mapping_2024.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/thailand/validation/schema_thailand_mapping_2024.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- thailand_mapping_2025.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/thailand/validation/schema_thailand_mapping_2025.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- thailand_mapping_2026.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/thailand/validation/schema_thailand_mapping_2026.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- thailand_strategyclean.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/thailand/validation/schema_thailand_strategyclean.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- thailand_risk_summary.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/thailand/validation/schema_thailand_risk_summary.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.
```

### validate_source_fidelity (L4)
```
--- thailand_budget_2023.xlsx
==============================================================================
SOURCE FIDELITY  -  thailand_budget_2023.xlsx
  verified against: 20220726_gov_tha_budget_in_brief_fy_2023.pdf (independent text extraction, 242,997 chars)
==============================================================================
  rows                 99
  amounts traced       99/99
  codes traced         99/99
  names matched        98/99

  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/thailand/validation/fidelity_thailand_budget_2023.xlsx

  RESULT: FAIL - 1 item(s) could not be traced to the source.
  Treat this extraction as unverified until each one is explained.

--- thailand_budget_2024.xlsx
==============================================================================
SOURCE FIDELITY  -  thailand_budget_2024.xlsx
  verified against: Book-2.pdf (independent text extraction, 247,242 chars)
==============================================================================
  rows                 128
  amounts traced       128/128
  codes traced         120/128
  names matched        127/128

  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/thailand/validation/fidelity_thailand_budget_2024.xlsx

  RESULT: FAIL - 9 item(s) could not be traced to the source.
  Treat this extraction as unverified until each one is explained.

--- thailand_budget_2025.xlsx
==============================================================================
SOURCE FIDELITY  -  thailand_budget_2025.xlsx
  verified against: Book.pdf (independent text extraction, 228,220 chars)
==============================================================================
  rows                 127
  amounts traced       127/127
  codes traced         120/127
  names matched        126/127

  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/thailand/validation/fidelity_thailand_budget_2025.xlsx

  RESULT: FAIL - 8 item(s) could not be traced to the source.
  Treat this extraction as unverified until each one is explained.

--- thailand_budget_2026.xlsx
==============================================================================
SOURCE FIDELITY  -  thailand_budget_2026.xlsx
  verified against: Thailand Budget 2026.pdf (independent text extraction, 228,831 chars)
==============================================================================
  rows                 104
  amounts traced       104/104
  codes traced         104/104
  names matched        103/104

  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/thailand/validation/fidelity_thailand_budget_2026.xlsx

  RESULT: FAIL - 1 item(s) could not be traced to the source.
  Treat this extraction as unverified until each one is explained.
```

### validate_recall (L4)
```
--- thailand_budget_2023.xlsx
RESULT: PASS - 66 programme code(s) extracted, none missed
report -> Files/outputs/thailand/validation/recall_thailand_budget_2023.xlsx

--- thailand_budget_2024.xlsx
RESULT: PASS - 94 programme code(s) extracted, none missed
report -> Files/outputs/thailand/validation/recall_thailand_budget_2024.xlsx

--- thailand_budget_2025.xlsx
RESULT: PASS - 94 programme code(s) extracted, none missed
report -> Files/outputs/thailand/validation/recall_thailand_budget_2025.xlsx

--- thailand_budget_2026.xlsx
RESULT: PASS - 70 programme code(s) extracted, none missed
report -> Files/outputs/thailand/validation/recall_thailand_budget_2026.xlsx
```

### validate_totals (L4)
```
--- ThaiBudget2026.xlsx
RESULT: PASS - 7 strategy total(s) reconcile and sum to the document's grand total (0.000% apart)
report -> Files/outputs/thailand/validation/totals_ThaiBudget2026.xlsx
```

### validate_refs (L3)
```
--- thailand references
RESULT: PASS - every one of 1330 reference(s) resolves
report -> Files/outputs/thailand/validation/refs_thailand_references.xlsx
```

### combine_budget_years
```
==============================================================================
COMBINED BUDGET LAYER  -  years: 2023, 2024, 2025, 2026  (4 file(s))
==============================================================================

RECONCILIATION (per year: sum of program rows vs strategy_total)

  FY2023   (national total = 3,185,000.0)
    strat 1: total=     296,003.6  progsum=     296,003.6  OK
    strat 2: total=     396,125.5  progsum=     396,125.5  OK
    strat 3: total=     549,514.0  progsum=     549,514.0  OK
    strat 4: total=     759,861.3  progsum=     759,861.3  OK
    strat 5: total=     122,964.9  progsum=     122,964.9  OK
    strat 6: total=     658,012.7  progsum=     658,012.7  OK
    strat 7: total=     402,518.0  progsum=     402,518.0  OK

  FY2024   (national total = 3,480,000.0)
    strat 1: total=     386,149.6  progsum=     386,149.6  OK
    strat 2: total=     392,028.6  progsum=     392,028.6  OK
    strat 3: total=     561,167.1  progsum=     561,167.1  OK
    strat 4: total=     836,382.5  progsum=     836,382.5  OK
    strat 5: total=     131,020.5  progsum=     131,020.5  OK
    strat 6: total=     608,210.5  progsum=     608,210.5  OK
    strat 7: total=     565,041.2  progsum=     565,041.2  OK

  FY2025   (national total = 3,752,700.0)
    strat 1: total=     403,868.0  progsum=     403,868.0  OK
    strat 2: total=     362,199.9  progsum=     362,199.9  OK
    strat 3: total=     582,704.1  progsum=     582,704.1  OK
    strat 4: total=     926,266.8  progsum=     926,266.8  OK
    strat 5: total=     136,851.3  progsum=     136,851.3  OK
    strat 6: total=     645,499.5  progsum=     645,499.5  OK
    strat 7: total=     695,310.4  progsum=     695,310.4  OK

  FY2026   (national total = 3,780,600.0)
    strat 1: total=     413,907.6  progsum=     413,907.6  OK
    strat 2: total=     399,334.9  progsum=     399,334.9  OK
    strat 3: total=     604,805.7  progsum=     604,805.7  OK
    strat 4: total=     941,299.9  progsum=     941,299.9  OK
    strat 5: total=     146,658.0  progsum=     146,658.0  OK
    strat 6: total=     604,228.4  progsum=     604,228.4  OK
    strat 7: total=     670,365.5  progsum=     670,365.5  OK

RECONCILIATION: PASS - all years reconcile

NATIONAL TOTAL (the denominator every share is computed against)
    FY2023  heads 3,185,000.0  programmes 3,185,000.0  gap   0.0%  -> GRAND_TOTAL
    FY2024  heads 3,480,000.0  programmes 3,480,000.0  gap   0.0%  -> GRAND_TOTAL
    FY2025  heads 3,752,700.0  programmes 3,752,700.0  gap   0.0%  -> GRAND_TOTAL
    FY2026  heads 3,780,600.0  programmes 3,780,600.0  gap   0.0%  -> GRAND_TOTAL
    FY2023  extracted 100.0% of the document's own grand total 3,185,000.0
    FY2024  extracted 100.0% of the document's own grand total 3,480,000.0
    FY2025  extracted 100.0% of the document's own grand total 3,752,700.0
    FY2026  extracted 100.0% of the document's own grand total 3,780,600.0

READABILITY  0 of 273 programme name(s) unreadable (0%), 0 of 28 head(s) (0%), 0% of the money

PROGRAMME CLASS (share of programme money)
    development           8,395,002.4   59.1%  (223 programme-year rows)
    standing_function       579,196.4    4.1%  (8 programme-year rows)
    overhead              5,213,989.3   36.7%  (41 programme-year rows)
    (unclassified)           10,111.9    0.1%  (0 programme-year rows)

Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/thailand/budget_layer_all_years.xlsx
  sheet 'budget_all_years' : 305 rows  (feeds Prompt 6 / build_final_panel - each intervention matches against EVERY year's programs)
  sheet 'programs_wide'    : 71 programs x 4 year(s) (funding-over-time)
  sheet 'reconciliation'   : 28 rows (audit)
  sheet 'data_quality'     : 28 flagged items (see summary below)

==============================================================================
DATA-QUALITY SUMMARY
==============================================================================
  HIGH: 4   MEDIUM: 6   LOW: 14   INFO: 4

  [HIGH] mixed_budget_views  (4)
      - FY2023: rows came from 2 different tables and together made 5,227,014.9 against a printed grand total of 3,185,000.0, so the same money was present twice. Kept 'Table I-4 Budget Allocation Strategy and Program FY 2023' (3,185,000.0, the closest to the grand total) and dropped 25 row(s) from the others.
      - FY2024: rows came from 2 different tables and together made 5,748,909.0 against a printed grand total of 3,480,000.0, so the same money was present twice. Kept 'Table I-4 Budget Allocation Strategy and Program FY 2024' (3,480,000.0, the closest to the grand total) and dropped 52 row(s) from the others.
      - FY2025: rows came from 2 different tables and together made 5,996,079.1 against a printed grand total of 3,752,700.0, so the same money was present twice. Kept 'Table I-4 Budget Allocation Strategy and Program FY 2025' (3,752,700.0, the closest to the grand total) and dropped 50 row(s) from the others.
      ... and 1 more (see 'data_quality' sheet)

  [MEDIUM] program_missing_in_year  (6)
      - FY2024,2025 strat 1 1.14: program '1.14' (Program on Public Sector Personnel) exists in ['2023', '2026'] but is absent in ['2024', '2025'] - check whether it was dropped during extraction or genuinely did not exist that year.
      - FY2023 strat 2 2.16: program '2.16' (Program on Public Sector Personnel) exists in ['2024', '2025', '2026'] but is absent in ['2023'] - check whether it was dropped during extraction or genuinely did not exist that year.
      - FY2023,2024,2026 strat 2 2.17: program '2.17' (Program on Public Sector Personnel) exists in ['2025'] but is absent in ['2023', '2024', '2026'] - check whether it was dropped during extraction or genuinely did not exist that year.
      ... and 3 more (see 'data_quality' sheet)

  [LOW] large_yoy_swing  (14)
      - FY2023->2024 strat 1 1.12: program '1.12' changed +6462% (536.8 -> 35,226.2) - verify this is real and not an extraction error.
      - FY2023->2024 strat 1 1.13: program '1.13' changed +503% (33,838.4 -> 204,072.1) - verify this is real and not an extraction error.
      - FY2024->2025 strat 2 2.10: program '2.10' changed +966% (446.3 -> 4,758.7) - verify this is real and not an extraction error.
      ... and 11 more (see 'data_quality' sheet)
==============================================================================
DATA QUALITY: REVIEW NEEDED - resolve HIGH items before relying on totals for those strategy-years
==============================================================================
```

### build_final_panel
```
STALE EDGES DROPPED: 52 edge(s) name a strategy the inventory does not hold (prog=52)
   ! Integrated Program on Development of Future Industries and Services
   ! Integrated Program on Digital Government
   ! Integrated Program on Preparedness to Accommodate the Aging Society
   ! Strategic Program on Coping with Repercussions from Climate Change
   ! Strategic Program on Creation of Sustainable Growth with Regard to Conservation, Rehabil
   ! Strategic Program on Development of Digital Economy and Society
   ! Strategic Program on Development of Education and Learning Quality
   ! Strategic Program on Development of Human Potentials on a Life-Long Basis
   ! Strategic Program on Development of Science, Technology and Innovation Potentials
   ! Strategic Program on Development of Special Economic Zones
   Re-run the stage that produced them against the current strategyclean.

Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/thailand/FINAL_PANEL.xlsx
  panel               : 99 strategies x 4 years (2023, 2024, 2025, 2026)
  match_review        : 732 matches (BOTH names + rationale)
  unmatched_codes     : 0 (codes NOT in that year's budget - REVIEW)
  unfunded_strategies : 3 (strategies with no budget any year)
  funding_by_program  : 153 (per programme x year, amount once - SAFE TO SUM)
  unmapped_programs   : 120 budget programmes with no matched strategy
  risk_panel          : 9 risks | ceiling: PASS
  enrichment          : strategyclean=yes risk_summary=yes
  maturity            : mean=0.829 | financing-weighted=0.849 | {'operational_programme': 92, 'partial_operation': 4, 'planned': 3}
  basket/reverse-pass : 131 shared programmes | reverse-pass edges=52 rows -> 0 new matches
  recall_review       : 6 large programmes matched to only 1 strategy (candidate baskets)
MATURITY: mean=0.829 financing_weighted=0.849
CEILING TEST: PASS - no strategy over-counted in any year
UNMATCHED CODES: 0
QA: PASS - 0 unmatched code(s), ceiling PASS, 0 year warning(s)
```

### build_analytics_html
```
dashboard -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/thailand/budget_strategy_analytics.html
  years        2023, 2024, 2025, 2026
  edges        732
  strategies   99 (3 unfunded)
  size         250 KB
```

### audit_checks
```
AUDIT CHECKS: thailand 18/19 PASS (A16 1 untraceable)
  ok   A1   Stored programme sums              28 strategy-year(s) / 0 disagree
  ok   A2   Stored strategy totals             28 strategy-year(s) / 0 disagree
  ok   A3   Programme counted once             153 row(s) / 0 duplicate key(s)
  ok   A4   Ceiling holds                      28 strategy-year(s) / 0 over ceiling
  ok   A6   Panel money matches its edges      396 strategy-year figure(s) / 0 disagree
  ok   A8   Edges cite real programmes         732 accepted edge(s) / 0 dangle
  ok   A9   No strategy dropped                99 strategyclean row(s) / 99 panel row(s)
  ok   A10  Unfunded list is complete          3 zero-funded / 3 listed
  ok   A11  Evidence chain resolves            525 distinct id(s) / 0 dangle
  ok   A12  Maturity summary is derivable      8 metric(s) / 0 disagree
  ok   A14  No duplicate edges                 732 edge(s) / 0 duplicate(s)
  ok   A15  One currency                       1 expected / 1 found
  FAIL A16  Components are traceable           890 component(s) / 1 untraceable
            SME regulatory reform, competition <- Fair Competition and Opportunity Promotion
  ok   A17  No workbook open in Excel          0 expected / 0 found
  ok   A18  Strategies come from the plan      99 strategy(ies) / 0 with no component
  ok   A19  Funding priority is reproducible   82 distinct (salience, funding) group(s) / 0 split across priorities
  ok   A20  The budget is readable             273 programme(s) / 0 unreadable (0%), carrying 0% of the money
  ok   A21  Ambiguous codes name their head    0 repeated code(s) / 0 edge(s) do not name a head
  ok   A22  Consolidation keeps every intervention 533 intervention(s) extracted / 8 dropped (1.5%)
            202
            369
            383
            452
            472
            497
  --   A23  The sector layer stayed out of the panel no sector run for this country
```

### data_issues
```
data issues  Files/outputs/DATA_ISSUES.xlsx
  5 detected across 1 country(ies): 2 high, 2 medium, 1 low
  51 hand-written entr(ies) in 04_Docs_and_Planning/data_issues.json
  HIGH  thailand  D12      An output predates the prompt that produced it
  HIGH  thailand  D7       Flag raised while combining the budget years
```
