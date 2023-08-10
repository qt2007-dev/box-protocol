## BOX device step birth example
> spBv1.0/box/DBIRTH/abba2020/deba0008 

```json
{
"timestamp": 1486144502122,
"seq": 0,
"metrics": [
    { "name": "bdSeq",                                  "dataType": 8/* Uint64 */,   "long_value": 0,                    "metadata":{"description":"[R]Birth-death sequence, 'online' - [DBIRTH > DDEATH], 'offline' - [DBIRTH <= DDEATH]  "} },
    { "name": "control/reboot",                         "dataType": 11/* Boolean */, "boolean_value": false,             "metadata":{"description":"[W]Software reboot device, send 'true' for reboot"} },
    { "name": "control/rebirth",                        "dataType": 11/* Boolean */, "boolean_value": false,             "metadata":{"description":"[W]Rebirth device, send 'true' for receive dbirth message again"} },
    { "name": "control/firmware/new",                   "dataType": 17/* Bytes */,   "bytes_value":"", "is_null": true,  "metadata":{"description":"[W]Receive new device firmware, firmware send in Base64 format, in birth always null"} },
    { "name": "control/metrics/save",                   "dataType": 11/* Boolean */, "boolean_value": true,              "metadata":{"description":"[RWP]Save metrics states after reboot, send 'true' for enable"} },
    { "name": "control/metrics/metadata",               "dataType": 11/* Boolean */, "boolean_value": true,              "metadata":{"description":"[RWP]Show metrics metadata in birth, send 'true' for enable"} },
    { "name": "control/group",                          "dataType": 12/* String */,  "string_value": "step",             "metadata":{"description":"[RWP]Global group for device, can be used instead id in topics and scenarios"} },

    { "name": "info/hardware/vendor",                   "dataType": 12/* String */,  "string_value": "QuintTech" ,       "metadata":{"description":"[R]Vendor name, hardcoded by vendor"} },
    { "name": "info/hardware/model",                    "dataType": 12/* String */,  "string_value": "stm32g474ce",      "metadata":{"description":"[R]Mcu model, hardcoded by vendor"} },
    { "name": "info/firmware/version",                  "dataType": 12/* String */,  "string_value": "0.1.220527.84852", "metadata":{"description":"[R]Firmware version, MAJOR.MINOR.YYMMDD.SSSSS"} },
    { "name": "info/type",                              "dataType": 12/* String */,  "string_value": "STEP 2",           "metadata":{"description":"[R]Device type, hardcoded by vendor"} },
    { "name": "info/id",                                "dataType": 12/* String */,  "string_value": "deba0008",         "metadata":{"description":"[R]Short id calculated by a hash from mcu uid"} },
    { "name": "info/error",                             "dataType": 12/* String */,  "string_value": "",                 "metadata":{"description":"[R]Last error message"} },

    { "name": "sensors/temperature",                    "dataType": 1/* Int8 */,     "int_value": 22,                    "metadata":{"description":"[R]Temperature sensor in mcu, value in Celsius"} },

    { "name": "motor/0/mode",                           "dataType": 12/* String */,  "string_value": "velocity",         "metadata":{"description":"[RWP]Motor motion type - ['velocity', 'position']"} },
    { "name": "motor/0/temperature",                    "dataType": 1/* Int8 */,     "int_value": 22,                    "metadata":{"description":"[R]Temperature sensor in motor driver, value in Celsius"} },

    { "name": "motor/0/current/boost",                  "dataType": 5/* UInt8 */,    "int_value": 160,                   "metadata":{"description":"[RWP]Motor boost current [0-254] 254 - max current (100%)"} },  
    { "name": "motor/0/current/drive",                  "dataType": 5/* UInt8 */,    "int_value": 128,                   "metadata":{"description":"[RWP]Motor drive current [0-254] 254 - max current (100%)"} },  
    { "name": "motor/0/current/boost",                  "dataType": 5/* UInt8 */,    "int_value": 128,                   "metadata":{"description":"[RWP]Motor hold current [0-254] 254 - max current (100%)"} },  
        
    { "name": "motor/0/ramp/acceleration",              "dataType": 7/* UInt32 */,  "int_value": 80000,                  "metadata":{"description":"[RWP]Maxium motor acceleration value"} },                     
    { "name": "motor/0/ramp/deceleration",              "dataType": 7/* UInt32 */,  "int_value": 120000,                 "metadata":{"description":"[RWP]Maxium motor deceleration value"} },                     
    { "name": "motor/0/ramp/bow/1",                     "dataType": 7/* UInt32 */,  "int_value": 40000,                  "metadata":{"description":"[RWP]Determines the value which increases the absolute acceleration value"} },                     
    { "name": "motor/0/ramp/bow/2",                     "dataType": 7/* UInt32 */,  "int_value": 20000,                  "metadata":{"description":"[RWP]Determines the value which decreases the absolute acceleration value"} },  
    { "name": "motor/0/ramp/bow/3",                     "dataType": 7/* UInt32 */,  "int_value": 20000,                  "metadata":{"description":"[RWP]Determines the value which increases the absolute deceleration value"} },  
    { "name": "motor/0/ramp/bow/4",                     "dataType": 7/* UInt32 */,  "int_value": 40000,                  "metadata":{"description":"[RWP]Determines the value which decreases the absolute deceleration value"} },  

    { "name": "motor/0/velocity",                       "dataType": 3/* Int32 */,   "int_value": 100000,                 "metadata":{"description":"[RWP]Motor velocity"} },                        
    { "name": "motor/0/enable",                         "dataType": 11/* Boolean */, "boolean_value": true,              "metadata":{"description":"[RWP]Enable motor driver, send 'true' for enable"} },                       

    { "name": "motor/1/mode",                           "dataType": 12/* String */,  "string_value": "position",         "metadata":{"description":"[RWP]Motor motion type - ['velocity', 'position']"} },
    { "name": "motor/1/temperature",                    "dataType": 1/* Int8 */,     "int_value": 22,                    "metadata":{"description":"[R]Temperature sensor in motor driver, value in Celsius"} },

    { "name": "motor/1/current/boost",                  "dataType": 5/* UInt8 */,    "int_value": 160,                   "metadata":{"description":"[RWP]Motor boost current [0-254] 254 - max current (100%)"} },  
    { "name": "motor/1/current/drive",                  "dataType": 5/* UInt8 */,    "int_value": 128,                   "metadata":{"description":"[RWP]Motor drive current [0-254] 254 - max current (100%)"} },  
    { "name": "motor/1/current/boost",                  "dataType": 5/* UInt8 */,    "int_value": 128,                   "metadata":{"description":"[RWP]Motor hold current [0-254] 254 - max current (100%)"} },  
        
    { "name": "motor/1/ramp/acceleration",              "dataType": 7/* UInt32 */,  "int_value": 80000,                  "metadata":{"description":"[RWP]Maxium motor acceleration value"} },                     
    { "name": "motor/1/ramp/deceleration",              "dataType": 7/* UInt32 */,  "int_value": 120000,                 "metadata":{"description":"[RWP]Maxium motor deceleration value"} },                     
    { "name": "motor/1/ramp/bow/1",                     "dataType": 7/* UInt32 */,  "int_value": 40000,                  "metadata":{"description":"[RWP]Determines the value which increases the absolute acceleration value"} },                     
    { "name": "motor/1/ramp/bow/2",                     "dataType": 7/* UInt32 */,  "int_value": 20000,                  "metadata":{"description":"[RWP]Determines the value which decreases the absolute acceleration value"} },  
    { "name": "motor/1/ramp/bow/3",                     "dataType": 7/* UInt32 */,  "int_value": 20000,                  "metadata":{"description":"[RWP]Determines the value which increases the absolute deceleration value"} },  
    { "name": "motor/1/ramp/bow/4",                     "dataType": 7/* UInt32 */,  "int_value": 40000,                  "metadata":{"description":"[RWP]Determines the value which decreases the absolute deceleration value"} },  

    { "name": "motor/1/home",                           "dataType": 3/* Int32 */,   "int_value": 0,                      "metadata":{"description":"[RWP]Motor home position"} },
    { "name": "motor/1/position",                       "dataType": 3/* Int32 */,   "int_value": 100000,                 "metadata":{"description":"[RWP]Motor position"} },                        
    { "name": "motor/1/enable",                         "dataType": 11/* Boolean */, "boolean_value": true,              "metadata":{"description":"[RWP]Enable motor driver, send 'true' for enable"} },    


  ]
         
}
```

## BOX device step death example
> spBv1.0/box/DDEATH/abba2020/deba0008 

```json
{
"timestamp": 1486144502122,
"metrics": [  
    { "name": "bdSeq",                                  "dataType": 8/* Uint64 */,   "long_value": 0,                    "metadata":{"description":"[R]Birth-death sequence, 'online' - [DBIRTH > DDEATH], 'offline' - [DBIRTH <= DDEATH]  "} },  
]
}
```