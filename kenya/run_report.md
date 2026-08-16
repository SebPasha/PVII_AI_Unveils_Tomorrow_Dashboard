# Run report - Kenya

**🔴 Overall: REVIEW NEEDED**  
Generated 2026-08-15 21:28 by run_pipeline.py

| Stage | Ran | Key QA |
|---|---|---|
| validate_stage_schema (L2) | ok | QA FAIL - FAIL 3/8 (kenya_mapping_2020.xlsx, kenya_mapping_2025.xlsx, kenya_strategyclean.xlsx) |
| validate_source_fidelity (L4) | ok | NOT CONFIGURED [advisory] |
| validate_recall (L4) | ok | NOT CONFIGURED [advisory] |
| validate_refs (L3) | ok | QA FAIL - FAIL 1/1 (kenya references) |
| combine_budget_years | ok | reconcile=FAIL - see MISMATCH rows | data_quality=REVIEW NEEDED - resolve HIGH items before relying on totals for those strategy-years |
| build_final_panel | ok | QA FAIL - ceiling=FAIL - see ceiling sheet | unmatched_codes=0 |
| build_analytics_html | ok | strategies=264 (10 unfunded) | edges=723 |
| audit_checks | ok | QA FAIL - 10/15 PASS (A2 4 disagree, A4 1 over ceiling, A11 10 dangle) [advisory] |
| data_issues | ok | 10 detected across 1 country(ies): 4 high, 4 medium, 2 low [advisory] |

## Outputs

- Budget layer: `Files/outputs/kenya/budget_layer_all_years.xlsx`
- FINAL panel (deliverable): `Files/outputs/kenya/FINAL_PANEL.xlsx`
- Dashboard: `Files/outputs/kenya/budget_strategy_analytics.html`
- Audit trail: `Files/outputs/union_dashboard.html`, Audit tab, filtered to this country
- Data oddities: `Files/outputs/DATA_ISSUES.xlsx`

## Full stage logs

### validate_stage_schema (L2)
```
--- kenya_budget_2020.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/kenya/validation/schema_kenya_budget_2020.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- kenya_budget_2025.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/kenya/validation/schema_kenya_budget_2025.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- kenya_coverage_2020.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/kenya/validation/schema_kenya_coverage_2020.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- kenya_coverage_2025.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/kenya/validation/schema_kenya_coverage_2025.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- kenya_mapping_2020.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/kenya/validation/schema_kenya_mapping_2020.xlsx

  RESULT: FAIL - 12 contract violation(s) across 1 file(s).
  The stage output is not accepted; re-run the stage or fix the prompt.

--- kenya_mapping_2025.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/kenya/validation/schema_kenya_mapping_2025.xlsx

  RESULT: FAIL - 8 contract violation(s) across 1 file(s).
  The stage output is not accepted; re-run the stage or fix the prompt.

--- kenya_strategyclean.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/kenya/validation/schema_kenya_strategyclean.xlsx

  RESULT: FAIL - 8 contract violation(s) across 1 file(s).
  The stage output is not accepted; re-run the stage or fix the prompt.

--- kenya_risk_summary.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/kenya/validation/schema_kenya_risk_summary.xlsx

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
--- kenya references
RESULT: FAIL - 37 dangling reference(s) of 2188
report -> Files/outputs/kenya/validation/refs_kenya_references.xlsx
```

