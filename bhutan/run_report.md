# Run report - Bhutan

**🔴 Overall: REVIEW NEEDED**  
Generated 2026-08-26 00:50 by run_pipeline.py

| Stage | Ran | Key QA |
|---|---|---|
| validate_stage_schema (L2) | ok | PASS 9/9 |
| validate_source_fidelity (L4) | ok | NOT CONFIGURED |
| validate_recall (L4) | ok | NOT CONFIGURED [advisory] |
| validate_refs (L3) | ok | PASS 1/1 |
| combine_budget_years | ok | reconcile=FAIL - see MISMATCH rows | data_quality=REVIEW NEEDED - resolve HIGH items before relying on totals for those strategy-years |
| build_final_panel | ok | ceiling=PASS - no strategy over-counted in any year | unmatched_codes=0 |
| build_analytics_html | ok | strategies=41 (18 unfunded) | edges=83 |
| audit_checks | ok | 19/19 PASS [advisory] |
| data_issues | FAILED | 6 detected across 1 country(ies): 2 high, 3 medium, 1 low [advisory] |

## Outputs

- Budget layer: `Files/outputs/bhutan/budget_layer_all_years.xlsx`
- FINAL panel (deliverable): `Files/outputs/bhutan/FINAL_PANEL.xlsx`
- Dashboard: `Files/outputs/bhutan/budget_strategy_analytics.html`
- Audit trail: `Files/outputs/union_dashboard.html`, Audit tab, filtered to this country
- Data oddities: `Files/outputs/DATA_ISSUES.xlsx`

## Full stage logs

### validate_stage_schema (L2)
```
--- bhutan_budget_2024.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/bhutan/validation/schema_bhutan_budget_2024.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- bhutan_budget_2025.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/bhutan/validation/schema_bhutan_budget_2025.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- bhutan_budget_2026.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/bhutan/validation/schema_bhutan_budget_2026.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- bhutan_budget_2027.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/bhutan/validation/schema_bhutan_budget_2027.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- bhutan_mapping_2024.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/bhutan/validation/schema_bhutan_mapping_2024.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- bhutan_mapping_2025.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/bhutan/validation/schema_bhutan_mapping_2025.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- bhutan_mapping_2026.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/bhutan/validation/schema_bhutan_mapping_2026.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- bhutan_strategyclean.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/bhutan/validation/schema_bhutan_strategyclean.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- bhutan_risk_summary.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/bhutan/validation/schema_bhutan_risk_summary.xlsx

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
--- bhutan references
RESULT: PASS - every one of 436 reference(s) resolves
report -> Files/outputs/bhutan/validation/refs_bhutan_references.xlsx
```

