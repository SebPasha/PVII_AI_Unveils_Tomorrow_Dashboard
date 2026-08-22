# Run report - Malaysia

**🔴 Overall: REVIEW NEEDED**  
Generated 2026-08-21 16:37 by run_pipeline.py

| Stage | Ran | Key QA |
|---|---|---|
| validate_stage_schema (L2) | ok | QA FAIL - FAIL 6/17 (malaysia_budget_2024.xlsx, malaysia_budget_2026.xlsx, malaysia_mapping_2024.xlsx) |
| validate_source_fidelity (L4) | ok | NOT CONFIGURED [advisory] |
| validate_recall (L4) | ok | NOT CONFIGURED [advisory] |
| validate_refs (L3) | ok | QA FAIL - FAIL 1/1 (malaysia references) |
| combine_budget_years | ok | reconcile=FAIL - see MISMATCH rows | data_quality=REVIEW NEEDED - resolve HIGH items before relying on totals for those strategy-years |
| build_final_panel | ok | ceiling=PASS - no strategy over-counted in any year | unmatched_codes=0 |
| build_analytics_html | ok | strategies=382 (44 unfunded) | edges=2895 |
| audit_checks | FAILED | QA FAIL - 16/18 PASS (A11 9 dangle, A16 1 untraceable) [advisory] |
| data_issues | FAILED | 7 detected across 1 country(ies): 3 high, 3 medium, 1 low [advisory] |

## Outputs

- Budget layer: `Files/outputs/malaysia/budget_layer_all_years.xlsx`
- FINAL panel (deliverable): `Files/outputs/malaysia/FINAL_PANEL.xlsx`
- Dashboard: `Files/outputs/malaysia/budget_strategy_analytics.html`
- Audit trail: `Files/outputs/union_dashboard.html`, Audit tab, filtered to this country
- Data oddities: `Files/outputs/DATA_ISSUES.xlsx`

## Full stage logs

### validate_stage_schema (L2)
```
--- malaysia_budget_2022.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/malaysia/validation/schema_malaysia_budget_2022.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- malaysia_budget_2023.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/malaysia/validation/schema_malaysia_budget_2023.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- malaysia_budget_2024.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/malaysia/validation/schema_malaysia_budget_2024.xlsx

  RESULT: FAIL - 50 contract violation(s) across 1 file(s).
  The stage output is not accepted; re-run the stage or fix the prompt.

--- malaysia_budget_2025.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/malaysia/validation/schema_malaysia_budget_2025.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- malaysia_budget_2026.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/malaysia/validation/schema_malaysia_budget_2026.xlsx

  RESULT: FAIL - 6 contract violation(s) across 1 file(s).
  The stage output is not accepted; re-run the stage or fix the prompt.

--- malaysia_coverage_2022.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/malaysia/validation/schema_malaysia_coverage_2022.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- malaysia_coverage_2023.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/malaysia/validation/schema_malaysia_coverage_2023.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- malaysia_coverage_2024.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/malaysia/validation/schema_malaysia_coverage_2024.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- malaysia_coverage_2025.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/malaysia/validation/schema_malaysia_coverage_2025.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- malaysia_coverage_2026.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/malaysia/validation/schema_malaysia_coverage_2026.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- malaysia_mapping_2022.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/malaysia/validation/schema_malaysia_mapping_2022.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- malaysia_mapping_2023.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/malaysia/validation/schema_malaysia_mapping_2023.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- malaysia_mapping_2024.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/malaysia/validation/schema_malaysia_mapping_2024.xlsx

  RESULT: FAIL - 59 contract violation(s) across 1 file(s).
  The stage output is not accepted; re-run the stage or fix the prompt.

--- malaysia_mapping_2025.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/malaysia/validation/schema_malaysia_mapping_2025.xlsx

  RESULT: FAIL - 1 contract violation(s) across 1 file(s).
  The stage output is not accepted; re-run the stage or fix the prompt.

--- malaysia_mapping_2026.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/malaysia/validation/schema_malaysia_mapping_2026.xlsx

  RESULT: FAIL - 2 contract violation(s) across 1 file(s).
  The stage output is not accepted; re-run the stage or fix the prompt.

--- malaysia_strategyclean.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/malaysia/validation/schema_malaysia_strategyclean.xlsx

  RESULT: FAIL - 4 contract violation(s) across 1 file(s).
  The stage output is not accepted; re-run the stage or fix the prompt.

--- malaysia_risk_summary.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/malaysia/validation/schema_malaysia_risk_summary.xlsx

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
--- malaysia references
RESULT: FAIL - 2894 dangling reference(s) of 4610
report -> Files/outputs/malaysia/validation/refs_malaysia_references.xlsx
```