### combine_budget_years
```
==============================================================================
COMBINED BUDGET LAYER  -  years: 2020, 2025  (2 file(s))
==============================================================================

RECONCILIATION (per year: sum of program rows vs strategy_total)

  FY2020   (national total = 1,847,095,440,273.0)
    strat 1011: total=11,320,261,970.0  progsum=11,320,261,970.0  OK
    strat 1021: total=139,194,117,587.0  progsum=139,194,117,587.0  OK
    strat 0101000: total=6,613,800,000.0  progsum=6,613,800,000.0  OK
    strat 0102000: total=13,641,493,609.0  progsum=13,641,493,609.0  OK
    strat 0103000: total=1,785,383,721.0  progsum=1,785,383,721.0  OK
    strat 0104000: total= 626,351,247.0  progsum= 626,351,247.0  OK
    strat 0105000: total=17,606,424,672.0  progsum=17,606,424,672.0  OK
    strat 0106000: total= 276,081,719.0  progsum= 349,247,063.0  ** MISMATCH diff=-73,165,344.0
    strat 0107000: total=3,798,433,232.0  progsum=3,798,433,232.0  OK
    strat 0108000: total=16,844,283,262.0  progsum=16,844,283,262.0  OK
    strat 0109000: total=1,587,283,506.0  progsum=1,587,283,506.0  OK
    strat 0111000: total=3,936,164,907.0  progsum=3,936,164,907.0  OK
    strat 0112000: total=6,987,200,000.0  progsum=6,987,200,000.0  OK
    strat 0116000: total=1,308,200,000.0  progsum=1,308,200,000.0  OK
    strat 0117000: total= 157,096,172.0  progsum= 157,096,172.0  OK
    strat 0118000: total=2,572,392,849.0  progsum=2,572,392,849.0  OK
    strat 0120000: total=6,356,333,367.0  progsum=6,356,333,367.0  OK
    strat 0201000: total= 830,613,449.0  progsum= 830,613,449.0  OK
    strat 0202000: total=186,416,600,000.0  progsum=186,416,600,000.0  OK
    strat 0203000: total=63,109,000,000.0  progsum=63,109,000,000.0  OK
    strat 0204000: total=19,931,690,741.0  progsum=19,931,690,741.0  OK
    strat 0205000: total=9,939,759,397.0  progsum=9,939,759,397.0  OK
    strat 0207000: total= 241,036,648.0  progsum= 241,036,648.0  OK
    strat 0208000: total=4,530,101,010.0  progsum=4,530,101,010.0  OK
    strat 0209000: total= 379,200,000.0  progsum= 379,200,000.0  OK
    strat 0210000: total=22,764,645,681.0  progsum=22,764,645,681.0  OK
    strat 0211000: total= 549,997,669.0  progsum= 549,997,669.0  OK
    strat 0212000: total=11,424,281,210.0  progsum=11,424,281,210.0  OK
    strat 0213000: total=64,569,092,000.0  progsum=64,569,092,000.0  OK
    strat 0214000: total= 875,629,121.0  progsum= 875,629,121.0  OK
    strat 0216000: total=  20,036,413.0  progsum=  20,036,413.0  OK
    strat 0217000: total=4,129,207,117.0  progsum=4,129,207,117.0  OK
    strat 0218000: total=1,595,408,768.0  progsum=1,595,408,768.0  OK
    strat 0220000: total=2,382,000,000.0  progsum=2,382,000,000.0  OK
    strat 0221000: total=1,099,110,554.0  progsum=1,099,110,554.0  OK
    strat 0301000: total= 693,155,981.0  progsum= 693,155,981.0  OK
    strat 0302000: total=3,261,989,956.0  progsum=3,261,989,956.0  OK
    strat 0303000: total=5,400,468,063.0  progsum=5,400,468,063.0  OK
    strat 0304000: total=4,460,400,000.0  progsum=4,460,400,000.0  OK
    strat 0305000: total= 671,300,000.0  progsum= 671,300,000.0  OK
    strat 0307000: total=2,152,900,000.0  progsum=2,152,900,000.0  OK
    strat 0401000: total=9,434,732,647.0  progsum=9,434,732,647.0  OK
    strat 0402000: total=36,995,699,834.0  progsum=36,995,699,834.0  OK
    strat 0403000: total=9,744,429,333.0  progsum=9,744,429,333.0  OK
    strat 0404000: total=8,957,251,274.0  progsum=8,957,251,274.0  OK
    strat 0405000: total=27,592,523,732.0  progsum=27,592,523,732.0  OK
    strat 0501000: total=19,332,757,236.0  progsum=19,332,757,236.0  OK
    strat 0502000: total=68,454,585,549.0  progsum=68,454,585,549.0  OK
    strat 0503000: total=4,752,552,077.0  progsum=4,752,552,077.0  OK
    strat 0504000: total=115,456,791,651.0  progsum=115,456,791,651.0  OK
    strat 0505000: total=24,059,102,734.0  progsum=24,059,102,734.0  OK
    strat 0506000: total=2,299,584,714.0  progsum=2,299,584,714.0  OK
    strat 0507000: total=2,094,756,558.0  progsum=2,094,756,558.0  OK
    strat 0508000: total= 164,025,309.0  progsum=2,991,357,360.0  ** MISMATCH diff=-2,827,332,051.0
    strat 0509000: total=245,725,880,386.0  progsum=245,725,880,386.0  OK
    strat 0510000: total= 419,501,366.0  progsum= 419,501,366.0  OK
    strat 0511000: total=6,805,618,248.0  progsum=6,805,618,248.0  OK
    strat 0512000: total=  48,500,000.0  progsum=  48,500,000.0  OK
    strat 0513000: total=  44,470,000.0  progsum=  44,470,000.0  OK
    strat 0604000: total=26,609,725,501.0  progsum=26,609,725,501.0  OK
    strat 0605000: total=3,511,400,000.0  progsum=3,511,400,000.0  OK
    strat 0606000: total=2,478,794,518.0  progsum=2,478,794,518.0  OK
    strat 0607000: total=2,017,202,641.0  progsum=2,017,202,641.0  OK
    strat 0609000: total= 837,502,841.0  progsum= 837,502,841.0  OK
    strat 0610000: total=18,857,000,000.0  progsum=18,857,000,000.0  OK
    strat 0611000: total=2,966,620,000.0  progsum=2,966,620,000.0  OK
    strat 0612000: total=3,043,680,000.0  progsum=3,043,680,000.0  OK
    strat 0614000: total=1,298,710,000.0  progsum=1,298,710,000.0  OK
    strat 0615000: total= 481,600,000.0  progsum= 481,600,000.0  OK
    strat 0616000: total= 384,301,220.0  progsum= 384,301,220.0  OK
    strat 0617000: total=4,270,393,635.0  progsum=4,270,393,635.0  OK
    strat 0618000: total= 533,016,365.0  progsum= 533,016,365.0  OK
    strat 0619000: total= 565,070,000.0  progsum= 565,070,000.0  OK
    strat 0620000: total= 736,870,000.0  progsum= 736,870,000.0  OK
    strat 0621000: total= 492,930,000.0  progsum= 492,930,000.0  OK
    strat 0622000: total= 892,700,000.0  progsum= 892,700,000.0  OK
    strat 0623000: total= 453,566,440.0  progsum= 453,566,440.0  OK
    strat 0703000: total=           0.0  progsum=           0.0  OK
    strat 0706000: total=43,916,436,041.0  progsum=43,916,436,041.0  OK
    strat 0707000: total=11,329,341,340.0  progsum=11,329,341,340.0  OK
    strat 0708000: total= 215,767,916.0  progsum= 215,767,916.0  OK
    strat 0709000: total= 401,872,342.0  progsum= 401,872,342.0  OK
    strat 0711000: total=17,395,362,000.0  progsum=17,395,362,000.0  OK
    strat 0712000: total=7,451,563,194.0  progsum=7,451,563,194.0  OK
    strat 0713000: total=  54,177,389.0  progsum=  54,177,389.0  OK
    strat 0714000: total=2,827,754,182.0  progsum=2,827,754,182.0  OK
    strat 0715000: total=15,971,697,034.0  progsum=15,971,697,034.0  OK
    strat 0717000: total=69,646,693,294.0  progsum=69,646,693,294.0  OK
    strat 0718000: total=43,907,039,900.0  progsum=43,907,039,900.0  OK
    strat 0719000: total=1,996,808,862.0  progsum=1,996,808,862.0  OK
    strat 0720000: total= 361,100,000.0  progsum= 361,100,000.0  OK
    strat 0721000: total=23,932,141,000.0  progsum=23,932,141,000.0  OK
    strat 0722000: total=7,215,144,400.0  progsum=7,215,144,400.0  OK
    strat 0723000: total=9,497,005,600.0  progsum=9,497,005,600.0  OK
    strat 0725000: total=1,796,049,259.0  progsum=1,796,049,259.0  OK
    strat 0726000: total= 261,328,622.0  progsum= 261,328,622.0  OK
    strat 0727000: total= 152,678,869.0  progsum= 152,678,869.0  OK
    strat 0728000: total= 450,360,000.0  progsum= 450,360,000.0  OK
    strat 0729000: total=5,713,110,000.0  progsum=5,713,110,000.0  OK
    strat 0730000: total= 703,100,000.0  progsum= 703,100,000.0  OK
    strat 0731000: total= 565,040,000.0  progsum= 565,040,000.0  OK
    strat 0732000: total= 886,759,350.0  progsum= 886,759,350.0  OK
    strat 0733000: total=4,919,812,570.0  progsum=4,919,812,570.0  OK
    strat 0737000: total= 469,376,899.0  progsum= 469,376,899.0  OK
    strat 0740000: total=           0.0  progsum=           0.0  OK
    strat 0741000: total=  87,835,044.0  progsum=  87,835,044.0  OK
    strat 0742000: total= 358,823,740.0  progsum= 358,823,740.0  OK
    strat 0744000: total=  26,423,250.0  progsum=  26,423,250.0  OK
    strat 0801000: total=119,808,049,600.0  progsum=119,808,049,600.0  OK
    strat 0802000: total= 200,000,000.0  progsum= 200,000,000.0  OK
    strat 0803000: total=1,402,033,000.0  progsum=1,402,033,000.0  OK
    strat 0804000: total=37,660,000,000.0  progsum=37,660,000,000.0  OK
    strat 0805000: total= 200,000,000.0  progsum= 200,000,000.0  OK
    strat 0901000: total=15,160,190,000.0  progsum=15,160,190,000.0  OK
    strat 0902000: total=1,927,142,058.0  progsum=1,927,142,058.0  OK
    strat 0903000: total= 235,469,333.0  progsum= 235,469,333.0  OK
    strat 0904000: total=1,235,227,227.0  progsum=1,235,227,227.0  OK
    strat 0905000: total= 172,361,382.0  progsum= 172,361,382.0  OK
    strat 0906000: total= 779,081,327.0  progsum= 779,081,327.0  OK
    strat 0907000: total=4,904,898,434.0  progsum=4,904,898,434.0  OK
    strat 0910000: total= 549,490,239.0  progsum= 549,490,239.0  OK
    strat 0911000: total=2,130,000,000.0  progsum=2,130,000,000.0  OK
    strat 0912000: total=1,949,731,889.0  progsum=1,949,731,889.0  OK
    strat 0913000: total= 413,650,875.0  progsum= 413,650,875.0  OK
    strat 1001000: total= 850,403,649.0  progsum= 850,403,649.0  OK
    strat 1002000: total=4,076,433,309.0  progsum=4,076,433,309.0  OK
    strat 1004000: total=11,228,809,218.0  progsum=11,228,809,218.0  OK
    strat 1008000: total=           0.0  progsum=           0.0  OK
    strat 1010000: total= 315,956,263.0  progsum= 315,956,263.0  OK
    strat 1012000: total=2,114,552,081.0  progsum=2,114,552,081.0  OK
    strat 1013000: total=5,374,200,000.0  progsum=5,374,200,000.0  OK
    strat 1014000: total=           0.0  progsum=7,655,824,962.0  ** MISMATCH diff=-7,655,824,962.0
    strat 1015000: total=9,798,000,000.0  progsum=9,798,000,000.0  OK
    strat 1016000: total= 686,838,438.0  progsum= 686,838,438.0  OK
    strat 1017000: total=40,627,270,799.0  progsum=40,627,270,799.0  OK
    strat 1018000: total=10,873,301,747.0  progsum=10,066,601,747.0  ** MISMATCH diff=806,700,000.0
    strat 1022000: total=1,058,975,901.0  progsum=1,058,975,901.0  OK

  FY2025   (national total = 4,728,874,072,135.0)
    strat 1011: total=5,432,190,119.0  progsum=5,432,190,119.0  OK
    strat 1012: total=4,896,000,000.0  progsum=4,896,000,000.0  OK
    strat 1013: total=1,140,788,324.0  progsum=1,140,788,324.0  OK
    strat 1014: total= 458,283,000.0  progsum= 458,283,000.0  OK
    strat 1015: total= 597,112,861.0  progsum= 597,112,861.0  OK
    strat 1016: total= 275,136,014.0  progsum= 275,136,014.0  OK
    strat 1017: total=9,496,000,000.0  progsum=9,496,000,000.0  OK
    strat 1023: total=35,550,346,616.0  progsum=35,550,346,616.0  OK
    strat 1024: total=14,959,813,872.0  progsum=14,959,813,872.0  OK
    strat 1025: total=110,552,072,775.0  progsum=110,552,072,775.0  OK
    strat 1026: total=35,877,114,720.0  progsum=35,877,114,720.0  OK
    strat 1032: total=4,242,428,367.0  progsum=4,242,428,367.0  OK
    strat 1036: total=12,540,387,586.0  progsum=12,540,387,586.0  OK
    strat 1041: total=173,086,817,170.0  progsum=173,086,817,170.0  OK
    strat 1053: total=23,097,447,602.0  progsum=23,097,447,602.0  OK
    strat 1054: total= 828,143,693.0  progsum= 828,143,693.0  OK
    strat 1064: total=30,688,638,919.0  progsum=30,688,638,919.0  OK
    strat 1065: total=125,386,194,444.0  progsum=125,386,194,444.0  OK
    strat 1066: total=142,263,122,192.0  progsum=142,263,122,192.0  OK
    strat 1071: total=135,122,137,600.0  progsum=135,122,137,600.0  OK
    strat 1072: total=66,782,133,355.0  progsum=66,782,133,355.0  OK
    strat 1082: total=98,983,407,719.0  progsum=98,983,407,719.0  OK
    strat 1083: total=28,187,735,123.0  progsum=28,187,735,123.0  OK
    strat 1091: total=198,961,988,075.0  progsum=198,961,988,075.0  OK
    strat 1092: total=51,631,203,728.0  progsum=51,631,203,728.0  OK
    strat 1093: total=3,593,974,935.0  progsum=3,593,974,935.0  OK
    strat 1094: total=87,566,192,681.0  progsum=87,566,192,681.0  OK
    strat 1095: total=5,009,078,552.0  progsum=5,009,078,552.0  OK
    strat 1104: total=23,132,162,500.0  progsum=23,132,162,500.0  OK
    strat 1109: total=52,409,738,911.0  progsum=52,409,738,911.0  OK
    strat 1112: total=10,020,536,000.0  progsum=10,020,536,000.0  OK
    strat 1122: total=22,354,880,752.0  progsum=22,354,880,752.0  OK
    strat 1123: total=6,061,310,364.0  progsum=6,061,310,364.0  OK
    strat 1132: total=17,743,686,404.0  progsum=17,743,686,404.0  OK
    strat 1134: total=3,030,997,321.0  progsum=3,030,997,321.0  OK
    strat 1135: total=4,048,471,229.0  progsum=4,048,471,229.0  OK
    strat 1152: total=69,663,515,207.0  progsum=69,663,515,207.0  OK
    strat 1162: total=12,316,954,089.0  progsum=12,316,954,089.0  OK
    strat 1166: total=11,996,725,869.0  progsum=11,996,725,869.0  OK
    strat 1169: total=45,730,425,195.0  progsum=45,730,425,195.0  OK
    strat 1173: total=8,080,953,583.0  progsum=8,080,953,583.0  OK
    strat 1174: total=3,598,361,146.0  progsum=3,598,361,146.0  OK
    strat 1175: total=8,439,676,621.0  progsum=8,439,676,621.0  OK
    strat 1176: total=9,369,058,500.0  progsum=9,369,058,500.0  OK
    strat 1177: total=4,716,043,914.0  progsum=4,716,043,914.0  OK
    strat 1184: total=5,832,415,243.0  progsum=5,832,415,243.0  OK
    strat 1185: total=35,304,805,645.0  progsum=35,304,805,645.0  OK
    strat 1192: total=1,758,158,447.0  progsum=1,758,158,447.0  OK
    strat 1193: total=31,200,411,883.0  progsum=31,200,411,883.0  OK
    strat 1202: total=10,328,821,808.0  progsum=10,328,821,808.0  OK
    strat 1203: total=14,343,194,935.0  progsum=14,343,194,935.0  OK
    strat 1212: total=6,114,541,404.0  progsum=6,114,541,404.0  OK
    strat 1213: total=19,612,689,909.0  progsum=19,612,689,909.0  OK
    strat 1221: total= 647,487,899.0  progsum= 647,487,899.0  OK
    strat 1252: total=6,977,570,997.0  progsum=6,977,570,997.0  OK
    strat 1261: total=23,737,400,000.0  progsum=23,737,400,000.0  OK
    strat 1271: total=4,171,550,000.0  progsum=4,171,550,000.0  OK
    strat 1281: total=46,351,000,000.0  progsum=46,351,000,000.0  OK
    strat 1291: total=4,007,520,000.0  progsum=4,007,520,000.0  OK
    strat 1311: total=2,037,871,453.0  progsum=2,037,871,453.0  OK
    strat 1321: total= 741,192,500.0  progsum= 741,192,500.0  OK
    strat 1331: total=5,019,131,295.0  progsum=5,019,131,295.0  OK
    strat 1332: total=13,063,930,000.0  progsum=13,063,930,000.0  OK
    strat 2011: total= 478,074,025.0  progsum= 478,074,025.0  OK
    strat 2021: total=2,016,222,679.0  progsum=2,016,222,679.0  OK
    strat 2031: total=3,755,219,680.0  progsum=3,755,219,680.0  OK
    strat 2041: total=1,167,000,000.0  progsum=1,167,000,000.0  OK
    strat 2042: total=26,775,000,000.0  progsum=26,775,000,000.0  OK
    strat 2043: total=8,646,000,000.0  progsum=8,646,000,000.0  OK
    strat 2044: total=8,010,000,000.0  progsum=8,010,000,000.0  OK
    strat 2051: total= 902,900,000.0  progsum= 902,900,000.0  OK
    strat 2061: total= 413,465,304.0  progsum= 413,465,304.0  OK
    strat 2071: total=3,667,530,017.0  progsum=3,667,530,017.0  OK
    strat 2081: total= 472,230,922.0  progsum= 472,230,922.0  OK
    strat 2091: total=358,216,066,118.0  progsum=358,216,066,118.0  OK
    strat 2101: total=1,131,272,317.0  progsum=1,131,272,317.0  OK
    strat 2111: total=8,666,770,850.0  progsum=8,666,770,850.0  OK
    strat 2121: total= 740,219,080.0  progsum= 740,219,080.0  OK
    strat 2131: total= 661,974,500.0  progsum= 661,974,500.0  OK
    strat 2141: total= 435,810,000.0  progsum= 435,810,000.0  OK
    strat 2151: total=1,107,672,060.0  progsum=1,107,672,060.0  OK
    strat 075000: total=  46,079,721.0  progsum=  46,079,721.0  OK
    strat 0101000: total=8,164,420,714.0  progsum=8,164,420,714.0  OK
    strat 0102000: total=77,638,978,602.0  progsum=77,638,978,602.0  OK
    strat 0103000: total=1,172,794,776.0  progsum=1,172,794,776.0  OK
    strat 0104000: total= 688,971,281.0  progsum= 688,971,281.0  OK
    strat 0105000: total=9,580,522,769.0  progsum=9,580,522,769.0  OK
    strat 0106000: total= 346,691,310.0  progsum= 418,347,116.0  ** MISMATCH diff=-71,655,806.0
    strat 0107000: total=10,241,030,217.0  progsum=10,241,030,217.0  OK
    strat 0108000: total=29,257,615,734.0  progsum=29,257,615,734.0  OK
    strat 0109000: total= 887,139,289.0  progsum= 887,139,289.0  OK
    strat 0111000: total=10,130,127,243.0  progsum=10,130,127,243.0  OK
    strat 0112000: total=12,316,954,089.0  progsum=12,316,954,089.0  OK
    strat 0117000: total= 221,040,100.0  progsum= 221,040,100.0  OK
    strat 0118000: total=1,645,558,526.0  progsum=1,645,558,526.0  OK
    strat 0119000: total=2,016,222,679.0  progsum=2,016,222,679.0  OK
    strat 0120000: total=5,344,639,955.0  progsum=5,344,639,955.0  OK
    strat 0121000: total= 649,760,000.0  progsum= 649,760,000.0  OK
    strat 0122000: total=1,206,355,286.0  progsum=1,206,355,286.0  OK
    strat 0201000: total=2,643,116,899.0  progsum=2,643,116,899.0  OK
    strat 0202000: total=198,961,988,075.0  progsum=198,961,988,075.0  OK
    strat 0203000: total=29,649,956,937.0  progsum=29,649,956,937.0  OK
    strat 0204000: total=3,089,035,822.0  progsum=3,089,035,822.0  OK
    strat 0205000: total=12,056,068,630.0  progsum=12,056,068,630.0  OK
    strat 0207000: total= 278,922,194.0  progsum= 278,922,194.0  OK
    strat 0208000: total=5,408,217,827.0  progsum=5,408,217,827.0  OK
    strat 0209000: total= 421,206,751.0  progsum= 421,206,751.0  OK
    strat 0210000: total=17,388,445,150.0  progsum=17,388,445,150.0  OK
    strat 0211000: total= 561,790,584.0  progsum= 561,790,584.0  OK
    strat 0212000: total=15,127,486,011.0  progsum=15,127,486,011.0  OK
    strat 0213000: total=51,830,521,893.0  progsum=51,830,521,893.0  OK
    strat 0214000: total=2,143,716,719.0  progsum=2,143,716,719.0  OK
    strat 0215000: total=31,200,411,883.0  progsum=31,200,411,883.0  OK
    strat 0216000: total=4,193,025,440.0  progsum=4,193,025,440.0  OK
    strat 0217000: total=4,687,513,408.0  progsum=4,687,513,408.0  OK
    strat 0218000: total=2,782,721,752.0  progsum=2,782,721,752.0  OK
    strat 0220000: total=3,593,974,935.0  progsum=3,593,974,935.0  OK
    strat 0221000: total= 709,818,720.0  progsum= 709,818,720.0  OK
    strat 0301000: total= 377,045,857.0  progsum= 377,045,857.0  OK
    strat 0304000: total=8,080,953,583.0  progsum=8,080,953,583.0  OK
    strat 0305000: total= 647,487,899.0  progsum= 647,487,899.0  OK
    strat 0309000: total=1,786,282,549.0  progsum=1,786,282,549.0  OK
    strat 0310000: total= 116,359,164.0  progsum= 116,359,164.0  OK
    strat 0311000: total=1,327,637,016.0  progsum=1,327,637,016.0  OK
    strat 0312000: total= 368,082,417.0  progsum= 368,082,417.0  OK
    strat 0313000: total= 566,260,000.0  progsum= 566,260,000.0  OK
    strat 0314000: total=9,493,712,966.0  progsum=9,493,712,966.0  OK
    strat 0315000: total= 268,848,842.0  progsum= 268,848,842.0  OK
    strat 0316000: total=3,021,579,288.0  progsum=3,021,579,288.0  OK
    strat 0317000: total= 467,326,000.0  progsum= 467,326,000.0  OK
    strat 0318000: total=5,550,700,000.0  progsum=5,550,700,000.0  OK
    strat 0319000: total= 329,453,212.0  progsum= 329,453,212.0  OK
    strat 0320000: total=5,616,703,169.0  progsum=5,616,703,169.0  OK
    strat 0321000: total=2,445,927,595.0  progsum=2,445,927,595.0  OK
    strat 0322000: total=4,716,043,914.0  progsum=4,716,043,914.0  OK
    strat 0402000: total=61,527,831,528.0  progsum=61,527,831,528.0  OK
    strat 0406000: total=9,007,646,807.0  progsum=9,007,646,807.0  OK
    strat 0407000: total=14,461,217,004.0  progsum=14,461,217,004.0  OK
    strat 0408000: total=4,067,504,378.0  progsum=4,067,504,378.0  OK
    strat 0410000: total=16,914,007,087.0  progsum=16,914,007,087.0  OK
    strat 0411000: total=4,012,450,000.0  progsum=4,012,450,000.0  OK
    strat 0412000: total=16,529,119,104.0  progsum=16,529,119,104.0  OK
    strat 0501000: total=29,935,724,959.0  progsum=29,935,724,959.0  OK
    strat 0502000: total=103,342,194,354.0  progsum=103,342,194,354.0  OK
    strat 0503000: total=4,308,175,684.0  progsum=4,308,175,684.0  OK
    strat 0504000: total=124,387,898,039.0  progsum=124,387,898,039.0  OK
    strat 0505000: total=30,194,342,427.0  progsum=30,194,342,427.0  OK
    strat 0506000: total= 700,497,147.0  progsum= 700,497,147.0  OK
    strat 0507000: total=  58,918,193.0  progsum=  58,918,193.0  OK
    strat 0508000: total= 435,378,299.0  progsum=3,536,217,818.0  ** MISMATCH diff=-3,100,839,519.0
    strat 0509000: total=347,685,463,808.0  progsum=347,685,463,808.0  OK
    strat 0510000: total=1,309,066,143.0  progsum=1,309,066,143.0  OK
    strat 0511000: total=9,221,536,167.0  progsum=9,221,536,167.0  OK
    strat 0601000: total=110,552,072,775.0  progsum=110,552,072,775.0  OK
    strat 0605000: total=6,969,014,189.0  progsum=6,969,014,189.0  OK
    strat 0606000: total=4,418,584,833.0  progsum=4,418,584,833.0  OK
    strat 0607000: total=1,445,207,486.0  progsum=1,445,207,486.0  OK
    strat 0609000: total=1,113,778,678.0  progsum=1,113,778,678.0  OK
    strat 0610000: total=23,737,400,000.0  progsum=23,737,400,000.0  OK
    strat 0611000: total=4,171,550,000.0  progsum=4,171,550,000.0  OK
    strat 0612000: total=4,007,520,000.0  progsum=4,007,520,000.0  OK
    strat 0614000: total=2,037,871,453.0  progsum=2,037,871,453.0  OK
    strat 0615000: total= 741,192,500.0  progsum= 741,192,500.0  OK
    strat 0616000: total= 478,074,025.0  progsum= 478,074,025.0  OK
    strat 0617000: total=3,719,172,948.0  progsum=3,719,172,948.0  OK
    strat 0618000: total=  36,046,732.0  progsum=  36,046,732.0  OK
    strat 0619000: total= 902,900,000.0  progsum= 902,900,000.0  OK
    strat 0620000: total=1,131,272,317.0  progsum=1,131,272,317.0  OK
    strat 0621000: total= 435,810,000.0  progsum= 435,810,000.0  OK
    strat 0622000: total=1,107,672,060.0  progsum=1,107,672,060.0  OK
    strat 0623000: total= 610,685,214.0  progsum= 610,685,214.0  OK
    strat 0626000: total=6,836,307,352.0  progsum=6,836,307,352.0  OK
    strat 0627000: total=32,660,722,559.0  progsum=32,660,722,559.0  OK
    strat 0628000: total=2,278,938,843.0  progsum=2,278,938,843.0  OK
    strat 0629000: total=15,517,946,400.0  progsum=15,517,946,400.0  OK
    strat 0630000: total=1,408,357,100.0  progsum=1,408,357,100.0  OK
    strat 0631000: total=1,154,492,331.0  progsum=1,154,492,331.0  OK
    strat 0632000: total=18,950,811,220.0  progsum=18,950,811,220.0  OK
    strat 0704000: total=9,496,000,000.0  progsum=9,496,000,000.0  OK
    strat 0706000: total=64,952,424,273.0  progsum=64,952,424,273.0  OK
    strat 0707000: total=1,474,298,000.0  progsum=1,474,298,000.0  OK
    strat 0709000: total= 233,471,082.0  progsum= 234,021,081.0  ** MISMATCH diff=-549,999.0
    strat 0710000: total=   2,000,000.0  progsum=4,177,242,813.0  ** MISMATCH diff=-4,175,242,813.0
    strat 0711000: total= 579,172,036.0  progsum= 579,172,036.0  OK
    strat 0712000: total=4,242,428,367.0  progsum=4,242,428,367.0  OK
    strat 0714000: total=3,085,407,779.0  progsum=3,085,407,779.0  OK
    strat 0715000: total=19,712,943,022.0  progsum=19,712,943,022.0  OK
    strat 0717000: total=76,480,295,458.0  progsum=76,480,295,458.0  OK
    strat 0718000: total=46,862,874,087.0  progsum=46,862,874,087.0  OK
    strat 0719000: total=11,270,463,665.0  progsum=11,270,463,665.0  OK
    strat 0720000: total= 508,504,390.0  progsum= 508,504,390.0  OK
    strat 0721000: total=26,775,000,000.0  progsum=26,775,000,000.0  OK
    strat 0723000: total=8,428,811,050.0  progsum=8,428,811,050.0  OK
    strat 0725000: total= 900,323,567.0  progsum= 900,323,567.0  OK
    strat 0726000: total=2,492,690,989.0  progsum=2,492,690,989.0  OK
    strat 0727000: total= 171,923,179.0  progsum= 171,923,179.0  OK
    strat 0728000: total= 472,230,922.0  progsum= 472,230,922.0  OK
    strat 0729000: total=8,666,770,850.0  progsum=8,666,770,850.0  OK
    strat 0730000: total= 740,219,080.0  progsum= 740,219,080.0  OK
    strat 0731000: total= 661,974,500.0  progsum= 661,974,500.0  OK
    strat 0733000: total=4,933,891,562.0  progsum=4,933,891,562.0  OK
    strat 0737000: total= 413,465,304.0  progsum= 413,465,304.0  OK
    strat 0741000: total=  49,859,065.0  progsum=  49,859,065.0  OK
    strat 0742000: total= 249,237,736.0  progsum= 249,237,736.0  OK
    strat 0743000: total= 478,489,218.0  progsum= 478,489,218.0  OK
    strat 0744000: total=  56,512,561.0  progsum=  56,512,561.0  OK
    strat 0746000: total= 217,188,950.0  progsum= 217,188,950.0  OK
    strat 0747000: total=10,399,289,030.0  progsum=10,399,289,030.0  OK
    strat 0748000: total=2,488,229,641.0  progsum=2,488,229,641.0  OK
    strat 0749000: total= 271,250,832.0  progsum= 271,250,832.0  OK
    strat 0752000: total= 828,143,693.0  progsum= 828,143,693.0  OK
    strat 0758000: total= 275,136,014.0  progsum= 275,136,014.0  OK
    strat 0765000: total=1,127,000,000.0  progsum=1,127,000,000.0  OK
    strat 0766000: total=  40,000,000.0  progsum=  40,000,000.0  OK
    strat 0767000: total=3,236,650,000.0  progsum=3,236,650,000.0  OK
    strat 0768000: total=2,178,199,100.0  progsum=2,178,199,100.0  OK
    strat 0769000: total=2,595,150,900.0  progsum=2,595,150,900.0  OK
    strat 0801000: total=169,815,800,000.0  progsum=169,815,800,000.0  OK
    strat 0802000: total= 350,000,000.0  progsum= 350,000,000.0  OK
    strat 0803000: total=2,608,517,170.0  progsum=2,608,517,170.0  OK
    strat 0804000: total=46,351,000,000.0  progsum=46,351,000,000.0  OK
    strat 0805000: total= 312,500,000.0  progsum= 312,500,000.0  OK
    strat 0901000: total=17,743,686,404.0  progsum=17,743,686,404.0  OK
    strat 0902000: total=1,927,613,312.0  progsum=1,927,613,312.0  OK
    strat 0903000: total= 350,586,020.0  progsum= 350,586,020.0  OK
    strat 0904000: total= 458,075,884.0  progsum= 458,075,884.0  OK
    strat 0905000: total= 166,222,722.0  progsum= 166,222,722.0  OK
    strat 0906000: total=1,515,528,331.0  progsum=1,515,528,331.0  OK
    strat 0907000: total=3,806,952,972.0  progsum=3,806,952,972.0  OK
    strat 0908000: total=4,764,300,070.0  progsum=4,764,300,070.0  OK
    strat 0909000: total=30,288,914,750.0  progsum=30,288,914,750.0  OK
    strat 0910000: total= 509,933,940.0  progsum= 509,933,940.0  OK
    strat 0911000: total=4,483,400,000.0  progsum=4,483,400,000.0  OK
    strat 0912000: total=1,377,186,225.0  progsum=1,377,186,225.0  OK
    strat 0913000: total= 253,955,179.0  progsum= 253,955,179.0  OK
    strat 0914000: total= 251,590,825.0  progsum= 251,590,825.0  OK
    strat 0916000: total= 128,499,383.0  progsum= 128,499,383.0  OK
    strat 1001000: total= 674,153,125.0  progsum= 674,153,125.0  OK
    strat 1002000: total=2,718,153,956.0  progsum=2,718,153,956.0  OK
    strat 1004000: total=12,136,834,006.0  progsum=12,136,834,006.0  OK
    strat 1007000: total= 436,382,218.0  progsum= 436,382,218.0  OK
    strat 1009000: total= 602,459,867.0  progsum= 602,459,867.0  OK
    strat 1010000: total= 686,386,346.0  progsum= 686,386,346.0  OK
    strat 1012000: total=1,584,090,993.0  progsum=1,584,090,993.0  OK
    strat 1013000: total=7,128,006,806.0  progsum=7,128,006,806.0  OK
    strat 1014000: total=17,480,116,660.0  progsum=17,480,116,660.0  OK
    strat 1015000: total=1,916,900,000.0  progsum=1,916,900,000.0  OK
    strat 1017000: total=39,598,751,780.0  progsum=39,598,751,780.0  OK
    strat 1018000: total=12,916,448,407.0  progsum=12,916,448,407.0  OK
    strat 1019000: total=14,343,194,935.0  progsum=14,343,194,935.0  OK
    strat 1021000: total= 719,316,362.0  progsum= 719,316,362.0  OK
    strat 1022000: total=3,578,224,860.0  progsum=3,578,224,860.0  OK
    strat 1023000: total= 156,920,980.0  progsum= 156,920,980.0  OK
    strat 1024000: total=  11,119,622.0  progsum=  11,119,622.0  OK
    strat 1025000: total= 136,361,971.0  progsum= 136,361,971.0  OK
    strat 07710000: total= 119,940,000.0  progsum= 119,940,000.0  OK

RECONCILIATION: FAIL - see MISMATCH rows

Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/kenya/budget_layer_all_years.xlsx
  sheet 'budget_all_years' : 1378 rows  (feeds Prompt 6 / build_final_panel - each intervention matches against EVERY year's programs)
  sheet 'programs_wide'    : 716 programs x 2 year(s) (funding-over-time)
  sheet 'reconciliation'   : 393 rows (audit)
  sheet 'data_quality'     : 502 flagged items (see summary below)

==============================================================================
DATA-QUALITY SUMMARY
==============================================================================
  HIGH: 8   MEDIUM: 470   LOW: 22   INFO: 2

  [HIGH] reconciliation_mismatch  (8)
      - FY2020 strat 0106000: programs sum to 349,247,063.0 but strategy_total is 276,081,719.0 (gap -73,165,344.0) - a program line is likely missing or mis-extracted for this strategy-year.
      - FY2020 strat 0508000: programs sum to 2,991,357,360.0 but strategy_total is 164,025,309.0 (gap -2,827,332,051.0) - a program line is likely missing or mis-extracted for this strategy-year.
      - FY2020 strat 1014000: programs sum to 7,655,824,962.0 but strategy_total is 0.0 (gap -7,655,824,962.0) - a program line is likely missing or mis-extracted for this strategy-year.
      ... and 5 more (see 'data_quality' sheet)

  [MEDIUM] blank_amount  (23)
      - FY2020 strat 0105000 0105060: amount is blank/unparseable.
      - FY2020 strat 0120000 0120040: amount is blank/unparseable.
      - FY2020 strat 0620000 0620020: amount is blank/unparseable.
      ... and 20 more (see 'data_quality' sheet)

  [MEDIUM] program_missing_in_year  (447)
      - FY2025 strat 0105000 0105060: program '0105060' (NAMATA) exists in ['2020'] but is absent in ['2025'] - check whether it was dropped during extraction or genuinely did not exist that year.
      - FY2025 strat 0116000 0119010: program '0119010' (General Administration, Planning and Support Services) exists in ['2020'] but is absent in ['2025'] - check whether it was dropped during extraction or genuinely did not exist that year.
      - FY2025 strat 0116000 0119020: program '0119020' (Land Administration and Management) exists in ['2020'] but is absent in ['2025'] - check whether it was dropped during extraction or genuinely did not exist that year.
      ... and 444 more (see 'data_quality' sheet)

  [LOW] large_yoy_swing  (22)
      - FY2020->2025 strat 0101000 0101050: program '0101050' changed +413% (819,947,827.0 -> 4,207,574,665.0) - verify this is real and not an extraction error.
      - FY2020->2025 strat 0102000 0102030: program '0102030' changed +801% (7,015,000,000.0 -> 63,220,000,000.0) - verify this is real and not an extraction error.
      - FY2020->2025 strat 0111000 0111010: program '0111010' changed +1829% (40,500,000.0 -> 781,401,118.0) - verify this is real and not an extraction error.
      ... and 19 more (see 'data_quality' sheet)
==============================================================================
DATA QUALITY: REVIEW NEEDED - resolve HIGH items before relying on totals for those strategy-years
==============================================================================
```

