# Run report - Jamaica

**🔴 Overall: REVIEW NEEDED**  
Generated 2026-08-15 10:40 by run_pipeline.py

| Stage | Ran | Key QA |
|---|---|---|
| validate_stage_schema (L2) | ok | QA FAIL - FAIL 1/11 (jamaica_budget_2024.xlsx) |
| validate_source_fidelity (L4) | ok | NOT CONFIGURED [advisory] |
| validate_recall (L4) | ok | NOT CONFIGURED [advisory] |
| validate_refs (L3) | ok | QA FAIL - FAIL 1/1 (jamaica references) |
| combine_budget_years | ok | reconcile=FAIL - see MISMATCH rows | data_quality=REVIEW NEEDED - resolve HIGH items before relying on totals for those strategy-years |
| build_final_panel | ok | QA FAIL - ceiling=FAIL - see ceiling sheet | unmatched_codes=0 |
| build_analytics_html | ok | strategies=117 (70 unfunded) | edges=92 |
| audit_checks | ok | QA FAIL - 12/15 PASS (A2 16 disagree, A4 1 over ceiling, A11 10 dangle) [advisory] |
| data_issues | ok | 8 detected across 1 country(ies): 2 high, 4 medium, 2 low [advisory] |

## Outputs

- Budget layer: `Files/outputs/jamaica/budget_layer_all_years.xlsx`
- FINAL panel (deliverable): `Files/outputs/jamaica/FINAL_PANEL.xlsx`
- Dashboard: `Files/outputs/jamaica/budget_strategy_analytics.html`
- Audit trail: `Files/outputs/union_dashboard.html`, Audit tab, filtered to this country
- Data oddities: `Files/outputs/DATA_ISSUES.xlsx`

## Full stage logs

### validate_stage_schema (L2)
```
--- jamaica_budget_2019.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/jamaica/validation/schema_jamaica_budget_2019.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- jamaica_budget_2022.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/jamaica/validation/schema_jamaica_budget_2022.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- jamaica_budget_2024.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/jamaica/validation/schema_jamaica_budget_2024.xlsx

  RESULT: FAIL - 4 contract violation(s) across 1 file(s).
  The stage output is not accepted; re-run the stage or fix the prompt.

--- jamaica_coverage_2019.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/jamaica/validation/schema_jamaica_coverage_2019.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- jamaica_coverage_2022.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/jamaica/validation/schema_jamaica_coverage_2022.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- jamaica_coverage_2024.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/jamaica/validation/schema_jamaica_coverage_2024.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- jamaica_mapping_2019.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/jamaica/validation/schema_jamaica_mapping_2019.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- jamaica_mapping_2022.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/jamaica/validation/schema_jamaica_mapping_2022.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- jamaica_mapping_2024.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/jamaica/validation/schema_jamaica_mapping_2024.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- jamaica_strategyclean.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/jamaica/validation/schema_jamaica_strategyclean.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- jamaica_risk_summary.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/jamaica/validation/schema_jamaica_risk_summary.xlsx

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
--- jamaica references
RESULT: FAIL - 7 dangling reference(s) of 1035
report -> Files/outputs/jamaica/validation/refs_jamaica_references.xlsx
```

