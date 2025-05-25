# BYD-PID-list
An attempted listing of all PIDs for BYD cars


## Known, working PIDs and their expressions

|Model|Year(s)|Name|Description|PID #|Class|Unit|Min|Max|Expression|Init|
|-|-|-|-|-|-|-|-|-|-|-|
|Atto 3|2025|SoC|State of Charge|221FFC1|Battery|%|0|100|((B5*256)+B4)/100||
|Atto 3|2025|BATT_TEMP|Battery Temperature|220032|Temperature|°C|-40|80|B4-40||



# References / sources:
(WiCAN BYD Atto 3 vehicle profile)[https://github.com/meatpiHQ/wican-fw/blob/main/vehicle_profiles/byd/atto3.json]
