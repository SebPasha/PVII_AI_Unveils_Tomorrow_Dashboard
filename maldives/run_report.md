# Run report - Maldives

**🔴 Overall: REVIEW NEEDED**  
Generated 2026-08-22 21:34 by run_pipeline.py

| Stage | Ran | Key QA |
|---|---|---|
| validate_stage_schema (L2) | ok | QA FAIL - FAIL 4/19 (maldives_mapping_2017.xlsx, maldives_mapping_2018.xlsx, maldives_mapping_2019.xlsx) |
| validate_source_fidelity (L4) | ok | NOT CONFIGURED |
| validate_recall (L4) | ok | NOT CONFIGURED [advisory] |
| validate_refs (L3) | ok | QA FAIL - FAIL 1/1 (maldives references) |
| combine_budget_years | ok | reconcile=FAIL - see MISMATCH rows | data_quality=REVIEW NEEDED - resolve HIGH items before relying on totals for those strategy-years |
| build_final_panel | ok | QA FAIL - ceiling=PASS - no strategy over-counted in any year | unmatched_codes=312 |
| build_analytics_html | ok | strategies=261 (153 unfunded) | edges=216 |
| audit_checks | FAILED | QA FAIL - 17/19 PASS (A2 11 disagree, A16 2 untraceable) [advisory] |
| data_issues | FAILED | 8 detected across 1 country(ies): 4 high, 3 medium, 1 low [advisory] |

## Outputs

- Budget layer: `Files/outputs/maldives/budget_layer_all_years.xlsx`
- FINAL panel (deliverable): `Files/outputs/maldives/FINAL_PANEL.xlsx`
- Dashboard: `Files/outputs/maldives/budget_strategy_analytics.html`
- Audit trail: `Files/outputs/union_dashboard.html`, Audit tab, filtered to this country
- Data oddities: `Files/outputs/DATA_ISSUES.xlsx`

## Full stage logs

### validate_stage_schema (L2)
```
--- maldives_budget_2007.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/maldives/validation/schema_maldives_budget_2007.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- maldives_budget_2008.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/maldives/validation/schema_maldives_budget_2008.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- maldives_budget_2011.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/maldives/validation/schema_maldives_budget_2011.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- maldives_budget_2012.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/maldives/validation/schema_maldives_budget_2012.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- maldives_budget_2013.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/maldives/validation/schema_maldives_budget_2013.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- maldives_budget_2014.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/maldives/validation/schema_maldives_budget_2014.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- maldives_budget_2015.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/maldives/validation/schema_maldives_budget_2015.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- maldives_budget_2016.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/maldives/validation/schema_maldives_budget_2016.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

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

  RESULT: FAIL - 2 contract violation(s) across 1 file(s).
  The stage output is not accepted; re-run the stage or fix the prompt.

--- maldives_mapping_2018.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/maldives/validation/schema_maldives_mapping_2018.xlsx

  RESULT: FAIL - 4 contract violation(s) across 1 file(s).
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
RESULT: FAIL - 323 dangling reference(s) of 3302
report -> Files/outputs/maldives/validation/refs_maldives_references.xlsx
```