### combine_budget_years
```
==============================================================================
COMBINED BUDGET LAYER  -  years: 2022, 2023, 2024, 2025, 2026  (5 file(s))
==============================================================================

RECONCILIATION (per year: sum of program rows vs strategy_total)

  FY2022   (national total = 171,388,197,600.0)
    strat 1: total=  13,533,000.0  progsum=  19,215,800.0  ** MISMATCH diff=-5,682,800.0
    strat 2: total=   1,337,000.0  progsum=   2,500,000.0  ** MISMATCH diff=-1,163,000.0
    strat 3: total= 110,000,000.0  progsum= 111,286,000.0  ** MISMATCH diff=-1,286,000.0
    strat 4: total=     836,700.0  progsum= 128,970,400.0  ** MISMATCH diff=-128,133,700.0
    strat 5: total=     564,000.0  progsum=  20,919,000.0  ** MISMATCH diff=-20,355,000.0
    strat 6: total=     504,000.0  progsum=5,704,861,700.0  ** MISMATCH diff=-5,704,357,700.0
    strat 7: total=   2,465,300.0  progsum= 256,675,300.0  ** MISMATCH diff=-254,210,000.0
    strat 8: total=      11,000.0  progsum=  75,123,900.0  ** MISMATCH diff=-75,112,900.0
    strat 9: total=   7,340,000.0  progsum=  45,324,000.0  ** MISMATCH diff=-37,984,000.0
    strat 10: total=   5,254,500.0  progsum=3,621,353,400.0  ** MISMATCH diff=-3,616,098,900.0
    strat 11: total=   1,969,500.0  progsum=10,635,228,700.0  ** MISMATCH diff=-10,633,259,200.0
    strat 12: total=6,343,326,200.0  progsum=6,726,656,600.0  ** MISMATCH diff=-383,330,400.0
    strat 13: total=43,100,000,000.0  progsum=43,783,892,500.0  ** MISMATCH diff=-683,892,500.0
    strat 14: total=27,500,000,000.0  progsum= 342,528,400.0  ** MISMATCH diff=27,157,471,600.0
    strat 15: total=           0.0  progsum=           0.0  OK
    strat 20: total= 417,482,300.0  progsum= 417,482,300.0  OK
    strat 21: total=3,281,428,300.0  progsum=3,281,428,300.0  OK
    strat 22: total=3,520,264,300.0  progsum=3,520,264,300.0  OK
    strat 23: total=1,120,915,300.0  progsum=1,120,915,300.0  OK
    strat 24: total= 585,753,000.0  progsum= 585,753,000.0  OK
    strat 25: total=1,094,676,700.0  progsum=1,094,676,700.0  OK
    strat 26: total= 195,036,300.0  progsum= 195,036,300.0  OK
    strat 27: total= 823,509,000.0  progsum= 823,509,000.0  OK
    strat 28: total=4,053,603,700.0  progsum=1,527,593,800.0  ** MISMATCH diff=2,526,009,900.0
    strat 30: total= 520,275,300.0  progsum= 520,275,300.0  OK
    strat 31: total=1,009,695,500.0  progsum=1,009,695,500.0  OK
    strat 32: total= 256,601,400.0  progsum= 256,601,400.0  OK
    strat 33: total= 565,535,200.0  progsum=           0.0  ** MISMATCH diff=565,535,200.0
    strat 40: total=  18,065,900.0  progsum=  36,131,800.0  ** MISMATCH diff=-18,065,900.0
    strat 42: total=28,030,000,000.0  progsum=35,694,562,100.0  ** MISMATCH diff=-7,664,562,100.0
    strat 43: total=1,776,018,800.0  progsum=2,080,367,600.0  ** MISMATCH diff=-304,348,800.0
    strat 45: total= 622,025,400.0  progsum= 622,025,400.0  OK
    strat 46: total= 835,666,800.0  progsum= 835,666,800.0  OK
    strat 47: total= 888,362,300.0  progsum= 888,362,300.0  OK
    strat 48: total=2,506,876,600.0  progsum=2,506,876,600.0  OK
    strat 60: total=11,105,479,300.0  progsum=11,105,479,300.0  OK
    strat 62: total=13,513,284,200.0  progsum=13,513,284,200.0  OK
    strat 63: total=4,013,756,600.0  progsum=86,583,502,200.0  ** MISMATCH diff=-82,569,745,600.0
    strat 64: total=11,546,744,200.0  progsum=11,546,744,200.0  OK
    strat 70: total=2,000,000,000.0  progsum=           0.0  ** MISMATCH diff=2,000,000,000.0

  FY2023   (national total = 172,422,614,400.0)
    strat 1: total=  13,533,000.0  progsum=  36,638,400.0  ** MISMATCH diff=-23,105,400.0
    strat 2: total=   1,337,000.0  progsum=   3,604,700.0  ** MISMATCH diff=-2,267,700.0
    strat 3: total= 115,000,000.0  progsum= 144,084,000.0  ** MISMATCH diff=-29,084,000.0
    strat 4: total=     900,400.0  progsum=   4,097,300.0  ** MISMATCH diff=-3,196,900.0
    strat 5: total=     564,000.0  progsum=  26,922,000.0  ** MISMATCH diff=-26,358,000.0
    strat 6: total=     504,000.0  progsum=5,001,705,500.0  ** MISMATCH diff=-5,001,201,500.0
    strat 7: total=   2,465,300.0  progsum= 560,210,000.0  ** MISMATCH diff=-557,744,700.0
    strat 8: total=      11,600.0  progsum= 284,084,600.0  ** MISMATCH diff=-284,073,000.0
    strat 9: total=   6,291,600.0  progsum= 356,247,300.0  ** MISMATCH diff=-349,955,700.0
    strat 10: total=   5,254,500.0  progsum=3,861,753,900.0  ** MISMATCH diff=-3,856,499,400.0
    strat 11: total=   2,132,200.0  progsum=51,375,853,700.0  ** MISMATCH diff=-51,373,721,500.0
    strat 12: total=6,644,653,100.0  progsum=7,145,727,600.0  ** MISMATCH diff=-501,074,500.0
    strat 13: total=46,100,000,000.0  progsum=46,909,613,800.0  ** MISMATCH diff=-809,613,800.0
    strat 14: total=30,500,000,000.0  progsum=30,500,000,000.0  OK
    strat 15: total=4,736,331,000.0  progsum= 535,476,300.0  ** MISMATCH diff=4,200,854,700.0
    strat 20: total= 671,697,000.0  progsum= 397,000,000.0  ** MISMATCH diff=274,697,000.0
    strat 21: total=3,775,105,000.0  progsum=7,165,315,000.0  ** MISMATCH diff=-3,390,210,000.0
    strat 22: total=3,616,367,700.0  progsum=7,232,735,400.0  ** MISMATCH diff=-3,616,367,700.0
    strat 23: total=1,674,694,400.0  progsum=1,674,694,400.0  OK
    strat 24: total= 625,096,500.0  progsum=1,250,193,000.0  ** MISMATCH diff=-625,096,500.0
    strat 25: total=1,191,811,400.0  progsum=1,529,680,800.0  ** MISMATCH diff=-337,869,400.0
    strat 26: total= 212,141,400.0  progsum= 424,282,800.0  ** MISMATCH diff=-212,141,400.0
    strat 27: total= 865,271,900.0  progsum=1,707,750,300.0  ** MISMATCH diff=-842,478,400.0
    strat 28: total=1,544,627,300.0  progsum=3,089,254,600.0  ** MISMATCH diff=-1,544,627,300.0
    strat 30: total= 673,501,200.0  progsum=1,347,002,400.0  ** MISMATCH diff=-673,501,200.0
    strat 31: total= 837,175,600.0  progsum=1,674,351,200.0  ** MISMATCH diff=-837,175,600.0
    strat 32: total=           0.0  progsum=           0.0  OK
    strat 33: total=           0.0  progsum=           0.0  OK
    strat 40: total=  21,142,400.0  progsum=  63,427,200.0  ** MISMATCH diff=-42,284,800.0
    strat 42: total=31,500,000,000.0  progsum=63,000,000,000.0  ** MISMATCH diff=-31,500,000,000.0
    strat 43: total=1,774,905,500.0  progsum=3,549,811,000.0  ** MISMATCH diff=-1,774,905,500.0
    strat 45: total= 621,098,300.0  progsum=1,242,196,600.0  ** MISMATCH diff=-621,098,300.0
    strat 46: total= 845,163,900.0  progsum= 845,163,900.0  OK
    strat 47: total= 991,449,100.0  progsum= 991,449,100.0  OK
    strat 48: total=3,196,960,900.0  progsum=3,196,960,900.0  OK
    strat 60: total=11,414,091,900.0  progsum=34,242,275,700.0  ** MISMATCH diff=-22,828,183,800.0
    strat 62: total=13,803,000,000.0  progsum=15,477,694,400.0  ** MISMATCH diff=-1,674,694,400.0
    strat 63: total=4,082,402,000.0  progsum=94,139,515,000.0  ** MISMATCH diff=-90,057,113,000.0
    strat 64: total= 355,933,300.0  progsum=11,550,000,000.0  ** MISMATCH diff=-11,194,066,700.0

  FY2024   (national total = 240,919,693,600.0)
    strat 1: total=  13,533,000.0  progsum=  20,573,000.0  ** MISMATCH diff=-7,040,000.0
    strat 2: total=   1,337,000.0  progsum=   2,487,400.0  ** MISMATCH diff=-1,150,400.0
    strat 3: total= 120,000,000.0  progsum= 122,125,000.0  ** MISMATCH diff=-2,125,000.0
    strat 4: total=     900,400.0  progsum=   3,371,200.0  ** MISMATCH diff=-2,470,800.0
    strat 5: total=     564,000.0  progsum=  21,988,500.0  ** MISMATCH diff=-21,424,500.0
    strat 6: total=     504,000.0  progsum=4,667,519,500.0  ** MISMATCH diff=-4,667,015,500.0
    strat 7: total=   2,623,900.0  progsum= 479,500,000.0  ** MISMATCH diff=-476,876,100.0
    strat 8: total=      11,600.0  progsum= 210,089,500.0  ** MISMATCH diff=-210,077,900.0
    strat 9: total=   6,291,600.0  progsum= 319,292,200.0  ** MISMATCH diff=-313,000,600.0
    strat 10: total=   5,245,500.0  progsum=8,462,733,500.0  ** MISMATCH diff=-8,457,488,000.0
    strat 11: total=   2,002,100.0  progsum=95,806,473,400.0  ** MISMATCH diff=-95,804,471,300.0
    strat 12: total=7,292,722,600.0  progsum=9,253,423,100.0  ** MISMATCH diff=-1,960,700,500.0
    strat 13: total=49,800,000,000.0  progsum=50,853,592,600.0  ** MISMATCH diff=-1,053,592,600.0
    strat 14: total=32,000,000,000.0  progsum=33,095,181,800.0  ** MISMATCH diff=-1,095,181,800.0
    strat 15: total= 551,686,500.0  progsum=1,103,373,000.0  ** MISMATCH diff=-551,686,500.0
    strat 20: total= 428,310,200.0  progsum= 428,310,200.0  OK
    strat 21: total=4,416,168,800.0  progsum=10,323,650,200.0  ** MISMATCH diff=-5,907,481,400.0
    strat 22: total=4,115,413,600.0  progsum=8,228,827,200.0  ** MISMATCH diff=-4,113,413,600.0
    strat 23: total=1,702,499,200.0  progsum=3,892,153,300.0  ** MISMATCH diff=-2,189,654,100.0
    strat 24: total= 640,811,600.0  progsum=1,897,197,200.0  ** MISMATCH diff=-1,256,385,600.0
    strat 25: total=1,813,000,000.0  progsum=2,557,715,800.0  ** MISMATCH diff=-744,715,800.0
    strat 26: total= 231,771,500.0  progsum= 510,672,900.0  ** MISMATCH diff=-278,901,400.0
    strat 27: total= 949,372,700.0  progsum=1,898,745,400.0  ** MISMATCH diff=-949,372,700.0
    strat 28: total=1,642,026,100.0  progsum=3,284,052,200.0  ** MISMATCH diff=-1,642,026,100.0
    strat 30: total= 705,625,500.0  progsum=1,411,251,000.0  ** MISMATCH diff=-705,625,500.0
    strat 31: total= 933,539,300.0  progsum=2,701,016,100.0  ** MISMATCH diff=-1,767,476,800.0
    strat 32: total=           0.0  progsum=           0.0  OK
    strat 33: total=           0.0  progsum=           0.0  OK
    strat 40: total=  22,023,900.0  progsum=  66,071,700.0  ** MISMATCH diff=-44,047,800.0
    strat 42: total=35,150,181,800.0  progsum=97,240,817,700.0  ** MISMATCH diff=-62,090,635,900.0
    strat 43: total=1,868,236,300.0  progsum=3,736,472,600.0  ** MISMATCH diff=-1,868,236,300.0
    strat 45: total= 632,722,100.0  progsum=1,264,444,200.0  ** MISMATCH diff=-631,722,100.0
    strat 46: total= 889,552,900.0  progsum=1,712,506,000.0  ** MISMATCH diff=-822,953,100.0
    strat 47: total=1,048,270,300.0  progsum=1,927,969,900.0  ** MISMATCH diff=-879,699,600.0
    strat 48: total= 265,784,800.0  progsum=           0.0  ** MISMATCH diff=265,784,800.0
    strat 60: total=12,678,525,900.0  progsum=12,678,525,900.0  OK
    strat 62: total=13,984,821,600.0  progsum=13,984,821,600.0  OK
    strat 63: total=52,790,824,900.0  progsum=46,966,269,700.0  ** MISMATCH diff=5,824,555,200.0
    strat 64: total=12,212,788,400.0  progsum=12,212,788,400.0  OK
    strat 70: total=2,000,000,000.0  progsum=           0.0  ** MISMATCH diff=2,000,000,000.0

  FY2025   (national total = 162,973,371,700.0)
    strat 1: total=  13,533,000.0  progsum=  36,234,700.0  ** MISMATCH diff=-22,701,700.0
    strat 2: total=   5,246,000.0  progsum=   5,246,000.0  OK
    strat 3: total= 120,000,000.0  progsum= 135,448,400.0  ** MISMATCH diff=-15,448,400.0
    strat 4: total=     900,400.0  progsum= 100,919,400.0  ** MISMATCH diff=-100,019,000.0
    strat 5: total=     564,000.0  progsum=  71,303,100.0  ** MISMATCH diff=-70,739,100.0
    strat 6: total=     504,000.0  progsum=6,174,394,100.0  ** MISMATCH diff=-6,173,890,100.0
    strat 7: total= 523,726,900.0  progsum= 523,726,900.0  OK
    strat 8: total= 267,974,200.0  progsum= 358,739,800.0  ** MISMATCH diff=-90,765,600.0
    strat 9: total=   6,291,600.0  progsum= 277,882,400.0  ** MISMATCH diff=-271,590,800.0
    strat 10: total=   5,795,400.0  progsum=3,262,347,900.0  ** MISMATCH diff=-3,256,552,500.0
    strat 11: total=49,867,423,700.0  progsum=49,867,423,700.0  OK
    strat 12: total=8,107,577,600.0  progsum=8,905,078,200.0  ** MISMATCH diff=-797,500,600.0
    strat 13: total=1,559,050,100.0  progsum=54,875,731,000.0  ** MISMATCH diff=-53,316,680,900.0
    strat 14: total= 587,351,800.0  progsum=39,084,161,000.0  ** MISMATCH diff=-38,496,809,200.0
    strat 15: total= 600,847,800.0  progsum= 600,847,800.0  OK
    strat 20: total= 446,019,400.0  progsum= 446,019,400.0  OK
    strat 21: total=4,648,958,100.0  progsum=8,874,721,800.0  ** MISMATCH diff=-4,225,763,700.0
    strat 22: total=4,465,472,200.0  progsum=7,051,452,500.0  ** MISMATCH diff=-2,585,980,300.0
    strat 23: total=1,407,183,200.0  progsum=1,407,183,200.0  OK
    strat 24: total= 947,901,400.0  progsum= 947,901,400.0  OK
    strat 25: total=2,004,131,000.0  progsum=4,008,262,000.0  ** MISMATCH diff=-2,004,131,000.0
    strat 26: total= 263,191,800.0  progsum= 263,191,800.0  OK
    strat 27: total=1,022,337,500.0  progsum= 930,298,100.0  ** MISMATCH diff=92,039,400.0
    strat 28: total=1,702,433,900.0  progsum=  92,184,400.0  ** MISMATCH diff=1,610,249,500.0
    strat 30: total= 738,945,500.0  progsum= 738,945,500.0  OK
    strat 31: total=1,188,449,400.0  progsum=1,188,449,400.0  OK
    strat 32: total=           0.0  progsum=           0.0  OK
    strat 33: total= 362,674,200.0  progsum= 362,674,200.0  OK
    strat 40: total=  23,675,900.0  progsum=  47,351,800.0  ** MISMATCH diff=-23,675,900.0
    strat 42: total=38,534,287,200.0  progsum=37,238,349,300.0  ** MISMATCH diff=1,295,937,900.0
    strat 43: total=1,971,705,100.0  progsum=1,971,705,100.0  OK
    strat 45: total= 628,109,600.0  progsum=1,256,219,200.0  ** MISMATCH diff=-628,109,600.0
    strat 46: total=1,005,944,400.0  progsum=1,005,944,400.0  OK
    strat 47: total=1,077,476,700.0  progsum=2,154,953,400.0  ** MISMATCH diff=-1,077,476,700.0
    strat 48: total=  59,355,500.0  progsum= 118,711,000.0  ** MISMATCH diff=-59,355,500.0
    strat 50: total= 201,390,400.0  progsum=1,508,726,300.0  ** MISMATCH diff=-1,307,335,900.0
    strat 60: total=1,134,673,400.0  progsum=10,728,889,000.0  ** MISMATCH diff=-9,594,215,600.0
    strat 62: total=15,527,945,100.0  progsum=31,055,890,200.0  ** MISMATCH diff=-15,527,945,100.0
    strat 63: total=6,098,070,600.0  progsum=60,706,990,600.0  ** MISMATCH diff=-54,608,920,000.0
    strat 64: total=13,846,253,700.0  progsum=13,846,253,700.0  OK
    strat 70: total=2,000,000,000.0  progsum=           0.0  ** MISMATCH diff=2,000,000,000.0

  FY2026   (national total = 218,690,309,800.0)
    strat 1: total=  13,533,000.0  progsum=  30,348,100.0  ** MISMATCH diff=-16,815,100.0
    strat 2: total=   1,337,000.0  progsum=   4,181,800.0  ** MISMATCH diff=-2,844,800.0
    strat 3: total= 119,141,000.0  progsum= 144,692,000.0  ** MISMATCH diff=-25,551,000.0
    strat 4: total=     900,400.0  progsum=   1,615,400.0  ** MISMATCH diff=-715,000.0
    strat 5: total=     564,000.0  progsum=  31,157,300.0  ** MISMATCH diff=-30,593,300.0
    strat 6: total=     504,000.0  progsum=5,369,231,300.0  ** MISMATCH diff=-5,368,727,300.0
    strat 7: total=   2,583,200.0  progsum= 308,940,800.0  ** MISMATCH diff=-306,357,600.0
    strat 8: total=      11,600.0  progsum= 176,723,500.0  ** MISMATCH diff=-176,711,900.0
    strat 9: total=   5,870,000.0  progsum= 682,523,300.0  ** MISMATCH diff=-676,653,300.0
    strat 10: total=   5,895,400.0  progsum=6,989,442,800.0  ** MISMATCH diff=-6,983,547,400.0
    strat 11: total=   2,506,500.0  progsum=76,001,009,800.0  ** MISMATCH diff=-75,998,503,300.0
    strat 12: total=8,357,357,600.0  progsum=10,298,458,100.0  ** MISMATCH diff=-1,941,100,500.0
    strat 13: total=58,300,000,000.0  progsum=59,282,698,600.0  ** MISMATCH diff=-982,698,600.0
    strat 14: total=42,310,983,600.0  progsum=42,310,983,600.0  OK
    strat 15: total= 632,395,100.0  progsum= 632,395,100.0  OK
    strat 20: total= 477,821,300.0  progsum=           0.0  ** MISMATCH diff=477,821,300.0
    strat 21: total=4,826,625,900.0  progsum=4,826,625,900.0  OK
    strat 22: total=4,613,177,700.0  progsum=4,613,177,700.0  OK
    strat 23: total=1,495,439,200.0  progsum=1,495,439,200.0  OK
    strat 24: total= 658,686,700.0  progsum=1,317,373,400.0  ** MISMATCH diff=-658,686,700.0
    strat 25: total=2,091,273,800.0  progsum=4,182,547,600.0  ** MISMATCH diff=-2,091,273,800.0
    strat 26: total= 275,730,700.0  progsum= 275,730,700.0  OK
    strat 27: total=1,084,692,100.0  progsum=1,084,692,100.0  OK
    strat 28: total=1,659,153,900.0  progsum=3,318,307,800.0  ** MISMATCH diff=-1,659,153,900.0
    strat 30: total= 759,683,800.0  progsum= 533,220,600.0  ** MISMATCH diff=226,463,200.0
    strat 31: total=1,298,673,800.0  progsum=1,275,805,600.0  ** MISMATCH diff=22,868,200.0
    strat 33: total= 392,742,500.0  progsum=           0.0  ** MISMATCH diff=392,742,500.0
    strat 40: total=  24,943,100.0  progsum=  50,698,600.0  ** MISMATCH diff=-25,755,500.0
    strat 42: total=39,775,712,300.0  progsum=68,132,498,600.0  ** MISMATCH diff=-28,356,786,300.0
    strat 43: total=2,071,920,400.0  progsum=2,071,920,400.0  OK
    strat 45: total= 700,170,300.0  progsum= 700,170,300.0  OK
    strat 46: total=1,045,931,000.0  progsum=1,045,931,000.0  OK
    strat 47: total=1,132,199,700.0  progsum=1,132,199,700.0  OK
    strat 48: total=3,962,162,500.0  progsum=3,962,162,500.0  OK
    strat 50: total= 248,505,800.0  progsum= 248,505,800.0  OK
    strat 60: total=1,082,103,100.0  progsum=14,108,301,700.0  ** MISMATCH diff=-13,026,198,600.0
    strat 62: total=17,350,811,800.0  progsum=17,350,811,800.0  OK
    strat 63: total=5,225,148,700.0  progsum=59,884,100,700.0  ** MISMATCH diff=-54,658,952,000.0
    strat 64: total=14,683,417,300.0  progsum=14,683,417,300.0  OK
    strat 70: total=2,000,000,000.0  progsum=           0.0  ** MISMATCH diff=2,000,000,000.0

RECONCILIATION: FAIL - see MISMATCH rows

PROGRAMME HIERARCHY: the programme list is NESTED (15 head-year(s) where the top level and the level below it sum to the same money, 175 where they do not). Only the top level is counted, because summing every row counts the budget twice.

NATIONAL TOTAL (the denominator every share is computed against)
    FY2022  heads 171,388,197,600.0  programmes 207,930,952,400.0  gap  17.6%  -> PROGRAMMES
    FY2023  heads 172,422,614,400.0  programmes 400,992,145,500.0  gap  57.0%  -> PROGRAMMES
    FY2024  heads 240,919,693,600.0  programmes 383,800,740,100.0  gap  37.2%  -> PROGRAMMES
    FY2025  heads 162,973,371,700.0  programmes 332,910,058,300.0  gap  51.0%  -> PROGRAMMES
    FY2026  heads 218,690,309,800.0  programmes 366,392,668,000.0  gap  40.3%  -> PROGRAMMES
    The head totals under-report in 5 year(s); the programme rows are the national budget there.

READABILITY  0 of 2815 programme name(s) unreadable (0%), 0 of 200 head(s) (0%), 0% of the money

PROGRAMME CLASS (share of programme money)
    development        97,184,789,500.0    5.3%  (660 programme-year rows)
    standing_function  878,259,138,400.0   47.5%  (1262 programme-year rows)
    overhead           846,164,137,100.0   45.8%  (846 programme-year rows)
    mixed              26,304,272,700.0    1.4%  (47 programme-year rows)

COUNTABLE: 397 programme row(s) are nested detail and are NOT summed; their money is already in the parent programme.

HEAD NAMES: 1482 row(s) renamed so a head reads the same in every year

Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/malaysia/budget_layer_all_years.xlsx
  sheet 'budget_all_years' : 3015 rows  (feeds Prompt 6 / build_final_panel - each intervention matches against EVERY year's programs)
  sheet 'programs_wide'    : 1207 programs x 5 year(s) (funding-over-time)
  sheet 'reconciliation'   : 200 rows (audit)
  sheet 'data_quality'     : 4185 flagged items (see summary below)

==============================================================================
DATA-QUALITY SUMMARY
==============================================================================
  HIGH: 143   MEDIUM: 3965   LOW: 72   INFO: 5

  [HIGH] national_basis_programmes  (5)
      - FY2022: head totals sum to 171,388,197,600.0 but the programmes beneath them sum to 207,930,952,400.0 (18% apart), so the national total for this year is taken from the PROGRAMME rows. Every share for FY2022 is computed against 207,930,952,400.0.
      - FY2023: head totals sum to 172,422,614,400.0 but the programmes beneath them sum to 400,992,145,500.0 (57% apart), so the national total for this year is taken from the PROGRAMME rows. Every share for FY2023 is computed against 400,992,145,500.0.
      - FY2024: head totals sum to 240,919,693,600.0 but the programmes beneath them sum to 383,800,740,100.0 (37% apart), so the national total for this year is taken from the PROGRAMME rows. Every share for FY2024 is computed against 383,800,740,100.0.
      ... and 2 more (see 'data_quality' sheet)

  [HIGH] reconciliation_mismatch  (138)
      - FY2022 strat 1: programs sum to 19,215,800.0 but strategy_total is 13,533,000.0 (gap -5,682,800.0) - a program line is likely missing or mis-extracted for this strategy-year.
      - FY2022 strat 2: programs sum to 2,500,000.0 but strategy_total is 1,337,000.0 (gap -1,163,000.0) - a program line is likely missing or mis-extracted for this strategy-year.
      - FY2022 strat 3: programs sum to 111,286,000.0 but strategy_total is 110,000,000.0 (gap -1,286,000.0) - a program line is likely missing or mis-extracted for this strategy-year.
      ... and 135 more (see 'data_quality' sheet)

  [MEDIUM] malformed_code_repaired  (2815)
      - FY2022 strat 1 1.010000: program_code '010000' looked malformed and was normalized to '1.010000' - verify against source; fix the year file to avoid this.
      - FY2022 strat 1 1.020000: program_code '020000' looked malformed and was normalized to '1.020000' - verify against source; fix the year file to avoid this.
      - FY2022 strat 1 1.030000: program_code '030000' looked malformed and was normalized to '1.030000' - verify against source; fix the year file to avoid this.
      ... and 2812 more (see 'data_quality' sheet)

  [MEDIUM] program_missing_in_year  (1114)
      - FY2022,2023,2024 strat 1 1.040000: program '1.040000' ("ONE-OFF") exists in ['2025', '2026'] but is absent in ['2022', '2023', '2024'] - check whether it was dropped during extraction or genuinely did not exist that year.
      - FY2026 strat 10 10.010000: program '10.010000' (PENGURUSAN KAKITANGAN) exists in ['2022', '2023', '2024', '2025'] but is absent in ['2026'] - check whether it was dropped during extraction or genuinely did not exist that year.
      - FY2022,2023 strat 10 10.010100: program '10.010100' (General Administration and Finance) exists in ['2024', '2025', '2026'] but is absent in ['2022', '2023'] - check whether it was dropped during extraction or genuinely did not exist that year.
      ... and 1111 more (see 'data_quality' sheet)

  [MEDIUM] zero_amount_programme  (36)
      - FY2022 strat 28 28.030600: programme carries no money; a strategy matched only to lines like this reads as funded while receiving nothing
      - FY2022 strat 28 28.031000: programme carries no money; a strategy matched only to lines like this reads as funded while receiving nothing
      - FY2022 strat 28 28.031200: programme carries no money; a strategy matched only to lines like this reads as funded while receiving nothing
      ... and 33 more (see 'data_quality' sheet)

  [LOW] large_yoy_swing  (72)
      - FY2022->2023 strat 1 1.030000: program '1.030000' changed +476% (3,000,000.0 -> 17,271,900.0) - verify this is real and not an extraction error.
      - FY2024->2025 strat 1 1.030000: program '1.030000' changed +344% (300,000.0 -> 1,331,700.0) - verify this is real and not an extraction error.
      - FY2024->2025 strat 10 10.060300: program '10.060300' changed +1828% (103,739,700.0 -> 2,000,000,000.0) - verify this is real and not an extraction error.
      ... and 69 more (see 'data_quality' sheet)
==============================================================================
DATA QUALITY: REVIEW NEEDED - resolve HIGH items before relying on totals for those strategy-years
==============================================================================
```

