# Run report - Bangladesh

**🔴 Overall: REVIEW NEEDED**  
Generated 2026-08-26 19:29 by run_pipeline.py

| Stage | Ran | Key QA |
|---|---|---|
| validate_stage_schema (L2) | ok | QA FAIL - FAIL 1/7 (bangladesh_strategyclean.xlsx) |
| validate_source_fidelity (L4) | ok | NOT CONFIGURED [advisory] |
| validate_recall (L4) | ok | NOT CONFIGURED [advisory] |
| validate_refs (L3) | ok | INPUT MISSING (1/1 not on this machine) |
| combine_budget_years | ok | reconcile=FAIL - see MISMATCH rows | data_quality=REVIEW NEEDED - resolve HIGH items before relying on totals for those strategy-years |
| build_final_panel | ok | ceiling=PASS - no strategy over-counted in any year | unmatched_codes=0 |
| build_analytics_html | ok | dashboard built, no summary printed |
| audit_checks | FAILED | QA FAIL - 8/11 PASS (A11 2 dangle, A15 2 found, A16 1 untraceable) [advisory] |
| data_issues | FAILED | 3 detected across 1 country(ies): 2 high, 1 medium, 0 low [advisory] |

## Outputs

- Budget layer: `Files/outputs/bangladesh/budget_layer_all_years.xlsx`
- FINAL panel (deliverable): `Files/outputs/bangladesh/FINAL_PANEL.xlsx`
- Dashboard: `Files/outputs/bangladesh/budget_strategy_analytics.html`
- Audit trail: `Files/outputs/union_dashboard.html`, Audit tab, filtered to this country
- Data oddities: `Files/outputs/DATA_ISSUES.xlsx`

## Full stage logs

### validate_stage_schema (L2)
```
--- bangladesh_budget_2022.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/bangladesh/validation/schema_bangladesh_budget_2022.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- bangladesh_budget_2023.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/bangladesh/validation/schema_bangladesh_budget_2023.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- bangladesh_budget_2024.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/bangladesh/validation/schema_bangladesh_budget_2024.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- bangladesh_budget_2025.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/bangladesh/validation/schema_bangladesh_budget_2025.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- bangladesh_budget_2026.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/bangladesh/validation/schema_bangladesh_budget_2026.xlsx

  RESULT: PASS - 1 file(s) match the schema their prompt promised.

--- bangladesh_strategyclean.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/bangladesh/validation/schema_bangladesh_strategyclean.xlsx

  RESULT: FAIL - 5 contract violation(s) across 1 file(s).
  The stage output is not accepted; re-run the stage or fix the prompt.

--- bangladesh_risk_summary.xlsx
  report -> /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/bangladesh/validation/schema_bangladesh_risk_summary.xlsx

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
--- bangladesh references
SKIPPED: input not on this machine: Files/outputs/bangladesh/budget_layer_all_years.xlsx
```