### combine_budget_years
```
==============================================================================
COMBINED BUDGET LAYER  -  years: 2019, 2022, 2024  (3 file(s))
==============================================================================

RECONCILIATION (per year: sum of program rows vs strategy_total)

  FY2019   (national total = 741,528,080.0)
    strat 01000: total=     290,111.0  progsum=      83,000.0  ** MISMATCH diff=207,111.0
    strat 02000: total=   1,089,639.0  progsum=     232,536.0  ** MISMATCH diff=857,103.0
    strat 03000: total=     137,953.0  progsum=     123,894.0  ** MISMATCH diff=14,059.0
    strat 05000: total=     847,741.0  progsum=     281,569.0  ** MISMATCH diff=566,172.0
    strat 06000: total=     330,541.0  progsum=      76,522.0  ** MISMATCH diff=254,019.0
    strat 07000: total=     201,331.0  progsum=     112,894.0  ** MISMATCH diff=88,437.0
    strat 08000: total=     642,858.0  progsum=     192,376.0  ** MISMATCH diff=450,482.0
    strat 09000: total=     712,147.0  progsum=     444,815.0  ** MISMATCH diff=267,332.0
    strat 15000: total=   8,490,861.0  progsum=     970,562.0  ** MISMATCH diff=7,520,299.0
    strat 15010: total=     697,424.0  progsum=     348,899.0  ** MISMATCH diff=348,525.0
    strat 15020: total=      10,480.0  progsum=     317,423.0  ** MISMATCH diff=-306,943.0
    strat 16000: total=     512,504.0  progsum=     512,504.0  OK
    strat 16049: total=     225,234.0  progsum=     277,298.0  ** MISMATCH diff=-52,064.0
    strat 17000: total=  11,525,361.0  progsum=     801,555.0  ** MISMATCH diff=10,723,806.0
    strat 19000: total=   7,263,805.0  progsum=   1,257,870.0  ** MISMATCH diff=6,005,935.0
    strat 19046: total=   1,078,318.0  progsum=     410,098.0  ** MISMATCH diff=668,220.0
    strat 19047: total=     766,552.0  progsum=   1,290,797.0  ** MISMATCH diff=-524,245.0
    strat 19048: total=   1,063,382.0  progsum=     137,582.0  ** MISMATCH diff=925,800.0
    strat 19050: total=     746,573.0  progsum=   1,210,259.0  ** MISMATCH diff=-463,686.0
    strat 20000: total=  62,287,861.0  progsum=     878,660.0  ** MISMATCH diff=61,409,201.0
    strat 20011: total=     863,877.0  progsum=     553,366.0  ** MISMATCH diff=310,511.0
    strat 20012: total=  10,347,021.0  progsum=   5,280,182.0  ** MISMATCH diff=5,066,839.0
    strat 20017: total= 138,321,395.0  progsum= 138,321,395.0  OK
    strat 20018: total= 136,125,364.0  progsum= 136,125,364.0  OK
    strat 20019: total=  38,012,825.0  progsum=   8,809,247.0  ** MISMATCH diff=29,203,578.0
    strat 20056: total=  10,054,843.0  progsum=   2,573,399.0  ** MISMATCH diff=7,481,444.0
    strat 26000: total=  24,607,058.0  progsum=  22,376,754.0  ** MISMATCH diff=2,230,304.0
    strat 26022: total=  39,423,260.0  progsum=   8,500,836.0  ** MISMATCH diff=30,922,424.0
    strat 26024: total=   7,611,526.0  progsum=     442,109.0  ** MISMATCH diff=7,169,417.0
    strat 26053: total=      28,811.0  progsum=   1,181,254.0  ** MISMATCH diff=-1,152,443.0
    strat 26057: total=     811,315.0  progsum=     148,806.0  ** MISMATCH diff=662,509.0
    strat 28000: total=   2,061,385.0  progsum=   1,043,750.0  ** MISMATCH diff=1,017,635.0
    strat 28023: total=           0.0  progsum=           0.0  OK
    strat 28025: total=     517,942.0  progsum=     508,291.0  ** MISMATCH diff=9,651.0
    strat 28026: total=           0.0  progsum=           0.0  OK
    strat 28027: total=           0.0  progsum=           0.0  OK
    strat 28028: total=           0.0  progsum=           0.0  OK
    strat 28029: total=           0.0  progsum=           0.0  OK
    strat 28030: total=     317,177.0  progsum=     542,177.0  ** MISMATCH diff=-225,000.0
    strat 28031: total=   1,031,846.0  progsum=   1,031,846.0  OK
    strat 28033: total=     173,892.0  progsum=     173,892.0  OK
    strat 28052: total=      96,405.0  progsum=      96,405.0  OK
    strat 28054: total=           0.0  progsum=           0.0  OK
    strat 28058: total=   4,348,842.0  progsum=     388,152.0  ** MISMATCH diff=3,960,690.0
    strat 30000: total=   4,811,749.0  progsum=     610,669.0  ** MISMATCH diff=4,201,080.0
    strat 40000: total=   3,181,784.0  progsum=     947,413.0  ** MISMATCH diff=2,234,371.0
    strat 41000: total= 106,723,489.0  progsum=     121,866.0  ** MISMATCH diff=106,601,623.0
    strat 41051: total=   2,716,424.0  progsum=     309,429.0  ** MISMATCH diff=2,406,995.0
    strat 42000: total=  67,845,615.0  progsum=   4,232,424.0  ** MISMATCH diff=63,613,191.0
    strat 42034: total=   1,727,702.0  progsum=   1,727,702.0  OK
    strat 42035: total=      64,205.0  progsum=      64,205.0  OK
    strat 46000: total=   4,119,479.0  progsum=     593,013.0  ** MISMATCH diff=3,526,466.0
    strat 50000: total=   9,597,784.0  progsum=   1,111,950.0  ** MISMATCH diff=8,485,834.0
    strat 50038: total=      14,019.0  progsum=     483,604.0  ** MISMATCH diff=-469,585.0
    strat 56000: total=   3,329,045.0  progsum=     521,290.0  ** MISMATCH diff=2,807,755.0
    strat 56039: total=   2,188,804.0  progsum=     678,513.0  ** MISMATCH diff=1,510,291.0
    strat 68000: total=  10,289,469.0  progsum=           0.0  ** MISMATCH diff=10,289,469.0
    strat 72000: total=  11,243,052.0  progsum=     707,730.0  ** MISMATCH diff=10,535,322.0

  FY2022   (national total = 860,228,870.0)
    strat 01000: total=     407,675.0  progsum=     407,675.0  OK
    strat 02000: total=   1,341,391.0  progsum=     363,385.0  ** MISMATCH diff=978,006.0
    strat 03000: total=     190,178.0  progsum=     126,397.0  ** MISMATCH diff=63,781.0
    strat 05000: total=   1,087,007.0  progsum=     393,778.0  ** MISMATCH diff=693,229.0
    strat 06000: total=     406,749.0  progsum=      88,253.0  ** MISMATCH diff=318,496.0
    strat 07000: total=     273,004.0  progsum=     141,071.0  ** MISMATCH diff=131,933.0
    strat 08000: total=     763,809.0  progsum=     212,956.0  ** MISMATCH diff=550,853.0
    strat 09000: total=   1,115,532.0  progsum=     745,371.0  ** MISMATCH diff=370,161.0
    strat 15000: total=   7,561,107.0  progsum=     953,722.0  ** MISMATCH diff=6,607,385.0
    strat 15010: total=     680,846.0  progsum=           0.0  ** MISMATCH diff=680,846.0
    strat 15020: total=     659,370.0  progsum=           0.0  ** MISMATCH diff=659,370.0
    strat 16000: total=     561,109.0  progsum=           0.0  ** MISMATCH diff=561,109.0
    strat 16049: total=     274,923.0  progsum=           0.0  ** MISMATCH diff=274,923.0
    strat 17000: total=  11,507,204.0  progsum=   1,076,497.0  ** MISMATCH diff=10,430,707.0
    strat 19000: total=   8,927,891.0  progsum=   2,030,751.0  ** MISMATCH diff=6,897,140.0
    strat 19046: total=   1,090,013.0  progsum=     410,520.0  ** MISMATCH diff=679,493.0
    strat 19047: total=     858,517.0  progsum=   1,602,825.0  ** MISMATCH diff=-744,308.0
    strat 19048: total=   1,192,291.0  progsum=     149,610.0  ** MISMATCH diff=1,042,681.0
    strat 19050: total=     873,915.0  progsum=   1,340,639.0  ** MISMATCH diff=-466,724.0
    strat 20000: total=  49,576,488.0  progsum=   2,041,836.0  ** MISMATCH diff=47,534,652.0
    strat 20011: total=   1,572,648.0  progsum=   1,056,925.0  ** MISMATCH diff=515,723.0
    strat 20012: total=  12,953,812.0  progsum=   7,553,105.0  ** MISMATCH diff=5,400,707.0
    strat 20017: total= 169,057,917.0  progsum=  22,007,668.0  ** MISMATCH diff=147,050,249.0
    strat 20018: total= 138,409,053.0  progsum=  57,299,363.0  ** MISMATCH diff=81,109,690.0
    strat 20019: total=  40,011,884.0  progsum=  41,745,753.0  ** MISMATCH diff=-1,733,869.0
    strat 20056: total=  14,045,294.0  progsum=   3,235,390.0  ** MISMATCH diff=10,809,904.0
    strat 21000: total=           0.0  progsum=           0.0  OK
    strat 21046: total=           0.0  progsum=           0.0  OK
    strat 26000: total=  34,248,397.0  progsum=  28,230,476.0  ** MISMATCH diff=6,017,921.0
    strat 26022: total=  46,117,077.0  progsum=  11,233,758.0  ** MISMATCH diff=34,883,319.0
    strat 26024: total=   8,903,647.0  progsum=     954,802.0  ** MISMATCH diff=7,948,845.0
    strat 26053: total=   1,121,806.0  progsum=   2,048,965.0  ** MISMATCH diff=-927,159.0
    strat 26057: total=     959,761.0  progsum=     168,257.0  ** MISMATCH diff=791,504.0
    strat 26059: total=   1,073,547.0  progsum=     454,275.0  ** MISMATCH diff=619,272.0
    strat 27000: total=     572,205.0  progsum=      71,561.0  ** MISMATCH diff=500,644.0
    strat 28000: total=   2,567,834.0  progsum=   1,381,715.0  ** MISMATCH diff=1,186,119.0
    strat 28025: total=     516,721.0  progsum=     138,793.0  ** MISMATCH diff=377,928.0
    strat 28030: total=     397,438.0  progsum=     332,462.0  ** MISMATCH diff=64,976.0
    strat 28031: total=   1,320,942.0  progsum=   1,011,304.0  ** MISMATCH diff=309,638.0
    strat 28033: total=           0.0  progsum=           0.0  OK
    strat 28052: total=           0.0  progsum=           0.0  OK
    strat 28058: total=   5,585,079.0  progsum=     580,707.0  ** MISMATCH diff=5,004,372.0
    strat 30000: total=   5,030,141.0  progsum=     578,269.0  ** MISMATCH diff=4,451,872.0
    strat 40000: total=  14,219,814.0  progsum=   1,320,741.0  ** MISMATCH diff=12,899,073.0
    strat 41000: total= 119,225,217.0  progsum=           0.0  ** MISMATCH diff=119,225,217.0
    strat 41051: total=   3,136,230.0  progsum=     412,828.0  ** MISMATCH diff=2,723,402.0
    strat 42000: total=  91,011,996.0  progsum=  12,968,255.0  ** MISMATCH diff=78,043,741.0
    strat 42034: total=   2,021,814.0  progsum=     163,641.0  ** MISMATCH diff=1,858,173.0
    strat 42035: total=      91,670.0  progsum=      46,949.0  ** MISMATCH diff=44,721.0
    strat 46000: total=   4,407,217.0  progsum=   1,194,196.0  ** MISMATCH diff=3,213,021.0
    strat 50000: total=           0.0  progsum=     845,882.0  ** MISMATCH diff=-845,882.0
    strat 50038: total=     222,444.0  progsum=     153,846.0  ** MISMATCH diff=68,598.0
    strat 51000: total=  10,224,964.0  progsum=   2,194,805.0  ** MISMATCH diff=8,030,159.0
    strat 53000: total=   4,290,996.0  progsum=     781,303.0  ** MISMATCH diff=3,509,693.0
    strat 53038: total=       8,860.0  progsum=     497,205.0  ** MISMATCH diff=-488,345.0
    strat 56000: total=   6,480,924.0  progsum=     890,255.0  ** MISMATCH diff=5,590,669.0
    strat 56039: total=   2,415,192.0  progsum=     935,474.0  ** MISMATCH diff=1,479,718.0
    strat 68000: total=  12,880,983.0  progsum=     925,644.0  ** MISMATCH diff=11,955,339.0
    strat 72000: total=  15,776,327.0  progsum=     760,988.0  ** MISMATCH diff=15,015,339.0

  FY2024   (national total = 782,755,385.0)
    strat 01000: total=     532,852.0  progsum=     532,852.0  OK
    strat 02000: total=   2,439,963.0  progsum=     657,408.0  ** MISMATCH diff=1,782,555.0
    strat 03000: total=     394,357.0  progsum=     229,739.0  ** MISMATCH diff=164,618.0
    strat 05000: total=   1,404,352.0  progsum=     495,754.0  ** MISMATCH diff=908,598.0
    strat 06000: total=     518,977.0  progsum=     133,868.0  ** MISMATCH diff=385,109.0
    strat 07000: total=     386,655.0  progsum=     195,973.0  ** MISMATCH diff=190,682.0
    strat 08000: total=     885,134.0  progsum=     281,505.0  ** MISMATCH diff=603,629.0
    strat 09000: total=   1,812,771.0  progsum=     985,199.0  ** MISMATCH diff=827,572.0
    strat 10000: total=     257,690.0  progsum=     178,500.0  ** MISMATCH diff=79,190.0
    strat 15000: total=  12,236,752.0  progsum=   1,284,508.0  ** MISMATCH diff=10,952,244.0
    strat 15010: total=   1,322,244.0  progsum=     469,602.0  ** MISMATCH diff=852,642.0
    strat 15020: total=   1,462,358.0  progsum=     581,404.0  ** MISMATCH diff=880,954.0
    strat 15039: total=   4,252,373.0  progsum=   1,205,663.0  ** MISMATCH diff=3,046,710.0
    strat 16000: total=     418,803.0  progsum=     352,774.0  ** MISMATCH diff=66,029.0
    strat 16049: total=     574,923.0  progsum=     322,727.0  ** MISMATCH diff=252,196.0
    strat 17000: total=  13,928,060.0  progsum=   1,177,997.0  ** MISMATCH diff=12,750,063.0
    strat 19000: total=  13,182,903.0  progsum=   2,732,725.0  ** MISMATCH diff=10,450,178.0
    strat 19046: total=   1,766,204.0  progsum=     696,184.0  ** MISMATCH diff=1,070,020.0
    strat 19047: total=   5,008,264.0  progsum=   2,319,751.0  ** MISMATCH diff=2,688,513.0
    strat 19048: total=   1,794,940.0  progsum=     197,372.0  ** MISMATCH diff=1,597,568.0
    strat 19050: total=   3,090,257.0  progsum=   1,842,134.0  ** MISMATCH diff=1,248,123.0
    strat 20000: total=  90,947,481.0  progsum=   4,690,226.0  ** MISMATCH diff=86,257,255.0
    strat 20011: total=   1,771,755.0  progsum=   1,192,392.0  ** MISMATCH diff=579,363.0
    strat 20012: total=  21,602,575.0  progsum=  10,307,030.0  ** MISMATCH diff=11,295,545.0
    strat 20017: total=           0.0  progsum=           0.0  OK
    strat 20018: total=           0.0  progsum=           0.0  OK
    strat 20019: total=  13,856,376.0  progsum=  13,856,376.0  OK
    strat 20056: total=  22,149,337.0  progsum=   6,022,082.0  ** MISMATCH diff=16,127,255.0
    strat 20060: total=   1,561,711.0  progsum=   1,561,711.0  OK
    strat 20061: total=     369,030.0  progsum=     369,030.0  OK
    strat 26000: total=  48,181,983.0  progsum=  41,716,884.0  ** MISMATCH diff=6,465,099.0
    strat 26022: total=  70,423,343.0  progsum=  20,505,357.0  ** MISMATCH diff=49,917,986.0
    strat 26024: total=  11,092,342.0  progsum=   1,152,555.0  ** MISMATCH diff=9,939,787.0
    strat 26053: total=   5,080,641.0  progsum=   2,311,741.0  ** MISMATCH diff=2,768,900.0
    strat 26057: total=   1,404,509.0  progsum=     384,176.0  ** MISMATCH diff=1,020,333.0
    strat 26059: total=   2,886,099.0  progsum=   1,033,661.0  ** MISMATCH diff=1,852,438.0
    strat 27000: total=   1,367,378.0  progsum=     739,535.0  ** MISMATCH diff=627,843.0
    strat 28000: total=   4,040,999.0  progsum=   1,613,048.0  ** MISMATCH diff=2,427,951.0
    strat 28025: total=     799,804.0  progsum=     269,562.0  ** MISMATCH diff=530,242.0
    strat 28030: total=     885,108.0  progsum=     467,797.0  ** MISMATCH diff=417,311.0
    strat 28031: total=   1,672,923.0  progsum=   1,260,998.0  ** MISMATCH diff=411,925.0
    strat 28058: total=   7,554,474.0  progsum=   1,136,598.0  ** MISMATCH diff=6,417,876.0
    strat 30000: total=   6,751,435.0  progsum=     921,129.0  ** MISMATCH diff=5,830,306.0
    strat 40000: total=  20,015,027.0  progsum=   1,880,279.0  ** MISMATCH diff=18,134,748.0
    strat 41000: total= 160,322,923.0  progsum=     256,247.0  ** MISMATCH diff=160,066,676.0
    strat 41051: total=   4,758,206.0  progsum=     620,677.0  ** MISMATCH diff=4,137,529.0
    strat 42000: total= 134,122,873.0  progsum=  10,473,308.0  ** MISMATCH diff=123,649,565.0
    strat 42034: total=   2,770,476.0  progsum=     247,300.0  ** MISMATCH diff=2,523,176.0
    strat 42035: total=     128,529.0  progsum=      60,596.0  ** MISMATCH diff=67,933.0
    strat 46000: total=   6,205,640.0  progsum=   1,100,763.0  ** MISMATCH diff=5,104,877.0
    strat 51000: total=  15,681,289.0  progsum=   2,451,889.0  ** MISMATCH diff=13,229,400.0
    strat 53000: total=   6,615,623.0  progsum=   1,057,868.0  ** MISMATCH diff=5,557,755.0
    strat 53038: total=   1,245,569.0  progsum=     806,865.0  ** MISMATCH diff=438,704.0
    strat 56000: total=           0.0  progsum=           0.0  OK
    strat 56039: total=           0.0  progsum=           0.0  OK
    strat 68000: total=           0.0  progsum=           0.0  OK
    strat 69000: total=  24,525,711.0  progsum=   2,129,851.0  ** MISMATCH diff=22,395,860.0
    strat 69039: total=           0.0  progsum=           0.0  OK
    strat 72000: total=  24,293,384.0  progsum=     966,407.0  ** MISMATCH diff=23,326,977.0

RECONCILIATION: FAIL - see MISMATCH rows

Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/jamaica/budget_layer_all_years.xlsx
  sheet 'budget_all_years' : 348 rows  (feeds Prompt 6 / build_final_panel - each intervention matches against EVERY year's programs)
  sheet 'programs_wide'    : 71 programs x 3 year(s) (funding-over-time)
  sheet 'reconciliation'   : 176 rows (audit)
  sheet 'data_quality'     : 215 flagged items (see summary below)

==============================================================================
DATA-QUALITY SUMMARY
==============================================================================
  HIGH: 147   MEDIUM: 61   LOW: 4   INFO: 3

  [HIGH] reconciliation_mismatch  (147)
      - FY2019 strat 01000: programs sum to 83,000.0 but strategy_total is 290,111.0 (gap 207,111.0) - a program line is likely missing or mis-extracted for this strategy-year.
      - FY2019 strat 02000: programs sum to 232,536.0 but strategy_total is 1,089,639.0 (gap 857,103.0) - a program line is likely missing or mis-extracted for this strategy-year.
      - FY2019 strat 03000: programs sum to 123,894.0 but strategy_total is 137,953.0 (gap 14,059.0) - a program line is likely missing or mis-extracted for this strategy-year.
      ... and 144 more (see 'data_quality' sheet)

  [MEDIUM] blank_amount  (34)
      - FY2019 strat 28023: amount is blank/unparseable.
      - FY2019 strat 28023 28023: amount is blank/unparseable.
      - FY2019 strat 28026: amount is blank/unparseable.
      ... and 31 more (see 'data_quality' sheet)

  [MEDIUM] program_missing_in_year  (27)
      - FY2019,2022 strat 10000 10000: program '10000' (Executive Direction and Administration) exists in ['2024'] but is absent in ['2019', '2022'] - check whether it was dropped during extraction or genuinely did not exist that year.
      - FY2022 strat 15010 15010: program '15010' (Executive Direction and Administration) exists in ['2019', '2024'] but is absent in ['2022'] - check whether it was dropped during extraction or genuinely did not exist that year.
      - FY2022 strat 15020 15020: program '15020' (Executive Direction and Administration) exists in ['2019', '2024'] but is absent in ['2022'] - check whether it was dropped during extraction or genuinely did not exist that year.
      ... and 24 more (see 'data_quality' sheet)

  [LOW] large_yoy_swing  (4)
      - FY2019->2022 strat 01000 01000: program '01000' changed +391% (83,000.0 -> 407,675.0) - verify this is real and not an extraction error.
      - FY2019->2022 strat 20019 20019: program '20019' changed +374% (8,809,247.0 -> 41,745,753.0) - verify this is real and not an extraction error.
      - FY2022->2024 strat 27000 27000: program '27000' changed +933% (71,561.0 -> 739,535.0) - verify this is real and not an extraction error.
      ... and 1 more (see 'data_quality' sheet)
==============================================================================
DATA QUALITY: REVIEW NEEDED - resolve HIGH items before relying on totals for those strategy-years
==============================================================================
```

