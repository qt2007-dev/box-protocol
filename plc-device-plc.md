## PLC device power line communication birth example
> spBv1.0/plc/DBIRTH/abba2020/deba0002 

```json
{
"timestamp": 1486144502122,
"seq": 0,
"metrics": [
    { "name": "bdSeq",                          "dataType": 8/* Uint64 */,   "long_value": 0,                    "metadata":{"description":"[R]Birth-death sequence, 'online' - [DBIRTH > DDEATH], 'offline' - [DBIRTH <= DDEATH]  "} },
    { "name": "control/reboot",                 "dataType": 11/* Boolean */, "boolean_value": false,             "metadata":{"description":"[W]Software reboot device, send 'true' for reboot"} },
    { "name": "control/rebirth",                "dataType": 11/* Boolean */, "boolean_value": false,             "metadata":{"description":"[W]Rebirth device, send 'true' for receive dbirth message again"} },
    { "name": "control/firmware/new",           "dataType": 17/* Bytes */,   "bytes_value":"", "is_null": true,  "metadata":{"description":"[W]Receive new device firmware, firmware send in Base64 format, in birth always null"} },
    { "name": "control/metrics/save",           "dataType": 11/* Boolean */, "boolean_value": true,              "metadata":{"description":"[RWP]Save metrics states after reboot, send 'true' for enable"} },
    { "name": "control/metrics/metadata",       "dataType": 11/* Boolean */, "boolean_value": true,              "metadata":{"description":"[RWP]Show metrics metadata in birth, send 'true' for enable"} },
    { "name": "control/group",                  "dataType": 12/* String */,  "string_value": "ro",               "metadata":{"description":"[RWP]Global group for device, can be used instead id in topics and scenarios"} },

    { "name": "info/hardware/vendor",           "dataType": 12/* String */,  "string_value": "QuintTech" ,       "metadata":{"description":"[R]Vendor name, hardcoded by vendor"} },
    { "name": "info/hardware/model",            "dataType": 12/* String */,  "string_value": "stm32g474ce",      "metadata":{"description":"[R]Mcu model, hardcoded by vendor"} },
    { "name": "info/firmware/version",          "dataType": 12/* String */,  "string_value": "0.1.220527.84852", "metadata":{"description":"[R]Firmware version, MAJOR.MINOR.YYMMDD.SSSSS"} },
    { "name": "info/type",                      "dataType": 12/* String */,  "string_value": "PLC",              "metadata":{"description":"[R]Device type, hardcoded by vendor"} },
    { "name": "info/id",                        "dataType": 12/* String */,  "string_value": "deba0002",         "metadata":{"description":"[R]Short id calculated by a hash from mcu uid"} },
    { "name": "info/error",                     "dataType": 12/* String */,  "string_value": "",                 "metadata":{"description":"[R]Last error message"} },

    { "name": "sensors/temperature",            "dataType": 1/* Int8 */,     "int_value": 22,                    "metadata":{"description":"[R]Temperature sensor in mcu, value in Celsius"} },  

    { "name": "plc/devices",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 1,
                        "columns": ["devices"],
                        "types": [7], /* UInt32 */
                        "rows": [ {"elements":[{"int_value": 11223344}]},
                                  {"elements":[{"int_value": 55667788}]},
                                  {"elements":[{"int_value": 22446688}]},
                                  {"elements":[{"int_value": 33669900}]},
                                  {"elements":[{"int_value": 99887766}]},
                                  {"elements":[{"int_value": 55533366}]}  ] },                                                  
      "metadata":{"description":"[RWP]Plc devices connected to plc module, change metric trigger rebirth"} }, 


    { "name": "plc/cmd",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 4,
                        "columns": ["addr-type", "addr", "cmd", "value"],
                        "types": [12,5,12,5], /* String, UInt8, String, UInt8 */
                        "rows": [ {"elements":[{"string_value": "group","int_value": 10,"string_value": "dim","int_value": 240}]} ] }, 
      "metadata":{"description":"[W]Dali send command to bus, 
                                 'addr-type' list of values = ['broadcast', 'group', 'plc'],
                                 'cmd' list of values = ['dim', 'fade-time', 'fade-rate']"} },     

    /* Group control metrics */
    /* plc/group/{group}    */ 
    { "name": "plc/group/0",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 1,
                        "columns": ["devices"],
                        "types": [7], /* UInt32 */
                        "rows": [ {"elements":[{"int_value": 11223344}]},
                                  {"elements":[{"int_value": 55667788}]},
                                  {"elements":[{"int_value": 22446688}]},
                                  {"elements":[{"int_value": 33669900}]},
                                  {"elements":[{"int_value": 99887766}]},
                                  {"elements":[{"int_value": 55533366}]}  ] },                                                  
      "metadata":{"description":"[RWP]Plc group contained plc device list"} }, 


    /* plc/{id}/.. id in hex form   */ 
    { "name": "plc/abba0001/type",                     "dataType": 12/* String */,  "string_value": "LED",              "metadata":{"description":"[R]Gear type, dali cmd 'QUERY DEVICE TYPE','QUERY NEXT DEVICE TYPE',
                                                                                                                                                    values = ['FLUORESCENT', 'EMERGENCY', 'HID', 'HALOGEN',
                                                                                                                                                    'INCANDESCENT', 'CONVERTOR', 'LED', 'RELAY', 'COLOR'],
                                                                                                                                                    can be multiple types at the same time ('LED|COLOR')"} }, 
    { "name": "plc/abba0001/status",                   "dataType": 12/* String */,  "string_value": "ok",               "metadata":{"description":"[R]Control gear status, values = ['ok', 'control-failure', 'lamp-failure', 'short-circuit',
                                                                                                                                                     'open-circuit', 'current-protector', 'thermal-shutdown', 'thermal-overload'],
                                                                                                                                                    dali cmd 'QUERY STATUS', LED - 'QUERY FAILURE STATUS',
                                                                                                                                                    can be multiple status at the same time ('lamp-failure|open-circuit')"} }, 
    { "name": "plc/abba0001/dim",                      "dataType": 5/* UInt8 */,    "int_value": 0,                     "metadata":{"description":"[RW]Gear dim level, dali cmd 'DAPC', values = [0-255], value 255(MASK) stop running fade. 
                                                                                                                                                    For read actual dim level using dali cmd 'QUERY ACTUAL LEVEL'"} },
    { "name": "plc/abba0001/dim/phyMin",               "dataType": 5/* UInt8 */,    "int_value": 0,                     "metadata":{"description":"[R]Gear physical minimum dim level, dali cmd 'QUERY PHYSICAL MINIMUM'"} },  
    { "name": "plc/abba0001/dim/min",                  "dataType": 5/* UInt8 */,    "int_value": 0,                     "metadata":{"description":"[RWP]Gear minimum dim level, dali cmd 'QUERY MIN LEVEL', 'SET MIN LEVEL'"} },  
    { "name": "plc/abba0001/dim/max",                  "dataType": 5/* UInt8 */,    "int_value": 0,                     "metadata":{"description":"[RWP]Gear maximum dim level, dali cmd 'QUERY MAX LEVEL', 'SET MAX LEVEL'"} },  
    { "name": "plc/abba0001/dim/powerOn",              "dataType": 5/* UInt8 */,    "int_value": 0,                     "metadata":{"description":"[RWP]Gear power on dim level, dali cmd 'QUERY POWER ON LEVEL', 'SET POWER ON LEVEL'"} },  
    { "name": "plc/abba0001/dim/failure",              "dataType": 5/* UInt8 */,    "int_value": 0,                     "metadata":{"description":"[RWP]Gear bus failure dim level, dali cmd 'QUERY SYSTEM FAILURE LEVEL', 'SET SYSTEM FAILURE LEVEL',
                                                                                                                                                    value 255(MASK) disable react to bus failure"} }, 
    { "name": "plc/abba0001/fade/time",                "dataType": 5/* UInt8 */,    "int_value": 0,                     "metadata":{"description":"[RWP]Gear fade time, dali cmd 'SET FADE TIME', 'QUERY FADE TIME/FADE RATE', values = [0-15]"} },    
    { "name": "plc/abba0001/fade/rate",                "dataType": 5/* UInt8 */,    "int_value": 1,                     "metadata":{"description":"[RWP]Gear fade rate, dali cmd 'SET FADE RATE', 'QUERY FADE TIME/FADE RATE', values = [0-15]"} },          

  ]
}
```

## PLC device power line communication death example
> spBv1.0/plc/DDEATH/abba2020/deba0002  

```json
{
"timestamp": 1486144502122,
"metrics": [  
    { "name": "bdSeq",                          "dataType": 8/* Uint64 */,   "long_value": 0,                    "metadata":{"description":"[R]Birth-death sequence, 'online' - [DBIRTH > DDEATH], 'offline' - [DBIRTH <= DDEATH]  "} },  
]
}
```