### build_final_panel
```
STALE EDGES DROPPED: 556 edge(s) name a strategy the inventory does not hold (prog=556)
   ! Accelerating Technology Adoption and Innovation
   ! Affordable Housing Access for B40 and M40 Households
   ! Affordable Housing Development Programme
   ! Agensi Pengurusan Bencana Negara (NADMA)
   ! Agricommodity Entrepreneur Development for Specialty Products
   ! Agricultural Market Access and Business Development Centres
   ! Agriculture Sector Reinvigoration and Food Security
   ! BUMIPUTERA AUTOMOTIVE FUND TRUST FUND
   ! Basic Development Projects
   ! Bumiputera Corporate Equity and Investment Participation
   Re-run the stage that produced them against the current strategyclean.

Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/malaysia/FINAL_PANEL.xlsx
  panel               : 382 strategies x 5 years (2022, 2023, 2024, 2025, 2026)
  match_review        : 2895 matches (BOTH names + rationale)
  unmatched_codes     : 0 (codes NOT in that year's budget - REVIEW)
  unfunded_strategies : 44 (strategies with no budget any year)
  funding_by_program  : 872 (per programme x year, amount once - SAFE TO SUM)
  unmapped_programs   : 1943 budget programmes with no matched strategy
  risk_panel          : 10 risks | ceiling: PASS
  enrichment          : strategyclean=yes risk_summary=yes
  maturity            : mean=0.758 | financing-weighted=0.845 | {'operational_programme': 209, 'partial_operation': 102, 'operational_funded': 27, 'aspirational': 12, 'planned': 32}
  basket/reverse-pass : 516 shared programmes | reverse-pass edges=558 rows -> 2 new matches
  recall_review       : 66 large programmes matched to only 1 strategy (candidate baskets)
MATURITY: mean=0.758 financing_weighted=0.845
CEILING TEST: PASS - no strategy over-counted in any year
UNMATCHED CODES: 0
QA: PASS - 0 unmatched code(s), ceiling PASS, 0 year warning(s)
```