### build_final_panel
```
Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/jamaica/FINAL_PANEL.xlsx
  panel               : 117 strategies x 3 years (2019, 2022, 2024)
  match_review        : 93 matches (BOTH names + rationale)
  unmatched_codes     : 0 (codes NOT in that year's budget - REVIEW)
  unfunded_strategies : 70 (strategies with no budget any year)
  funding_by_program  : 48 (per programme x year, amount once - SAFE TO SUM)
  unmapped_programs   : 124 budget programmes with no matched strategy
  risk_panel          : 10 risks | ceiling: FAIL - see 'ceiling' sheet
  enrichment          : strategyclean=yes risk_summary=yes
  maturity            : mean=0.505 | financing-weighted=0.829 | {'operational_programme': 22, 'partial_operation': 23, 'operational_funded': 2, 'planned_specific': 2, 'planned': 52, 'aspirational': 16}
  basket/reverse-pass : 23 shared programmes | reverse-pass edges=1 rows -> 0 new matches
  recall_review       : 3 large programmes matched to only 1 strategy (candidate baskets)
MATURITY: mean=0.505 financing_weighted=0.829
CEILING TEST: FAIL - see ceiling sheet
UNMATCHED CODES: 0
QA: FAIL - 0 unmatched code(s), ceiling FAIL, 0 year warning(s)
```