### combine_budget_years
```
==============================================================================
COMBINED BUDGET LAYER  -  years: 2024, 2025, 2026, 2027  (4 file(s))
==============================================================================

RECONCILIATION (per year: sum of program rows vs strategy_total)

  FY2024   (national total = 85,716.5)
    strat 1: total=      24,591.2  progsum=      24,592.6  ** MISMATCH diff=-1.4
    strat 2: total=      22,827.2  progsum=      22,827.2  OK
    strat 3: total=       1,418.6  progsum=         316.2  ** MISMATCH diff=1,102.4
    strat 4: total=       2,647.6  progsum=         130.7  ** MISMATCH diff=2,516.9
    strat 5: total=      17,992.3  progsum=          23.0  ** MISMATCH diff=17,969.3
    strat 6: total=      16,045.6  progsum=      16,052.1  ** MISMATCH diff=-6.5
    strat 7: total=         193.9  progsum=         193.9  OK

  FY2025   (national total = 97,654.8)
    strat 1: total=      32,753.0  progsum=      33,210.9  ** MISMATCH diff=-457.9
    strat 2: total=      26,210.7  progsum=      26,210.7  OK
    strat 3: total=       2,226.1  progsum=       1,410.2  ** MISMATCH diff=815.9
    strat 4: total=       4,095.1  progsum=       1,300.1  ** MISMATCH diff=2,795.0
    strat 5: total=      16,721.9  progsum=         992.0  ** MISMATCH diff=15,729.9
    strat 6: total=      15,648.0  progsum=      15,914.6  ** MISMATCH diff=-266.7

  FY2026   (national total = 138,500.7)
    strat 1: total=      40,903.3  progsum=      40,903.3  OK
    strat 2: total=      35,224.0  progsum=      35,224.0  OK
    strat 3: total=       2,805.2  progsum=           0.0  ** MISMATCH diff=2,805.2
    strat 4: total=       5,703.5  progsum=           0.0  ** MISMATCH diff=5,703.5
    strat 5: total=      23,667.4  progsum=           0.0  ** MISMATCH diff=23,667.4
    strat 6: total=      30,197.3  progsum=      30,197.3  OK

  FY2027   (national total = 147,151.4)
    strat 1: total=         438.0  progsum=           0.0  ** MISMATCH diff=438.0
    strat 2: total=       1,741.7  progsum=           0.0  ** MISMATCH diff=1,741.7
    strat 3: total=      57,946.3  progsum=           0.0  ** MISMATCH diff=57,946.3
    strat 4: total=      43,523.8  progsum=           0.0  ** MISMATCH diff=43,523.8
    strat 5: total=      31,915.0  progsum=           0.0  ** MISMATCH diff=31,915.0
    strat 20: total=          33.3  progsum=           0.0  ** MISMATCH diff=33.3
    strat 21: total=          29.0  progsum=           0.0  ** MISMATCH diff=29.0
    strat 22: total=          32.0  progsum=           0.0  ** MISMATCH diff=32.0
    strat 23: total=          30.8  progsum=           0.0  ** MISMATCH diff=30.8
    strat 24: total=          28.3  progsum=           0.0  ** MISMATCH diff=28.3
    strat 25: total=          31.6  progsum=           0.0  ** MISMATCH diff=31.6
    strat 26: total=         172.0  progsum=           0.0  ** MISMATCH diff=172.0
    strat 27: total=          96.8  progsum=           0.0  ** MISMATCH diff=96.8
    strat 28: total=          45.1  progsum=           0.0  ** MISMATCH diff=45.1
    strat 29: total=          28.7  progsum=           0.0  ** MISMATCH diff=28.7
    strat 30: total=          32.3  progsum=           0.0  ** MISMATCH diff=32.3
    strat 31: total=          72.5  progsum=           0.0  ** MISMATCH diff=72.5
    strat 32: total=          91.4  progsum=           0.0  ** MISMATCH diff=91.4
    strat 33: total=          42.1  progsum=           0.0  ** MISMATCH diff=42.1
    strat 34: total=          20.7  progsum=           0.0  ** MISMATCH diff=20.7
    strat 35: total=         405.6  progsum=           0.0  ** MISMATCH diff=405.6
    strat 36: total=          40.0  progsum=           0.0  ** MISMATCH diff=40.0
    strat 37: total=          28.2  progsum=           0.0  ** MISMATCH diff=28.2
    strat 38: total=          28.2  progsum=           0.0  ** MISMATCH diff=28.2
    strat 39: total=          36.2  progsum=           0.0  ** MISMATCH diff=36.2
    strat 40: total=          36.9  progsum=           0.0  ** MISMATCH diff=36.9
    strat 41: total=         167.4  progsum=           0.0  ** MISMATCH diff=167.4
    strat 42: total=          24.4  progsum=           0.0  ** MISMATCH diff=24.4
    strat 43: total=          32.9  progsum=           0.0  ** MISMATCH diff=32.9
    strat 44: total=          39.6  progsum=           0.0  ** MISMATCH diff=39.6
    strat 45: total=          71.9  progsum=           0.0  ** MISMATCH diff=71.9
    strat 46: total=          31.6  progsum=           0.0  ** MISMATCH diff=31.6
    strat 47: total=          30.6  progsum=           0.0  ** MISMATCH diff=30.6
    strat 48: total=         138.2  progsum=           0.0  ** MISMATCH diff=138.2
    strat 49: total=          33.2  progsum=           0.0  ** MISMATCH diff=33.2
    strat 50: total=          89.9  progsum=           0.0  ** MISMATCH diff=89.9
    strat 51: total=          39.6  progsum=           0.0  ** MISMATCH diff=39.6
    strat 52: total=          21.7  progsum=           0.0  ** MISMATCH diff=21.7
    strat 53: total=          31.3  progsum=           0.0  ** MISMATCH diff=31.3
    strat 54: total=          19.8  progsum=           0.0  ** MISMATCH diff=19.8
    strat 55: total=         173.4  progsum=           0.0  ** MISMATCH diff=173.4
    strat 56: total=         130.3  progsum=           0.0  ** MISMATCH diff=130.3
    strat 57: total=          18.7  progsum=           0.0  ** MISMATCH diff=18.7
    strat 58: total=          20.1  progsum=           0.0  ** MISMATCH diff=20.1
    strat 59: total=          21.0  progsum=           0.0  ** MISMATCH diff=21.0
    strat 60: total=          25.0  progsum=           0.0  ** MISMATCH diff=25.0
    strat 61: total=          34.8  progsum=           0.0  ** MISMATCH diff=34.8
    strat 62: total=          19.7  progsum=           0.0  ** MISMATCH diff=19.7
    strat 63: total=          20.3  progsum=           0.0  ** MISMATCH diff=20.3
    strat 64: total=         127.4  progsum=           0.0  ** MISMATCH diff=127.4
    strat 65: total=          20.5  progsum=           0.0  ** MISMATCH diff=20.5
    strat 66: total=          34.1  progsum=           0.0  ** MISMATCH diff=34.1
    strat 67: total=          50.5  progsum=           0.0  ** MISMATCH diff=50.5
    strat 68: total=          38.3  progsum=           0.0  ** MISMATCH diff=38.3
    strat 69: total=          18.6  progsum=           0.0  ** MISMATCH diff=18.6
    strat 70: total=          26.5  progsum=           0.0  ** MISMATCH diff=26.5
    strat 71: total=         111.6  progsum=           0.0  ** MISMATCH diff=111.6
    strat 72: total=          27.4  progsum=           0.0  ** MISMATCH diff=27.4
    strat 73: total=          18.1  progsum=           0.0  ** MISMATCH diff=18.1
    strat 74: total=          24.0  progsum=           0.0  ** MISMATCH diff=24.0
    strat 75: total=          41.4  progsum=           0.0  ** MISMATCH diff=41.4
    strat 76: total=          32.4  progsum=           0.0  ** MISMATCH diff=32.4
    strat 77: total=          24.9  progsum=           0.0  ** MISMATCH diff=24.9
    strat 78: total=          22.0  progsum=           0.0  ** MISMATCH diff=22.0
    strat 79: total=          22.5  progsum=           0.0  ** MISMATCH diff=22.5
    strat 80: total=          21.4  progsum=           0.0  ** MISMATCH diff=21.4
    strat 81: total=          39.4  progsum=           0.0  ** MISMATCH diff=39.4
    strat 82: total=          23.9  progsum=           0.0  ** MISMATCH diff=23.9
    strat 83: total=          29.3  progsum=           0.0  ** MISMATCH diff=29.3
    strat 84: total=         422.3  progsum=           0.0  ** MISMATCH diff=422.3
    strat 85: total=          37.3  progsum=           0.0  ** MISMATCH diff=37.3
    strat 86: total=          38.1  progsum=           0.0  ** MISMATCH diff=38.1
    strat 87: total=          34.0  progsum=           0.0  ** MISMATCH diff=34.0
    strat 88: total=         230.1  progsum=           0.0  ** MISMATCH diff=230.1
    strat 89: total=          33.9  progsum=           0.0  ** MISMATCH diff=33.9
    strat 90: total=          29.4  progsum=           0.0  ** MISMATCH diff=29.4
    strat 91: total=          35.3  progsum=           0.0  ** MISMATCH diff=35.3
    strat 92: total=          43.6  progsum=           0.0  ** MISMATCH diff=43.6
    strat 93: total=          27.6  progsum=           0.0  ** MISMATCH diff=27.6
    strat 94: total=          38.5  progsum=           0.0  ** MISMATCH diff=38.5
    strat 95: total=         122.2  progsum=           0.0  ** MISMATCH diff=122.2
    strat 96: total=         108.1  progsum=           0.0  ** MISMATCH diff=108.1
    strat 97: total=          41.2  progsum=           0.0  ** MISMATCH diff=41.2
    strat 98: total=          34.2  progsum=           0.0  ** MISMATCH diff=34.2
    strat 99: total=          43.6  progsum=           0.0  ** MISMATCH diff=43.6
    strat 100: total=          19.2  progsum=           0.0  ** MISMATCH diff=19.2
    strat 101: total=          20.3  progsum=           0.0  ** MISMATCH diff=20.3
    strat 102: total=          27.4  progsum=           0.0  ** MISMATCH diff=27.4
    strat 103: total=          16.9  progsum=           0.0  ** MISMATCH diff=16.9
    strat 104: total=          54.0  progsum=           0.0  ** MISMATCH diff=54.0
    strat 105: total=          22.6  progsum=           0.0  ** MISMATCH diff=22.6
    strat 106: total=          26.2  progsum=           0.0  ** MISMATCH diff=26.2
    strat 107: total=          18.9  progsum=           0.0  ** MISMATCH diff=18.9
    strat 108: total=          18.1  progsum=           0.0  ** MISMATCH diff=18.1
    strat 109: total=          18.4  progsum=           0.0  ** MISMATCH diff=18.4
    strat 110: total=          88.4  progsum=           0.0  ** MISMATCH diff=88.4
    strat 111: total=         116.1  progsum=           0.0  ** MISMATCH diff=116.1
    strat 112: total=          27.8  progsum=           0.0  ** MISMATCH diff=27.8
    strat 113: total=          64.9  progsum=           0.0  ** MISMATCH diff=64.9
    strat 114: total=          30.4  progsum=           0.0  ** MISMATCH diff=30.4
    strat 115: total=          41.8  progsum=           0.0  ** MISMATCH diff=41.8
    strat 116: total=         127.4  progsum=           0.0  ** MISMATCH diff=127.4
    strat 117: total=          72.1  progsum=           0.0  ** MISMATCH diff=72.1
    strat 118: total=          28.4  progsum=           0.0  ** MISMATCH diff=28.4
    strat 119: total=         111.8  progsum=           0.0  ** MISMATCH diff=111.8
    strat 120: total=          25.4  progsum=           0.0  ** MISMATCH diff=25.4
    strat 121: total=          28.2  progsum=           0.0  ** MISMATCH diff=28.2
    strat 122: total=          25.4  progsum=           0.0  ** MISMATCH diff=25.4
    strat 123: total=          27.3  progsum=           0.0  ** MISMATCH diff=27.3
    strat 124: total=          39.3  progsum=           0.0  ** MISMATCH diff=39.3
    strat 125: total=          67.9  progsum=           0.0  ** MISMATCH diff=67.9
    strat 126: total=          43.9  progsum=           0.0  ** MISMATCH diff=43.9
    strat 127: total=          36.5  progsum=           0.0  ** MISMATCH diff=36.5
    strat 128: total=          25.3  progsum=           0.0  ** MISMATCH diff=25.3
    strat 129: total=         245.5  progsum=           0.0  ** MISMATCH diff=245.5
    strat 130: total=          27.9  progsum=           0.0  ** MISMATCH diff=27.9
    strat 131: total=          31.5  progsum=           0.0  ** MISMATCH diff=31.5
    strat 132: total=          90.8  progsum=           0.0  ** MISMATCH diff=90.8
    strat 133: total=          33.2  progsum=           0.0  ** MISMATCH diff=33.2
    strat 134: total=          38.6  progsum=           0.0  ** MISMATCH diff=38.6
    strat 135: total=          31.0  progsum=           0.0  ** MISMATCH diff=31.0
    strat 136: total=          19.2  progsum=           0.0  ** MISMATCH diff=19.2
    strat 137: total=          43.1  progsum=           0.0  ** MISMATCH diff=43.1
    strat 138: total=          96.3  progsum=           0.0  ** MISMATCH diff=96.3
    strat 139: total=          99.4  progsum=           0.0  ** MISMATCH diff=99.4
    strat 140: total=          25.4  progsum=           0.0  ** MISMATCH diff=25.4
    strat 141: total=          42.7  progsum=           0.0  ** MISMATCH diff=42.7
    strat 142: total=          81.5  progsum=           0.0  ** MISMATCH diff=81.5
    strat 143: total=          36.8  progsum=           0.0  ** MISMATCH diff=36.8
    strat 144: total=         133.8  progsum=           0.0  ** MISMATCH diff=133.8
    strat 145: total=          45.2  progsum=           0.0  ** MISMATCH diff=45.2
    strat 146: total=          25.5  progsum=           0.0  ** MISMATCH diff=25.5
    strat 147: total=         126.4  progsum=           0.0  ** MISMATCH diff=126.4
    strat 148: total=          35.6  progsum=           0.0  ** MISMATCH diff=35.6
    strat 149: total=          19.3  progsum=           0.0  ** MISMATCH diff=19.3
    strat 150: total=          46.0  progsum=           0.0  ** MISMATCH diff=46.0
    strat 151: total=          48.7  progsum=           0.0  ** MISMATCH diff=48.7
    strat 152: total=          81.8  progsum=           0.0  ** MISMATCH diff=81.8
    strat 153: total=          95.6  progsum=           0.0  ** MISMATCH diff=95.6
    strat 154: total=          23.5  progsum=           0.0  ** MISMATCH diff=23.5
    strat 155: total=          41.6  progsum=           0.0  ** MISMATCH diff=41.6
    strat 156: total=         105.7  progsum=           0.0  ** MISMATCH diff=105.7
    strat 157: total=          26.9  progsum=           0.0  ** MISMATCH diff=26.9
    strat 158: total=          72.3  progsum=           0.0  ** MISMATCH diff=72.3
    strat 159: total=          32.0  progsum=           0.0  ** MISMATCH diff=32.0
    strat 160: total=          24.2  progsum=           0.0  ** MISMATCH diff=24.2
    strat 161: total=          53.0  progsum=           0.0  ** MISMATCH diff=53.0
    strat 162: total=         111.5  progsum=           0.0  ** MISMATCH diff=111.5
    strat 163: total=          42.0  progsum=           0.0  ** MISMATCH diff=42.0
    strat 164: total=          33.9  progsum=           0.0  ** MISMATCH diff=33.9
    strat 165: total=         103.7  progsum=           0.0  ** MISMATCH diff=103.7
    strat 166: total=          84.8  progsum=           0.0  ** MISMATCH diff=84.8
    strat 167: total=          31.6  progsum=           0.0  ** MISMATCH diff=31.6
    strat 168: total=         359.1  progsum=           0.0  ** MISMATCH diff=359.1
    strat 169: total=          44.7  progsum=           0.0  ** MISMATCH diff=44.7
    strat 170: total=          40.8  progsum=           0.0  ** MISMATCH diff=40.8
    strat 171: total=          30.4  progsum=           0.0  ** MISMATCH diff=30.4
    strat 172: total=          44.3  progsum=           0.0  ** MISMATCH diff=44.3
    strat 173: total=          90.7  progsum=           0.0  ** MISMATCH diff=90.7
    strat 174: total=         117.4  progsum=           0.0  ** MISMATCH diff=117.4
    strat 175: total=         129.1  progsum=           0.0  ** MISMATCH diff=129.1
    strat 176: total=          38.6  progsum=           0.0  ** MISMATCH diff=38.6
    strat 177: total=          95.6  progsum=           0.0  ** MISMATCH diff=95.6
    strat 178: total=          21.4  progsum=           0.0  ** MISMATCH diff=21.4
    strat 179: total=          31.9  progsum=           0.0  ** MISMATCH diff=31.9
    strat 180: total=          37.1  progsum=           0.0  ** MISMATCH diff=37.1
    strat 181: total=          84.7  progsum=           0.0  ** MISMATCH diff=84.7
    strat 182: total=          30.8  progsum=           0.0  ** MISMATCH diff=30.8
    strat 183: total=          31.9  progsum=           0.0  ** MISMATCH diff=31.9
    strat 184: total=          49.1  progsum=           0.0  ** MISMATCH diff=49.1
    strat 185: total=          29.1  progsum=           0.0  ** MISMATCH diff=29.1
    strat 186: total=          44.1  progsum=           0.0  ** MISMATCH diff=44.1
    strat 187: total=         102.2  progsum=           0.0  ** MISMATCH diff=102.2
    strat 188: total=         102.0  progsum=           0.0  ** MISMATCH diff=102.0
    strat 189: total=          39.0  progsum=           0.0  ** MISMATCH diff=39.0
    strat 190: total=          42.6  progsum=           0.0  ** MISMATCH diff=42.6
    strat 191: total=          37.0  progsum=           0.0  ** MISMATCH diff=37.0
    strat 192: total=          55.4  progsum=           0.0  ** MISMATCH diff=55.4
    strat 193: total=          39.9  progsum=           0.0  ** MISMATCH diff=39.9
    strat 194: total=         146.4  progsum=           0.0  ** MISMATCH diff=146.4
    strat 195: total=          18.4  progsum=           0.0  ** MISMATCH diff=18.4
    strat 196: total=          99.2  progsum=           0.0  ** MISMATCH diff=99.2
    strat 197: total=         669.3  progsum=           0.0  ** MISMATCH diff=669.3
    strat 198: total=         124.5  progsum=           0.0  ** MISMATCH diff=124.5
    strat 199: total=          74.2  progsum=           0.0  ** MISMATCH diff=74.2
    strat 200: total=         105.0  progsum=           0.0  ** MISMATCH diff=105.0
    strat 201: total=          42.0  progsum=           0.0  ** MISMATCH diff=42.0
    strat 202: total=          35.4  progsum=           0.0  ** MISMATCH diff=35.4
    strat 203: total=          28.5  progsum=           0.0  ** MISMATCH diff=28.5
    strat 204: total=         113.0  progsum=           0.0  ** MISMATCH diff=113.0
    strat 205: total=          33.2  progsum=           0.0  ** MISMATCH diff=33.2

RECONCILIATION: FAIL - see MISMATCH rows

NATIONAL TOTAL (the denominator every share is computed against)
    FY2024  heads 85,716.5  programmes 64,135.7  gap  25.2%  -> GRAND_TOTAL
    FY2025  heads 97,654.8  programmes 79,038.6  gap  19.1%  -> GRAND_TOTAL
    FY2026  heads 138,500.7  programmes 106,324.6  gap  23.2%  -> GRAND_TOTAL
    FY2027  heads 147,151.4  programmes 0.0  gap 100.0%  -> GRAND_TOTAL
    FY2024  extracted 100.2% of the document's own grand total 85,522.5
    FY2025  extracted 100.0% of the document's own grand total 97,654.8
    FY2026  extracted 100.0% of the document's own grand total 138,500.7
    FY2027  extracted 108.5% of the document's own grand total 135,564.8

READABILITY  0 of 92 programme name(s) unreadable (0%), 0 of 210 head(s) (0%), 0% of the money

HEAD NAMES: 72 row(s) renamed so a head reads the same in every year

Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/bhutan/budget_layer_all_years.xlsx
  sheet 'budget_all_years' : 306 rows  (feeds Prompt 6 / build_final_panel - each intervention matches against EVERY year's programs)
  sheet 'programs_wide'    : 59 programs x 4 year(s) (funding-over-time)
  sheet 'reconciliation'   : 210 rows (audit)
  sheet 'data_quality'     : 285 flagged items (see summary below)

==============================================================================
DATA-QUALITY SUMMARY
==============================================================================
  HIGH: 207   MEDIUM: 61   LOW: 13   INFO: 4

  [HIGH] granularity_mismatch  (1)
      - the years were not extracted to the same depth: FY2024 has 56 programme rows and FY2026 has 10, a factor of 5.6. Each year's totals may still be right, but a programme cannot be followed across years and any funding-over-time figure is comparing different levels of the same budget.

  [HIGH] mixed_budget_views  (2)
      - FY2025: rows came from 2 different tables and together made 110,189.5 against a printed grand total of 97,654.8, so the same money was present twice. Kept 'Table 5.3 Summary of Sector Allocation for FY 2024-25' (97,654.8, the closest to the grand total) and dropped 70 row(s) from the others.
      - FY2026: rows came from 2 different tables and together made 153,367.6 against a printed grand total of 138,500.7, so the same money was present twice. Kept 'Table 5.3 Summary of Sector Allocation for FY 2025-26' (138,500.7, the closest to the grand total) and dropped 14 row(s) from the others.

  [HIGH] reconciliation_mismatch  (204)
      - FY2024 strat 1: programs sum to 24,592.6 but strategy_total is 24,591.2 (gap -1.4) - a program line is likely missing or mis-extracted for this strategy-year.
      - FY2024 strat 3: programs sum to 316.2 but strategy_total is 1,418.6 (gap 1,102.4) - a program line is likely missing or mis-extracted for this strategy-year.
      - FY2024 strat 4: programs sum to 130.7 but strategy_total is 2,647.6 (gap 2,516.9) - a program line is likely missing or mis-extracted for this strategy-year.
      ... and 201 more (see 'data_quality' sheet)

  [MEDIUM] program_missing_in_year  (59)
      - FY2027 strat 1 1.1: program '1.1' (Health) exists in ['2024', '2025', '2026'] but is absent in ['2027'] - check whether it was dropped during extraction or genuinely did not exist that year.
      - FY2027 strat 1 1.2: program '1.2' (Education) exists in ['2024', '2025', '2026'] but is absent in ['2027'] - check whether it was dropped during extraction or genuinely did not exist that year.
      - FY2026,2027 strat 1 1.3: program '1.3' (Project-Tied External (C)) exists in ['2024', '2025'] but is absent in ['2026', '2027'] - check whether it was dropped during extraction or genuinely did not exist that year.
      ... and 56 more (see 'data_quality' sheet)

  [MEDIUM] zero_amount_programme  (2)
      - FY2024 strat 3 3.4: programme carries no money; a strategy matched only to lines like this reads as funded while receiving nothing
      - FY2024 strat 3 3.6: programme carries no money; a strategy matched only to lines like this reads as funded while receiving nothing

  [LOW] large_yoy_swing  (13)
      - FY2024->2025 strat 1 1.3: program '1.3' changed +7498% (0.6 -> 46.5) - verify this is real and not an extraction error.
      - FY2024->2025 strat 1 1.4: program '1.4' changed +52441% (0.8 -> 411.4) - verify this is real and not an extraction error.
      - FY2025->2026 strat 2 2.4: program '2.4' changed +201% (3,871.8 -> 11,665.9) - verify this is real and not an extraction error.
      ... and 10 more (see 'data_quality' sheet)
==============================================================================
DATA QUALITY: REVIEW NEEDED - resolve HIGH items before relying on totals for those strategy-years
==============================================================================
```

