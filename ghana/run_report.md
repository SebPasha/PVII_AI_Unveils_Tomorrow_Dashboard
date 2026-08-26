# Run report - Ghana

**🔴 Overall: REVIEW NEEDED**  
Generated 2026-08-26 09:18 by run_pipeline.py

| Stage | Ran | Key QA |
|---|---|---|
| validate_stage_schema (L2) | ok | QA FAIL - FAIL 3/6 (ghana_budget_2024.xlsx, ghana_mapping_2024.xlsx, ghana_strategyclean.xlsx) |
| validate_source_fidelity (L4) | ok | NOT CONFIGURED [advisory] |
| validate_recall (L4) | ok | NOT CONFIGURED [advisory] |
| validate_refs (L3) | ok | INPUT MISSING (1/1 not on this machine) |
| combine_budget_years | ok | reconcile=FAIL - see MISMATCH rows | data_quality=REVIEW NEEDED - resolve HIGH items before relying on totals for those strategy-years |
| build_final_panel | ok | ceiling=PASS - no strategy over-counted in any year | unmatched_codes=0 |
| build_analytics_html | ok | strategies=241 (55 unfunded) | edges=328 |
| audit_checks | FAILED | QA FAIL - 18/19 PASS (A16 2 untraceable) [advisory] |
| data_issues | FAILED | 6 detected across 1 country(ies): 2 high, 3 medium, 1 low [advisory] |

## Outputs

- Budget layer: `Files/outputs/ghana/budget_layer_all_years.xlsx`
- FINAL panel (deliverable): `Files/outputs/ghana/FINAL_PANEL.xlsx`
- Dashboard: `Files/outputs/ghana/budget_strategy_analytics.html`
- Audit trail: `Files/outputs/union_dashboard.html`, Audit tab, filtered to this country
- Data oddities: `Files/outputs/DATA_ISSUES.xlsx`

## Full stage logs

### validate_stage_schema (L2)
```
--- ghana_budget_2019.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/ghana/validation/schema_ghana_budget_2019.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- ghana_budget_2024.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/ghana/validation/schema_ghana_budget_2024.xlsx

  RESULT: FAIL - 2 contract violation(s) across 1 file(s).
  The stage output is not accepted; re-run the stage or fix the prompt.

--- ghana_mapping_2019.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/ghana/validation/schema_ghana_mapping_2019.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- ghana_mapping_2024.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/ghana/validation/schema_ghana_mapping_2024.xlsx

  RESULT: FAIL - 6 contract violation(s) across 1 file(s).
  The stage output is not accepted; re-run the stage or fix the prompt.

--- ghana_strategyclean.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/ghana/validation/schema_ghana_strategyclean.xlsx

  RESULT: FAIL - 4 contract violation(s) across 1 file(s).
  The stage output is not accepted; re-run the stage or fix the prompt.

--- ghana_risk_summary.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/ghana/validation/schema_ghana_risk_summary.xlsx

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
--- ghana references
SKIPPED: input not on this machine: Files/outputs/ghana/budget_layer_all_years.xlsx
```