### build_analytics_html
```
dashboard -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/jamaica/budget_strategy_analytics.html
  years        2019, 2022, 2024
  edges        92
  strategies   117 (70 unfunded)
  size         53 KB
```

### audit_checks
```
AUDIT CHECKS: jamaica 12/15 PASS (A2 16 disagree, A4 1 over ceiling, A11 10 dangle)
  ok   A1   Stored programme sums              176 strategy-year(s) / 0 disagree
  FAIL A2   Stored strategy totals             176 strategy-year(s) / 16 disagree
            FY2019 strategy 28023: stored 0.0, layer -
            FY2019 strategy 28026: stored 0.0, layer -
            FY2019 strategy 28027: stored 0.0, layer -
            FY2019 strategy 28028: stored 0.0, layer -
            FY2019 strategy 28029: stored 0.0, layer -
            FY2019 strategy 28054: stored 0.0, layer -
  ok   A3   Programme counted once             48 row(s) / 0 duplicate key(s)
  FAIL A4   Ceiling holds                      176 strategy-year(s) / 1 over ceiling
            FY2022 strategy 19050: matched 1,340,639.0 of 873,915.0
  ok   A6   Panel money matches its edges      351 strategy-year figure(s) / 0 disagree
  ok   A8   Edges cite real programmes         93 accepted edge(s) / 0 dangle
  ok   A9   No strategy dropped                117 strategyclean row(s) / 117 panel row(s)
  ok   A10  Unfunded list is complete          70 zero-funded / 70 listed
  FAIL A11  Evidence chain resolves            830 distinct id(s) / 10 dangle
            chunk id 0 has no stage-3 row
            chunk id 1 has no stage-3 row
            chunk id 2 has no stage-3 row
            chunk id 3 has no stage-3 row
            chunk id 4 has no stage-3 row
            chunk id 5 has no stage-3 row
  ok   A12  Maturity summary is derivable      8 metric(s) / 0 disagree
  ok   A14  No duplicate edges                 92 edge(s) / 0 duplicate(s)
  ok   A15  One currency                       1 expected / 1 found
  ok   A16  Components are traceable           1067 component(s) / 0 untraceable
  ok   A17  No workbook open in Excel          0 expected / 0 found
  ok   A18  Strategies come from the plan      117 strategy(ies) / 0 with no component
```

### data_issues
```
data issues  Files/outputs/DATA_ISSUES.xlsx
  8 detected across 1 country(ies): 2 high, 4 medium, 2 low
  11 hand-written entr(ies) in 04_Docs_and_Planning/data_issues.json
  HIGH  jamaica   D7       Flag raised while combining the budget years
  HIGH  jamaica   D8       A strategy total its own programmes do not add up to
```
