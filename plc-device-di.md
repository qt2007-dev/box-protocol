## PLC device digital input birth example
> spBv1.0/plc/DBIRTH/abba2020/deba0003  

```json
{
"timestamp": 1486144502122,
"seq": 0,
"metrics": [
    { "name": "bdSeq",                          "dataType": 8/* Uint64 */,   "long_value": 0,                      "metadata":{"description":"[R]Birth-death sequence, 'online' - [DBIRTH > DDEATH], 'offline' - [DBIRTH <= DDEATH]  "} },
    { "name": "control/reboot",                 "dataType": 11/* Boolean */, "boolean_value": false,               "metadata":{"description":"[W]Software reboot device, send 'true' for reboot"} },
    { "name": "control/rebirth",                "dataType": 11/* Boolean */, "boolean_value": false,               "metadata":{"description":"[W]Rebirth device, send 'true' for receive dbirth message again"} },
    { "name": "control/firmware/new",           "dataType": 17/* Bytes */,   "bytes_value":"", "is_null": true,    "metadata":{"description":"[W]Receive new device firmware, firmware send in Base64 format, in birth always null"} },
    { "name": "control/metrics/save",           "dataType": 11/* Boolean */, "boolean_value": true,                "metadata":{"description":"[RWP]Save metrics states after reboot, send 'true' for enable"} },
    { "name": "control/metrics/metadata",       "dataType": 11/* Boolean */, "boolean_value": true,                "metadata":{"description":"[RWP]Show metrics metadata in birth, send 'true' for enable"} },
    { "name": "control/group",                  "dataType": 12/* String */,  "string_value": "di",                 "metadata":{"description":"[RWP]Global group for device, can be used instead id in topics and scenarios"} },
  
    { "name": "info/hardware/vendor",           "dataType": 12/* String */,  "string_value": "QuintTech" ,         "metadata":{"description":"[R]Vendor name, hardcoded by vendor"} },
    { "name": "info/hardware/model",            "dataType": 12/* String */,  "string_value": "stm32g474ce",        "metadata":{"description":"[R]Mcu model, hardcoded by vendor"} },
    { "name": "info/firmware/version",          "dataType": 12/* String */,  "string_value": "0.1.220527.84852",   "metadata":{"description":"[R]Firmware version, MAJOR.MINOR.YYMMDD.SSSSS"} },
    { "name": "info/type",                      "dataType": 12/* String */,  "string_value": "16 Digital inputs",  "metadata":{"description":"[R]Device type, hardcoded by vendor"} },
    { "name": "info/id",                        "dataType": 12/* String */,  "string_value": "deba0003",           "metadata":{"description":"[R]Short id calculated by a hash from mcu uid"} },
    { "name": "info/error",                     "dataType": 12/* String */,  "string_value": "",                   "metadata":{"description":"[R]Last error message"} },
  
    { "name": "sensors/temperature",            "dataType": 1/* Int8 */,     "int_value": 22,                      "metadata":{"description":"[R]Temperature sensor in mcu, value in Celsius"} },  
  
    { "name": "bitmask/0",                      "dataType": 5/* UInt8 */,    "int_value": 0,                       "metadata":{"description":"[R]Bitmask of digital inputs, [0-7] in"} },  
    { "name": "bitmask/1",                      "dataType": 5/* UInt8 */,    "int_value": 0,                       "metadata":{"description":"[R]Bitmask of digital inputs, [8-18] in"} },
  
    { "name": "in/0",                          "dataType": 11/* Boolean */, "boolean_value": false,               "metadata":{"description":"[R]Digital input 0 state"} },
    { "name": "in/1",                          "dataType": 11/* Boolean */, "boolean_value": false,               "metadata":{"description":"[R]Digital input 1 state"} },
    { "name": "in/2",                          "dataType": 11/* Boolean */, "boolean_value": false,               "metadata":{"description":"[R]Digital input 2 state"} },
    { "name": "in/3",                          "dataType": 11/* Boolean */, "boolean_value": false,               "metadata":{"description":"[R]Digital input 3 state"} },
    { "name": "in/4",                          "dataType": 11/* Boolean */, "boolean_value": false,               "metadata":{"description":"[R]Digital input 4 state"} },
    { "name": "in/5",                          "dataType": 11/* Boolean */, "boolean_value": false,               "metadata":{"description":"[R]Digital input 5 state"} },
    { "name": "in/6",                          "dataType": 11/* Boolean */, "boolean_value": false,               "metadata":{"description":"[R]Digital input 6 state"} },
    { "name": "in/7",                          "dataType": 11/* Boolean */, "boolean_value": false,               "metadata":{"description":"[R]Digital input 7 state"} },
    { "name": "in/8",                          "dataType": 11/* Boolean */, "boolean_value": false,               "metadata":{"description":"[R]Digital input 8 state"} },
    { "name": "in/9",                          "dataType": 11/* Boolean */, "boolean_value": false,               "metadata":{"description":"[R]Digital input 9 state"} },
    { "name": "in/10",                         "dataType": 11/* Boolean */, "boolean_value": false,               "metadata":{"description":"[R]Digital input 10 state"} },
    { "name": "in/11",                         "dataType": 11/* Boolean */, "boolean_value": false,               "metadata":{"description":"[R]Digital input 11 state"} },
    { "name": "in/12",                         "dataType": 11/* Boolean */, "boolean_value": false,               "metadata":{"description":"[R]Digital input 12 state"} },
    { "name": "in/13",                         "dataType": 11/* Boolean */, "boolean_value": false,               "metadata":{"description":"[R]Digital input 13 state"} },
    { "name": "in/14",                         "dataType": 11/* Boolean */, "boolean_value": false,               "metadata":{"description":"[R]Digital input 14 state"} },
    { "name": "in/15",                         "dataType": 11/* Boolean */, "boolean_value": false,               "metadata":{"description":"[R]Digital input 15 state"} },     
  ]
}
```

## PLC device digital input death example
> spBv1.0/plc/DDEATH/abba2020/deba0003  

```json
{
"timestamp": 1486144502122,
"metrics": [  
    { "name": "bdSeq",                          "dataType": 8/* Uint64 */,   "long_value": 0,                    "metadata":{"description":"[R]Birth-death sequence, 'online' - [DBIRTH > DDEATH], 'offline' - [DBIRTH <= DDEATH]  "} },  
]
}
```