### build_final_panel
```
Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/kenya/FINAL_PANEL.xlsx
  panel               : 264 strategies x 2 years (2020, 2025)
  match_review        : 824 matches (BOTH names + rationale)
  unmatched_codes     : 0 (codes NOT in that year's budget - REVIEW)
  unfunded_strategies : 10 (strategies with no budget any year)
  funding_by_program  : 475 (per programme x year, amount once - SAFE TO SUM)
  unmapped_programs   : 502 budget programmes with no matched strategy
  risk_panel          : 10 risks | ceiling: FAIL - see 'ceiling' sheet
  enrichment          : strategyclean=yes risk_summary=yes
  maturity            : mean=0.837 | financing-weighted=0.855 | {'operational_programme': 243, 'operational_funded': 11, 'planned': 10}
  basket/reverse-pass : 181 shared programmes | reverse-pass edges=216 rows -> 115 new matches
  recall_review       : 67 large programmes matched to only 1 strategy (candidate baskets)
MATURITY: mean=0.837 financing_weighted=0.855
CEILING TEST: FAIL - see ceiling sheet
UNMATCHED CODES: 0
QA: FAIL - 0 unmatched code(s), ceiling FAIL, 0 year warning(s)
```

### build_analytics_html
```
dashboard -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/kenya/budget_strategy_analytics.html
  years        2020, 2025
  edges        723
  strategies   264 (10 unfunded)
  size         235 KB
```

