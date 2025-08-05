# BYD-PID-list
An attempted listing of all PIDs for BYD cars


## Known, working PIDs and their expressions

|Model|Year(s)|Name|Description|PID #|Class|Unit|Min|Max|Expression|Init|Remarks
|-|-|-|-|-|-|-|-|-|-|-|-|
|Atto 3|2025|SoC|State of Charge|221FFC1|Battery|%|0|100|((B5*256)+B4)/100|||
|Atto 3|2025|BATT_TEMP|Battery Temperature|220032|Temperature|°C|-40|80|B4-40|||
|Dolphin|2023–2025|SoC|State of Charge|221FFC1|Battery|%|-5|105|(B4 + B5*256)/100|Yes|confirmed working|
|Dolphin|2023–2025|VOLTAGE|Battery Voltage|220008|Voltage|V|200|1000|B4 + B5*256 ? need to confirm|Yes|needs confirmation|
|Dolphin|2023–2025|CURRENT|Battery Current|220009|Current|A|-600|1000|((A + B*256) - 5000) / 10 |Yes|currently not getting the values to lign up with the car scanner app|
|Dolphin|2023–2025|BATT_TEMP|Battery Temperature|220032|Temperature|°C|-40|80|B4 - 40|Yes|confirmed working|
|Dolphin|2023–2025|CHARGE_TIMES|Charge Times|22000B1| - | - |0|?|(B4 + B5*256)0|?|confirmed working|

<br><br>

## Initialisation strings
### BYD Dolphoin
"byd:dolphin:23:45": {
  "init": [
    "ATZ", "ATE0", "ATD", "ATD0", "ATE0", "ATH1", "ATSP6",
    "ATE0", "ATH1", "ATM0", "ATS0", "ATAT1", "ATAL", "STCSEGT1", "ATST96", "ATSH7E7"
  ],
  "protocol": 6
}

<br><br>

## Comments
Everything i saw so far shows that Dolphin and Atto3 use the same codes. Possible also Seal

## Wanted PIDs
- Charging state
- Cabin temperature
- Odometer

<br><br>


## References / sources:
[WiCAN BYD Atto 3 vehicle profile](https://github.com/meatpiHQ/wican-fw/blob/main/vehicle_profiles/byd/atto3.json)

[Dolphin comes from ABRP via HA community](https://community.home-assistant.io/t/source-for-byd-atto-3-battery-state-of-charge/603428/46?u=delorean)