### build_final_panel
```
Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/bhutan/FINAL_PANEL.xlsx
  panel               : 41 strategies x 3 years (2024, 2025, 2026)
  match_review        : 83 matches (BOTH names + rationale)
  unmatched_codes     : 0 (codes NOT in that year's budget - REVIEW)
  unfunded_strategies : 18 (strategies with no budget any year)
  funding_by_program  : 48 (per programme x year, amount once - SAFE TO SUM)
  unmapped_programs   : 44 budget programmes with no matched strategy
  risk_panel          : 9 risks | ceiling: PASS
  enrichment          : strategyclean=yes risk_summary=yes
  maturity            : mean=0.607 | financing-weighted=0.861 | {'operational_programme': 11, 'operational_funded': 3, 'partial_operation': 9, 'planned': 11, 'planned_specific': 4, 'aspirational': 3}
  basket/reverse-pass : 33 shared programmes | reverse-pass edges=none (run Prompt 6b + --coverage)
  recall_review       : 4 large programmes matched to only 1 strategy (candidate baskets)
MATURITY: mean=0.607 financing_weighted=0.861
CEILING TEST: PASS - no strategy over-counted in any year
UNMATCHED CODES: 0
QA: PASS - 0 unmatched code(s), ceiling PASS, 0 year warning(s)
```