### combine_budget_years
```
==============================================================================
COMBINED BUDGET LAYER  -  years: 2019, 2024  (2 file(s))
==============================================================================

RECONCILIATION (per year: sum of program rows vs strategy_total)

  FY2019   (national total = 68,449,776,421.0)
    strat 1: total=1,928,735,250.0  progsum=1,773,070,250.0  ** MISMATCH diff=155,665,000.0
    strat 2: total=  17,571,445.0  progsum=           0.0  ** MISMATCH diff=17,571,445.0
    strat 3: total=   2,668,000.0  progsum=           0.0  ** MISMATCH diff=2,668,000.0
    strat 4: total=   1,718,350.0  progsum=           0.0  ** MISMATCH diff=1,718,350.0
    strat 5: total= 122,787,463.0  progsum=           0.0  ** MISMATCH diff=122,787,463.0
    strat 6: total= 262,692,717.0  progsum=           0.0  ** MISMATCH diff=262,692,717.0
    strat 7: total= 307,119,810.0  progsum=           0.0  ** MISMATCH diff=307,119,810.0
    strat 8: total=   8,056,040.0  progsum=           0.0  ** MISMATCH diff=8,056,040.0
    strat 9: total=  28,261,155.0  progsum=           0.0  ** MISMATCH diff=28,261,155.0
    strat 10: total= 766,357,713.0  progsum=           0.0  ** MISMATCH diff=766,357,713.0
    strat 11: total= 381,049,104.0  progsum=           0.0  ** MISMATCH diff=381,049,104.0
    strat 12: total= 339,381,110.0  progsum=           0.0  ** MISMATCH diff=339,381,110.0
    strat 13: total=  67,734,094.0  progsum= 680,355,804.0  ** MISMATCH diff=-612,621,710.0
    strat 14: total=   3,917,254.0  progsum=           0.0  ** MISMATCH diff=3,917,254.0
    strat 15: total=   7,312,555.0  progsum=           0.0  ** MISMATCH diff=7,312,555.0
    strat 16: total=  86,513,829.0  progsum=           0.0  ** MISMATCH diff=86,513,829.0
    strat 17: total=   2,127,498.0  progsum=           0.0  ** MISMATCH diff=2,127,498.0
    strat 18: total= 468,581,710.0  progsum=           0.0  ** MISMATCH diff=468,581,710.0
    strat 19: total=  19,672,524.0  progsum=           0.0  ** MISMATCH diff=19,672,524.0
    strat 20: total= 253,836,468.0  progsum=  11,400,000.0  ** MISMATCH diff=242,436,468.0
    strat 21: total= 158,566,030.0  progsum=           0.0  ** MISMATCH diff=158,566,030.0
    strat 22: total=  53,150,060.0  progsum=           0.0  ** MISMATCH diff=53,150,060.0
    strat 23: total= 240,723,130.0  progsum=           0.0  ** MISMATCH diff=240,723,130.0
    strat 24: total=  86,416,134.0  progsum=           0.0  ** MISMATCH diff=86,416,134.0
    strat 25: total=  49,168,950.0  progsum=           0.0  ** MISMATCH diff=49,168,950.0
    strat 26: total=  71,047,355.0  progsum=           0.0  ** MISMATCH diff=71,047,355.0
    strat 27: total= 184,151,965.0  progsum=           0.0  ** MISMATCH diff=184,151,965.0
    strat 28: total= 426,565,371.0  progsum=           0.0  ** MISMATCH diff=426,565,371.0
    strat 29: total=  31,457,512.0  progsum=           0.0  ** MISMATCH diff=31,457,512.0
    strat 30: total= 101,065,009.0  progsum=           0.0  ** MISMATCH diff=101,065,009.0
    strat 31: total=   4,921,600.0  progsum=           0.0  ** MISMATCH diff=4,921,600.0
    strat 32: total=  21,641,626.0  progsum=           0.0  ** MISMATCH diff=21,641,626.0
    strat 33: total=1,321,543,928.0  progsum=1,126,771,424.0  ** MISMATCH diff=194,772,504.0
    strat 34: total= 109,942,001.0  progsum=           0.0  ** MISMATCH diff=109,942,001.0
    strat 35: total=11,023,387,197.0  progsum=1,682,641,924.0  ** MISMATCH diff=9,340,745,273.0
    strat 36: total=  49,393,718.0  progsum=           0.0  ** MISMATCH diff=49,393,718.0
    strat 37: total=  38,007,618.0  progsum=           0.0  ** MISMATCH diff=38,007,618.0
    strat 38: total=  45,578,190.0  progsum=           0.0  ** MISMATCH diff=45,578,190.0
    strat 39: total=  42,502,066.0  progsum=           0.0  ** MISMATCH diff=42,502,066.0
    strat 40: total=3,468,776,474.0  progsum=           0.0  ** MISMATCH diff=3,468,776,474.0
    strat 41: total= 468,150,788.0  progsum= 430,016,517.0  ** MISMATCH diff=38,134,271.0
    strat 42: total=   5,315,359.0  progsum=           0.0  ** MISMATCH diff=5,315,359.0
    strat 43: total= 104,655,796.0  progsum=           0.0  ** MISMATCH diff=104,655,796.0
    strat 44: total=1,206,479,434.0  progsum=           0.0  ** MISMATCH diff=1,206,479,434.0
    strat 45: total=  31,948,070.0  progsum=           0.0  ** MISMATCH diff=31,948,070.0
    strat 46: total= 311,556,380.0  progsum=           0.0  ** MISMATCH diff=311,556,380.0
    strat 47: total=2,365,026,950.0  progsum=           0.0  ** MISMATCH diff=2,365,026,950.0
    strat 48: total= 554,919,923.0  progsum=           0.0  ** MISMATCH diff=554,919,923.0
    strat 49: total= 180,160,231.0  progsum=           0.0  ** MISMATCH diff=180,160,231.0
    strat 51: total=1,243,941,758.0  progsum=           0.0  ** MISMATCH diff=1,243,941,758.0
    strat 52: total= 388,731,799.0  progsum=           0.0  ** MISMATCH diff=388,731,799.0
    strat 53: total=1,768,729,687.0  progsum=           0.0  ** MISMATCH diff=1,768,729,687.0
    strat 54: total= 113,795,815.0  progsum=           0.0  ** MISMATCH diff=113,795,815.0
    strat 55: total= 254,658,836.0  progsum= 120,000,000.0  ** MISMATCH diff=134,658,836.0
    strat 56: total=  95,616,060.0  progsum=           0.0  ** MISMATCH diff=95,616,060.0
    strat 58: total= 204,770,633.0  progsum=           0.0  ** MISMATCH diff=204,770,633.0
    strat 60: total=18,645,707,469.0  progsum=           0.0  ** MISMATCH diff=18,645,707,469.0
    strat 61: total= 180,260,489.0  progsum=           0.0  ** MISMATCH diff=180,260,489.0
    strat 62: total=1,692,678,294.0  progsum=           0.0  ** MISMATCH diff=1,692,678,294.0
    strat 63: total=1,206,763,545.0  progsum=           0.0  ** MISMATCH diff=1,206,763,545.0
    strat 64: total= 964,236,288.0  progsum=           0.0  ** MISMATCH diff=964,236,288.0
    strat 65: total=  22,751,251.0  progsum=           0.0  ** MISMATCH diff=22,751,251.0
    strat 66: total=2,079,426,613.0  progsum=           0.0  ** MISMATCH diff=2,079,426,613.0
    strat 67: total=1,264,945,726.0  progsum=           0.0  ** MISMATCH diff=1,264,945,726.0
    strat 68: total=2,141,089,300.0  progsum=           0.0  ** MISMATCH diff=2,141,089,300.0
    strat 70: total= 730,000,000.0  progsum=           0.0  ** MISMATCH diff=730,000,000.0
    strat 72: total=5,331,065,107.0  progsum=           0.0  ** MISMATCH diff=5,331,065,107.0
    strat 73: total=2,288,294,797.0  progsum=           0.0  ** MISMATCH diff=2,288,294,797.0

  FY2024   (national total = 260,644,180,885.0)
    strat 1: total=2,074,827,164.0  progsum=2,074,827,164.0  OK
    strat 2: total=  58,415,102.0  progsum=  58,415,102.0  OK
    strat 3: total=1,029,466,639.0  progsum=           0.0  ** MISMATCH diff=1,029,466,639.0
    strat 4: total= 633,740,507.0  progsum=           0.0  ** MISMATCH diff=633,740,507.0
    strat 5: total=  23,614,645.0  progsum=           0.0  ** MISMATCH diff=23,614,645.0
    strat 6: total= 786,934,764.0  progsum=           0.0  ** MISMATCH diff=786,934,764.0
    strat 7: total=1,127,787,155.0  progsum=           0.0  ** MISMATCH diff=1,127,787,155.0
    strat 8: total=2,249,577,038.0  progsum=2,249,577,038.0  OK
    strat 9: total=2,812,541,905.0  progsum=2,812,541,905.0  OK
    strat 10: total=  23,542,520.0  progsum=           0.0  ** MISMATCH diff=23,542,520.0
    strat 11: total=  63,275,187.0  progsum=           0.0  ** MISMATCH diff=63,275,187.0
    strat 12: total= 267,798,909.0  progsum=           0.0  ** MISMATCH diff=267,798,909.0
    strat 13: total=  22,890,222.0  progsum=           0.0  ** MISMATCH diff=22,890,222.0
    strat 14: total=   9,423,774.0  progsum=           0.0  ** MISMATCH diff=9,423,774.0
    strat 15: total=3,320,653,634.0  progsum=3,320,653,634.0  OK
    strat 16: total= 298,772,253.0  progsum= 298,772,253.0  OK
    strat 17: total=1,734,758,575.0  progsum=1,734,758,575.0  OK
    strat 18: total=1,021,060,398.0  progsum=1,021,060,398.0  OK
    strat 19: total= 175,388,099.0  progsum=           0.0  ** MISMATCH diff=175,388,099.0
    strat 20: total=1,173,985,819.0  progsum=1,173,985,819.0  OK
    strat 21: total=1,499,754,383.0  progsum=1,499,754,383.0  OK
    strat 22: total= 741,052,380.0  progsum= 741,052,380.0  OK
    strat 23: total= 600,376,600.0  progsum= 600,376,600.0  OK
    strat 24: total=4,613,561,787.0  progsum=4,613,561,787.0  OK
    strat 25: total=1,237,216,612.0  progsum=1,237,216,612.0  OK
    strat 26: total= 267,212,801.0  progsum= 267,212,801.0  OK
    strat 27: total= 800,032,705.0  progsum= 800,032,705.0  OK
    strat 28: total=29,514,197,713.0  progsum=29,514,197,713.0  OK
    strat 29: total= 191,041,070.0  progsum=           0.0  ** MISMATCH diff=191,041,070.0
    strat 30: total= 135,204,490.0  progsum=           0.0  ** MISMATCH diff=135,204,490.0
    strat 31: total= 195,795,973.0  progsum= 195,795,973.0  OK
    strat 32: total= 167,547,192.0  progsum=           0.0  ** MISMATCH diff=167,547,192.0
    strat 33: total= 111,008,416.0  progsum=           0.0  ** MISMATCH diff=111,008,416.0
    strat 34: total=15,727,237,279.0  progsum=15,727,237,279.0  OK
    strat 35: total=2,392,960,280.0  progsum=2,392,960,280.0  OK
    strat 36: total=  21,021,668.0  progsum=           0.0  ** MISMATCH diff=21,021,668.0
    strat 37: total= 481,279,367.0  progsum= 481,279,368.0  ** MISMATCH diff=-1.0
    strat 38: total=  33,424,217.0  progsum=           0.0  ** MISMATCH diff=33,424,217.0
    strat 39: total=3,891,151,856.0  progsum=3,891,151,856.0  OK
    strat 40: total=  88,277,405.0  progsum=           0.0  ** MISMATCH diff=88,277,405.0
    strat 41: total= 944,780,576.0  progsum= 944,780,576.0  OK
    strat 42: total=8,378,262,940.0  progsum=8,378,262,940.0  OK
    strat 43: total=1,636,239,088.0  progsum=1,636,239,088.0  OK
    strat 44: total= 149,005,669.0  progsum=           0.0  ** MISMATCH diff=149,005,669.0
    strat 45: total=9,803,993,401.0  progsum=14,583,993,401.0  ** MISMATCH diff=-4,780,000,000.0
    strat 46: total=1,010,000,000.0  progsum=           0.0  ** MISMATCH diff=1,010,000,000.0
    strat 47: total=4,018,973,864.0  progsum=           0.0  ** MISMATCH diff=4,018,973,864.0
    strat 48: total= 350,659,152.0  progsum=           0.0  ** MISMATCH diff=350,659,152.0
    strat 49: total=1,058,732,451.0  progsum=1,058,732,451.0  OK
    strat 50: total=2,563,967,644.0  progsum=           0.0  ** MISMATCH diff=2,563,967,644.0
    strat 51: total= 384,595,147.0  progsum=           0.0  ** MISMATCH diff=384,595,147.0
    strat 52: total=3,729,210,800.0  progsum=           0.0  ** MISMATCH diff=3,729,210,800.0
    strat 53: total=55,932,447,620.0  progsum=           0.0  ** MISMATCH diff=55,932,447,620.0
    strat 54: total= 426,132,222.0  progsum=           0.0  ** MISMATCH diff=426,132,222.0
    strat 55: total=6,717,181,683.0  progsum=           0.0  ** MISMATCH diff=6,717,181,683.0
    strat 56: total=3,273,770,485.0  progsum=           0.0  ** MISMATCH diff=3,273,770,485.0
    strat 57: total=1,192,715,344.0  progsum=           0.0  ** MISMATCH diff=1,192,715,344.0
    strat 58: total=  26,789,328.0  progsum=           0.0  ** MISMATCH diff=26,789,328.0
    strat 59: total=5,758,254,325.0  progsum= 401,819,931.0  ** MISMATCH diff=5,356,434,394.0
    strat 60: total=1,812,493,968.0  progsum=1,812,493,968.0  OK
    strat 61: total=1,443,530,842.0  progsum=           0.0  ** MISMATCH diff=1,443,530,842.0
    strat 62: total=7,906,336,129.0  progsum=           0.0  ** MISMATCH diff=7,906,336,129.0
    strat 63: total= 870,000,000.0  progsum= 870,000,000.0  OK
    strat 64: total=26,395,018,327.0  progsum=26,395,018,327.0  OK
    strat 65: total=11,613,000,000.0  progsum=           0.0  ** MISMATCH diff=11,613,000,000.0
    strat 66: total=20,758,575,240.0  progsum=           0.0  ** MISMATCH diff=20,758,575,240.0
    strat 230: total=     896,541.0  progsum=           0.0  ** MISMATCH diff=896,541.0
    strat 250: total=     852,041.0  progsum=           0.0  ** MISMATCH diff=852,041.0
    strat 251: total=  15,698,882.0  progsum=           0.0  ** MISMATCH diff=15,698,882.0
    strat 252: total=     817,041.0  progsum=           0.0  ** MISMATCH diff=817,041.0
    strat 253: total=   4,438,365.0  progsum=           0.0  ** MISMATCH diff=4,438,365.0
    strat 254: total=     683,290.0  progsum=           0.0  ** MISMATCH diff=683,290.0
    strat 255: total=     926,541.0  progsum=           0.0  ** MISMATCH diff=926,541.0
    strat 256: total=     858,951.0  progsum=           0.0  ** MISMATCH diff=858,951.0
    strat 257: total=     866,541.0  progsum=           0.0  ** MISMATCH diff=866,541.0
    strat 258: total=     866,541.0  progsum=           0.0  ** MISMATCH diff=866,541.0
    strat 259: total=     860,586.0  progsum=           0.0  ** MISMATCH diff=860,586.0
    strat 260: total=     811,086.0  progsum=           0.0  ** MISMATCH diff=811,086.0
    strat 261: total=     759,700.0  progsum=           0.0  ** MISMATCH diff=759,700.0
    strat 262: total=     896,541.0  progsum=           0.0  ** MISMATCH diff=896,541.0
    strat 263: total=     957,586.0  progsum=           0.0  ** MISMATCH diff=957,586.0
    strat 264: total=  33,784,293.0  progsum=           0.0  ** MISMATCH diff=33,784,293.0
    strat 265: total=     901,541.0  progsum=           0.0  ** MISMATCH diff=901,541.0
    strat 266: total=     856,086.0  progsum=           0.0  ** MISMATCH diff=856,086.0
    strat 267: total=     866,541.0  progsum=           0.0  ** MISMATCH diff=866,541.0
    strat 268: total=     817,041.0  progsum=           0.0  ** MISMATCH diff=817,041.0
    strat 269: total=     852,996.0  progsum=           0.0  ** MISMATCH diff=852,996.0
    strat 270: total=     841,086.0  progsum=           0.0  ** MISMATCH diff=841,086.0
    strat 271: total=     846,086.0  progsum=           0.0  ** MISMATCH diff=846,086.0
    strat 272: total=     852,041.0  progsum=           0.0  ** MISMATCH diff=852,041.0
    strat 273: total=     852,996.0  progsum=           0.0  ** MISMATCH diff=852,996.0
    strat 274: total=     877,041.0  progsum=           0.0  ** MISMATCH diff=877,041.0
    strat 275: total=     817,041.0  progsum=           0.0  ** MISMATCH diff=817,041.0
    strat 276: total=     811,086.0  progsum=           0.0  ** MISMATCH diff=811,086.0
    strat 277: total=     890,586.0  progsum=           0.0  ** MISMATCH diff=890,586.0
    strat 278: total=     817,041.0  progsum=           0.0  ** MISMATCH diff=817,041.0
    strat 279: total=     819,596.0  progsum=           0.0  ** MISMATCH diff=819,596.0
    strat 280: total=     901,541.0  progsum=           0.0  ** MISMATCH diff=901,541.0
    strat 281: total=     866,541.0  progsum=           0.0  ** MISMATCH diff=866,541.0
    strat 282: total=  19,737,261.0  progsum=           0.0  ** MISMATCH diff=19,737,261.0
    strat 283: total=  21,603,426.0  progsum=           0.0  ** MISMATCH diff=21,603,426.0
    strat 284: total=  21,285,509.0  progsum=           0.0  ** MISMATCH diff=21,285,509.0
    strat 285: total=     872,496.0  progsum=           0.0  ** MISMATCH diff=872,496.0
    strat 286: total=     817,041.0  progsum=           0.0  ** MISMATCH diff=817,041.0
    strat 287: total=     817,041.0  progsum=           0.0  ** MISMATCH diff=817,041.0
    strat 288: total=     822,996.0  progsum=           0.0  ** MISMATCH diff=822,996.0
    strat 289: total=     817,041.0  progsum=           0.0  ** MISMATCH diff=817,041.0
    strat 290: total=  11,211,214.0  progsum=           0.0  ** MISMATCH diff=11,211,214.0
    strat 291: total=     847,041.0  progsum=           0.0  ** MISMATCH diff=847,041.0
    strat 292: total=     890,586.0  progsum=           0.0  ** MISMATCH diff=890,586.0
    strat 293: total=  15,919,986.0  progsum=           0.0  ** MISMATCH diff=15,919,986.0
    strat 294: total=   8,286,441.0  progsum=           0.0  ** MISMATCH diff=8,286,441.0
    strat 295: total=     866,541.0  progsum=           0.0  ** MISMATCH diff=866,541.0
    strat 296: total=     901,541.0  progsum=           0.0  ** MISMATCH diff=901,541.0
    strat 297: total=   9,245,622.0  progsum=           0.0  ** MISMATCH diff=9,245,622.0
    strat 298: total=     826,086.0  progsum=           0.0  ** MISMATCH diff=826,086.0
    strat 299: total=  26,284,148.0  progsum=           0.0  ** MISMATCH diff=26,284,148.0
    strat 301: total=  30,175,198.0  progsum=           0.0  ** MISMATCH diff=30,175,198.0
    strat 302: total=     902,496.0  progsum=           0.0  ** MISMATCH diff=902,496.0
    strat 303: total=     841,086.0  progsum=           0.0  ** MISMATCH diff=841,086.0
    strat 304: total=     841,086.0  progsum=           0.0  ** MISMATCH diff=841,086.0
    strat 305: total=     822,996.0  progsum=           0.0  ** MISMATCH diff=822,996.0
    strat 306: total=     852,041.0  progsum=           0.0  ** MISMATCH diff=852,041.0
    strat 307: total=     852,041.0  progsum=           0.0  ** MISMATCH diff=852,041.0
    strat 308: total=     891,541.0  progsum=           0.0  ** MISMATCH diff=891,541.0
    strat 309: total=     892,041.0  progsum=           0.0  ** MISMATCH diff=892,041.0
    strat 310: total=     677,334.0  progsum=           0.0  ** MISMATCH diff=677,334.0
    strat 311: total=     836,086.0  progsum=           0.0  ** MISMATCH diff=836,086.0
    strat 312: total=     847,996.0  progsum=           0.0  ** MISMATCH diff=847,996.0
    strat 313: total=     857,041.0  progsum=           0.0  ** MISMATCH diff=857,041.0
    strat 314: total=     837,996.0  progsum=           0.0  ** MISMATCH diff=837,996.0
    strat 315: total=     667,334.0  progsum=           0.0  ** MISMATCH diff=667,334.0
    strat 316: total=     847,041.0  progsum=           0.0  ** MISMATCH diff=847,041.0
    strat 317: total=     847,996.0  progsum=           0.0  ** MISMATCH diff=847,996.0
    strat 318: total=     842,041.0  progsum=           0.0  ** MISMATCH diff=842,041.0
    strat 330: total=   9,763,853.0  progsum=           0.0  ** MISMATCH diff=9,763,853.0
    strat 331: total=  20,406,037.0  progsum=           0.0  ** MISMATCH diff=20,406,037.0
    strat 332: total=   6,235,476.0  progsum=           0.0  ** MISMATCH diff=6,235,476.0
    strat 333: total=  22,444,839.0  progsum=           0.0  ** MISMATCH diff=22,444,839.0
    strat 334: total=  10,227,050.0  progsum=           0.0  ** MISMATCH diff=10,227,050.0
    strat 335: total=   9,889,755.0  progsum=           0.0  ** MISMATCH diff=9,889,755.0
    strat 336: total=  10,372,487.0  progsum=           0.0  ** MISMATCH diff=10,372,487.0
    strat 337: total=     915,586.0  progsum=           0.0  ** MISMATCH diff=915,586.0
    strat 338: total=     856,086.0  progsum=           0.0  ** MISMATCH diff=856,086.0
    strat 339: total=  11,685,300.0  progsum=           0.0  ** MISMATCH diff=11,685,300.0
    strat 340: total=   5,640,321.0  progsum=           0.0  ** MISMATCH diff=5,640,321.0
    strat 341: total=  10,773,550.0  progsum=           0.0  ** MISMATCH diff=10,773,550.0
    strat 342: total=     811,086.0  progsum=           0.0  ** MISMATCH diff=811,086.0
    strat 343: total=  10,524,112.0  progsum=           0.0  ** MISMATCH diff=10,524,112.0
    strat 344: total=  11,215,327.0  progsum=           0.0  ** MISMATCH diff=11,215,327.0
    strat 345: total=     856,086.0  progsum=           0.0  ** MISMATCH diff=856,086.0
    strat 346: total=  10,478,889.0  progsum=           0.0  ** MISMATCH diff=10,478,889.0
    strat 347: total=     822,996.0  progsum=           0.0  ** MISMATCH diff=822,996.0
    strat 348: total=  10,085,416.0  progsum=           0.0  ** MISMATCH diff=10,085,416.0
    strat 349: total=     852,996.0  progsum=           0.0  ** MISMATCH diff=852,996.0
    strat 350: total=   9,884,523.0  progsum=           0.0  ** MISMATCH diff=9,884,523.0
    strat 351: total=     841,086.0  progsum=           0.0  ** MISMATCH diff=841,086.0
    strat 352: total=  55,563,987.0  progsum=           0.0  ** MISMATCH diff=55,563,987.0
    strat 353: total=  10,568,380.0  progsum=           0.0  ** MISMATCH diff=10,568,380.0
    strat 354: total=  10,617,648.0  progsum=           0.0  ** MISMATCH diff=10,617,648.0
    strat 355: total=     818,086.0  progsum=           0.0  ** MISMATCH diff=818,086.0
    strat 356: total=     836,086.0  progsum=           0.0  ** MISMATCH diff=836,086.0
    strat 357: total=      11,165.0  progsum=           0.0  ** MISMATCH diff=11,165.0
    strat 358: total=   9,710,764.0  progsum=           0.0  ** MISMATCH diff=9,710,764.0
    strat 360: total=  24,366,502.0  progsum=           0.0  ** MISMATCH diff=24,366,502.0
    strat 361: total=  11,436,219.0  progsum=           0.0  ** MISMATCH diff=11,436,219.0
    strat 362: total=  26,123,678.0  progsum=           0.0  ** MISMATCH diff=26,123,678.0
    strat 363: total=  11,792,782.0  progsum=           0.0  ** MISMATCH diff=11,792,782.0
    strat 364: total=  10,905,906.0  progsum=           0.0  ** MISMATCH diff=10,905,906.0
    strat 365: total=  11,576,166.0  progsum=           0.0  ** MISMATCH diff=11,576,166.0
    strat 366: total=  11,486,443.0  progsum=           0.0  ** MISMATCH diff=11,486,443.0
    strat 367: total=  11,677,336.0  progsum=           0.0  ** MISMATCH diff=11,677,336.0
    strat 368: total=  11,375,996.0  progsum=           0.0  ** MISMATCH diff=11,375,996.0
    strat 369: total=  11,888,228.0  progsum=           0.0  ** MISMATCH diff=11,888,228.0
    strat 370: total=  11,928,452.0  progsum=           0.0  ** MISMATCH diff=11,928,452.0
    strat 371: total=  11,285,550.0  progsum=           0.0  ** MISMATCH diff=11,285,550.0
    strat 372: total=  11,124,880.0  progsum=           0.0  ** MISMATCH diff=11,124,880.0
    strat 373: total=  11,325,773.0  progsum=           0.0  ** MISMATCH diff=11,325,773.0
    strat 374: total=  11,737,559.0  progsum=           0.0  ** MISMATCH diff=11,737,559.0
    strat 380: total=  10,487,210.0  progsum=           0.0  ** MISMATCH diff=10,487,210.0
    strat 381: total=  11,038,711.0  progsum=           0.0  ** MISMATCH diff=11,038,711.0
    strat 382: total=  10,080,193.0  progsum=           0.0  ** MISMATCH diff=10,080,193.0
    strat 383: total=  10,781,423.0  progsum=           0.0  ** MISMATCH diff=10,781,423.0
    strat 384: total=  33,522,529.0  progsum=           0.0  ** MISMATCH diff=33,522,529.0
    strat 385: total=  10,833,541.0  progsum=           0.0  ** MISMATCH diff=10,833,541.0
    strat 386: total=  10,773,318.0  progsum=           0.0  ** MISMATCH diff=10,773,318.0
    strat 387: total=  10,215,862.0  progsum=           0.0  ** MISMATCH diff=10,215,862.0
    strat 388: total=  10,679,782.0  progsum=           0.0  ** MISMATCH diff=10,679,782.0
    strat 389: total=  10,929,943.0  progsum=           0.0  ** MISMATCH diff=10,929,943.0
    strat 390: total=  10,315,328.0  progsum=           0.0  ** MISMATCH diff=10,315,328.0
    strat 450: total=     817,041.0  progsum=           0.0  ** MISMATCH diff=817,041.0
    strat 451: total=     822,996.0  progsum=           0.0  ** MISMATCH diff=822,996.0
    strat 452: total=     822,996.0  progsum=           0.0  ** MISMATCH diff=822,996.0

RECONCILIATION: FAIL - see MISMATCH rows

NATIONAL TOTAL (the denominator every share is computed against)
    FY2019  heads 68,449,776,421.0  programmes 5,824,255,919.0  gap  91.5%  -> GRAND_TOTAL
    FY2024  heads 260,644,180,885.0  programmes 132,787,762,307.0  gap  49.0%  -> GRAND_TOTAL
    FY2019  extracted 99.2% of the document's own grand total 69,036,454,467.0
    FY2024  extracted 100.6% of the document's own grand total 259,052,474,750.0

READABILITY  0 of 124 programme name(s) unreadable (0%), 1 of 261 head(s) (0%), 0% of the money

HEAD NAMES: 111 row(s) renamed so a head reads the same in every year

Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/ghana/budget_layer_all_years.xlsx
  sheet 'budget_all_years' : 387 rows  (feeds Prompt 6 / build_final_panel - each intervention matches against EVERY year's programs)
  sheet 'programs_wide'    : 114 programs x 2 year(s) (funding-over-time)
  sheet 'reconciliation'   : 261 rows (audit)
  sheet 'data_quality'     : 350 flagged items (see summary below)

==============================================================================
DATA-QUALITY SUMMARY
==============================================================================
  HIGH: 234   MEDIUM: 110   LOW: 4   INFO: 2

  [HIGH] granularity_mismatch  (1)
      - the years were not extracted to the same depth: FY2024 has 110 programme rows and FY2019 has 14, a factor of 7.9. Each year's totals may still be right, but a programme cannot be followed across years and any funding-over-time figure is comparing different levels of the same budget.

  [HIGH] reconciliation_mismatch  (233)
      - FY2019 strat 1: programs sum to 1,773,070,250.0 but strategy_total is 1,928,735,250.0 (gap 155,665,000.0) - a program line is likely missing or mis-extracted for this strategy-year.
      - FY2019 strat 2: programs sum to 0.0 but strategy_total is 17,571,445.0 (gap 17,571,445.0) - a program line is likely missing or mis-extracted for this strategy-year.
      - FY2019 strat 3: programs sum to 0.0 but strategy_total is 2,668,000.0 (gap 2,668,000.0) - a program line is likely missing or mis-extracted for this strategy-year.
      ... and 230 more (see 'data_quality' sheet)

  [MEDIUM] blank_amount  (3)
      - FY2024 strat 23 23.2: amount is blank/unparseable.
      - FY2024 strat 39 39.4: amount is blank/unparseable.
      - FY2024 strat 42 42.2: amount is blank/unparseable.

  [MEDIUM] program_missing_in_year  (104)
      - FY2019 strat 1 1.7: program '1.7' (Infrastructure for Poverty Eradication Programme (Development Authorities)) exists in ['2024'] but is absent in ['2019'] - check whether it was dropped during extraction or genuinely did not exist that year.
      - FY2019 strat 1 1.8: program '1.8' (Home Rental Scheme) exists in ['2024'] but is absent in ['2019'] - check whether it was dropped during extraction or genuinely did not exist that year.
      - FY2019 strat 1 1.9: program '1.9' (Council of State) exists in ['2024'] but is absent in ['2019'] - check whether it was dropped during extraction or genuinely did not exist that year.
      ... and 101 more (see 'data_quality' sheet)

  [MEDIUM] zero_amount_programme  (3)
      - FY2024 strat 23 23.2: programme carries no money; a strategy matched only to lines like this reads as funded while receiving nothing
      - FY2024 strat 39 39.4: programme carries no money; a strategy matched only to lines like this reads as funded while receiving nothing
      - FY2024 strat 42 42.2: programme carries no money; a strategy matched only to lines like this reads as funded while receiving nothing

  [LOW] large_yoy_swing  (4)
      - FY2019->2024 strat 1 1.1: program '1.1' changed +251% (300,760,250.0 -> 1,055,799,984.0) - verify this is real and not an extraction error.
      - FY2019->2024 strat 1 1.3: program '1.3' changed +216% (95,000,000.0 -> 300,000,000.0) - verify this is real and not an extraction error.
      - FY2019->2024 strat 20 20.1: program '20.1' changed +9039% (11,400,000.0 -> 1,041,794,319.0) - verify this is real and not an extraction error.
      ... and 1 more (see 'data_quality' sheet)
==============================================================================
DATA QUALITY: REVIEW NEEDED - resolve HIGH items before relying on totals for those strategy-years
==============================================================================
```

