## BOX device digital output birth example
> spBv1.0/box/DBIRTH/abba2020/deba0001 

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
    { "name": "control/group",                  "dataType": 12/* String */,  "string_value": "do",                 "metadata":{"description":"[RWP]Global group for device, can be used instead id in topics and scenarios"} },
  
    { "name": "info/hardware/vendor",           "dataType": 12/* String */,  "string_value": "QuintTech" ,         "metadata":{"description":"[R]Vendor name, hardcoded by vendor"} },
    { "name": "info/hardware/model",            "dataType": 12/* String */,  "string_value": "stm32g474ce",        "metadata":{"description":"[R]Mcu model, hardcoded by vendor"} },
    { "name": "info/firmware/version",          "dataType": 12/* String */,  "string_value": "0.1.220527.84852",   "metadata":{"description":"[R]Firmware version, MAJOR.MINOR.YYMMDD.SSSSS"} },
    { "name": "info/type",                      "dataType": 12/* String */,  "string_value": "16 Digital outputs", "metadata":{"description":"[R]Device type, hardcoded by vendor"} },
    { "name": "info/id",                        "dataType": 12/* String */,  "string_value": "deba0001",           "metadata":{"description":"[R]Short id calculated by a hash from mcu uid"} },
    { "name": "info/error",                     "dataType": 12/* String */,  "string_value": "",                   "metadata":{"description":"[R]Last error message"} },
  
    { "name": "sensors/temperature",            "dataType": 1/* Int8 */,     "int_value": 22,                      "metadata":{"description":"[R]Temperature sensor in mcu, value in Celsius"} },  
  
    { "name": "bitmask/0",                      "dataType": 5/* UInt8 */,    "int_value": 0,                       "metadata":{"description":"[RWP]Bitmask of digital outputs, [0-7] out"} },  
    { "name": "bitmask/1",                      "dataType": 5/* UInt8 */,    "int_value": 0,                       "metadata":{"description":"[RWP]Bitmask of digital outputs, [8-15] out"} },
  
    { "name": "out/0",                          "dataType": 11/* Boolean */, "boolean_value": false,               "metadata":{"description":"[RWP]Digital output 0 control"} },
    { "name": "out/1",                          "dataType": 11/* Boolean */, "boolean_value": false,               "metadata":{"description":"[RWP]Digital output 1 control"} },
    { "name": "out/2",                          "dataType": 11/* Boolean */, "boolean_value": false,               "metadata":{"description":"[RWP]Digital output 2 control"} },
    { "name": "out/3",                          "dataType": 11/* Boolean */, "boolean_value": false,               "metadata":{"description":"[RWP]Digital output 3 control"} },
    { "name": "out/4",                          "dataType": 11/* Boolean */, "boolean_value": false,               "metadata":{"description":"[RWP]Digital output 4 control"} },
    { "name": "out/5",                          "dataType": 11/* Boolean */, "boolean_value": false,               "metadata":{"description":"[RWP]Digital output 5 control"} },
    { "name": "out/6",                          "dataType": 11/* Boolean */, "boolean_value": false,               "metadata":{"description":"[RWP]Digital output 6 control"} },
    { "name": "out/7",                          "dataType": 11/* Boolean */, "boolean_value": false,               "metadata":{"description":"[RWP]Digital output 7 control"} },
    { "name": "out/8",                          "dataType": 11/* Boolean */, "boolean_value": false,               "metadata":{"description":"[RWP]Digital output 8 control"} },
    { "name": "out/9",                          "dataType": 11/* Boolean */, "boolean_value": false,               "metadata":{"description":"[RWP]Digital output 9 control"} },
    { "name": "out/10",                         "dataType": 11/* Boolean */, "boolean_value": false,               "metadata":{"description":"[RWP]Digital output 10 control"} },
    { "name": "out/11",                         "dataType": 11/* Boolean */, "boolean_value": false,               "metadata":{"description":"[RWP]Digital output 11 control"} },
    { "name": "out/12",                         "dataType": 11/* Boolean */, "boolean_value": false,               "metadata":{"description":"[RWP]Digital output 12 control"} },
    { "name": "out/13",                         "dataType": 11/* Boolean */, "boolean_value": false,               "metadata":{"description":"[RWP]Digital output 13 control"} },
    { "name": "out/14",                         "dataType": 11/* Boolean */, "boolean_value": false,               "metadata":{"description":"[RWP]Digital output 14 control"} },
    { "name": "out/15",                         "dataType": 11/* Boolean */, "boolean_value": false,               "metadata":{"description":"[RWP]Digital output 15 control"} },    
  ]
}
```

## BOX device digital output death example
> spBv1.0/box/DDEATH/abba2020/deba0001  

```json
{
"timestamp": 1486144502122,
"metrics": [  
    { "name": "bdSeq",                          "dataType": 8/* Uint64 */,   "long_value": 0,                    "metadata":{"description":"[R]Birth-death sequence, 'online' - [DBIRTH > DDEATH], 'offline' - [DBIRTH <= DDEATH]  "} },  
]
}
```