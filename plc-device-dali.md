## PLC device dali birth example
> spBv1.0/plc/DBIRTH/abba2020/deba0006 

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
    { "name": "control/group",                          "dataType": 12/* String */,  "string_value": "dali",             "metadata":{"description":"[RWP]Global group for device, can be used instead id in topics and scenarios"} },

    { "name": "info/hardware/vendor",                   "dataType": 12/* String */,  "string_value": "QuintTech" ,       "metadata":{"description":"[R]Vendor name, hardcoded by vendor"} },
    { "name": "info/hardware/model",                    "dataType": 12/* String */,  "string_value": "stm32g474ce",      "metadata":{"description":"[R]Mcu model, hardcoded by vendor"} },
    { "name": "info/firmware/version",                  "dataType": 12/* String */,  "string_value": "0.1.220527.84852", "metadata":{"description":"[R]Firmware version, MAJOR.MINOR.YYMMDD.SSSSS"} },
    { "name": "info/type",                              "dataType": 12/* String */,  "string_value": "DALI 2",           "metadata":{"description":"[R]Device type, hardcoded by vendor"} },
    { "name": "info/id",                                "dataType": 12/* String */,  "string_value": "deba0006",         "metadata":{"description":"[R]Short id calculated by a hash from mcu uid"} },
    { "name": "info/error",                             "dataType": 12/* String */,  "string_value": "",                 "metadata":{"description":"[R]Last error message"} },

    { "name": "sensors/temperature",                    "dataType": 1/* Int8 */,     "int_value": 22,                    "metadata":{"description":"[R]Temperature sensor in mcu, value in Celsius"} },

    /* Bus 0 control metrics */
    { "name": "dali/0/source",                          "dataType": 11/* Boolean */, "boolean_value": true,              "metadata":{"description":"[RW]Dali bus power source state, 'true' - enabled, 'false' - disabled"} },    
    { "name": "dali/0/source/shortCurrent",             "dataType": 11/* Boolean */, "boolean_value": false,             "metadata":{"description":"[R]Dali bus power source short current"} },    
    { "name": "dali/0/source/voltage",                  "dataType": 6/* UInt16 */,   "int_value": 5635,                  "metadata":{"description":"[R]Dali bus voltage, value in mV"} },    
    { "name": "dali/0/source/current",                  "dataType": 6/* UInt16 */,   "int_value": 5635,                  "metadata":{"description":"[R]Dali bus current, value in mA"} },    

    { "name": "dali/0/swap",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 1,
                        "columns": ["from", "target"],
                        "types": [5,5], /* UInt8, UInt8 */
                        "rows": [ {"elements":[{"int_value": 23,"int_value": 34,}]} ] },                                 
      "metadata":{"description":"[W]Dali swap short address on bus"} },
    
    { "name": "dali/0/cmd",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 4,
                        "columns": ["addr-type", "addr", "cmd", "value"],
                        "types": [12,5,12,5], /* String, UInt8, String, UInt8 */
                        "rows": [ {"elements":[{"string_value": "group","int_value": 10,"string_value": "dim","int_value": 240}]} ] }, 
      "metadata":{"description":"[W]Dali send comand to bus, 
                                 'addr-type' list of values = ['broadcast', 'group', 'gear'],
                                 'cmd' list of values = ['dim', 'scene', 'fade-time', 'fade-rate']"} },                    

    /* Group control metrics */
    /* dali/{bus}/group/{group}    */ 
    { "name": "dali/0/group/0",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 1,
                        "columns": ["gear"],
                        "types": [5], /* UInt8 */
                        "rows": [ {"elements":[{"int_value": 0}]},
                                  {"elements":[{"int_value": 1}]},
                                  {"elements":[{"int_value": 2}]},
                                  {"elements":[{"int_value": 3}]},
                                  {"elements":[{"int_value": 4}]},
                                  {"elements":[{"int_value": 5}]}  ] },                                                  
      "metadata":{"description":"[RWP]Dali group contained gear list, dali cmd 'ADD TO GROUP','REMOVE FROM GROUP','QUERY GROUPS'"} }, 
   
    /* Control gear metrics */
    /* dali/{bus}/gear/{gear}  */  
    { "name": "dali/0/gear/0/id",                       "dataType": 12/* String */,  "string_value": "0000-1121",        "metadata":{"description":"[R]Gear id stored in memory bank 0, dali cmd 'READ MEMORY LOCATION'"} },
    { "name": "dali/0/gear/0/type",                     "dataType": 12/* String */,  "string_value": "LED",              "metadata":{"description":"[R]Gear type, dali cmd 'QUERY DEVICE TYPE','QUERY NEXT DEVICE TYPE',
                                                                                                                                                    values = ['FLUORESCENT', 'EMERGENCY', 'HID', 'HALOGEN',
                                                                                                                                                    'INCANDESCENT', 'CONVERTOR', 'LED', 'RELAY', 'COLOR'],
                                                                                                                                                    can be multiple types at the same time ('LED|COLOR')"} }, 
    { "name": "dali/0/gear/0/status",                   "dataType": 12/* String */,  "string_value": "ok",               "metadata":{"description":"[R]Control gear status, values = ['ok', 'control-failure', 'lamp-failure', 'short-circuit',
                                                                                                                                                     'open-circuit', 'current-protector', 'thermal-shutdown', 'thermal-overload'],
                                                                                                                                                    dali cmd 'QUERY STATUS', LED - 'QUERY FAILURE STATUS',
                                                                                                                                                    can be multiple status at the same time ('lamp-failure|open-circuit')"} }, 
    { "name": "dali/0/gear/0/dim",                      "dataType": 5/* UInt8 */,    "int_value": 0,                     "metadata":{"description":"[RW]Gear dim level, dali cmd 'DAPC', values = [0-255], value 255(MASK) stop running fade. 
                                                                                                                                                    For read actual dim level using dali cmd 'QUERY ACTUAL LEVEL'"} },    
    { "name": "dali/0/gear/0/dim/phyMin",               "dataType": 5/* UInt8 */,    "int_value": 0,                     "metadata":{"description":"[R]Gear physical minimum dim level, dali cmd 'QUERY PHYSICAL MINIMUM'"} },  
    { "name": "dali/0/gear/0/dim/min",                  "dataType": 5/* UInt8 */,    "int_value": 0,                     "metadata":{"description":"[RWP]Gear minimum dim level, dali cmd 'QUERY MIN LEVEL', 'SET MIN LEVEL'"} },  
    { "name": "dali/0/gear/0/dim/max",                  "dataType": 5/* UInt8 */,    "int_value": 0,                     "metadata":{"description":"[RWP]Gear maximum dim level, dali cmd 'QUERY MAX LEVEL', 'SET MAX LEVEL'"} },  
    { "name": "dali/0/gear/0/dim/powerOn",              "dataType": 5/* UInt8 */,    "int_value": 0,                     "metadata":{"description":"[RWP]Gear power on dim level, dali cmd 'QUERY POWER ON LEVEL', 'SET POWER ON LEVEL'"} },  
    { "name": "dali/0/gear/0/dim/failure",              "dataType": 5/* UInt8 */,    "int_value": 0,                     "metadata":{"description":"[RWP]Gear bus failure dim level, dali cmd 'QUERY SYSTEM FAILURE LEVEL', 'SET SYSTEM FAILURE LEVEL',
                                                                                                                                                    value 255(MASK) disable react to bus failure"} },
    { "name": "dali/0/gear/0/fade/time",                "dataType": 5/* UInt8 */,    "int_value": 0,                     "metadata":{"description":"[RWP]Gear fade time, dali cmd 'SET FADE TIME', 'QUERY FADE TIME/FADE RATE', values = [0-15]"} },    
    { "name": "dali/0/gear/0/fade/rate",                "dataType": 5/* UInt8 */,    "int_value": 1,                     "metadata":{"description":"[RWP]Gear fade rate, dali cmd 'SET FADE RATE', 'QUERY FADE TIME/FADE RATE', values = [0-15]"} },  
    { "name": "dali/0/gear/0/scenes",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 1, 
                        "columns": ["dim"],
                        "types": [5], /* UInt8 */
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
                                  {"elements":[{"int_value": 128}]} ] }, /* Scene 15 */                                  
      "metadata":{"description":"[RWP]Dali gear scenes, dali cmd 'QUERY SCENE LEVEL', 'SET SCENE'"} }, 

    { "name": "dali/0/gear/1/id",                       "dataType": 12/* String */,  "string_value": "0000-1121",        "metadata":{"description":"[R]Gear id stored in memory bank 0, dali cmd 'READ MEMORY LOCATION'"} },
    { "name": "dali/0/gear/1/type",                     "dataType": 12/* String */,  "string_value": "COLOR",            "metadata":{"description":"[R]Gear type, dali cmd 'QUERY DEVICE TYPE','QUERY NEXT DEVICE TYPE',
                                                                                                                                                    values = ['FLUORESCENT', 'EMERGENCY', 'HID', 'HALOGEN',
                                                                                                                                                    'INCANDESCENT', 'CONVERTOR', 'LED', 'RELAY', 'COLOR'],
                                                                                                                                                    can be multiple types at the same time ('LED|COLOR')"} }, 
    { "name": "dali/0/gear/1/status",                   "dataType": 12/* String */,  "string_value": "ok",               "metadata":{"description":"[R]Control gear status, values = ['ok', 'control-failure', 'lamp-failure', 'short-circuit',
                                                                                                                                                    'open-circuit', 'current-protector', 'thermal-shutdown', 'thermal-overload'],
                                                                                                                                                    dali cmd 'QUERY STATUS', LED - 'QUERY FAILURE STATUS', 
                                                                                                                                                    can be multiple status at the same time ('lamp-failure|open-circuit')"} },
    { "name": "dali/0/gear/1/dim",                      "dataType": 5/* UInt8 */,    "int_value": 0,                     "metadata":{"description":"[RW]Gear dim level, dali cmd 'DAPC', values = [0-255], value 255(MASK) stop running fade. 
                                                                                                                                                    For read actual dim level using dali cmd 'QUERY ACTUAL LEVEL'"} },
    { "name": "dali/0/gear/1/dim/phyMin",               "dataType": 5/* UInt8 */,    "int_value": 0,                     "metadata":{"description":"[R]Gear physical minimum dim level, dali cmd 'QUERY PHYSICAL MINIMUM'"} },  
    { "name": "dali/0/gear/1/dim/min",                  "dataType": 5/* UInt8 */,    "int_value": 0,                     "metadata":{"description":"[RWP]Gear minimum dim level, dali cmd 'QUERY MIN LEVEL', 'SET MIN LEVEL'"} },  
    { "name": "dali/0/gear/1/dim/max",                  "dataType": 5/* UInt8 */,    "int_value": 0,                     "metadata":{"description":"[RWP]Gear maximum dim level, dali cmd 'QUERY MAX LEVEL', 'SET MAX LEVEL'"} },  
    { "name": "dali/0/gear/1/dim/powerOn",              "dataType": 5/* UInt8 */,    "int_value": 0,                     "metadata":{"description":"[RWP]Gear power on dim level, dali cmd 'QUERY POWER ON LEVEL', 'SET POWER ON LEVEL'"} },  
    { "name": "dali/0/gear/1/dim/failure",              "dataType": 5/* UInt8 */,    "int_value": 0,                     "metadata":{"description":"[RWP]Gear bus failure dim level, dali cmd 'QUERY SYSTEM FAILURE LEVEL', 'SET SYSTEM FAILURE LEVEL',
                                                                                                                                                    value 255(MASK) disable react to bus failure"} },
    { "name": "dali/0/gear/1/color",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 9,
                        "columns": ["red","green","blue","white","amber","free", "temperature", "x","y"],
                        "types": [5,5,5,5,5,5, 6, 6,6], /* UInt8, UInt8, UInt8, UInt8, UInt8, UInt8, UInt16, UInt16, UInt16 */
                        "rows": [ {"elements":[{"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0}]} ] },                                                  
      "metadata":{"description":"[RW]Gear color, columns depends on color type, dali cmd 'STORE ACTUAL LEVEL IN THE DTR', 'REPORT COLOUR TYPE', 'REPORT COLOUR VALUE', 'QUERY COLOUR STATUS',
                                'SET TEMPORARY RGB DIMLEVEL','SET TEMPORARY WAF DIMLEVEL','SET TEMPORARY COLOUR TEMPERATURE', 'SET TEMPORARY x-COORDINATE','SET TEMPORARY y-COORDINATE', 'ACTIVATE '"} },
    { "name": "dali/0/gear/1/color/powerOn",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 9,
                        "columns": ["red","green","blue","white","amber","free", "temperature", "x","y"],
                        "types": [5,5,5,5,5,5, 6, 6,6], /* UInt8, UInt8, UInt8, UInt8, UInt8, UInt8, UInt16, UInt16, UInt16 */
                        "rows": [ {"elements":[{"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0}]} ] },                                                  
      "metadata":{"description":"[RW]Gear power on color, columns depends on color type, dali cmd 'QUERY POWER ON LEVEL', 'REPORT COLOUR TYPE', 'REPORT COLOUR VALUE',
                                'SET TEMPORARY RGB DIMLEVEL','SET TEMPORARY WAF DIMLEVEL','SET TEMPORARY COLOUR TEMPERATURE', 'SET TEMPORARY x-COORDINATE','SET TEMPORARY y-COORDINATE', 'SET POWER ON LEVEL'"} }, 
    { "name": "dali/0/gear/1/color/failure",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 9,
                        "columns": ["red","green","blue","white","amber","free", "temperature", "x","y"],
                        "types": [5,5,5,5,5,5, 6, 6,6], /* UInt8, UInt8, UInt8, UInt8, UInt8, UInt8, UInt16, UInt16, UInt16 */
                        "rows": [ {"elements":[{"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0}]} ] },                                                  
      "metadata":{"description":"[RW]Gear bus failure color, columns depends on color type, dali cmd 'QUERY SYSTEM FAILURE LEVEL', 'REPORT COLOUR TYPE', 'REPORT COLOUR VALUE',
                                'SET TEMPORARY RGB DIMLEVEL','SET TEMPORARY WAF DIMLEVEL','SET TEMPORARY COLOUR TEMPERATURE', 'SET TEMPORARY x-COORDINATE','SET TEMPORARY y-COORDINATE', 'SET SYSTEM FAILURE LEVEL'"} },                                 

    { "name": "dali/0/gear/1/color/temperature/coolest","dataType": 6/* UInt16 */,   "int_value": 0,                     "metadata":{"description":"[RWP]Gear coolest color temperature, dali cmd 'QUERY COLOUR VALUE', 
                                                                                                                                                   'STORE COLOUR TEMPERATURE TC LIMIT'"} },
    { "name": "dali/0/gear/1/color/temperature/warmest","dataType": 6/* UInt16 */,   "int_value": 0,                     "metadata":{"description":"[RWP]Gear warmest color temperature, dali cmd 'QUERY COLOUR VALUE', 
                                                                                                                                                   'STORE COLOUR TEMPERATURE TC LIMIT'"} },


    { "name": "dali/0/gear/1/fade/time",                "dataType": 5/* UInt8 */,    "int_value": 0,                     "metadata":{"description":"[RWP]Gear fade time, dali cmd 'SET FADE TIME', 'QUERY FADE TIME/FADE RATE', values = [0-15]"} },    
    { "name": "dali/0/gear/1/fade/rate",                "dataType": 5/* UInt8 */,    "int_value": 1,                     "metadata":{"description":"[RWP]Gear fade rate, dali cmd 'SET FADE RATE', 'QUERY FADE TIME/FADE RATE', values = [0-15]"} },  
    { "name": "dali/0/gear/1/scenes",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 10, 
                        "columns": ["dim","red","green","blue","white","amber","free", "temperature", "x","y"],
                        "types": [5, 5,5,5,5,5,5, 6, 6,6], /* UInt8, UInt8, UInt8, UInt8, UInt8, UInt8, UInt8, UInt16, UInt16, UInt16 */
                        "rows": [ {"elements":[{"int_value": 128,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0}]},     /* Scene 0 */
                                  {"elements":[{"int_value": 128,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0}]},     /* Scene 1 */
                                  {"elements":[{"int_value": 128,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0}]},     /* Scene 2 */
                                  {"elements":[{"int_value": 128,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0}]},     /* Scene 3 */
                                  {"elements":[{"int_value": 128,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0}]},     /* Scene 4 */
                                  {"elements":[{"int_value": 128,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0}]},     /* Scene 5 */
                                  {"elements":[{"int_value": 128,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0}]},     /* Scene 6 */
                                  {"elements":[{"int_value": 128,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0}]},     /* Scene 7 */
                                  {"elements":[{"int_value": 128,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0}]},     /* Scene 8 */
                                  {"elements":[{"int_value": 128,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0}]},     /* Scene 9 */
                                  {"elements":[{"int_value": 128,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0}]},     /* Scene 10 */ 
                                  {"elements":[{"int_value": 128,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0}]},     /* Scene 11 */
                                  {"elements":[{"int_value": 128,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0}]},     /* Scene 12 */ 
                                  {"elements":[{"int_value": 128,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0}]},     /* Scene 13 */
                                  {"elements":[{"int_value": 128,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0}]},     /* Scene 14 */  
                                  {"elements":[{"int_value": 128,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0,"int_value": 0}]} ] }, /* Scene 15 */                                  
      "metadata":{"description":"[RWP]Dali gear scenes, dali cmd 'QUERY SCENE LEVEL','REPORT COLOUR TYPE', 'REPORT COLOUR VALUE', 'QUERY COLOUR STATUS',
                                'SET TEMPORARY RGB DIMLEVEL','SET TEMPORARY WAF DIMLEVEL','SET TEMPORARY COLOUR TEMPERATURE', 'SET TEMPORARY x-COORDINATE','SET TEMPORARY y-COORDINATE', 'SET SCENE'"} },



    /* Control device metrics */
    /* dali/{bus}/device/{device}/instance/{instance}  */ 
    { "name": "dali/0/device/0/id",                           "dataType": 12/* String */,  "string_value": "0000-1121",               "metadata":{"description":"[R]Device id stored in memory bank 0, dali cmd 'READ MEMORY LOCATION'"} },
    { "name": "dali/0/device/0/instance/0/type",              "dataType": 12/* String */,  "string_value": "PUSH-BUTTON",             "metadata":{"description":"[R]Device instance type, dali cmd 'QUERY INSTANCE TYPE',
                                                                                                                                                                values = ['PUSH-BUTTON', 'ABSOLUTE-INPUT-DEVICE', 'OCCUPANCY-SENSOR', 'LIGHT-SENSOR']"} },
    { "name": "dali/0/device/0/instance/0/value",             "dataType": 12/* String */,  "string_value": "released",                "metadata":{"description":"[R]Last button event, values = ['released', 'pressed', 'short-press','double-press',
                                                                                                                                                                'long-press-start','long-press-repeat','long-press-stop','stuck','free'],
                                                                                                                                                                dali cmd 'QUERY INPUT VALUE'"} },
    { "name": "dali/0/device/0/instance/0/filter",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 1,
                        "columns": ["released", "pressed", "short-press","double-press","long-press-start","long-press-repeat","long-press-stop","stuck/free"],
                        "types": [11,11,11,11,11,11,11,11], /* Boolean, Boolean, Boolean, Boolean, Boolean, Boolean, Boolean, Boolean */
                        "rows": [ {"elements":[{"boolean_value": false,"boolean_value": false,"boolean_value": true,"boolean_value": true,"boolean_value": true,"boolean_value": false,"boolean_value": true,"boolean_value": false}]} ] }, 
      "metadata":{"description":"[RWP]Dali device enabled states, dali cmd 'SET EVENT FILTER', 'QUERY EVENT FILTER 0-7'"} }, 
    { "name": "dali/0/device/0/instance/0/timer/short",       "dataType": 5/* UInt8 */,    "int_value": 0,                            "metadata":{"description":"[RWP]Time which differentiates a short press from a long press, 
                                                                                                                                                                dali cmd 'SET SHORT TIMER', 'QUERY SHORT TIMER'"} },  
    { "name": "dali/0/device/0/instance/0/timer/double",      "dataType": 5/* UInt8 */,    "int_value": 0,                            "metadata":{"description":"[RWP]Time which differentiates a single (short) press from a double press, 
                                                                                                                                                                dali cmd 'SET DOUBLE TIMER', 'QUERY DOUBLE TIMER'"} },  
    { "name": "dali/0/device/0/instance/0/timer/repeat",      "dataType": 5/* UInt8 */,    "int_value": 0,                            "metadata":{"description":"[RWP]Repetition interval of long press repeat events, 
                                                                                                                                                                dali cmd 'SET REPEAT TIMER', 'QUERY REPEAT TIMER'"} },  
    { "name": "dali/0/device/0/instance/0/timer/stuck",       "dataType": 5/* UInt8 */,    "int_value": 0,                            "metadata":{"description":"[RWP]Time when button is pressed or bouncing, 
                                                                                                                                                                dali cmd 'SET STUCK TIMER', 'QUERY STUCK TIMER'"} },
    { "name": "dali/0/device/0/instance/1/type",              "dataType": 12/* String */,  "string_value": "ABSOLUTE-INPUT-DEVICE",   "metadata":{"description":"[R]Device instance type, dali cmd 'QUERY INSTANCE TYPE',
                                                                                                                                                                values = ['PUSH-BUTTON', 'ABSOLUTE-INPUT-DEVICE', 'OCCUPANCY-SENSOR', 'LIGHT-SENSOR']"} },
    { "name": "dali/0/device/0/instance/1/value",             "dataType": 6/* UInt16 */,   "int_value": 0,                            "metadata":{"description":"[R]Dali input device position, dali cmd 'QUERY INPUT VALUE'"} },
    { "name": "dali/0/device/0/instance/1/filter",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 8,
                        "columns": ["position"],
                        "types": [11], /* Boolean */
                        "rows": [ {"elements":[{"boolean_value": true}]} ] }, 
      "metadata":{"description":"[RWP]Dali device enabled states, dali cmd 'SET EVENT FILTER', 'QUERY EVENT FILTER 0-7'"} },    
    { "name": "dali/0/device/0/instance/1/timer/deadtime",    "dataType": 5/* UInt8 */,    "int_value": 0,                            "metadata":{"description":"[RWP]If the deadtime timer is set, the instance shall not send out an event until the deadtime timer
                                                                                                                                                                has expired, dali cmd 'SET DEADTIME TIMER', 'QUERY DEADTIME TIMER'"} },  
    { "name": "dali/0/device/0/instance/1/timer/report",      "dataType": 5/* UInt8 */,    "int_value": 0,                            "metadata":{"description":"[RWP]If the report timer is set, it shall trigger an event every tReport even if the value has not
                                                                                                                                                                changed, dali cmd 'SET REPORT TIMER', 'QUERY REPORT TIMER'"} },  



    { "name": "dali/0/device/1/id",                           "dataType": 12/* String */,  "string_value": "0000-1121",               "metadata":{"description":"[R]Device id stored in memory bank 0, dali cmd 'READ MEMORY LOCATION'"} },
    { "name": "dali/0/device/1/instance/0/type",              "dataType": 12/* String */,  "string_value": "OCCUPANCY-SENSOR",        "metadata":{"description":"[R]Device instance type, dali cmd 'QUERY INSTANCE TYPE',
                                                                                                                                                                values = ['PUSH-BUTTON', 'ABSOLUTE-INPUT-DEVICE', 'OCCUPANCY-SENSOR', 'LIGHT-SENSOR']"} },
    { "name": "dali/0/device/1/instance/0/value",             "dataType": 12/* String */,  "string_value": "vacant",                  "metadata":{"description":"[R]Last button event, values = ['vacant', 'occupied'], dali cmd 'QUERY INPUT VALUE'"} },
    { "name": "dali/0/device/1/instance/0/filter",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 5,
                        "columns": ["occupied", "vacant", "repeat", "movement", "no-movement"],
                        "types": [11,11,11,11,11], /* Boolean, Boolean, Boolean, Boolean, Boolean */
                        "rows": [ {"elements":[{"boolean_value": true,"boolean_value": false,"boolean_value": true,"boolean_value": true,"boolean_value": true}]} ] }, 
      "metadata":{"description":"[RWP]Dali device enabled states, dali cmd 'SET EVENT FILTER', 'QUERY EVENT FILTER 0-7'"} },        
    { "name": "dali/0/device/1/instance/0/timer/deadtime",    "dataType": 5/* UInt8 */,    "int_value": 0,                            "metadata":{"description":"[RWP]If the deadtime timer is set, the instance shall not send out an event until the deadtime timer
                                                                                                                                                                has expired, dali cmd 'SET DEADTIME TIMER', 'QUERY DEADTIME TIMER'"} },  
    { "name": "dali/0/device/1/instance/0/timer/report",      "dataType": 5/* UInt8 */,    "int_value": 0,                            "metadata":{"description":"[RWP]If the report timer is set, it shall trigger an event every tReport even if the value has not
                                                                                                                                                                changed, dali cmd 'SET REPORT TIMER', 'QUERY REPORT TIMER'"} },  
    { "name": "dali/0/device/1/instance/0/timer/hold",        "dataType": 5/* UInt8 */,    "int_value": 0,                            "metadata":{"description":"[RWP]Timeout value, which shall be (re)started each time movement is detected, 
                                                                                                                                                                dali cmd 'SET HOLD TIMER', 'QUERY HOLD TIMER'"} },
    { "name": "dali/0/device/1/instance/1/type",              "dataType": 12/* String */,  "string_value": "LIGHT-SENSOR",            "metadata":{"description":"[R]Device instance type, dali cmd 'QUERY INSTANCE TYPE',
                                                                                                                                                                values = ['PUSH-BUTTON', 'ABSOLUTE-INPUT-DEVICE', 'OCCUPANCY-SENSOR', 'LIGHT-SENSOR']"} },
    { "name": "dali/0/device/1/instance/1/value",             "dataType": 6/* UInt16 */,   "int_value": 0,                            "metadata":{"description":"[R]Dali light sensor illuminance value, dali cmd 'QUERY INPUT VALUE'"} },
    { "name": "dali/0/device/1/instance/1/filter",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 8,
                        "columns": ["illuminance"],
                        "types": [11], /* Boolean */
                        "rows": [ {"elements":[{"boolean_value": true}]} ] }, 
      "metadata":{"description":"[RWP]Dali device enabled states, dali cmd 'SET EVENT FILTER', 'QUERY EVENT FILTER 0-7'"} },        
    { "name": "dali/0/device/1/instance/1/timer/deadtime",    "dataType": 5/* UInt8 */,    "int_value": 0,                            "metadata":{"description":"[RWP]If the deadtime timer is set, the instance shall not send out an event until the deadtime timer
                                                                                                                                                                has expired, dali cmd 'SET DEADTIME TIMER', 'QUERY DEADTIME TIMER'"} },  
    { "name": "dali/0/device/1/instance/1/timer/report",      "dataType": 5/* UInt8 */,    "int_value": 0,                            "metadata":{"description":"[RWP]If the report timer is set, it shall trigger an event every tReport even if the value has not
                                                                                                                                                                changed, dali cmd 'SET REPORT TIMER', 'QUERY REPORT TIMER'"} },
    { "name": "dali/0/device/1/instance/1/hysteresis",        "dataType": 5/* UInt8 */,    "int_value": 0,                            "metadata":{"description":"[RWP]Precentage from value when illuminance was updated, max value = 25%, 
                                                                                                                                                                dali cmd 'SET HYSTERESIS', 'QUERY HYSTERESIS'"} },
    { "name": "dali/0/device/1/instance/1/hysteresisMin",     "dataType": 5/* UInt8 */,    "int_value": 0,                            "metadata":{"description":"[RWP]Absolute value when illuminance was updated, 
                                                                                                                                                                dali cmd 'SET HYSTERESIS MIN', 'QUERY HYSTERESIS MIN'"} },
  ]
         
}
```

## PLC device dali death example
> spBv1.0/plc/DDEATH/abba2020/deba0006 

```json
{
"timestamp": 1486144502122,
"metrics": [  
    { "name": "bdSeq",                                  "dataType": 8/* Uint64 */,   "long_value": 0,                    "metadata":{"description":"[R]Birth-death sequence, 'online' - [DBIRTH > DDEATH], 'offline' - [DBIRTH <= DDEATH]  "} },  
]
}
```