### combine_budget_years
```
==============================================================================
COMBINED BUDGET LAYER  -  years: 2007, 2008, 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018, 2019  (11 file(s))
==============================================================================

RECONCILIATION (per year: sum of program rows vs strategy_total)

  FY2007   (national total = 7,153,280,224.0)
    strat 1: total= 122,286,620.0  progsum= 122,286,620.0  OK
    strat 2: total= 177,300,831.0  progsum= 177,300,831.0  OK
    strat 3: total= 135,573,086.0  progsum= 135,573,086.0  OK
    strat 4: total=   8,875,883.0  progsum=  98,252,906.0  ** MISMATCH diff=-89,377,023.0
    strat 5: total=  63,545,102.0  progsum=  40,942,424.0  ** MISMATCH diff=22,602,678.0
    strat 6: total=  15,857,098.0  progsum= 755,291,197.0  ** MISMATCH diff=-739,434,099.0
    strat 7: total=  10,900,137.0  progsum= 307,832,026.0  ** MISMATCH diff=-296,931,889.0
    strat 8: total=   5,045,332.0  progsum= 978,128,413.0  ** MISMATCH diff=-973,083,081.0
    strat 9: total=  16,409,460.0  progsum=1,741,592,346.0  ** MISMATCH diff=-1,725,182,886.0
    strat 10: total=   2,721,030.0  progsum=  87,351,543.0  ** MISMATCH diff=-84,630,513.0
    strat 11: total=   3,673,885.0  progsum= 132,626,027.0  ** MISMATCH diff=-128,952,142.0
    strat 12: total=   3,941,083.0  progsum= 728,141,909.0  ** MISMATCH diff=-724,200,826.0
    strat 13: total=   2,577,978.0  progsum= 625,414,568.0  ** MISMATCH diff=-622,836,590.0
    strat 14: total=  58,487,229.0  progsum=  58,487,229.0  OK
    strat 15: total=     713,263.0  progsum= 142,985,194.0  ** MISMATCH diff=-142,271,931.0
    strat 16: total=  10,031,460.0  progsum=  93,510,331.0  ** MISMATCH diff=-83,478,871.0
    strat 17: total= 378,171,297.0  progsum= 378,171,297.0  OK
    strat 18: total=  98,252,906.0  progsum=  98,252,906.0  OK
    strat 19: total=  40,942,424.0  progsum=  40,942,424.0  OK
    strat 20: total= 755,291,197.0  progsum= 755,291,197.0  OK
    strat 21: total= 307,832,026.0  progsum= 307,832,026.0  OK
    strat 22: total= 978,128,413.0  progsum= 978,128,413.0  OK
    strat 23: total=1,741,592,346.0  progsum=1,741,592,346.0  OK
    strat 24: total=  87,351,543.0  progsum=  87,351,543.0  OK
    strat 25: total= 132,626,027.0  progsum= 132,626,027.0  OK
    strat 26: total= 728,141,909.0  progsum= 728,141,909.0  OK
    strat 27: total= 625,414,568.0  progsum= 625,414,568.0  OK
    strat 28: total=  13,008,063.0  progsum=           0.0  ** MISMATCH diff=13,008,063.0
    strat 29: total= 142,985,194.0  progsum= 142,985,194.0  OK
    strat 30: total=  93,510,331.0  progsum=  93,510,331.0  OK
    strat 31: total=  18,167,175.0  progsum=  18,167,175.0  OK
    strat 32: total= 117,167,765.0  progsum= 117,167,765.0  OK
    strat 33: total=  21,159,461.0  progsum=  21,159,461.0  OK
    strat 34: total= 108,255,997.0  progsum= 108,255,997.0  OK
    strat 35: total=  83,022,550.0  progsum=  83,022,550.0  OK
    strat 36: total=  30,068,492.0  progsum=  30,068,492.0  OK
    strat 37: total=  14,251,063.0  progsum=  14,251,063.0  OK

  FY2008   (national total = 9,513,687,178.0)
    strat 1: total=2,409,321,000.0  progsum= 171,759,278.0  ** MISMATCH diff=2,237,561,722.0
    strat 2: total= 589,668,000.0  progsum= 176,665,173.0  ** MISMATCH diff=413,002,827.0
    strat 3: total=           0.0  progsum= 101,283,435.0  ** MISMATCH diff=-101,283,435.0
    strat 4: total=  19,044,000.0  progsum=     200,000.0  ** MISMATCH diff=18,844,000.0
    strat 5: total= 185,000,000.0  progsum=     260,000.0  ** MISMATCH diff=184,740,000.0
    strat 6: total=  35,414,000.0  progsum=   3,000,000.0  ** MISMATCH diff=32,414,000.0
    strat 7: total=   5,798,000.0  progsum=     504,900.0  ** MISMATCH diff=5,293,100.0
    strat 8: total=  18,287,000.0  progsum=   5,652,910.0  ** MISMATCH diff=12,634,090.0
    strat 9: total=  29,000,000.0  progsum=   1,500,000.0  ** MISMATCH diff=27,500,000.0
    strat 10: total=  69,902,000.0  progsum=     624,445.0  ** MISMATCH diff=69,277,555.0
    strat 11: total=   9,900,000.0  progsum=     100,000.0  ** MISMATCH diff=9,800,000.0
    strat 12: total=           0.0  progsum= 324,150,608.0  ** MISMATCH diff=-324,150,608.0
    strat 13: total= 150,000,000.0  progsum=           0.0  ** MISMATCH diff=150,000,000.0
    strat 14: total=  60,000,000.0  progsum=           0.0  ** MISMATCH diff=60,000,000.0
    strat 15: total= 129,000,000.0  progsum=           0.0  ** MISMATCH diff=129,000,000.0
    strat 16: total=   6,565,000.0  progsum=           0.0  ** MISMATCH diff=6,565,000.0
    strat 17: total=   8,259,000.0  progsum=           0.0  ** MISMATCH diff=8,259,000.0
    strat 18: total= 188,002,000.0  progsum= 379,782,921.0  ** MISMATCH diff=-191,780,921.0
    strat 19: total=  15,000,000.0  progsum= 148,343,827.0  ** MISMATCH diff=-133,343,827.0
    strat 20: total=  30,790,000.0  progsum=  66,698,312.0  ** MISMATCH diff=-35,908,312.0
    strat 21: total=  20,000,000.0  progsum= 753,060,544.0  ** MISMATCH diff=-733,060,544.0
    strat 22: total=  47,584,000.0  progsum= 269,657,508.0  ** MISMATCH diff=-222,073,508.0
    strat 23: total=  37,920,000.0  progsum= 564,385,977.0  ** MISMATCH diff=-526,465,977.0
    strat 24: total=   2,000,000.0  progsum=2,655,478,039.0  ** MISMATCH diff=-2,653,478,039.0
    strat 25: total=           0.0  progsum=  98,857,980.0  ** MISMATCH diff=-98,857,980.0
    strat 26: total=           0.0  progsum= 153,042,407.0  ** MISMATCH diff=-153,042,407.0
    strat 27: total=  23,800,000.0  progsum=1,024,094,524.0  ** MISMATCH diff=-1,000,294,524.0
    strat 28: total=   2,249,000.0  progsum= 692,652,831.0  ** MISMATCH diff=-690,403,831.0
    strat 29: total= 101,607,000.0  progsum=           0.0  ** MISMATCH diff=101,607,000.0
    strat 30: total=  27,252,000.0  progsum= 142,639,349.0  ** MISMATCH diff=-115,387,349.0
    strat 31: total=1,403,602,000.0  progsum= 130,536,575.0  ** MISMATCH diff=1,273,065,425.0
    strat 32: total=2,502,694,583.0  progsum=  28,680,652.0  ** MISMATCH diff=2,474,013,931.0
    strat 33: total=   7,477,000.0  progsum= 110,099,478.0  ** MISMATCH diff=-102,622,478.0
    strat 34: total=   3,255,000.0  progsum=  25,645,469.0  ** MISMATCH diff=-22,390,469.0
    strat 35: total= 192,260,000.0  progsum= 112,253,580.0  ** MISMATCH diff=80,006,420.0
    strat 36: total=  84,000,000.0  progsum= 104,854,863.0  ** MISMATCH diff=-20,854,863.0
    strat 37: total=   6,683,000.0  progsum= 113,359,710.0  ** MISMATCH diff=-106,676,710.0
    strat 38: total=  17,142,000.0  progsum=  12,926,777.0  ** MISMATCH diff=4,215,223.0
    strat 39: total= 193,968,000.0  progsum=           0.0  ** MISMATCH diff=193,968,000.0
    strat 40: total= 140,707,000.0  progsum=           0.0  ** MISMATCH diff=140,707,000.0
    strat 41: total= 178,586,000.0  progsum=           0.0  ** MISMATCH diff=178,586,000.0
    strat 42: total=  12,323,000.0  progsum=           0.0  ** MISMATCH diff=12,323,000.0
    strat 43: total=   6,853,000.0  progsum=           0.0  ** MISMATCH diff=6,853,000.0
    strat 44: total=   5,879,000.0  progsum=           0.0  ** MISMATCH diff=5,879,000.0
    strat 45: total=  58,216,000.0  progsum=           0.0  ** MISMATCH diff=58,216,000.0
    strat 46: total=  33,007,000.0  progsum=           0.0  ** MISMATCH diff=33,007,000.0
    strat 47: total=  12,950,000.0  progsum=           0.0  ** MISMATCH diff=12,950,000.0
    strat 53: total=  48,147,500.0  progsum=  17,000,000.0  ** MISMATCH diff=31,147,500.0
    strat 57: total=   9,000,000.0  progsum=   9,000,000.0  OK
    strat 58: total=   3,000,000.0  progsum=   3,000,000.0  OK
    strat 59: total=  27,020,000.0  progsum=   3,320,000.0  ** MISMATCH diff=23,700,000.0
    strat 61: total=   6,002,700.0  progsum=   1,529,500.0  ** MISMATCH diff=4,473,200.0
    strat 65: total=   2,500,000.0  progsum=   2,500,000.0  OK
    strat 66: total=   2,908,270.0  progsum=   2,908,270.0  OK
    strat 72: total=  16,824,110.0  progsum=   3,000,000.0  ** MISMATCH diff=13,824,110.0
    strat 85: total=  57,458,339.0  progsum=   5,291,300.0  ** MISMATCH diff=52,167,039.0
    strat 87: total=   8,530,203.0  progsum=     446,131.0  ** MISMATCH diff=8,084,072.0
    strat 155: total=   1,800,000.0  progsum=     700,000.0  ** MISMATCH diff=1,100,000.0
    strat 157: total=   7,097,521.0  progsum=   1,776,881.0  ** MISMATCH diff=5,320,640.0
    strat 158: total=     600,000.0  progsum=     600,000.0  OK
    strat 173: total=  27,010,000.0  progsum=   3,150,000.0  ** MISMATCH diff=23,860,000.0
    strat 177: total=   5,700,000.0  progsum=   1,500,000.0  ** MISMATCH diff=4,200,000.0
    strat 203: total=   4,000,000.0  progsum=   4,000,000.0  OK
    strat 211: total=   7,500,000.0  progsum=           0.0  ** MISMATCH diff=7,500,000.0
    strat 213: total=  22,192,130.0  progsum=   4,196,380.0  ** MISMATCH diff=17,995,750.0
    strat 215: total= 118,548,321.0  progsum=  39,380,821.0  ** MISMATCH diff=79,167,500.0
    strat 216: total=   3,029,605.0  progsum=   3,029,605.0  OK
    strat 217: total=     500,000.0  progsum=     500,000.0  OK
    strat 218: total=   1,500,000.0  progsum=   1,500,000.0  OK
    strat 219: total=   1,500,000.0  progsum=   1,500,000.0  OK
    strat 223: total=   9,141,657.0  progsum=     478,295.0  ** MISMATCH diff=8,663,362.0
    strat 229: total=  10,000,000.0  progsum=   6,000,000.0  ** MISMATCH diff=4,000,000.0
    strat 235: total=           0.0  progsum=           0.0  OK
    strat 237: total=   8,840,000.0  progsum=   3,412,500.0  ** MISMATCH diff=5,427,500.0
    strat 238: total=     500,000.0  progsum=           0.0  ** MISMATCH diff=500,000.0
    strat 239: total=   2,400,000.0  progsum=   1,500,000.0  ** MISMATCH diff=900,000.0
    strat 245: total=  19,472,239.0  progsum=   5,904,250.0  ** MISMATCH diff=13,567,989.0

  FY2011   (national total = 13,693,186,597.0)
    strat 1: total=11,751,042,052.0  progsum= 382,010,914.0  ** MISMATCH diff=11,369,031,138.0
    strat 2: total=  40,000,000.0  progsum= 387,674,434.0  ** MISMATCH diff=-347,674,434.0
    strat 3: total=           0.0  progsum=1,323,076,111.0  ** MISMATCH diff=-1,323,076,111.0
    strat 4: total=  45,000,000.0  progsum= 281,356,511.0  ** MISMATCH diff=-236,356,511.0
    strat 5: total= 100,000,000.0  progsum=  87,229,010.0  ** MISMATCH diff=12,770,990.0
    strat 6: total=1,679,252,954.0  progsum=5,525,697,542.0  ** MISMATCH diff=-3,846,444,588.0
    strat 7: total=  11,764,878.0  progsum=  11,764,878.0  OK
    strat 8: total=  10,120,516.0  progsum=  10,109,136.0  ** MISMATCH diff=11,380.0
    strat 9: total=   2,866,399.0  progsum=   2,866,399.0  OK
    strat 10: total=  25,910,684.0  progsum=  26,056,592.0  ** MISMATCH diff=-145,908.0
    strat 11: total=  18,209,868.0  progsum=  18,209,868.0  OK
    strat 12: total=   3,820,814.0  progsum=   3,820,814.0  OK
    strat 13: total=   2,370,472.0  progsum=   2,358,822.0  ** MISMATCH diff=11,650.0
    strat 14: total=   2,827,960.0  progsum=   2,827,960.0  OK

  FY2012   (national total = 17,067.8)
    strat 1: total=       5,307.9  progsum= 561,786,642.8  ** MISMATCH diff=-561,781,334.9
    strat 2: total=       7,843.0  progsum=  34,121,255.0  ** MISMATCH diff=-34,113,412.0
    strat 3: total=         641.6  progsum=   2,778,731.7  ** MISMATCH diff=-2,778,090.1
    strat 4: total=       3,275.3  progsum=  50,191,246.3  ** MISMATCH diff=-50,187,971.0

  FY2013   (national total = 16,117,228,137.0)
    strat 0: total= 130,000,000.0  progsum= 330,137,018.0  ** MISMATCH diff=-200,137,018.0
    strat 1: total= 130,000,000.0  progsum= 161,877,346.0  ** MISMATCH diff=-31,877,346.0
    strat 2: total= 187,998,178.0  progsum= 187,998,178.0  OK
    strat 3: total=  12,138,840.0  progsum=  12,138,840.0  OK
    strat 4: total= 391,056,668.0  progsum= 705,319,716.0  ** MISMATCH diff=-314,263,048.0
    strat 5: total= 120,081,853.0  progsum= 120,081,853.0  OK
    strat 6: total=  29,676,709.0  progsum=  29,676,709.0  OK
    strat 7: total=  21,461,062.0  progsum=  21,461,062.0  OK
    strat 8: total=  21,007,635.0  progsum=  21,007,635.0  OK
    strat 9: total=  57,831,363.0  progsum=  57,831,363.0  OK
    strat 04: total= 391,056,668.0  progsum= 391,056,668.0  OK
    strat 05: total= 120,081,853.0  progsum= 120,081,853.0  OK
    strat 06: total=  29,676,709.0  progsum=  29,676,709.0  OK
    strat 07: total=  21,461,062.0  progsum=  21,461,062.0  OK
    strat 08: total=  21,007,635.0  progsum=  21,007,635.0  OK
    strat 09: total=  57,831,363.0  progsum=  57,831,363.0  OK
    strat 10: total=  29,798,500.0  progsum=  29,798,500.0  OK
    strat 11: total=   8,386,301.0  progsum=   8,386,301.0  OK
    strat 12: total=  62,444,037.0  progsum=  62,444,037.0  OK
    strat 13: total=           0.0  progsum=           0.0  OK
    strat 14: total=   7,010,098.0  progsum=   7,010,098.0  OK
    strat 15: total=   3,958,192.0  progsum=   3,958,192.0  OK
    strat 16: total= 200,837,875.0  progsum= 200,837,875.0  OK
    strat 17: total=  10,001,612.0  progsum=  10,001,612.0  OK
    strat 18: total=   4,567,810.0  progsum=   4,567,810.0  OK
    strat 19: total=  26,628,663.0  progsum=  26,628,663.0  OK
    strat 20: total=3,854,526,304.0  progsum=3,979,097,853.0  ** MISMATCH diff=-124,571,549.0
    strat 21: total= 913,041,249.0  progsum= 913,041,249.0  OK
    strat 22: total=1,167,650,838.0  progsum=2,080,692,086.0  ** MISMATCH diff=-913,041,248.0
    strat 23: total=2,238,605,324.0  progsum=3,406,256,161.0  ** MISMATCH diff=-1,167,650,837.0
    strat 24: total= 158,101,141.0  progsum=2,396,706,465.0  ** MISMATCH diff=-2,238,605,324.0
    strat 25: total=  30,010,645.0  progsum=  30,010,645.0  OK
    strat 26: total= 162,524,329.0  progsum= 325,048,658.0  ** MISMATCH diff=-162,524,329.0
    strat 27: total=2,524,873,761.0  progsum=5,049,747,522.0  ** MISMATCH diff=-2,524,873,761.0
    strat 28: total=  30,058,285.0  progsum=  30,058,285.0  OK
    strat 29: total=  46,511,470.0  progsum=  46,511,470.0  OK
    strat 30: total= 115,263,452.0  progsum= 115,263,452.0  OK
    strat 31: total= 842,501,753.0  progsum= 842,501,753.0  OK
    strat 32: total=  71,888,635.0  progsum=  71,888,635.0  OK
    strat 33: total= 138,076,654.0  progsum= 138,076,654.0  OK
    strat 34: total= 126,948,921.0  progsum= 126,948,921.0  OK
    strat 35: total= 223,803,140.0  progsum= 223,803,140.0  OK
    strat 36: total=  93,389,403.0  progsum=  93,389,403.0  OK
    strat 37: total=1,090,213,556.0  progsum= 152,299,740.0  ** MISMATCH diff=937,913,816.0
    strat 38: total=  44,392,910.0  progsum=  44,392,910.0  OK
    strat 39: total=  66,456,974.0  progsum=  66,456,974.0  OK
    strat 491: total=   6,385,551.0  progsum=   6,385,551.0  OK
    strat 492: total=  38,001,596.0  progsum=  38,001,596.0  OK
    strat 581: total=   9,249,869.0  progsum=           0.0  ** MISMATCH diff=9,249,869.0
    strat 582: total=  28,751,691.0  progsum=  41,195,112.0  ** MISMATCH diff=-12,443,421.0

  FY2014   (national total = 15,395,930,997.0)
    strat 1: total=  82,548,776.0  progsum=       6,205.1  ** MISMATCH diff=82,542,570.9
    strat 2: total= 169,112,640.0  progsum=       7,358.4  ** MISMATCH diff=169,105,281.6
    strat 3: total=  10,824,214.0  progsum=       1,088.1  ** MISMATCH diff=10,823,125.9
    strat 4: total= 338,759,143.0  progsum= 338,761,779.8  ** MISMATCH diff=-2,636.8
    strat 5: total=  69,481,253.0  progsum=           0.0  ** MISMATCH diff=69,481,253.0
    strat 6: total=  27,482,484.0  progsum=           0.0  ** MISMATCH diff=27,482,484.0
    strat 7: total=  21,894,017.0  progsum=           0.0  ** MISMATCH diff=21,894,017.0
    strat 8: total=  22,037,263.0  progsum=           0.0  ** MISMATCH diff=22,037,263.0
    strat 9: total=  44,000,000.0  progsum=           0.0  ** MISMATCH diff=44,000,000.0
    strat 01: total=  57,238,250.0  progsum=  46,087,723.0  ** MISMATCH diff=11,150,527.0
    strat 02: total= 169,112,640.0  progsum= 169,112,640.0  OK
    strat 03: total=  10,824,214.0  progsum=  10,824,214.0  OK
    strat 04: total=  52,991,494.0  progsum= 338,759,144.0  ** MISMATCH diff=-285,767,650.0
    strat 05: total=  69,481,253.0  progsum=  69,481,253.0  OK
    strat 06: total=  27,482,484.0  progsum=  27,482,484.0  OK
    strat 07: total=  21,894,017.0  progsum=  21,894,017.0  OK
    strat 08: total=  22,037,263.0  progsum=  22,037,263.0  OK
    strat 09: total=  44,000,000.0  progsum=  44,000,000.0  OK
    strat 10: total=  27,176,792.0  progsum=  27,176,792.0  OK
    strat 11: total=   8,505,313.0  progsum=   8,505,313.0  OK
    strat 12: total=  43,147,675.0  progsum=  43,147,675.0  OK
    strat 13: total=   7,171,095.0  progsum=           0.0  ** MISMATCH diff=7,171,095.0
    strat 14: total=   3,998,199.0  progsum=   7,171,095.0  ** MISMATCH diff=-3,172,896.0
    strat 15: total= 195,278,799.0  progsum=   3,998,199.0  ** MISMATCH diff=191,280,600.0
    strat 16: total=   8,689,965.0  progsum= 195,278,799.0  ** MISMATCH diff=-186,588,834.0
    strat 17: total=   4,261,849.0  progsum=   8,689,965.0  ** MISMATCH diff=-4,428,116.0
    strat 18: total=  32,747,372.0  progsum=   4,261,849.0  ** MISMATCH diff=28,485,523.0
    strat 19: total=           0.0  progsum=  32,747,372.0  ** MISMATCH diff=-32,747,372.0
    strat 20: total=  75,121,626.0  progsum= 147,765,502.0  ** MISMATCH diff=-72,643,876.0
    strat 21: total=4,479,847,704.0  progsum=4,554,969,331.0  ** MISMATCH diff=-75,121,627.0
    strat 22: total= 927,969,684.0  progsum=5,407,817,389.0  ** MISMATCH diff=-4,479,847,705.0
    strat 23: total=1,143,511,073.0  progsum=2,071,480,757.0  ** MISMATCH diff=-927,969,684.0
    strat 24: total=1,900,124,390.0  progsum=1,666,902,842.0  ** MISMATCH diff=233,221,548.0
    strat 25: total= 147,765,501.0  progsum= 282,293,315.0  ** MISMATCH diff=-134,527,814.0
    strat 26: total=  18,470,076.0  progsum=  18,470,076.0  OK
    strat 27: total= 142,402,437.0  progsum= 142,402,437.0  OK
    strat 28: total=2,667,164,952.0  progsum=2,667,164,952.0  OK
    strat 29: total=  62,293,051.0  progsum=  62,293,051.0  OK
    strat 30: total=  84,220,926.0  progsum=  84,220,926.0  OK
    strat 31: total=  95,866,144.0  progsum=  95,866,144.0  OK
    strat 32: total= 443,932,392.0  progsum= 443,932,392.0  OK
    strat 33: total=  62,526,767.0  progsum=  62,526,767.0  OK
    strat 34: total= 124,899,589.0  progsum= 124,899,589.0  OK
    strat 35: total=  66,120,979.0  progsum=  66,120,979.0  OK
    strat 36: total= 187,637,696.0  progsum= 187,637,696.0  OK
    strat 37: total=  77,622,095.0  progsum=  77,622,095.0  OK
    strat 38: total= 937,307,241.0  progsum= 133,494,146.0  ** MISMATCH diff=803,813,095.0
    strat 39: total=  45,683,583.0  progsum=  45,683,583.0  OK
    strat 40: total=   7,478,815.0  progsum=  58,939,801.0  ** MISMATCH diff=-51,460,986.0
    strat 41: total=   6,535,381.0  progsum=  60,907,910.0  ** MISMATCH diff=-54,372,529.0
    strat 42: total=   6,520,801.0  progsum=  53,269,927.0  ** MISMATCH diff=-46,749,126.0
    strat 43: total=   5,662,720.0  progsum=  45,872,508.0  ** MISMATCH diff=-40,209,788.0
    strat 44: total=   7,638,120.0  progsum=  60,472,201.0  ** MISMATCH diff=-52,834,081.0
    strat 45: total=   5,433,400.0  progsum=  45,438,318.0  ** MISMATCH diff=-40,004,918.0
    strat 46: total=   5,347,809.0  progsum=  25,486,957.0  ** MISMATCH diff=-20,139,148.0
    strat 47: total=   4,785,644.0  progsum=  36,706,591.0  ** MISMATCH diff=-31,920,947.0
    strat 48: total=   4,936,719.0  progsum=  27,416,449.0  ** MISMATCH diff=-22,479,730.0
    strat 49: total=   5,202,227.0  progsum=  36,960,769.0  ** MISMATCH diff=-31,758,542.0
    strat 50: total=   4,529,731.0  progsum=  15,616,611.0  ** MISMATCH diff=-11,086,880.0
    strat 51: total=   5,297,377.0  progsum=  28,645,208.0  ** MISMATCH diff=-23,347,831.0
    strat 52: total=   5,705,310.0  progsum=  24,951,450.0  ** MISMATCH diff=-19,246,140.0
    strat 53: total=   5,256,674.0  progsum=  27,020,124.0  ** MISMATCH diff=-21,763,450.0
    strat 54: total=   6,209,500.0  progsum=  46,744,789.0  ** MISMATCH diff=-40,535,289.0
    strat 55: total=   8,621,672.0  progsum=  49,976,293.0  ** MISMATCH diff=-41,354,621.0
    strat 56: total=   4,870,770.0  progsum=  37,686,531.0  ** MISMATCH diff=-32,815,761.0
    strat 57: total=   6,333,428.0  progsum=  42,580,079.0  ** MISMATCH diff=-36,246,651.0
    strat 58: total=   6,898,529.0  progsum=  33,436,996.0  ** MISMATCH diff=-26,538,467.0

  FY2015   (national total = 18,653,260,526.0)
    strat 1: total=  94,754,477.0  progsum=  94,760,520.3  ** MISMATCH diff=-6,043.3
    strat 2: total= 195,443,500.0  progsum= 195,485,139.9  ** MISMATCH diff=-41,639.9
    strat 3: total=  12,344,664.0  progsum=  12,345,487.1  ** MISMATCH diff=-823.1
    strat 4: total= 438,605,235.0  progsum= 438,607,823.9  ** MISMATCH diff=-2,588.9
    strat 5: total=  25,916,686.0  progsum=  46,386,686.0  ** MISMATCH diff=-20,470,000.0
    strat 6: total=  25,493,285.0  progsum=  25,493,285.0  OK
    strat 7: total=  25,554,940.0  progsum=  26,147,940.0  ** MISMATCH diff=-593,000.0
    strat 8: total=  32,499,312.0  progsum=  32,515,312.0  ** MISMATCH diff=-16,000.0
    strat 9: total=  46,252,641.0  progsum=  49,245,520.0  ** MISMATCH diff=-2,992,879.0
    strat 10: total=  34,242,715.0  progsum=  34,242,715.0  OK
    strat 11: total=   9,196,572.0  progsum=   9,196,572.0  OK
    strat 12: total=  59,661,167.0  progsum=  59,661,167.0  OK
    strat 13: total=   6,867,832.0  progsum=   6,867,832.0  OK
    strat 14: total=   4,488,748.0  progsum=   4,938,748.0  ** MISMATCH diff=-450,000.0
    strat 15: total= 210,443,500.0  progsum= 210,468,500.0  ** MISMATCH diff=-25,000.0
    strat 16: total=   9,354,513.0  progsum=   9,354,513.0  OK
    strat 17: total=   4,304,806.0  progsum=   4,304,806.0  OK
    strat 18: total=  64,134,987.0  progsum=  64,134,987.0  OK
    strat 19: total=  74,125,000.0  progsum=  74,125,000.0  OK
    strat 20: total=   8,797,954.0  progsum=   8,797,954.0  OK
    strat 21: total=   6,121,560.0  progsum=   6,121,560.0  OK
    strat 22: total=6,794,275,717.0  progsum=6,794,275,717.0  OK
    strat 23: total= 999,285,579.0  progsum= 999,285,579.0  OK
    strat 24: total=1,201,192,155.0  progsum=1,201,192,155.0  OK
    strat 25: total=2,450,198,297.0  progsum=2,433,211,455.0  ** MISMATCH diff=16,986,842.0
    strat 26: total= 153,438,254.0  progsum= 153,438,254.0  OK
    strat 27: total= 176,179,533.0  progsum= 176,179,533.0  OK
    strat 28: total=3,241,610,069.0  progsum=3,241,610,069.0  OK
    strat 29: total= 106,056,745.0  progsum= 106,056,745.0  OK
    strat 30: total= 125,011,808.0  progsum= 125,011,808.0  OK
    strat 31: total= 300,000,000.0  progsum= 303,576,911.0  ** MISMATCH diff=-3,576,911.0
    strat 32: total=1,485,030,957.0  progsum=1,485,030,957.0  OK
    strat 33: total= 165,919,213.0  progsum=           0.0  ** MISMATCH diff=165,919,213.0
    strat 34: total=     249,816.0  progsum=     249,816.0  OK
    strat 35: total=   1,452,000.0  progsum=1,431,576,896.0  ** MISMATCH diff=-1,430,124,896.0
    strat 36: total=     319,509.0  progsum=  58,352,459.0  ** MISMATCH diff=-58,032,950.0
    strat 37: total=           0.0  progsum=           0.0  OK
    strat 38: total=           0.0  progsum=           0.0  OK
    strat 39: total=  64,436,780.0  progsum= 867,196,368.0  ** MISMATCH diff=-802,759,588.0

  FY2016   (national total = 23,355,280,219.0)
    strat 1: total= 101,735,649.0  progsum= 115,849,698.9  ** MISMATCH diff=-14,114,049.9
    strat 2: total= 216,485,156.0  progsum= 221,522,738.2  ** MISMATCH diff=-5,037,582.2
    strat 3: total=  11,959,541.0  progsum=  11,963,996.9  ** MISMATCH diff=-4,455.9
    strat 4: total= 461,015,501.0  progsum= 811,070,109.5  ** MISMATCH diff=-350,054,608.5
    strat 5: total=  71,588,336.0  progsum=1,079,256,104.0  ** MISMATCH diff=-1,007,667,768.0
    strat 6: total=  23,653,845.0  progsum=2,680,801,586.0  ** MISMATCH diff=-2,657,147,741.0
    strat 7: total=  28,337,202.0  progsum= 339,937,618.0  ** MISMATCH diff=-311,600,416.0
    strat 8: total=  32,370,894.0  progsum=1,141,531,577.0  ** MISMATCH diff=-1,109,160,683.0
    strat 9: total=  46,260,836.0  progsum= 188,937,939.0  ** MISMATCH diff=-142,677,103.0
    strat 10: total=  43,475,263.0  progsum=1,214,499,632.0  ** MISMATCH diff=-1,171,024,369.0
    strat 11: total=           0.0  progsum=  88,903,072.0  ** MISMATCH diff=-88,903,072.0
    strat 12: total=  59,261,293.0  progsum=   6,994,535.0  ** MISMATCH diff=52,266,758.0
    strat 13: total=   6,994,535.0  progsum=   4,657,328.0  ** MISMATCH diff=2,337,207.0
    strat 14: total=   4,607,328.0  progsum=   9,074,089.0  ** MISMATCH diff=-4,466,761.0
    strat 15: total=   9,074,089.0  progsum=   4,370,220.0  ** MISMATCH diff=4,703,869.0
    strat 16: total=   4,370,220.0  progsum= 100,480,580.0  ** MISMATCH diff=-96,110,360.0
    strat 17: total= 100,480,580.0  progsum=   5,556,151.0  ** MISMATCH diff=94,924,429.0
    strat 18: total=           0.0  progsum=  15,626,026.0  ** MISMATCH diff=-15,626,026.0
    strat 19: total=           0.0  progsum=  16,277,800.0  ** MISMATCH diff=-16,277,800.0
    strat 20: total=   5,556,151.0  progsum=7,122,028,860.0  ** MISMATCH diff=-7,116,472,709.0
    strat 21: total=  15,626,026.0  progsum=1,425,977,405.0  ** MISMATCH diff=-1,410,351,379.0
    strat 22: total=6,080,478,541.0  progsum=6,082,925,529.0  ** MISMATCH diff=-2,446,988.0
    strat 23: total=1,360,063,140.0  progsum=3,392,097,633.0  ** MISMATCH diff=-2,032,034,493.0
    strat 24: total=1,852,763,857.0  progsum=1,926,946,626.0  ** MISMATCH diff=-74,182,769.0
    strat 25: total=2,762,618,696.0  progsum=2,762,618,696.0  OK
    strat 26: total=  74,182,769.0  progsum= 220,147,728.0  ** MISMATCH diff=-145,964,959.0
    strat 27: total= 159,404,143.0  progsum= 771,823,954.0  ** MISMATCH diff=-612,419,811.0
    strat 28: total= 220,147,728.0  progsum= 220,147,728.0  OK
    strat 29: total=3,773,396,850.0  progsum=3,773,396,850.0  OK
    strat 30: total= 135,063,971.0  progsum= 137,763,278.0  ** MISMATCH diff=-2,699,307.0
    strat 31: total= 321,478,978.0  progsum= 358,470,233.0  ** MISMATCH diff=-36,991,255.0
    strat 32: total= 378,362,402.0  progsum= 501,698,460.0  ** MISMATCH diff=-123,336,058.0
    strat 33: total=2,483,284,338.0  progsum=2,485,838,311.0  ** MISMATCH diff=-2,553,973.0
    strat 34: total= 113,323,505.0  progsum=1,822,729,293.0  ** MISMATCH diff=-1,709,405,788.0
    strat 35: total= 178,546,002.0  progsum= 236,725,923.0  ** MISMATCH diff=-58,179,921.0
    strat 36: total=1,161,642,178.0  progsum=1,335,957,059.0  ** MISMATCH diff=-174,314,881.0
    strat 37: total= 118,299,270.0  progsum= 118,299,270.0  OK
    strat 38: total=  13,412,511.0  progsum=           0.0  ** MISMATCH diff=13,412,511.0
    strat 39: total= 925,958,895.0  progsum= 713,872,360.0  ** MISMATCH diff=212,086,535.0

  FY2017   (national total = 26,791,522,461.0)
    strat 1: total=13,881,748,090.0  progsum=23,185,312,192.0  ** MISMATCH diff=-9,303,564,102.0
    strat 2: total=12,541,564,079.0  progsum=8,366,648,627.0  ** MISMATCH diff=4,174,915,452.0
    strat 3: total= 300,000,000.0  progsum= 291,967,033.0  ** MISMATCH diff=8,032,967.0
    strat 4: total=  68,210,292.0  progsum=1,085,020,890.0  ** MISMATCH diff=-1,016,810,598.0

  FY2018   (national total = 24,248,670,940.0)
    strat 1: total= 106,937,119.0  progsum= 106,937,119.0  OK
    strat 2: total= 178,110,976.0  progsum=           0.0  ** MISMATCH diff=178,110,976.0
    strat 3: total=  10,808,542.0  progsum=           0.0  ** MISMATCH diff=10,808,542.0
    strat 4: total= 395,781,981.0  progsum= 395,781,981.0  OK
    strat 5: total= 116,640,968.0  progsum=           0.0  ** MISMATCH diff=116,640,968.0
    strat 6: total=  17,185,357.0  progsum=           0.0  ** MISMATCH diff=17,185,357.0
    strat 7: total=  22,617,101.0  progsum=           0.0  ** MISMATCH diff=22,617,101.0
    strat 8: total=  27,354,797.0  progsum=           0.0  ** MISMATCH diff=27,354,797.0
    strat 9: total=  50,599,993.0  progsum=           0.0  ** MISMATCH diff=50,599,993.0
    strat 10: total=  55,567,565.0  progsum=           0.0  ** MISMATCH diff=55,567,565.0
    strat 11: total=  76,578,436.0  progsum=           0.0  ** MISMATCH diff=76,578,436.0
    strat 12: total=   7,113,960.0  progsum=           0.0  ** MISMATCH diff=7,113,960.0
    strat 13: total=   3,871,575.0  progsum=           0.0  ** MISMATCH diff=3,871,575.0
    strat 14: total=   9,169,865.0  progsum=           0.0  ** MISMATCH diff=9,169,865.0
    strat 15: total=   4,148,333.0  progsum=           0.0  ** MISMATCH diff=4,148,333.0
    strat 16: total=  28,711,608.0  progsum=           0.0  ** MISMATCH diff=28,711,608.0
    strat 17: total=   3,750,412.0  progsum=           0.0  ** MISMATCH diff=3,750,412.0
    strat 18: total=   9,111,740.0  progsum=           0.0  ** MISMATCH diff=9,111,740.0
    strat 19: total= 619,747,281.0  progsum= 619,747,281.0  OK
    strat 20: total=1,240,859,935.0  progsum=1,240,859,935.0  OK
    strat 21: total= 457,853,358.0  progsum= 457,853,358.0  OK
    strat 22: total=2,609,006,595.0  progsum=2,609,006,595.0  OK
    strat 23: total=  33,798,897.0  progsum=           0.0  ** MISMATCH diff=33,798,897.0
    strat 24: total= 151,052,672.0  progsum= 151,052,672.0  OK
    strat 25: total= 220,622,470.0  progsum= 220,622,470.0  OK
    strat 26: total=1,286,241,727.0  progsum=1,286,508,682.0  ** MISMATCH diff=-266,955.0
    strat 27: total= 289,061,638.0  progsum= 289,061,638.0  OK
    strat 28: total= 547,333,257.0  progsum= 547,333,257.0  OK
    strat 29: total= 202,138,264.0  progsum= 202,138,264.0  OK
    strat 30: total=1,460,412,545.0  progsum=1,460,412,545.0  OK
    strat 31: total=  87,929,905.0  progsum=           0.0  ** MISMATCH diff=87,929,905.0
    strat 32: total= 313,772,568.0  progsum= 313,772,568.0  OK
    strat 33: total= 907,119,208.0  progsum= 907,119,208.0  OK
    strat 34: total=  22,362,856.0  progsum=           0.0  ** MISMATCH diff=22,362,856.0
    strat 35: total=  70,323,057.0  progsum=  70,323,057.0  OK
    strat 36: total=7,111,403,554.0  progsum=           0.0  ** MISMATCH diff=7,111,403,554.0
    strat 37: total=1,243,656,717.0  progsum=           0.0  ** MISMATCH diff=1,243,656,717.0
    strat 38: total=1,291,323,207.0  progsum=           0.0  ** MISMATCH diff=1,291,323,207.0
    strat 39: total= 196,905,766.0  progsum=           0.0  ** MISMATCH diff=196,905,766.0
    strat 40: total=1,085,922,672.0  progsum=           0.0  ** MISMATCH diff=1,085,922,672.0
    strat 41: total=1,120,999,134.0  progsum=1,120,999,134.0  OK
    strat 42: total= 554,763,329.0  progsum= 398,633,774.0  ** MISMATCH diff=156,129,555.0

  FY2019   (national total = 29,647.3)
    strat 1: total=       1,613.3  progsum=  75,313,347.0  ** MISMATCH diff=-75,311,733.7
    strat 2: total=       4,889.4  progsum= 685,209,227.0  ** MISMATCH diff=-685,204,337.6
    strat 3: total=       1,258.3  progsum= 299,484,547.0  ** MISMATCH diff=-299,483,288.7
    strat 4: total=       2,472.0  progsum= 549,298,857.0  ** MISMATCH diff=-549,296,385.0
    strat 5: total=       5,278.4  progsum=1,360,376,122.0  ** MISMATCH diff=-1,360,370,843.6
    strat 6: total=       1,588.7  progsum=2,690,493,443.0  ** MISMATCH diff=-2,690,491,854.3
    strat 7: total=       1,609.3  progsum=  55,013,327.0  ** MISMATCH diff=-55,011,717.7
    strat 8: total=       3,059.0  progsum= 396,448,307.0  ** MISMATCH diff=-396,445,248.0
    strat 9: total=         777.7  progsum= 201,259,017.0  ** MISMATCH diff=-201,258,239.3
    strat 10: total=       3,276.9  progsum= 744,903,944.0  ** MISMATCH diff=-744,900,667.1
    strat 11: total=       3,824.3  progsum= 142,620,122.0  ** MISMATCH diff=-142,616,297.7

RECONCILIATION: FAIL - see MISMATCH rows

NATIONAL TOTAL (the denominator every share is computed against)
    FY2007  heads 7,153,280,224.0  programmes 12,728,049,334.0  gap  43.8%  -> GRAND_TOTAL
    FY2008  heads 9,513,687,178.0  programmes 8,499,876,005.0  gap  10.7%  -> GRAND_TOTAL
    FY2011  heads 13,693,186,597.0  programmes 8,065,058,991.0  gap  41.1%  -> GRAND_TOTAL
    FY2012  heads 17,067.8  programmes 648,877,875.8  gap 100.0%  -> GRAND_TOTAL
    FY2013  heads 16,117,228,137.0  programmes 22,860,052,333.0  gap  29.5%  -> GRAND_TOTAL
    FY2014  heads 15,395,930,997.0  programmes 20,521,125,709.4  gap  25.0%  -> GRAND_TOTAL
    FY2015  heads 18,653,260,526.0  programmes 20,789,446,790.2  gap  10.3%  -> GRAND_TOTAL
    FY2016  heads 23,355,280,219.0  programmes 43,466,775,996.5  gap  46.3%  -> GRAND_TOTAL
    FY2017  heads 26,791,522,461.0  programmes 32,928,948,742.0  gap  18.6%  -> GRAND_TOTAL
    FY2018  heads 24,248,670,940.0  programmes 12,398,163,538.0  gap  48.9%  -> GRAND_TOTAL
    FY2019  heads 29,647.3  programmes 7,200,420,260.0  gap 100.0%  -> PROGRAMMES
    The head totals under-report in 1 year(s); the programme rows are the national budget there.
    FY2007  extracted 103.1% of the document's own grand total 12,343,818,001.0
    FY2008  extracted 104.8% of the document's own grand total 9,080,964,583.0
    FY2011  extracted 100.6% of the document's own grand total 13,615,295,006.0
    FY2012  extracted 3801788.6% of the document's own grand total 17,067.7
    FY2013  extracted 134.7% of the document's own grand total 16,972,718,211.0
    FY2014  extracted 138.9% of the document's own grand total 14,776,683,091.0
    FY2015  extracted 101.7% of the document's own grand total 20,442,357,602.0
    FY2016  extracted 186.0% of the document's own grand total 23,365,209,576.0
    FY2017  extracted 122.9% of the document's own grand total 26,791,522,461.0
    FY2018  extracted 99.9% of the document's own grand total 24,272,919,611.0

READABILITY  0 of 2844 programme name(s) unreadable (0%), 0 of 384 head(s) (0%), 0% of the money

PROGRAMME CLASS (share of programme money)
    development        12,601,050,557.0    6.6%  (38 programme-year rows)
    standing_function  20,555,586,207.0   10.8%  (552 programme-year rows)
    overhead           56,831,864,363.0   29.9%  (86 programme-year rows)
    (unclassified)     100,118,294,447.9   52.7%  (0 programme-year rows)

HEAD NAMES: 1893 row(s) renamed so a head reads the same in every year

Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/maldives/budget_layer_all_years.xlsx
  sheet 'budget_all_years' : 3238 rows  (feeds Prompt 6 / build_final_panel - each intervention matches against EVERY year's programs)
  sheet 'programs_wide'    : 1760 programs x 11 year(s) (funding-over-time)
  sheet 'reconciliation'   : 384 rows (audit)
  sheet 'data_quality'     : 2876 flagged items (see summary below)

==============================================================================
DATA-QUALITY SUMMARY
==============================================================================
  HIGH: 251   MEDIUM: 2482   LOW: 132   INFO: 11

  [HIGH] granularity_mismatch  (1)
      - the years were not extracted to the same depth: FY2016 has 565 programme rows and FY2019 has 29, a factor of 19.5. Each year's totals may still be right, but a programme cannot be followed across years and any funding-over-time figure is comparing different levels of the same budget.

  [HIGH] mixed_budget_views  (3)
      - FY2017: rows came from 3 different tables and together made 50,335,862,440.0 against a printed grand total of 26,791,522,461.0, so the same money was present twice. Kept 'Budget Information (1)' (26,791,522,461.0, the closest to the grand total) and dropped 446 row(s) from the others.
      - FY2018: rows came from 3 different tables and together made 28,667,968,991.0 against a printed grand total of 24,272,919,611.0, so the same money was present twice. Kept '2018 General Budget of Offices - Recurrent and Capital Expen' (24,248,670,940.0, the closest to the grand total) and dropped 57 row(s) from the others.
      - FY2019: rows came from 5 different tables and together made 31,140,233,705.8 against a printed grand total of 29,647.4, so the same money was present twice. Kept 'Table 2: Total expenditure by sector' (29,647.3, the closest to the grand total) and dropped 293 row(s) from the others.

  [HIGH] national_basis_programmes  (1)
      - FY2019: head totals sum to 29,647.3 but the programmes beneath them sum to 7,200,420,260.0 (100% apart), so the national total for this year is taken from the PROGRAMME rows. Every share for FY2019 is computed against 7,200,420,260.0.

  [HIGH] over_extraction  (5)
      - FY2012: the heads extracted sum to 648,877,875.8 against a printed grand total of 17,067.7 (3801789%), so the same money is being counted more than once.
      - FY2013: the heads extracted sum to 22,860,052,333.0 against a printed grand total of 16,972,718,211.0 (135%), so the same money is being counted more than once.
      - FY2014: the heads extracted sum to 20,521,125,709.4 against a printed grand total of 14,776,683,091.0 (139%), so the same money is being counted more than once.
      ... and 2 more (see 'data_quality' sheet)

  [HIGH] reconciliation_mismatch  (240)
      - FY2007 strat 4: programs sum to 98,252,906.0 but strategy_total is 8,875,883.0 (gap -89,377,023.0) - a program line is likely missing or mis-extracted for this strategy-year.
      - FY2007 strat 5: programs sum to 40,942,424.0 but strategy_total is 63,545,102.0 (gap 22,602,678.0) - a program line is likely missing or mis-extracted for this strategy-year.
      - FY2007 strat 6: programs sum to 755,291,197.0 but strategy_total is 15,857,098.0 (gap -739,434,099.0) - a program line is likely missing or mis-extracted for this strategy-year.
      ... and 237 more (see 'data_quality' sheet)

  [HIGH] scale_mismatch  (1)
      - the years are not in the same scale: FY2017 states 26,791,522,461.0 and FY2012 states 17,067.7, a factor of 1569721, and both are labelled 'MVR'. A national budget does not change by that much between years, so one extraction is in absolute currency and the other in millions. Every cross-year figure is wrong until they agree.

  [MEDIUM] blank_amount  (98)
      - FY2007 strat 5 5.03: amount is blank/unparseable.
      - FY2007 strat 17 17.03: amount is blank/unparseable.
      - FY2007 strat 17 17.04: amount is blank/unparseable.
      ... and 95 more (see 'data_quality' sheet)

  [MEDIUM] malformed_code_repaired  (525)
      - FY2008 strat 1 1.1: program_code '1' looked malformed and was normalized to '1.1' - verify against source; fix the year file to avoid this.
      - FY2008 strat 1 1.2: program_code '2' looked malformed and was normalized to '1.2' - verify against source; fix the year file to avoid this.
      - FY2008 strat 1 1.3: program_code '3' looked malformed and was normalized to '1.3' - verify against source; fix the year file to avoid this.
      ... and 522 more (see 'data_quality' sheet)

  [MEDIUM] no_grand_total  (1)
      - FY2019: the document printed no grand total that stage 5 could find, so there is nothing to check the extraction's completeness against. Every share for FY2019 rests on the heads being all of them.

  [MEDIUM] program_missing_in_year  (1760)
      - FY2007,2008,2011,2012,2014,2015,2016,2017,2018,2019 strat 0 0.001: program '0.001' (Carrying out the powers and responsibilities vested in the President under the Constitution) exists in ['2013'] but is absent in ['2007', '2008', '2011', '2012', '2014', '2015', '2016', '2017', '2018', '2019'] - check whether it was dropped during extraction or genuinely did not exist that year.
      - FY2007,2008,2011,2012,2014,2015,2016,2017,2018,2019 strat 0 0.002: program '0.002' (Providing all services required for the President and family at a satisfactory standard) exists in ['2013'] but is absent in ['2007', '2008', '2011', '2012', '2014', '2015', '2016', '2017', '2018', '2019'] - check whether it was dropped during extraction or genuinely did not exist that year.
      - FY2007,2008,2011,2012,2014,2015,2016,2017,2018,2019 strat 0 0.003: program '0.003' (Providing all services required for the Vice President and family at a satisfactory standard) exists in ['2013'] but is absent in ['2007', '2008', '2011', '2012', '2014', '2015', '2016', '2017', '2018', '2019'] - check whether it was dropped during extraction or genuinely did not exist that year.
      ... and 1757 more (see 'data_quality' sheet)

  [MEDIUM] zero_amount_programme  (98)
      - FY2007 strat 5 5.03: programme carries no money; a strategy matched only to lines like this reads as funded while receiving nothing
      - FY2007 strat 17 17.03: programme carries no money; a strategy matched only to lines like this reads as funded while receiving nothing
      - FY2007 strat 17 17.04: programme carries no money; a strategy matched only to lines like this reads as funded while receiving nothing
      ... and 95 more (see 'data_quality' sheet)

  [LOW] large_yoy_swing  (132)
      - FY2016->2017 strat 1 1.1: program '1.1' changed +640563349% (3,243.4 -> 20,776,034,912.0) - verify this is real and not an extraction error.
      - FY2011->2012 strat 1 1.2: program '1.2' changed +336312% (162,400.0 -> 546,333,158.0) - verify this is real and not an extraction error.
      - FY2016->2017 strat 1 1.2: program '1.2' changed +170737559% (1,199.4 -> 2,047,827,477.0) - verify this is real and not an extraction error.
      ... and 129 more (see 'data_quality' sheet)
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
  panel               : 261 strategies x 11 years (2007, 2008, 2011, 2012, 2013, 2014, 2015, 2016, 2017, 2018, 2019)
  match_review        : 528 matches (BOTH names + rationale)
  unmatched_codes     : 312 (codes NOT in that year's budget - REVIEW)  <-- !!
  unfunded_strategies : 153 (strategies with no budget any year)
  funding_by_program  : 97 (per programme x year, amount once - SAFE TO SUM)
  unmapped_programs   : 2747 budget programmes with no matched strategy
  risk_panel          : 10 risks | ceiling: PASS
  enrichment          : strategyclean=yes risk_summary=yes
  maturity            : mean=0.504 | financing-weighted=0.709 | {'partial_operation': 105, 'operational_funded': 3, 'planned': 128, 'planned_specific': 21, 'aspirational': 4}
  basket/reverse-pass : 46 shared programmes | reverse-pass edges=1 rows -> 0 new matches
  recall_review       : 11 large programmes matched to only 1 strategy (candidate baskets)
MATURITY: mean=0.504 financing_weighted=0.709
CEILING TEST: PASS - no strategy over-counted in any year
UNMATCHED CODES: 312
QA: FAIL - 312 unmatched code(s), ceiling PASS, 0 year warning(s)
```

