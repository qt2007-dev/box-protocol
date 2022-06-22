## PLC device dali birth example
> spBv1.0/plc/DBIRTH/abba2020/deba0006 

```json
{
"timestamp": 1486144502122,
"seq": 0,
"metrics": [
    { "name": "control/reboot",                         "dataType": 11/* Boolean */, "boolean_value": false,             "metadata":{"description":"[W]Sofrware reboot device, send 'true' for reboot"} },
    { "name": "control/rebirth",                        "dataType": 11/* Boolean */, "boolean_value": false,             "metadata":{"description":"[W]Rebirth device, send 'true' for receive dbirth message again"} },
    { "name": "control/firmware/new",                   "dataType": 17/* Bytes */,   "bytes_value":"", "is_null": true,  "metadata":{"description":"[W]Receive new device firmware, firmware send in Base64 format, in birth always null"} },
    { "name": "control/metrics/save",                   "dataType": 11/* Boolean */, "boolean_value": true,              "metadata":{"description":"[RWP]Save metrics states after reboot, send 'true' for enable"} },
    { "name": "control/group",                          "dataType": 12/* String */,  "string_value": "io",               "metadata":{"description":"[RWP]Global group for device, can be used instead id in topics and scenarios"} },

    { "name": "info/hardware/vendor",                   "dataType": 12/* String */,  "string_value": "QuintTech" ,       "metadata":{"description":"[R]Vendor name, hardcoded by vendor"} },
    { "name": "info/hardware/model",                    "dataType": 12/* String */,  "string_value": "stm32g474ce",      "metadata":{"description":"[R]Mcu model, hardcoded by vendor"} },
    { "name": "info/firmware/version",                  "dataType": 12/* String */,  "string_value": "0.1.220527.84852", "metadata":{"description":"[R]Firmware version, MAJOR.MINOR.YYMMDD.SSSSS"} },
    { "name": "info/type",                              "dataType": 12/* String */,  "string_value": "8 IO",             "metadata":{"description":"[R]Device type, hardcoded by vendor"} },
    { "name": "info/id",                                "dataType": 12/* String */,  "string_value": "deba0008",         "metadata":{"description":"[R]Short id calculated by a hash from mcu uid"} },
    { "name": "info/error",                             "dataType": 12/* String */,  "string_value": "",                 "metadata":{"description":"[R]Last error message"} },

    { "name": "sensors/temperature",                    "dataType": 1/* Int8 */,     "int_value": 22,                    "metadata":{"description":"[R]Temperature sensor in mcu, value in Celsius"} },

    /* Bus 0 control metrics */
    { "name": "dali/0/status",                          "dataType": 12/* String */,  "string_value": "online",           "metadata":{"description":"[R]Dali bus status, list of states = ['online','short-current','offline']"} },    
    { "name": "dali/0/source",                          "dataType": 11/* Boolean */, "boolean_value": true,              "metadata":{"description":"[RW]Dali bus power source state, 'true' - enabled, 'false' - disabled"} },    
    
    { "name": "dali/0/dim",                             "dataType": 5/* UInt8 */,    "int_value": 0,                     "metadata":{"description":"[W]Broadcast set dimming level, dali cmd 'DAPC', values = [0-255], value 255(MASK) stop running fade"} },    
    { "name": "dali/0/scene",                           "dataType": 5/* UInt8 */,    "int_value": 0,                     "metadata":{"description":"[W]Broadcast set current scene, dali cmd 'GO TO SCENE', values = [0-15]"} },    
    { "name": "dali/0/fade/time",                       "dataType": 5/* UInt8 */,    "int_value": 8,                     "metadata":{"description":"[W]Broadcast set fade time, dali cmd 'SET FADE TIME', values = [0-15]"} },    
    { "name": "dali/0/fade/rate",                       "dataType": 5/* UInt8 */,    "int_value": 8,                     "metadata":{"description":"[W]Broadcast set fade rate, dali cmd 'SET FADE RATE', values = [0-15]"} }, 
        
    /* Group control metrics */
    /* dali/{bus}/group/{group}    */ 
    { "name": "dali/0/group/0",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 1,
                        "columns": ["gears"],
                        "types": [8], /* UInt8 */
                        "rows": [ {"elements":[{"int_value": 0}]},
                                  {"elements":[{"int_value": 1}]},
                                  {"elements":[{"int_value": 2}]},
                                  {"elements":[{"int_value": 3}]},
                                  {"elements":[{"int_value": 4}]},
                                  {"elements":[{"int_value": 5}]}  ] },                                                  "metadata":{"description":"[RW]Dali group contained gear list, dali cmd 'ADD TO GROUP','REMOVE FROM GROUP','QUERY GROUPS'"} }, 
    { "name": "dali/0/group/0/dim",                     "dataType": 5/* UInt8 */,    "int_value": 0,                     "metadata":{"description":"[W]Group set dimming level, dali cmd 'DAPC', values = [0-255], value 255(MASK) stop running fade "} },  
    { "name": "dali/0/group/0/scene",                   "dataType": 5/* UInt8 */,    "int_value": 0,                     "metadata":{"description":"[W]Group set current scene, dali cmd 'GO TO SCENE', values = [0-15]"} },    
    { "name": "dali/0/group/0/time",                    "dataType": 5/* UInt8 */,    "int_value": 8,                     "metadata":{"description":"[W]Group set fade time, dali cmd 'SET FADE TIME', values = [0-15]"} },    
    { "name": "dali/0/group/0/rate",                    "dataType": 5/* UInt8 */,    "int_value": 8,                     "metadata":{"description":"[W]Group set fade rate, dali cmd 'SET FADE RATE', values = [0-15]"} }, 
    
    /* Control gear metrics */
    /* dali/{bus}/gear/{gear}  */  
    { "name": "dali/0/gear/0/type",                     "dataType": 12/* String */,  "string_value": "LED",              "metadata":{"description":"[R]Gear type, dali cmd 'QUERY DEVICE TYPE','QUERY NEXT DEVICE TYPE',
                                                                                                                                                    values = ['FLUORESCENT, 'EMERGENCY', 'HID', 'HALOGEN',
                                                                                                                                                    'INCANDESCENT', 'CONVERTOR', 'LED', 'RELAY', 'COLOR'],
                                                                                                                                                    can be multiple types at the same time ('LED|COLOR')"} }, 
    { "name": "dali/0/gear/0/id",                       "dataType": 12/* String */,  "string_value": "0000-1121",        "metadata":{"description":"[R]Gear id stored in memory bank 0, dali cmd 'READ MEMORY LOCATION'"} },
    { "name": "dali/0/gear/0/dim",                      "dataType": 5/* UInt8 */,    "int_value": 0,                     "metadata":{"description":"[RWP]Gear dim level, dali cmd 'DAPC', values = [0-255], value 255(MASK) stop running fade. 
                                                                                                                                                    For read actual dim level using dali cmd 'QUERY ACTUAL LEVEL'"} },    
    { "name": "dali/0/gear/0/dim/phyMin",               "dataType": 5/* UInt8 */,    "int_value": 0,                     "metadata":{"description":"[R]Gear physical minimum dim level, dali cmd 'QUERY PHYSICAL MINIMUM'"} },  
    { "name": "dali/0/gear/0/dim/min",                  "dataType": 5/* UInt8 */,    "int_value": 0,                     "metadata":{"description":"[RWP]Gear minimum dim level, dali cmd 'QUERY MIN LEVEL', 'SET MIN LEVEL'"} },  
    { "name": "dali/0/gear/0/dim/max",                  "dataType": 5/* UInt8 */,    "int_value": 0,                     "metadata":{"description":"[RWP]Gear maximum dim level, dali cmd 'QUERY MAX LEVEL', 'SET MAX LEVEL'"} },  
    { "name": "dali/0/gear/0/dim/powerOn",              "dataType": 5/* UInt8 */,    "int_value": 0,                     "metadata":{"description":"[RWP]Gear power on dim level, dali cmd 'QUERY POWER ON LEVEL', 'SET POWER ON LEVEL'"} },  
    { "name": "dali/0/gear/0/dim/failure",              "dataType": 5/* UInt8 */,    "int_value": 0,                     "metadata":{"description":"[RWP]Gear bus failure dim level, dali cmd 'QUERY SYSTEM FAILURE LEVEL', 'SET SYSTEM FAILURE LEVEL',
                                                                                                                                                    value 255(MASK) disable react to bus failure"} },
    { "name": "dali/0/gear/0/fade/time",                "dataType": 5/* UInt8 */,    "int_value": 0,                     "metadata":{"description":"[RWP]Gear fade time, dali cmd 'SET FADE TIME', 'QUERY FADE TIME/FADE RATE', values = [0-15]"} },    
    { "name": "dali/0/gear/0/fade/rate",                "dataType": 5/* UInt8 */,    "int_value": 0,                     "metadata":{"description":"[RWP]Gear fade rate, dali cmd 'SET FADE RATE', 'QUERY FADE TIME/FADE RATE', values = [0-15]"} },  
  
    { "name": "dali/0/gear/0/status/controlFailure",    "dataType": 11/* Boolean */, "boolean_value": false,             "metadata":{"description":"[R]Control gear cannot operate as intended, dali cmd 'QUERY STATUS'"} },                  
    { "name": "dali/0/gear/0/status/lampFailure",       "dataType": 11/* Boolean */, "boolean_value": false,             "metadata":{"description":"[R]Lamp cannot be operated as intended, dali cmd 'QUERY STATUS'"} },                
    { "name": "dali/0/gear/0/status/lampOn",            "dataType": 11/* Boolean */, "boolean_value": true,              "metadata":{"description":"[R]Lamp on/off status, dali cmd 'QUERY STATUS'"} },                 
    { "name": "dali/0/gear/0/status/limitError",        "dataType": 11/* Boolean */, "boolean_value": false,             "metadata":{"description":"[R]Last requested target level exceed limitations, dali cmd 'QUERY STATUS'"} },                
    { "name": "dali/0/gear/0/status/fadeRunning",       "dataType": 11/* Boolean */, "boolean_value": false,             "metadata":{"description":"[R]Fade running status, dali cmd 'QUERY STATUS'"} },               
    { "name": "dali/0/gear/0/status/resetState",        "dataType": 11/* Boolean */, "boolean_value": false,             "metadata":{"description":"[R]Control gear failure, dali cmd 'QUERY STATUS'"} },               
    { "name": "dali/0/gear/0/status/powerCycle",        "dataType": 11/* Boolean */, "boolean_value": false,             "metadata":{"description":"[R]Control gear failure, dali cmd 'QUERY STATUS'"} },                

    { "name": "dali/0/gear/0/scene",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 1, 
                        "columns": ["level"],
                        "types": [8], /* UInt8 */
                        "rows": [ {"elements":[{"int_value": 128}]},     /* Scene 0 */
                                  {"elements":[{"int_value": 128}]},     /* Scene 1 */
                                  {"elements":[{"int_value": 128}]},     /* Scene 2 */
                                  {"elements":[{"int_value": 128}]},     /* Scene 3 */
                                  {"elements":[{"int_value": 128}]},     /* Scene 4 */
                                  {"elements":[{"int_value": 128}]},     /* Scene 5 */
                                  {"elements":[{"int_value": 128}]},     /* Scene 6 */
                                  {"elements":[{"int_value": 128}]},     /* Scene 7 */
                                  {"elements":[{"int_value": 128}]},     /* Scene 8 */
                                  {"elements":[{"int_value": 128}]},     /* Scene 9 */
                                  {"elements":[{"int_value": 128}]},     /* Scene 10 */ 
                                  {"elements":[{"int_value": 128}]},     /* Scene 11 */
                                  {"elements":[{"int_value": 128}]},     /* Scene 12 */ 
                                  {"elements":[{"int_value": 128}]},     /* Scene 13 */
                                  {"elements":[{"int_value": 128}]},     /* Scene 14 */  
                                  {"elements":[{"int_value": 128}]} ] }, /* Scene 15 */                                  "metadata":{"description":"[RW]Dali gear scenes, dali cmd 'SET SCENE','QUERY SCENE LEVEL'"} }, 



         
}
```

## PLC device dali death example
> spBv1.0/plc/DDEATH/abba2020/deba0006 

```json
{
"timestamp": 1486144502122,
"seq": 0
}
```