### build_analytics_html
```
dashboard -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/malaysia/budget_strategy_analytics.html
  years        2022, 2023, 2024, 2025, 2026
  edges        2895
  strategies   382 (44 unfunded)
  size         854 KB
```

### audit_checks
```
AUDIT CHECKS: malaysia 16/18 PASS (A11 9 dangle, A16 1 untraceable)
  ok   A1   Stored programme sums              200 strategy-year(s) / 0 disagree
  ok   A2   Stored strategy totals             200 strategy-year(s) / 0 disagree
  ok   A3   Programme counted once             872 row(s) / 0 duplicate key(s)
  ok   A4   Ceiling holds                      200 strategy-year(s) / 0 over ceiling, 15 head(s) capped on their programme sum
  ok   A6   Panel money matches its edges      1910 strategy-year figure(s) / 0 disagree
  ok   A8   Edges cite real programmes         2895 accepted edge(s) / 0 dangle
  ok   A9   No strategy dropped                382 strategyclean row(s) / 382 panel row(s)
  ok   A10  Unfunded list is complete          44 zero-funded / 44 listed
  FAIL A11  Evidence chain resolves            1447 distinct id(s) / 9 dangle
            chunk id 0 has no stage-3 row
            chunk id 1 has no stage-3 row
            chunk id 2 has no stage-3 row
            chunk id 3 has no stage-3 row
            chunk id 4 has no stage-3 row
            chunk id 5 has no stage-3 row
  ok   A12  Maturity summary is derivable      8 metric(s) / 0 disagree
  ok   A14  No duplicate edges                 2895 edge(s) / 0 duplicate(s)
  ok   A15  One currency                       1 expected / 1 found
  FAIL A16  Components are traceable           3666 component(s) / 1 untraceable
            Affordable and Inclusive Urban Liv <- Accessible Public Infrastructure Improvement
  ok   A17  No workbook open in Excel          0 expected / 0 found
  ok   A18  Strategies come from the plan      382 strategy(ies) / 0 with no component
  ok   A19  Funding priority is reproducible   336 distinct (salience, funding) group(s) / 0 split across priorities
  ok   A20  The budget is readable             2815 programme(s) / 0 unreadable (0%), carrying 0% of the money
  ok   A21  Ambiguous codes name their head    0 repeated code(s) / 0 edge(s) do not name a head
```

### data_issues
```
data issues  Files/outputs/DATA_ISSUES.xlsx
  7 detected across 1 country(ies): 3 high, 3 medium, 1 low
  37 hand-written entr(ies) in 04_Docs_and_Planning/data_issues.json
  HIGH  malaysia  D12      An output predates the prompt that produced it
  HIGH  malaysia  D7       Flag raised while combining the budget years
  HIGH  malaysia  D8       A strategy total its own programmes do not add up to
```