### combine_budget_years
```
==============================================================================
COMBINED BUDGET LAYER  -  years: 2022, 2023, 2024, 2025, 2026  (5 file(s))
==============================================================================

RECONCILIATION (per year: sum of program rows vs strategy_total)

  FY2022   (national total = 603,681.0)
    strat 1: total=          30.0  progsum=           0.0  ** MISMATCH diff=30.0
    strat 2: total=         336.0  progsum=           0.0  ** MISMATCH diff=336.0
    strat 3: total=       3,907.0  progsum=           0.0  ** MISMATCH diff=3,907.0
    strat 4: total=         239.0  progsum=           0.0  ** MISMATCH diff=239.0
    strat 5: total=         225.0  progsum=           0.0  ** MISMATCH diff=225.0
    strat 6: total=       1,729.0  progsum=           0.0  ** MISMATCH diff=1,729.0
    strat 7: total=       3,758.0  progsum=           0.0  ** MISMATCH diff=3,758.0
    strat 8: total=         115.0  progsum=           0.0  ** MISMATCH diff=115.0
    strat 9: total=     157,642.0  progsum=           0.0  ** MISMATCH diff=157,642.0
    strat 10: total=         283.0  progsum=           0.0  ** MISMATCH diff=283.0
    strat 11: total=       3,124.0  progsum=           0.0  ** MISMATCH diff=3,124.0
    strat 12: total=       2,559.0  progsum=           0.0  ** MISMATCH diff=2,559.0
    strat 13: total=       6,981.0  progsum=           0.0  ** MISMATCH diff=6,981.0
    strat 14: total=       1,133.0  progsum=           0.0  ** MISMATCH diff=1,133.0
    strat 15: total=         257.0  progsum=           0.0  ** MISMATCH diff=257.0
    strat 16: total=       1,673.0  progsum=           0.0  ** MISMATCH diff=1,673.0
    strat 17: total=         683.0  progsum=           0.0  ** MISMATCH diff=683.0
    strat 18: total=       1,656.0  progsum=           0.0  ** MISMATCH diff=1,656.0
    strat 19: total=      37,691.0  progsum=           0.0  ** MISMATCH diff=37,691.0
    strat 20: total=          44.0  progsum=           0.0  ** MISMATCH diff=44.0
    strat 21: total=       1,815.0  progsum=           0.0  ** MISMATCH diff=1,815.0
    strat 22: total=      23,080.0  progsum=           0.0  ** MISMATCH diff=23,080.0
    strat 23: total=          36.0  progsum=           0.0  ** MISMATCH diff=36.0
    strat 24: total=      26,311.0  progsum=           0.0  ** MISMATCH diff=26,311.0
    strat 25: total=      36,486.0  progsum=           0.0  ** MISMATCH diff=36,486.0
    strat 26: total=      21,204.0  progsum=           0.0  ** MISMATCH diff=21,204.0
    strat 27: total=      25,914.0  progsum=           0.0  ** MISMATCH diff=25,914.0
    strat 28: total=       1,721.0  progsum=           0.0  ** MISMATCH diff=1,721.0
    strat 29: total=       9,124.0  progsum=           0.0  ** MISMATCH diff=9,124.0
    strat 30: total=       4,191.0  progsum=           0.0  ** MISMATCH diff=4,191.0
    strat 31: total=         365.0  progsum=           0.0  ** MISMATCH diff=365.0
    strat 32: total=       6,345.0  progsum=           0.0  ** MISMATCH diff=6,345.0
    strat 33: total=       1,008.0  progsum=           0.0  ** MISMATCH diff=1,008.0
    strat 34: total=         587.0  progsum=           0.0  ** MISMATCH diff=587.0
    strat 35: total=       2,240.0  progsum=           0.0  ** MISMATCH diff=2,240.0
    strat 36: total=       1,115.0  progsum=           0.0  ** MISMATCH diff=1,115.0
    strat 37: total=      39,219.0  progsum=           0.0  ** MISMATCH diff=39,219.0
    strat 38: total=       1,791.0  progsum=           0.0  ** MISMATCH diff=1,791.0
    strat 39: total=       1,585.0  progsum=           0.0  ** MISMATCH diff=1,585.0
    strat 40: total=         702.0  progsum=           0.0  ** MISMATCH diff=702.0
    strat 41: total=         692.0  progsum=           0.0  ** MISMATCH diff=692.0
    strat 42: total=       2,086.0  progsum=           0.0  ** MISMATCH diff=2,086.0
    strat 43: total=      16,201.0  progsum=           0.0  ** MISMATCH diff=16,201.0
    strat 44: total=       3,437.0  progsum=           0.0  ** MISMATCH diff=3,437.0
    strat 45: total=       1,221.0  progsum=           0.0  ** MISMATCH diff=1,221.0
    strat 46: total=       2,225.0  progsum=           0.0  ** MISMATCH diff=2,225.0
    strat 47: total=       8,827.0  progsum=           0.0  ** MISMATCH diff=8,827.0
    strat 48: total=       5,310.0  progsum=           0.0  ** MISMATCH diff=5,310.0
    strat 49: total=       9,951.0  progsum=           0.0  ** MISMATCH diff=9,951.0
    strat 50: total=      32,942.0  progsum=           0.0  ** MISMATCH diff=32,942.0
    strat 51: total=      17,486.0  progsum=           0.0  ** MISMATCH diff=17,486.0
    strat 52: total=       5,137.0  progsum=           0.0  ** MISMATCH diff=5,137.0
    strat 53: total=       4,032.0  progsum=           0.0  ** MISMATCH diff=4,032.0
    strat 54: total=       2,549.0  progsum=           0.0  ** MISMATCH diff=2,549.0
    strat 55: total=       1,182.0  progsum=           0.0  ** MISMATCH diff=1,182.0
    strat 56: total=      25,398.0  progsum=           0.0  ** MISMATCH diff=25,398.0
    strat 57: total=       6,343.0  progsum=           0.0  ** MISMATCH diff=6,343.0
    strat 58: total=         159.0  progsum=           0.0  ** MISMATCH diff=159.0
    strat 59: total=       9,820.0  progsum=           0.0  ** MISMATCH diff=9,820.0
    strat 60: total=       9,154.0  progsum=           0.0  ** MISMATCH diff=9,154.0
    strat 61: total=       3,808.0  progsum=           0.0  ** MISMATCH diff=3,808.0
    strat 62: total=       6,817.0  progsum=           0.0  ** MISMATCH diff=6,817.0

  FY2023   (national total = 678,064.0)
    strat 1: total=          31.0  progsum=           0.0  ** MISMATCH diff=31.0
    strat 2: total=         341.0  progsum=           0.0  ** MISMATCH diff=341.0
    strat 3: total=       5,775.0  progsum=           0.0  ** MISMATCH diff=5,775.0
    strat 4: total=         137.0  progsum=           0.0  ** MISMATCH diff=137.0
    strat 5: total=         230.0  progsum=           0.0  ** MISMATCH diff=230.0
    strat 6: total=       1,539.0  progsum=           0.0  ** MISMATCH diff=1,539.0
    strat 7: total=       4,074.0  progsum=           0.0  ** MISMATCH diff=4,074.0
    strat 8: total=         123.0  progsum=           0.0  ** MISMATCH diff=123.0
    strat 9: total=     190,713.0  progsum=           0.0  ** MISMATCH diff=190,713.0
    strat 10: total=         291.0  progsum=           0.0  ** MISMATCH diff=291.0
    strat 11: total=       3,478.0  progsum=           0.0  ** MISMATCH diff=3,478.0
    strat 12: total=       2,852.0  progsum=           0.0  ** MISMATCH diff=2,852.0
    strat 13: total=       8,093.0  progsum=           0.0  ** MISMATCH diff=8,093.0
    strat 14: total=       1,364.0  progsum=           0.0  ** MISMATCH diff=1,364.0
    strat 15: total=         274.0  progsum=           0.0  ** MISMATCH diff=274.0
    strat 16: total=         410.0  progsum=           0.0  ** MISMATCH diff=410.0
    strat 17: total=         545.0  progsum=           0.0  ** MISMATCH diff=545.0
    strat 18: total=       1,651.0  progsum=           0.0  ** MISMATCH diff=1,651.0
    strat 19: total=      40,360.0  progsum=           0.0  ** MISMATCH diff=40,360.0
    strat 20: total=          45.0  progsum=           0.0  ** MISMATCH diff=45.0
    strat 21: total=       1,924.0  progsum=           0.0  ** MISMATCH diff=1,924.0
    strat 22: total=      24,594.0  progsum=           0.0  ** MISMATCH diff=24,594.0
    strat 23: total=          40.0  progsum=           0.0  ** MISMATCH diff=40.0
    strat 24: total=      31,759.0  progsum=           0.0  ** MISMATCH diff=31,759.0
    strat 25: total=      39,961.0  progsum=           0.0  ** MISMATCH diff=39,961.0
    strat 26: total=      16,614.0  progsum=           0.0  ** MISMATCH diff=16,614.0
    strat 27: total=      29,282.0  progsum=           0.0  ** MISMATCH diff=29,282.0
    strat 28: total=       1,916.0  progsum=           0.0  ** MISMATCH diff=1,916.0
    strat 29: total=      10,198.0  progsum=           0.0  ** MISMATCH diff=10,198.0
    strat 30: total=       4,290.0  progsum=           0.0  ** MISMATCH diff=4,290.0
    strat 31: total=         357.0  progsum=           0.0  ** MISMATCH diff=357.0
    strat 32: total=       6,821.0  progsum=           0.0  ** MISMATCH diff=6,821.0
    strat 33: total=       1,099.0  progsum=           0.0  ** MISMATCH diff=1,099.0
    strat 34: total=         637.0  progsum=           0.0  ** MISMATCH diff=637.0
    strat 35: total=       2,353.0  progsum=           0.0  ** MISMATCH diff=2,353.0
    strat 36: total=       1,275.0  progsum=           0.0  ** MISMATCH diff=1,275.0
    strat 37: total=      41,707.0  progsum=           0.0  ** MISMATCH diff=41,707.0
    strat 38: total=       1,645.0  progsum=           0.0  ** MISMATCH diff=1,645.0
    strat 39: total=       1,521.0  progsum=           0.0  ** MISMATCH diff=1,521.0
    strat 40: total=         990.0  progsum=           0.0  ** MISMATCH diff=990.0
    strat 41: total=         628.0  progsum=           0.0  ** MISMATCH diff=628.0
    strat 42: total=       1,870.0  progsum=           0.0  ** MISMATCH diff=1,870.0
    strat 43: total=      24,224.0  progsum=           0.0  ** MISMATCH diff=24,224.0
    strat 44: total=       3,808.0  progsum=           0.0  ** MISMATCH diff=3,808.0
    strat 45: total=       1,501.0  progsum=           0.0  ** MISMATCH diff=1,501.0
    strat 46: total=       2,381.0  progsum=           0.0  ** MISMATCH diff=2,381.0
    strat 47: total=      10,196.0  progsum=           0.0  ** MISMATCH diff=10,196.0
    strat 48: total=       6,213.0  progsum=           0.0  ** MISMATCH diff=6,213.0
    strat 49: total=      10,229.0  progsum=           0.0  ** MISMATCH diff=10,229.0
    strat 50: total=      36,648.0  progsum=           0.0  ** MISMATCH diff=36,648.0
    strat 51: total=      18,852.0  progsum=           0.0  ** MISMATCH diff=18,852.0
    strat 52: total=       7,224.0  progsum=           0.0  ** MISMATCH diff=7,224.0
    strat 53: total=       7,004.0  progsum=           0.0  ** MISMATCH diff=7,004.0
    strat 54: total=       2,487.0  progsum=           0.0  ** MISMATCH diff=2,487.0
    strat 55: total=       1,338.0  progsum=           0.0  ** MISMATCH diff=1,338.0
    strat 56: total=      24,196.0  progsum=           0.0  ** MISMATCH diff=24,196.0
    strat 57: total=       6,984.0  progsum=           0.0  ** MISMATCH diff=6,984.0
    strat 58: total=         178.0  progsum=           0.0  ** MISMATCH diff=178.0
    strat 59: total=       9,297.0  progsum=           0.0  ** MISMATCH diff=9,297.0
    strat 60: total=       9,728.0  progsum=           0.0  ** MISMATCH diff=9,728.0
    strat 61: total=       4,187.0  progsum=           0.0  ** MISMATCH diff=4,187.0
    strat 62: total=       7,582.0  progsum=           0.0  ** MISMATCH diff=7,582.0

  FY2024   (national total = 511,500.0)
    strat 1: total=      42,837.0  progsum=           0.0  ** MISMATCH diff=42,837.0
    strat 2: total=      34,722.0  progsum=           0.0  ** MISMATCH diff=34,722.0
    strat 3: total=      29,430.0  progsum=           0.0  ** MISMATCH diff=29,430.0
    strat 4: total=      68,785.0  progsum=           0.0  ** MISMATCH diff=68,785.0
    strat 5: total=       6,016.0  progsum=           0.0  ** MISMATCH diff=6,016.0
    strat 6: total=      10,118.0  progsum=           0.0  ** MISMATCH diff=10,118.0
    strat 7: total=      25,118.0  progsum=           0.0  ** MISMATCH diff=25,118.0
    strat 8: total=      10,244.0  progsum=           0.0  ** MISMATCH diff=10,244.0
    strat 9: total=      46,703.0  progsum=           0.0  ** MISMATCH diff=46,703.0
    strat 10: total=      10,976.0  progsum=           0.0  ** MISMATCH diff=10,976.0
    strat 11: total=      39,710.0  progsum=           0.0  ** MISMATCH diff=39,710.0
    strat 12: total=      19,010.0  progsum=           0.0  ** MISMATCH diff=19,010.0
    strat 13: total=       9,073.0  progsum=           0.0  ** MISMATCH diff=9,073.0
    strat 14: total=      17,398.0  progsum=           0.0  ** MISMATCH diff=17,398.0
    strat 15: total=      11,057.0  progsum=           0.0  ** MISMATCH diff=11,057.0
    strat 16: total=     130,303.0  progsum=           0.0  ** MISMATCH diff=130,303.0

  FY2025   (national total = 797,000.0)
    strat 1: total=          33.0  progsum=           0.0  ** MISMATCH diff=33.0
    strat 2: total=         347.0  progsum=           0.0  ** MISMATCH diff=347.0
    strat 3: total=       4,600.0  progsum=           0.0  ** MISMATCH diff=4,600.0
    strat 4: total=         122.0  progsum=           0.0  ** MISMATCH diff=122.0
    strat 5: total=         248.0  progsum=           0.0  ** MISMATCH diff=248.0
    strat 6: total=       1,230.0  progsum=           0.0  ** MISMATCH diff=1,230.0
    strat 7: total=       5,377.0  progsum=           0.0  ** MISMATCH diff=5,377.0
    strat 8: total=         166.0  progsum=           0.0  ** MISMATCH diff=166.0
    strat 9: total=     248,205.0  progsum=           0.0  ** MISMATCH diff=248,205.0
    strat 10: total=         290.0  progsum=           0.0  ** MISMATCH diff=290.0
    strat 11: total=       3,217.0  progsum=           0.0  ** MISMATCH diff=3,217.0
    strat 12: total=       3,418.0  progsum=           0.0  ** MISMATCH diff=3,418.0
    strat 13: total=      21,308.0  progsum=           0.0  ** MISMATCH diff=21,308.0
    strat 14: total=       6,492.0  progsum=           0.0  ** MISMATCH diff=6,492.0
    strat 15: total=         195.0  progsum=           0.0  ** MISMATCH diff=195.0
    strat 16: total=         662.0  progsum=           0.0  ** MISMATCH diff=662.0
    strat 17: total=         932.0  progsum=           0.0  ** MISMATCH diff=932.0
    strat 18: total=       1,726.0  progsum=           0.0  ** MISMATCH diff=1,726.0
    strat 19: total=      42,315.0  progsum=           0.0  ** MISMATCH diff=42,315.0
    strat 20: total=          46.0  progsum=           0.0  ** MISMATCH diff=46.0
    strat 21: total=       2,022.0  progsum=           0.0  ** MISMATCH diff=2,022.0
    strat 22: total=      26,877.0  progsum=           0.0  ** MISMATCH diff=26,877.0
    strat 23: total=          45.0  progsum=           0.0  ** MISMATCH diff=45.0
    strat 24: total=      38,819.0  progsum=           0.0  ** MISMATCH diff=38,819.0
    strat 25: total=      44,108.0  progsum=           0.0  ** MISMATCH diff=44,108.0
    strat 26: total=      13,573.0  progsum=           0.0  ** MISMATCH diff=13,573.0
    strat 27: total=      30,125.0  progsum=           0.0  ** MISMATCH diff=30,125.0
    strat 28: total=       2,872.0  progsum=           0.0  ** MISMATCH diff=2,872.0
    strat 29: total=      12,869.0  progsum=           0.0  ** MISMATCH diff=12,869.0
    strat 30: total=       5,222.0  progsum=           0.0  ** MISMATCH diff=5,222.0
    strat 31: total=         463.0  progsum=           0.0  ** MISMATCH diff=463.0
    strat 32: total=       6,929.0  progsum=           0.0  ** MISMATCH diff=6,929.0
    strat 33: total=       1,108.0  progsum=           0.0  ** MISMATCH diff=1,108.0
    strat 34: total=         779.0  progsum=           0.0  ** MISMATCH diff=779.0
    strat 35: total=       2,602.0  progsum=           0.0  ** MISMATCH diff=2,602.0
    strat 36: total=       2,212.0  progsum=           0.0  ** MISMATCH diff=2,212.0
    strat 37: total=      45,206.0  progsum=           0.0  ** MISMATCH diff=45,206.0
    strat 38: total=       1,346.0  progsum=           0.0  ** MISMATCH diff=1,346.0
    strat 39: total=       2,510.0  progsum=           0.0  ** MISMATCH diff=2,510.0
    strat 40: total=       1,217.0  progsum=           0.0  ** MISMATCH diff=1,217.0
    strat 41: total=         574.0  progsum=           0.0  ** MISMATCH diff=574.0
    strat 42: total=       1,087.0  progsum=           0.0  ** MISMATCH diff=1,087.0
    strat 43: total=      27,214.0  progsum=           0.0  ** MISMATCH diff=27,214.0
    strat 44: total=       4,288.0  progsum=           0.0  ** MISMATCH diff=4,288.0
    strat 45: total=       2,130.0  progsum=           0.0  ** MISMATCH diff=2,130.0
    strat 46: total=       2,505.0  progsum=           0.0  ** MISMATCH diff=2,505.0
    strat 47: total=      11,194.0  progsum=           0.0  ** MISMATCH diff=11,194.0
    strat 48: total=       6,757.0  progsum=           0.0  ** MISMATCH diff=6,757.0
    strat 49: total=      11,003.0  progsum=           0.0  ** MISMATCH diff=11,003.0
    strat 50: total=      38,143.0  progsum=           0.0  ** MISMATCH diff=38,143.0
    strat 51: total=      18,072.0  progsum=           0.0  ** MISMATCH diff=18,072.0
    strat 52: total=      11,270.0  progsum=           0.0  ** MISMATCH diff=11,270.0
    strat 53: total=       5,695.0  progsum=           0.0  ** MISMATCH diff=5,695.0
    strat 54: total=       2,420.0  progsum=           0.0  ** MISMATCH diff=2,420.0
    strat 55: total=       1,400.0  progsum=           0.0  ** MISMATCH diff=1,400.0
    strat 56: total=      29,230.0  progsum=           0.0  ** MISMATCH diff=29,230.0
    strat 57: total=       7,474.0  progsum=           0.0  ** MISMATCH diff=7,474.0
    strat 58: total=         191.0  progsum=           0.0  ** MISMATCH diff=191.0
    strat 59: total=       7,318.0  progsum=           0.0  ** MISMATCH diff=7,318.0
    strat 60: total=      11,783.0  progsum=           0.0  ** MISMATCH diff=11,783.0
    strat 61: total=       4,137.0  progsum=           0.0  ** MISMATCH diff=4,137.0
    strat 62: total=      11,282.0  progsum=           0.0  ** MISMATCH diff=11,282.0

  FY2026   (national total = 520,444.0)
    strat 1: total=      47,563.0  progsum=           0.0  ** MISMATCH diff=47,563.0
    strat 2: total=      35,403.0  progsum=           0.0  ** MISMATCH diff=35,403.0
    strat 3: total=      31,022.0  progsum=           0.0  ** MISMATCH diff=31,022.0
    strat 4: total=      74,957.0  progsum=           0.0  ** MISMATCH diff=74,957.0
    strat 5: total=       8,322.0  progsum=           0.0  ** MISMATCH diff=8,322.0
    strat 6: total=      10,362.0  progsum=           0.0  ** MISMATCH diff=10,362.0
    strat 7: total=      27,224.0  progsum=           0.0  ** MISMATCH diff=27,224.0
    strat 8: total=      11,204.0  progsum=           0.0  ** MISMATCH diff=11,204.0
    strat 9: total=      42,433.0  progsum=           0.0  ** MISMATCH diff=42,433.0
    strat 10: total=      10,302.0  progsum=           0.0  ** MISMATCH diff=10,302.0
    strat 11: total=      38,496.0  progsum=           0.0  ** MISMATCH diff=38,496.0
    strat 12: total=      11,944.0  progsum=           0.0  ** MISMATCH diff=11,944.0
    strat 13: total=       6,022.0  progsum=           0.0  ** MISMATCH diff=6,022.0
    strat 14: total=      12,734.0  progsum=           0.0  ** MISMATCH diff=12,734.0
    strat 15: total=       7,481.0  progsum=           0.0  ** MISMATCH diff=7,481.0
    strat 16: total=     144,975.0  progsum=           0.0  ** MISMATCH diff=144,975.0

RECONCILIATION: FAIL - see MISMATCH rows

NATIONAL TOTAL (the denominator every share is computed against)
    FY2022  heads 603,681.0  programmes 0.0  gap 100.0%  -> GRAND_TOTAL
    FY2023  heads 678,064.0  programmes 0.0  gap 100.0%  -> GRAND_TOTAL
    FY2024  heads 511,500.0  programmes 0.0  gap 100.0%  -> GRAND_TOTAL
    FY2025  heads 797,000.0  programmes 0.0  gap 100.0%  -> GRAND_TOTAL
    FY2026  heads 520,444.0  programmes 0.0  gap 100.0%  -> GRAND_TOTAL
    FY2022  extracted 100.0% of the document's own grand total 603,681.0
    FY2023  extracted 100.0% of the document's own grand total 678,064.0
    FY2024  extracted 67.1% of the document's own grand total 761,785.0
    FY2025  extracted 100.0% of the document's own grand total 797,000.0
    FY2026  extracted 65.9% of the document's own grand total 790,000.0

READABILITY  0 of 0 programme name(s) unreadable (0%), 0 of 218 head(s) (0%), 0% of the money

HEAD NAMES: 36 row(s) renamed so a head reads the same in every year

Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/bangladesh/budget_layer_all_years.xlsx
  sheet 'budget_all_years' : 223 rows  (feeds Prompt 6 / build_final_panel - each intervention matches against EVERY year's programs)
  sheet 'programs_wide'    : 0 programs x 5 year(s) (funding-over-time)
  sheet 'reconciliation'   : 218 rows (audit)
  sheet 'data_quality'     : 225 flagged items (see summary below)

==============================================================================
DATA-QUALITY SUMMARY
==============================================================================
  HIGH: 220   MEDIUM: 0   LOW: 0   INFO: 5

  [HIGH] partial_budget  (2)
      - FY2024: the heads extracted sum to 511,500.0 but the document's own grand total is 761,785.0, so only 67% of the budget is here. A section was taken rather than the budget, and every share computed for FY2024 is a share of that section. Re-run stage 5 against the full summary of expenditure.
      - FY2026: the heads extracted sum to 520,444.0 but the document's own grand total is 790,000.0, so only 66% of the budget is here. A section was taken rather than the budget, and every share computed for FY2026 is a share of that section. Re-run stage 5 against the full summary of expenditure.

  [HIGH] reconciliation_mismatch  (218)
      - FY2022 strat 1: programs sum to 0.0 but strategy_total is 30.0 (gap 30.0) - a program line is likely missing or mis-extracted for this strategy-year.
      - FY2022 strat 2: programs sum to 0.0 but strategy_total is 336.0 (gap 336.0) - a program line is likely missing or mis-extracted for this strategy-year.
      - FY2022 strat 3: programs sum to 0.0 but strategy_total is 3,907.0 (gap 3,907.0) - a program line is likely missing or mis-extracted for this strategy-year.
      ... and 215 more (see 'data_quality' sheet)
==============================================================================
DATA QUALITY: REVIEW NEEDED - resolve HIGH items before relying on totals for those strategy-years
==============================================================================
```