### build_analytics_html
```
dashboard -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/bhutan/budget_strategy_analytics.html
  years        2024, 2025, 2026
  edges        83
  strategies   41 (18 unfunded)
  size         50 KB
```

### audit_checks
```
AUDIT CHECKS: bhutan 19/19 PASS
  ok   A1   Stored programme sums              210 strategy-year(s) / 0 disagree
  ok   A2   Stored strategy totals             210 strategy-year(s) / 0 disagree
  ok   A3   Programme counted once             48 row(s) / 0 duplicate key(s)
  ok   A4   Ceiling holds                      19 strategy-year(s) / 0 over ceiling
  ok   A6   Panel money matches its edges      123 strategy-year figure(s) / 0 disagree
  ok   A8   Edges cite real programmes         83 accepted edge(s) / 0 dangle
  ok   A9   No strategy dropped                41 strategyclean row(s) / 41 panel row(s)
  ok   A10  Unfunded list is complete          18 zero-funded / 18 listed
  ok   A11  Evidence chain resolves            323 distinct id(s) / 0 dangle
  ok   A12  Maturity summary is derivable      8 metric(s) / 0 disagree
  ok   A14  No duplicate edges                 83 edge(s) / 0 duplicate(s)
  ok   A15  One currency                       1 expected / 1 found
  ok   A16  Components are traceable           584 component(s) / 0 untraceable
  ok   A17  No workbook open in Excel          0 expected / 0 found
  ok   A18  Strategies come from the plan      41 strategy(ies) / 0 with no component
  ok   A19  Funding priority is reproducible   26 distinct (salience, funding) group(s) / 0 split across priorities
  ok   A20  The budget is readable             92 programme(s) / 0 unreadable (0%), carrying 0% of the money
  ok   A21  Ambiguous codes name their head    0 repeated code(s) / 0 edge(s) do not name a head
  ok   A22  Every intervention is traceable to a strategy 323 intervention(s) extracted / 0 uncited (0.0%)
  --   A23  The sector layer stayed out of the panel no sector run for this country
```

### data_issues
```
data issues  Files/outputs/DATA_ISSUES.xlsx
  6 detected across 1 country(ies): 2 high, 3 medium, 1 low
  70 hand-written entr(ies) in 04_Docs_and_Planning/data_issues.json
  HIGH  bhutan    D7       Flag raised while combining the budget years
  HIGH  bhutan    D8       A strategy total its own programmes do not add up to
```