### build_final_panel
```
Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/ghana/FINAL_PANEL.xlsx
  panel               : 241 strategies x 2 years (2019, 2024)
  match_review        : 328 matches (BOTH names + rationale)
  unmatched_codes     : 0 (codes NOT in that year's budget - REVIEW)
  unfunded_strategies : 55 (strategies with no budget any year)
  funding_by_program  : 82 (per programme x year, amount once - SAFE TO SUM)
  unmapped_programs   : 42 budget programmes with no matched strategy
  risk_panel          : 10 risks | ceiling: PASS
  enrichment          : strategyclean=yes risk_summary=yes
  maturity            : mean=0.741 | financing-weighted=0.868 | {'operational_programme': 163, 'operational_funded': 23, 'planned': 39, 'aspirational': 15, 'planned_specific': 1}
  basket/reverse-pass : 61 shared programmes | reverse-pass edges=none (run Prompt 6b + --coverage)
  recall_review       : 8 large programmes matched to only 1 strategy (candidate baskets)
MATURITY: mean=0.741 financing_weighted=0.868
CEILING TEST: PASS - no strategy over-counted in any year
UNMATCHED CODES: 0
QA: PASS - 0 unmatched code(s), ceiling PASS, 0 year warning(s)
```

### build_analytics_html
```
dashboard -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/ghana/budget_strategy_analytics.html
  years        2019, 2024
  edges        328
  strategies   241 (55 unfunded)
  size         114 KB
```