### build_final_panel
```
PLAN ONLY: the budget layer carries 218 strategy total(s) and no programme line, so the mapping stage had nothing to match. The panel carries the plan's 438 strategies with no money against them, which is what the documents held for this country support.

Wrote /Users/sebastianpasha/Developer/Environment_UNDP/PV2/Files/outputs/bangladesh/FINAL_PANEL.xlsx
  panel               : 438 strategies x 0 years ()
  match_review        : 0 matches (BOTH names + rationale)
  unmatched_codes     : 0 (codes NOT in that year's budget - REVIEW)
  unfunded_strategies : 438 (strategies with no budget any year)
  funding_by_program  : 0 (per programme x year, amount once - SAFE TO SUM)
  unmapped_programs   : 0 budget programmes with no matched strategy
  risk_panel          : 10 risks | ceiling: PASS
  enrichment          : strategyclean=yes risk_summary=yes
  maturity            : mean=0.311 | financing-weighted=0.0 | {'aspirational': 148, 'planned_specific': 51, 'planned': 239}
  basket/reverse-pass : 0 shared programmes | reverse-pass edges=none (run Prompt 6b + --coverage)
  recall_review       : 0 large programmes matched to only 1 strategy (candidate baskets)
MATURITY: mean=0.311 financing_weighted=0.0
CEILING TEST: PASS - no strategy over-counted in any year
UNMATCHED CODES: 0
QA: PASS - 0 unmatched code(s), ceiling PASS, 0 year warning(s)
```

