## BOX device relay output birth example
> spBv1.0/box/DBIRTH/abba2020/deba0003 

```json
{
"timestamp": 1486144502122,
"seq": 0,
"metrics": [
    { "name": "bdSeq",                          "dataType": 8/* UInt64 */,   "long_value": 0,                    "metadata":{"description":"[R]Birth-death sequence, 'online' - [BIRTH > DEATH], 'offline' - [BIRTH <= DEATH]"} },
    { "name": "control/reboot",                 "dataType": 11/* Boolean */, "boolean_value": false,             "metadata":{"description":"[W]Software reboot, send 'true' for reboot"} },
    { "name": "control/rebirth",                "dataType": 11/* Boolean */, "boolean_value": false,             "metadata":{"description":"[W]Rebirth, send 'true' for receive birth message again"} },
    { "name": "control/firmware/new",           "dataType": 17/* Bytes */,   "bytes_value":"", "is_null": true,  "metadata":{"description":"[W]Receive new firmware, firmware send in Base64 format, in birth always null"} },
    { "name": "control/metrics/save",           "dataType": 11/* Boolean */, "boolean_value": true,              "metadata":{"description":"[RWP]Save metrics states after reboot, send 'true' for enable"} },
    { "name": "control/metrics/metadata",       "dataType": 11/* Boolean */, "boolean_value": true,              "metadata":{"description":"[RWP]Show metrics metadata in birth, send 'true' for enable"} },
    { "name": "control/group",                  "dataType": 12/* String */,  "string_value": "ro",               "metadata":{"description":"[RWP]Global group, can be used instead id in topics and scenarios"} },

    { "name": "info/hardware/vendor",           "dataType": 12/* String */,  "string_value": "QuintTech" ,       "metadata":{"description":"[R]Vendor name, hardcoded by vendor"} },
    { "name": "info/hardware/model",            "dataType": 12/* String */,  "string_value": "stm32g474ce",      "metadata":{"description":"[R]Mcu model, hardcoded by vendor"} },
    { "name": "info/firmware/version",          "dataType": 12/* String */,  "string_value": "0.1.22a5f27",      "metadata":{"description":"[R]Firmware version, MAJOR.MINOR.buildOrCommit"} },
    { "name": "info/type",                      "dataType": 12/* String */,  "string_value": "8 Relay outputs",  "metadata":{"description":"[R]Device type, hardcoded by vendor"} },
    { "name": "info/id",                        "dataType": 12/* String */,  "string_value": "deba0003",         "metadata":{"description":"[R]Short device id"} },
    { "name": "info/error",                     "dataType": 12/* String */,  "string_value": "",                 "metadata":{"description":"[R]Last error message"} },

    { "name": "sensors/temperature",            "dataType": 1/* Int8 */,     "int_value": 22,                    "metadata":{"description":"[R]Temperature sensor in mcu, value in Celsius"} },  

    { "name": "bitmask",                        "dataType": 5/* UInt8 */,    "int_value": 0,                     "metadata":{"description":"[RWP]Bitmask of relay outputs, [0-1] mechanical relay out, [2-7] solid state relay out"} },  

    { "name": "mr/0",                           "dataType": 11/* Boolean */, "boolean_value": false,             "metadata":{"description":"[RWP]Mechanical relay output 0 control"} },
    { "name": "mr/1",                           "dataType": 11/* Boolean */, "boolean_value": false,             "metadata":{"description":"[RWP]Mechanical relay output 1 control"} },

    { "name": "ssr/0",                          "dataType": 11/* Boolean */, "boolean_value": false,             "metadata":{"description":"[RWP]Solid state relay output 0 control"} },
    { "name": "ssr/1",                          "dataType": 11/* Boolean */, "boolean_value": false,             "metadata":{"description":"[RWP]Solid state relay output 1 control"} },
    { "name": "ssr/2",                          "dataType": 11/* Boolean */, "boolean_value": false,             "metadata":{"description":"[RWP]Solid state relay output 2 control"} },
    { "name": "ssr/3",                          "dataType": 11/* Boolean */, "boolean_value": false,             "metadata":{"description":"[RWP]Solid state relay output 3 control"} },
    { "name": "ssr/4",                          "dataType": 11/* Boolean */, "boolean_value": false,             "metadata":{"description":"[RWP]Solid state relay output 4 control"} },
    { "name": "ssr/5",                          "dataType": 11/* Boolean */, "boolean_value": false,             "metadata":{"description":"[RWP]Solid state relay output 5 control"} }


  ]
}
```

## BOX device relay output death example
> spBv1.0/box/DDEATH/abba2020/deba0003  

```json
{
"timestamp": 1486144502122,
"metrics": [  
    { "name": "bdSeq",                          "dataType": 8/* UInt64 */,   "long_value": 0,                    "metadata":{"description":"[R]Birth-death sequence, 'online' - [BIRTH > DEATH], 'offline' - [BIRTH <= DEATH]"} },  
]
}
```