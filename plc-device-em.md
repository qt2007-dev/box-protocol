## PLC device energymeter birth example
> spBv1.0/plc/DBIRTH/abba2020/deba0009 

```json
{
"timestamp": 1486144502122,
"seq": 0,
"metrics": [
    { "name": "control/reboot",                 "dataType": 11/* Boolean */, "boolean_value": false,             "metadata":{"description":"[W]Sofrware reboot device, send 'true' for reboot"} },
    { "name": "control/rebirth",                "dataType": 11/* Boolean */, "boolean_value": false,             "metadata":{"description":"[W]Rebirth device, send 'true' for receive dbirth message again"} },
    { "name": "control/firmware/new",           "dataType": 17/* Bytes */,   "bytes_value":"", "is_null": true,  "metadata":{"description":"[W]Receive new device firmware, firmware send in Base64 format, in birth always null"} },
    { "name": "control/metrics/save",           "dataType": 11/* Boolean */, "boolean_value": true,              "metadata":{"description":"[RWP]Save metrics states after reboot, send 'true' for enable"} },
    { "name": "control/metrics/metadata",       "dataType": 11/* Boolean */, "boolean_value": true,              "metadata":{"description":"[RWP]Show metrics metadata in birth, send 'true' for enable"} },
    { "name": "control/group",                  "dataType": 12/* String */,  "string_value": "em",               "metadata":{"description":"[RWP]Global group for device, can be used instead id in topics and scenarios"} },

    { "name": "info/hardware/vendor",           "dataType": 12/* String */,  "string_value": "QuintTech" ,       "metadata":{"description":"[R]Vendor name, hardcoded by vendor"} },
    { "name": "info/hardware/model",            "dataType": 12/* String */,  "string_value": "stm32g474ce",      "metadata":{"description":"[R]Mcu model, hardcoded by vendor"} },
    { "name": "info/firmware/version",          "dataType": 12/* String */,  "string_value": "0.1.220527.84852", "metadata":{"description":"[R]Firmware version, MAJOR.MINOR.YYMMDD.SSSSS"} },
    { "name": "info/type",                      "dataType": 12/* String */,  "string_value": "Energymeter",      "metadata":{"description":"[R]Device type, hardcoded by vendor"} },
    { "name": "info/id",                        "dataType": 12/* String */,  "string_value": "deba0009",         "metadata":{"description":"[R]Short id calculated by a hash from mcu uid"} },
    { "name": "info/error",                     "dataType": 12/* String */,  "string_value": "",                 "metadata":{"description":"[R]Last error message"} },

    { "name": "sensors/temperature",            "dataType": 1/* Int8 */,     "int_value": 22,                    "metadata":{"description":"[R]Temperature sensor in mcu, value in Celsius"} },

    { "name": "phase/a/voltage",                "dataType": 7/* Int32 */,    "int_value": 5,                     "metadata":{"description":"[R]Phase A rms voltage, value in mV"} },
    { "name": "phase/a/current",                "dataType": 7/* Int32 */,    "int_value": 5,                     "metadata":{"description":"[R]Phase A rms current, value in mA"} },
    { "name": "phase/a/power/active",           "dataType": 7/* Int32 */,    "int_value": 5,                     "metadata":{"description":"[R]Phase A active power, value in mW"} },
    { "name": "phase/a/power/reactive",         "dataType": 7/* Int32 */,    "int_value": 5,                     "metadata":{"description":"[R]Phase A reactive power, value in mVAR"} },
    { "name": "phase/a/power/apparent",         "dataType": 7/* Int32 */,    "int_value": 5,                     "metadata":{"description":"[R]Phase A apparent power, value in mVA"} },
    { "name": "phase/a/power/factor",           "dataType": 9/* Float */,    "float_value": 0.1,                 "metadata":{"description":"[R]Phase A power factor"} },
    { "name": "phase/a/energy/active",          "dataType": 4/* Int64 */,    "int_value": 5,                     "metadata":{"description":"[R]Phase A active energy"} },
    { "name": "phase/a/energy/reactive",        "dataType": 4/* Int64 */,    "int_value": 5,                     "metadata":{"description":"[R]Phase A reactive energy"} },
    { "name": "phase/a/energy/apparent",        "dataType": 4/* Int64 */,    "int_value": 5,                     "metadata":{"description":"[R]Phase A apparent energy"} },

    { "name": "phase/b/voltage",                "dataType": 7/* Int32 */,    "int_value": 5,                     "metadata":{"description":"[R]Phase B rms voltage, value in mV"} },
    { "name": "phase/b/current",                "dataType": 7/* Int32 */,    "int_value": 5,                     "metadata":{"description":"[R]Phase B rms current, value in mA"} },
    { "name": "phase/b/power/active",           "dataType": 7/* Int32 */,    "int_value": 5,                     "metadata":{"description":"[R]Phase B active power, value in mW"} },
    { "name": "phase/b/power/reactive",         "dataType": 7/* Int32 */,    "int_value": 5,                     "metadata":{"description":"[R]Phase B reactive power, value in mVAR"} },
    { "name": "phase/b/power/apparent",         "dataType": 7/* Int32 */,    "int_value": 5,                     "metadata":{"description":"[R]Phase B apparent power, value in mVA"} },
    { "name": "phase/b/power/factor",           "dataType": 9/* Float */,    "float_value": 0.1,                 "metadata":{"description":"[R]Phase B power factor"} },
    { "name": "phase/b/energy/active",          "dataType": 4/* Int64 */,    "int_value": 5,                     "metadata":{"description":"[R]Phase B active energy"} },
    { "name": "phase/b/energy/reactive",        "dataType": 4/* Int64 */,    "int_value": 5,                     "metadata":{"description":"[R]Phase B reactive energy"} },
    { "name": "phase/b/energy/apparent",        "dataType": 4/* Int64 */,    "int_value": 5,                     "metadata":{"description":"[R]Phase B apparent energy"} },

    { "name": "phase/c/voltage",                "dataType": 7/* Int32 */,    "int_value": 5,                     "metadata":{"description":"[R]Phase C rms voltage, value in mV"} },
    { "name": "phase/c/current",                "dataType": 7/* Int32 */,    "int_value": 5,                     "metadata":{"description":"[R]Phase C rms current, value in mA"} },
    { "name": "phase/c/power/active",           "dataType": 7/* Int32 */,    "int_value": 5,                     "metadata":{"description":"[R]Phase C active power, value in mW"} },
    { "name": "phase/c/power/reactive",         "dataType": 7/* Int32 */,    "int_value": 5,                     "metadata":{"description":"[R]Phase C reactive power, value in mVAR"} },
    { "name": "phase/c/power/apparent",         "dataType": 7/* Int32 */,    "int_value": 5,                     "metadata":{"description":"[R]Phase C apparent power, value in mVA"} },
    { "name": "phase/c/power/factor",           "dataType": 9/* Float */,    "float_value": 0.1,                 "metadata":{"description":"[R]Phase C power factor"} },
    { "name": "phase/c/energy/active",          "dataType": 4/* Int64 */,    "int_value": 5,                     "metadata":{"description":"[R]Phase C active energy"} },
    { "name": "phase/c/energy/reactive",        "dataType": 4/* Int64 */,    "int_value": 5,                     "metadata":{"description":"[R]Phase C reactive energy"} },
    { "name": "phase/c/energy/apparent",        "dataType": 4/* Int64 */,    "int_value": 5,                     "metadata":{"description":"[R]Phase C apparent energy"} },

    { "name": "neutral/current",                "dataType": 7/* Int32 */,    "int_value": 5,                     "metadata":{"description":"[R]Neutral rms current, value in mA"} },


  ]
}

```

## PLC device energymeter death example
> spBv1.0/plc/DDEATH/abba2020/deba0009 

```json
{
"timestamp": 1486144502122,
"seq": 0
}
```