### build_analytics_html
```
PLAN ONLY: no programme line in this country's budget layer, so there is no money for this page to show. The plan's strategies are in FINAL_PANEL.xlsx and on the union dashboard, each with no funding against it.
```

### audit_checks
```
AUDIT CHECKS: bangladesh 8/11 PASS (A11 2 dangle, A15 2 found, A16 1 untraceable)
  ok   A1   Stored programme sums              218 strategy-year(s) / 0 disagree
  ok   A2   Stored strategy totals             218 strategy-year(s) / 0 disagree
  --   A3   Programme counted once             sheet absent
  --   A4   Ceiling holds                      sheet absent
  --   A6   Panel money matches its edges      sheets absent
  --   A8   Edges cite real programmes         sheets absent
  ok   A9   No strategy dropped                438 strategyclean row(s) / 438 panel row(s)
  ok   A10  Unfunded list is complete          438 zero-funded / 438 listed
  FAIL A11  Evidence chain resolves            2963 distinct id(s) / 2 dangle
            chunk id 1499 has no stage-3 row
            chunk id 1500 has no stage-3 row
  ok   A12  Maturity summary is derivable      8 metric(s) / 0 disagree
  --   A14  No duplicate edges                 sheet absent
  FAIL A15  One currency                       1 expected / 2 found
            Crore Tk.
            crore Taka
  FAIL A16  Components are traceable           4711 component(s) / 1 untraceable
            Urban governance, municipal financ <- Local Government Institutional Strengthening
  ok   A17  No workbook open in Excel          0 expected / 0 found
  ok   A18  Strategies come from the plan      438 strategy(ies) / 0 with no component
  --   A19  Funding priority is reproducible   no panel rows or no budget columns
  --   A20  The budget is readable             no programme rows
  --   A21  Ambiguous codes name their head    no budget rows or no accepted edges
  ok   A22  Every intervention is traceable to a strategy 2962 intervention(s) extracted / 1 uncited (0.0%)
            1613
  --   A23  The sector layer stayed out of the panel no sector run for this country
```

### data_issues
```
data issues  Files/outputs/DATA_ISSUES.xlsx
  3 detected across 1 country(ies): 2 high, 1 medium, 0 low
  72 hand-written entr(ies) in 04_Docs_and_Planning/data_issues.json
  HIGH  bangladesh D7       Flag raised while combining the budget years
  HIGH  bangladesh D8       A strategy total its own programmes do not add up to
```