### audit_checks
```
AUDIT CHECKS: kenya 10/15 PASS (A2 4 disagree, A4 1 over ceiling, A11 10 dangle)
  ok   A1   Stored programme sums              393 strategy-year(s) / 0 disagree
  FAIL A2   Stored strategy totals             393 strategy-year(s) / 4 disagree
            FY2020 strategy 0703000: stored 0.0, layer -
            FY2020 strategy 0740000: stored 0.0, layer -
            FY2020 strategy 1008000: stored 0.0, layer -
            FY2020 strategy 1014000: stored 0.0, layer -
  ok   A3   Programme counted once             475 row(s) / 0 duplicate key(s)
  FAIL A4   Ceiling holds                      393 strategy-year(s) / 1 over ceiling
            FY2025 strategy 0710000: matched 4,065,815,260.0 of 2,000,000.0
  ok   A6   Panel money matches its edges      528 strategy-year figure(s) / 0 disagree
  ok   A8   Edges cite real programmes         824 accepted edge(s) / 0 dangle
  ok   A9   No strategy dropped                264 strategyclean row(s) / 264 panel row(s)
  ok   A10  Unfunded list is complete          10 zero-funded / 10 listed
  FAIL A11  Evidence chain resolves            1060 distinct id(s) / 10 dangle
            chunk id 0 has no stage-3 row
            chunk id 1 has no stage-3 row
            chunk id 2 has no stage-3 row
            chunk id 3 has no stage-3 row
            chunk id 4 has no stage-3 row
            chunk id 5 has no stage-3 row
  ok   A12  Maturity summary is derivable      8 metric(s) / 0 disagree
  ok   A14  No duplicate edges                 723 edge(s) / 0 duplicate(s)
  FAIL A15  One currency                       1 expected / 2 found
            KSHS
            KShs.
  FAIL A16  Components are traceable           2082 component(s) / 9 untraceable
            Promotion and Development of MSMEs <- MSMEs Development and Promotion
            Promotion and Development of MSMEs <- Entreprenuership and Business Development Se
            Promotion and Development of MSMEs <- Value Addition, Innovation and Incubation fo
            Product and Market Development for <- Market Linkages for MSMEs
            0107010 | Agricultural Policy, Leg <- Agricultural mechanization Bill
            0107010 | Agricultural Policy, Leg <- Livestock Bill
  ok   A17  No workbook open in Excel          0 expected / 0 found
  ok   A18  Strategies come from the plan      264 strategy(ies) / 0 with no component
```

### data_issues
```
data issues  Files/outputs/DATA_ISSUES.xlsx
  10 detected across 1 country(ies): 4 high, 4 medium, 2 low
  11 hand-written entr(ies) in 04_Docs_and_Planning/data_issues.json
  HIGH  kenya     D1       A programme code is not unique within a year
  HIGH  kenya     D11      Strategy named after the budget line funding it
  HIGH  kenya     D7       Flag raised while combining the budget years
  HIGH  kenya     D8       A strategy total its own programmes do not add up to
```