### audit_checks
```
AUDIT CHECKS: ghana 18/19 PASS (A16 2 untraceable)
  ok   A1   Stored programme sums              261 strategy-year(s) / 0 disagree
  ok   A2   Stored strategy totals             261 strategy-year(s) / 0 disagree
  ok   A3   Programme counted once             82 row(s) / 0 duplicate key(s)
  ok   A4   Ceiling holds                      261 strategy-year(s) / 0 over ceiling
  ok   A6   Panel money matches its edges      482 strategy-year figure(s) / 0 disagree
  ok   A8   Edges cite real programmes         328 accepted edge(s) / 0 dangle
  ok   A9   No strategy dropped                241 strategyclean row(s) / 241 panel row(s)
  ok   A10  Unfunded list is complete          55 zero-funded / 55 listed
  ok   A11  Evidence chain resolves            1392 distinct id(s) / 0 dangle
  ok   A12  Maturity summary is derivable      8 metric(s) / 0 disagree
  ok   A14  No duplicate edges                 328 edge(s) / 0 duplicate(s)
  ok   A15  One currency                       1 expected / 1 found
  FAIL A16  Components are traceable           2408 component(s) / 2 untraceable
            Universal electrification and rura <- Lifeline Consumers of Electricity
            Fisheries and aquaculture developm <- Raising for Food and Jobs Programme
  ok   A17  No workbook open in Excel          0 expected / 0 found
  ok   A18  Strategies come from the plan      241 strategy(ies) / 0 with no component
  ok   A19  Funding priority is reproducible   131 distinct (salience, funding) group(s) / 0 split across priorities
  ok   A20  The budget is readable             124 programme(s) / 0 unreadable (0%), carrying 0% of the money
  ok   A21  Ambiguous codes name their head    0 repeated code(s) / 0 edge(s) do not name a head
  ok   A22  Every intervention is traceable to a strategy 1392 intervention(s) extracted / 0 uncited (0.0%)
  --   A23  The sector layer stayed out of the panel no sector run for this country
```

### data_issues
```
data issues  Files/outputs/DATA_ISSUES.xlsx
  6 detected across 1 country(ies): 2 high, 3 medium, 1 low
  70 hand-written entr(ies) in 04_Docs_and_Planning/data_issues.json
  HIGH  ghana     D7       Flag raised while combining the budget years
  HIGH  ghana     D8       A strategy total its own programmes do not add up to
```
