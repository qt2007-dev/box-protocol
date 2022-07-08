## PLC device wiegand birth example
> spBv1.0/plc/DBIRTH/abba2020/deba0007 

```json
{
"timestamp": 1486144502122,
"seq": 0,
"metrics": [
    { "name": "bdSeq",                                  "dataType": 8/* Uint64 */,   "long_value": 0,                    "metadata":{"description":"[R]Birth-death sequence, 'online' - [DBIRTH > DDEATH}, 'offline' - [DBIRTH <= DDEATH]  "} },
    { "name": "control/reboot",                         "dataType": 11/* Boolean */, "boolean_value": false,             "metadata":{"description":"[W]Software reboot device, send 'true' for reboot"} },
    { "name": "control/rebirth",                        "dataType": 11/* Boolean */, "boolean_value": false,             "metadata":{"description":"[W]Rebirth device, send 'true' for receive dbirth message again"} },
    { "name": "control/firmware/new",                   "dataType": 17/* Bytes */,   "bytes_value":"", "is_null": true,  "metadata":{"description":"[W]Receive new device firmware, firmware send in Base64 format, in birth always null"} },
    { "name": "control/metrics/save",                   "dataType": 11/* Boolean */, "boolean_value": true,              "metadata":{"description":"[RWP]Save metrics states after reboot, send 'true' for enable"} },
    { "name": "control/metrics/metadata",               "dataType": 11/* Boolean */, "boolean_value": true,              "metadata":{"description":"[RWP]Show metrics metadata in birth, send 'true' for enable"} },
    { "name": "control/group",                          "dataType": 12/* String */,  "string_value": "wiegand",          "metadata":{"description":"[RWP]Global group for device, can be used instead id in topics and scenarios"} },

    { "name": "info/hardware/vendor",                   "dataType": 12/* String */,  "string_value": "QuintTech" ,       "metadata":{"description":"[R]Vendor name, hardcoded by vendor"} },
    { "name": "info/hardware/model",                    "dataType": 12/* String */,  "string_value": "stm32g474ce",      "metadata":{"description":"[R]Mcu model, hardcoded by vendor"} },
    { "name": "info/firmware/version",                  "dataType": 12/* String */,  "string_value": "0.1.220527.84852", "metadata":{"description":"[R]Firmware version, MAJOR.MINOR.YYMMDD.SSSSS"} },
    { "name": "info/type",                              "dataType": 12/* String */,  "string_value": "Wiegand 2",        "metadata":{"description":"[R]Device type, hardcoded by vendor"} },
    { "name": "info/id",                                "dataType": 12/* String */,  "string_value": "deba0007",         "metadata":{"description":"[R]Short id calculated by a hash from mcu uid"} },
    { "name": "info/error",                             "dataType": 12/* String */,  "string_value": "",                 "metadata":{"description":"[R]Last error message"} },

    { "name": "sensors/temperature",                    "dataType": 1/* Int8 */,     "int_value": 22,                    "metadata":{"description":"[R]Temperature sensor in mcu, value in Celsius"} },

    { "name": "wiegand/0/mode",                         "dataType": 12/* String */,  "string_value": "normal",           "metadata":{"description":"[RW]Wiegand operational mode, list of values = ['normal', 'add-keys']"} },              
    { "name": "wiegand/0/open",                         "dataType": 11/* Boolean */, "boolean_value": false,             "metadata":{"description":"[RW]Door open value, 'true' - open, 'false' - close"} },                
    { "name": "wiegand/0/open/state",                   "dataType": 12/* String */,  "string_value": "high",             "metadata":{"description":"[RW]Door open state, values = ['high', 'low']"} },                 
    { "name": "wiegand/0/open/time",                    "dataType": 7/* Int32 */,    "int_value": 5,                     "metadata":{"description":"[RW]Door open time, value in seconds"} },                         
    { "name": "wiegand/0/key/add",                      "dataType": 8/* Uint64 */,   "long_value": 0,                    "metadata":{"description":"[W]Wiegand key add to allow list"} },                        
    { "name": "wiegand/0/key/delete",                   "dataType": 8/* Uint64 */,   "long_value": 0,                    "metadata":{"description":"[W]Wiegand key delete from allow list"} },                       
    { "name": "wiegand/0/key/slots",                    "dataType": 7/* Int32 */ ,   "int_value": 1000,                  "metadata":{"description":"[R]Wiegand keys slots left"} },                       
    { "name": "wiegand/0/key/list",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 1,
                        "columns": ["keys"],
                        "types": [8], /* Uint64 */
                        "rows": [ {"elements":[{"long_value": 0}]},
                                  {"elements":[{"long_value": 1}]},
                                  {"elements":[{"long_value": 2}]},
                                  {"elements":[{"long_value": 3}]},
                                  {"elements":[{"long_value": 4}]},
                                  {"elements":[{"long_value": 5}]}  ] },                                                 "metadata":{"description":"[R]Wiegand keys slots left"} }, 
 
    
  ]
}
```

## PLC device wiegand death example
> spBv1.0/plc/DDEATH/abba2020/deba0007 

```json
{
"timestamp": 1486144502122,
"metrics": [  
    { "name": "bdSeq",                                  "dataType": 8/* Uint64 */,   "long_value": 0,                    "metadata":{"description":"[R]Birth-death sequence, 'online' - [DBIRTH > DDEATH}, 'offline' - [DBIRTH <= DDEATH]  "} },  
]
}
```