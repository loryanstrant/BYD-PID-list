# BYD-PID-list
An attempted listing of all PIDs for BYD cars


## Known, working PIDs and their expressions

|Model|Year(s)|Name|Description|PID #|Class|Unit|Min|Max|Expression|Init|
|-|-|-|-|-|-|-|-|-|-|-|
|Atto 3|2025|SoC|State of Charge|221FFC1|Battery|%|0|100|((B5*256)+B4)/100||
|Atto 3|2025|BATT_TEMP|Battery Temperature|220032|Temperature|°C|-40|80|B4-40||
|Dolphin|2023–2025|SoC|State of Charge|221FFC|Battery|%|-5|105|(A + B*256)/100|Yes|
|Dolphin|2023–2025|VOLTAGE|Battery Voltage|220008|Voltage|V|200|1000|A + B*256|Yes|
|Dolphin|2023–2025|CURRENT|Battery Current|220009|Current|A|-600|1000|((A + B*256) - 5000) / 10|Yes|
|Dolphin|2023–2025|BATT_TEMP|Battery Temperature|220032|Temperature|°C|-40|80|A - 40|Yes|


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


## Wanted PIDs
- Charging state
- Cabin temperature
- Odometer

<br><br>


## References / sources:
[WiCAN BYD Atto 3 vehicle profile](https://github.com/meatpiHQ/wican-fw/blob/main/vehicle_profiles/byd/atto3.json)

[Dolphin comes from ABRP via HA community](https://community.home-assistant.io/t/source-for-byd-atto-3-battery-state-of-charge/603428/46?u=delorean)