### build_analytics_html
```
dashboard -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/maldives/budget_strategy_analytics.html
  years        2017, 2018, 2019
  edges        216
  strategies   261 (153 unfunded)
  size         83 KB
```

### audit_checks
```
AUDIT CHECKS: maldives 17/19 PASS (A2 11 disagree, A16 2 untraceable)
  ok   A1   Stored programme sums              384 strategy-year(s) / 0 disagree
  FAIL A2   Stored strategy totals             384 strategy-year(s) / 11 disagree
            FY2008 strategy 3: stored 0.0, layer -
            FY2008 strategy 12: stored 0.0, layer -
            FY2008 strategy 25: stored 0.0, layer -
            FY2008 strategy 26: stored 0.0, layer -
            FY2011 strategy 3: stored 0.0, layer -
            FY2014 strategy 19: stored 0.0, layer -
  ok   A3   Programme counted once             97 row(s) / 0 duplicate key(s)
  ok   A4   Ceiling holds                      384 strategy-year(s) / 0 over ceiling
  ok   A6   Panel money matches its edges      2871 strategy-year figure(s) / 0 disagree
  ok   A8   Edges cite real programmes         528 accepted edge(s) / 0 dangle
  ok   A9   No strategy dropped                261 strategyclean row(s) / 261 panel row(s)
  ok   A10  Unfunded list is complete          153 zero-funded / 153 listed
  ok   A11  Evidence chain resolves            2705 distinct id(s) / 0 dangle
  ok   A12  Maturity summary is derivable      8 metric(s) / 0 disagree
  ok   A14  No duplicate edges                 216 edge(s) / 0 duplicate(s)
  ok   A15  One currency                       1 expected / 1 found
  FAIL A16  Components are traceable           2803 component(s) / 2 untraceable
            Gender equality law and institutio <- Women's Political Participation and Decision
            Women's economic empowerment, entr <- Women's Economic Participation and Shared Ca
  ok   A17  No workbook open in Excel          0 expected / 0 found
  ok   A18  Strategies come from the plan      261 strategy(ies) / 0 with no component
  ok   A19  Funding priority is reproducible   71 distinct (salience, funding) group(s) / 0 split across priorities
  ok   A20  The budget is readable             2844 programme(s) / 0 unreadable (0%), carrying 0% of the money
  ok   A21  Ambiguous codes name their head    46 repeated code(s) / 0 edge(s) do not name a head
  ok   A22  Every intervention is traceable to a strategy 2727 intervention(s) extracted / 22 uncited (0.8%)
            149
            154
            282
            346
            469
            712
  --   A23  The sector layer stayed out of the panel no sector run for this country
```

### data_issues
```
data issues  Files/outputs/DATA_ISSUES.xlsx
  8 detected across 1 country(ies): 4 high, 3 medium, 1 low
  54 hand-written entr(ies) in 04_Docs_and_Planning/data_issues.json
  HIGH  maldives  D1       A programme code is not unique within a year
  HIGH  maldives  D12      An output predates the prompt that produced it
  HIGH  maldives  D7       Flag raised while combining the budget years
  HIGH  maldives  D8       A strategy total its own programmes do not add up to
```
