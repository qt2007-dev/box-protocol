## BOX device dali birth example
> spBv1.0/box/DBIRTH/abba2020/deba0006 

```json
{
"timestamp": 1486144502122,
"seq": 0,
"metrics": [
    { "name": "bdSeq",                                  "dataType": 8/* Uint64 */,   "long_value": 0,                    "metadata":{"description":"[R]Birth-death sequence, 'online' - [DBIRTH > DDEATH], 'offline' - [DBIRTH <= DDEATH]"} },
    { "name": "control/reboot",                         "dataType": 11/* Boolean */, "boolean_value": false,             "metadata":{"description":"[W]Software reboot, send 'true' for reboot"} },
    { "name": "control/rebirth",                        "dataType": 11/* Boolean */, "boolean_value": false,             "metadata":{"description":"[W]Rebirth, send 'true' for receive birth message again"} },
    { "name": "control/firmware/new",                   "dataType": 17/* Bytes */,   "bytes_value":"", "is_null": true,  "metadata":{"description":"[W]Receive new firmware, firmware send in Base64 format, in birth always null"} },
    { "name": "control/metrics/save",                   "dataType": 11/* Boolean */, "boolean_value": true,              "metadata":{"description":"[RWP]Save metrics states after reboot, send 'true' for enable"} },
    { "name": "control/metrics/metadata",               "dataType": 11/* Boolean */, "boolean_value": true,              "metadata":{"description":"[RWP]Show metrics metadata in birth, send 'true' for enable"} },
    { "name": "control/group",                          "dataType": 12/* String */,  "string_value": "dali",             "metadata":{"description":"[RWP]Global group, can be used instead id in topics and scenarios"} },

    { "name": "info/hardware/vendor",                   "dataType": 12/* String */,  "string_value": "QuintTech" ,       "metadata":{"description":"[R]Vendor name, hardcoded by vendor"} },
    { "name": "info/hardware/model",                    "dataType": 12/* String */,  "string_value": "stm32g474ce",      "metadata":{"description":"[R]Mcu model, hardcoded by vendor"} },
    { "name": "info/firmware/version",                  "dataType": 12/* String */,  "string_value": "0.1.220527.84852", "metadata":{"description":"[R]Firmware version, MAJOR.MINOR.buildOrCommit"} },
    { "name": "info/type",                              "dataType": 12/* String */,  "string_value": "DALI 2",           "metadata":{"description":"[R]Device type, hardcoded by vendor"} },
    { "name": "info/id",                                "dataType": 12/* String */,  "string_value": "deba0006",         "metadata":{"description":"[R]Short device id"} },
    { "name": "info/error",                             "dataType": 12/* String */,  "string_value": "",                 "metadata":{"description":"[R]Last error message"} },

    { "name": "sensors/temperature",                    "dataType": 1/* Int8 */,     "int_value": 22,                    "metadata":{"description":"[R]Temperature sensor in mcu, value in Celsius"} },

    { "name": "ref/dali/color/xy",
      "dataType": 19, /* Template */
      "template_value":{ "version": "color",
                         "is_definition": true,
                         "metrics":[
                          { "name": "x",            "dataType": 6  /* UInt16 */, "metadata":{"description":"Gear x color"}},
                          { "name": "y",            "dataType": 6  /* UInt16 */, "metadata":{"description":"Gear y color"}}
                        ] }, 
        "metadata":{"description":"Template definition xy color type"} },

    { "name": "ref/dali/color/temperature",
      "dataType": 19, /* Template */
      "template_value":{ "version": "color",
                         "is_definition": true,
                         "metrics":[
                          { "name": "temperature",  "dataType": 6  /* UInt16 */, 
                            "properties":{ "keys": ["phy-warmest","warmest","phy-coolest","coolest"], 
                              "values": [{"type":6, "int_value": 1},{"type":6, "int_value": 1},{"type":6, "int_value": 65535},{"type":6, "int_value": 65535}] }, 
                            "metadata":{"description":"Gear color temperature"}}
                        ] }, 
        "metadata":{"description":"Template definition temperature color type"} },

    { "name": "ref/dali/color/rgbwaf",
      "dataType": 19, /* Template */
      "template_value":{ "version": "color",
                         "is_definition": true,
                         "metrics":[
                          { "name": "red",          "dataType": 5  /* UInt8 */, "metadata":{"description":"Gear red color"}   },
                          { "name": "green",        "dataType": 5  /* UInt8 */, "metadata":{"description":"Gear green color"} },
                          { "name": "blue",         "dataType": 5  /* UInt8 */, "metadata":{"description":"Gear blue color"}  },
                          { "name": "white",        "dataType": 5  /* UInt8 */, "metadata":{"description":"Gear white color"} },
                          { "name": "amber",        "dataType": 5  /* UInt8 */, "metadata":{"description":"Gear amber color"} },
                          { "name": "free",         "dataType": 5  /* UInt8 */, "metadata":{"description":"Gear free color"}  }
                        ] }, 
        "metadata":{"description":"Template definition rgbwaf color type"} },                   

    { "name": "ref/dali/level",
      "dataType": 19, /* Template */
      "template_value":{ "version": "level",
                         "is_definition": true,
                         "metrics":[
                          { "name": "dim",          "dataType": 5   /* UInt8 */, "properties":{ "keys": ["phy","min","max"], "values": [{"type":5, "int_value": 0},{"type":5, "int_value": 0},{"type":5, "int_value": 254}] },
                                                    "metadata": {"description":"Gear dim level, values = [0-255], value 255(MASK) stop running fade"}},
                          { "name": "color",        
                            "dataType": 19  /* Template */, 
                            "metadata":{"description":"Multi template color control metric, allow ref/dali/color/* template types"},
                            "template_value": {
                             "version" : "color",
                             "template_ref": null,
                             "is_definition": false,
                             "metrics": []
                            }}
                        ] }, 
        "metadata":{"description":"Template definition gear current levels"} },

    { "name": "ref/dali/fade",
      "dataType": 19, /* Template */
      "template_value":{ "version": "fade",
                         "is_definition": true,
                         "metrics":[
                            { "name": "time",        "dataType": 5  /* UInt8 */, "metadata":{"description":"Gear fade time, values = [0-15]"} },
                            { "name": "rate",        "dataType": 5  /* UInt8 */, "metadata":{"description":"Gear fade rate, values = [1-15]"} }
                        ] }, 
        "metadata":{"description":"Template definition gear fade"} },

    { "name": "ref/dali/scenes",
      "dataType": 19, /* Template */
      "template_value":{ "version": "scenes",
                         "is_definition": true,
                         "metrics":[
                          { "name": "0",        "dataType": 19  /* Template */,
                            "template_value": {
                              "version" : "level",
                              "template_ref": null,
                              "is_definition": false,
                              "metrics": []
                            },
                            "metadata":{"description":"Scene 0 level"}},
                          { "name": "1",        "dataType": 19  /* Template */, 
                            "template_value": {
                              "version" : "level",
                              "template_ref": null,
                              "is_definition": false,
                              "metrics": []
                            },
                            "metadata":{"description":"Scene 1 level"}},
                          { "name": "2",        "dataType": 19  /* Template */,
                            "template_value": {
                              "version" : "level",
                              "template_ref": null,
                              "is_definition": false,
                              "metrics": []
                            },
                            "metadata":{"description":"Scene 2 level"}},
                          { "name": "3",        "dataType": 19  /* Template */,
                            "template_value": {
                              "version" : "level",
                              "template_ref": null,
                              "is_definition": false,
                              "metrics": []
                            },
                            "metadata":{"description":"Scene 3 level"}},
                          { "name": "4",        "dataType": 19  /* Template */,
                            "template_value": {
                              "version" : "level",
                              "template_ref": null,
                              "is_definition": false,
                              "metrics": []
                            },
                            "metadata":{"description":"Scene 4 level"}},
                          { "name": "5",        "dataType": 19  /* Template */,
                            "template_value": {
                              "version" : "level",
                              "template_ref": null,
                              "is_definition": false,
                              "metrics": []
                            },
                            "metadata":{"description":"Scene 5 level"}},
                          { "name": "6",        "dataType": 19  /* Template */,
                            "template_value": {
                              "version" : "level",
                              "template_ref": null,
                              "is_definition": false,
                              "metrics": []
                            },
                            "metadata":{"description":"Scene 6 level"}},
                          { "name": "7",        "dataType": 19  /* Template */,
                            "template_value": {
                              "version" : "level",
                              "template_ref": null,
                              "is_definition": false,
                              "metrics": []
                            },
                            "metadata":{"description":"Scene 7 level"}},
                          { "name": "8",        "dataType": 19  /* Template */,
                            "template_value": {
                              "version" : "level",
                              "template_ref": null,
                              "is_definition": false,
                              "metrics": []
                            },
                            "metadata":{"description":"Scene 8 level"}},
                          { "name": "9",        "dataType": 19  /* Template */,
                            "template_value": {
                              "version" : "level",
                              "template_ref": null,
                              "is_definition": false,
                              "metrics": []
                            },
                            "metadata":{"description":"Scene 9 level"}},
                          { "name": "10",       "dataType": 19  /* Template */,
                            "template_value": {
                              "version" : "level",
                              "template_ref": null,
                              "is_definition": false,
                              "metrics": []
                            },
                            "metadata":{"description":"Scene 10 level"}},
                          { "name": "11",       "dataType": 19  /* Template */,
                            "template_value": {
                              "version" : "level",
                              "template_ref": null,
                              "is_definition": false,
                              "metrics": []
                            },
                            "metadata":{"description":"Scene 11 level"}},
                          { "name": "12",       "dataType": 19  /* Template */,
                            "template_value": {
                              "version" : "level",
                              "template_ref": null,
                              "is_definition": false,
                              "metrics": []
                            },
                            "metadata":{"description":"Scene 12 level"}},
                          { "name": "13",       "dataType": 19  /* Template */,
                            "template_value": {
                              "version" : "level",
                              "template_ref": null,
                              "is_definition": false,
                              "metrics": []
                            },
                            "metadata":{"description":"Scene 13 level"}},
                          { "name": "14",       "dataType": 19  /* Template */,
                            "template_value": {
                              "version" : "level",
                              "template_ref": null,
                              "is_definition": false,
                              "metrics": []
                            },
                            "metadata":{"description":"Scene 14 level"}},
                          { "name": "15",       "dataType": 19  /* Template */,
                            "template_value": {
                              "version" : "level",
                              "template_ref": null,
                              "is_definition": false,
                              "metrics": []
                            },
                            "metadata":{"description":"Scene 15 level"}}
                        ] }, 
        "metadata":{"description":"Template definition gear scenes control"} },

    /* Bus 0 control metrics */
    { "name": "dali/0/source",                          "dataType": 11/* Boolean */, "boolean_value": true,              "metadata":{"description":"[RW]Dali bus power source state, 'true' - enabled, 'false' - disabled"} },    
    { "name": "dali/0/source/shortCurrent",             "dataType": 11/* Boolean */, "boolean_value": false,             "metadata":{"description":"[R]Dali bus power source short current"} },    
    { "name": "dali/0/source/voltage",                  "dataType": 6/* UInt16 */,   "int_value": 5635,                  "metadata":{"description":"[R]Dali bus voltage, value in mV"} },    
    { "name": "dali/0/source/current",                  "dataType": 6/* UInt16 */,   "int_value": 5635,                  "metadata":{"description":"[R]Dali bus current, value in mA"} },    

    { "name": "dali/0/gear/swap",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 2,
                        "columns": ["from", "target"],
                        "types": [5,5], /* UInt8, UInt8 */
                        "rows": [ {"elements":[{"int_value": 23}, {"int_value": 34}]} ] },                                 
      "metadata":{"description":"[W]Dali swap short address on bus"} },
    
    { "name": "dali/0/cmd",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 4,
                        "columns": ["addr-type", "addr", "cmd", "value"],
                        "types": [12,5,12,5], /* String, UInt8, String, UInt8 */
                        "rows": [ {"elements":[{"string_value": "group","int_value": 10,"string_value": "dim","int_value": 240}]} ] }, 
      "metadata":{"description":"[W]Dali send command to bus, 'addr-type' list of values = ['broadcast', 'group', 'gear'], 'cmd' list of values = ['dim', 'scene', 'fade-time', 'fade-rate', 'step-up', 'step-down', 'on-and-step-up', 'step-down-and-off']"} },                    

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
      "metadata":{"description":"[RWP]Dali group contained gear list"} }, 
    { "name": "dali/0/group/1",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 1,
                        "columns": ["gear"],
                        "types": [5], /* UInt8 */
                        "rows": [ ] },                                                  
      "metadata":{"description":"[RWP]Dali group contained gear list"} }, 
    { "name": "dali/0/group/2",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 1,
                        "columns": ["gear"],
                        "types": [5], /* UInt8 */
                        "rows": [ ] },                                                  
      "metadata":{"description":"[RWP]Dali group contained gear list"} }, 
    { "name": "dali/0/group/3",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 1,
                        "columns": ["gear"],
                        "types": [5], /* UInt8 */
                        "rows": [ ] },                                                  
      "metadata":{"description":"[RWP]Dali group contained gear list"} }, 
    { "name": "dali/0/group/4",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 1,
                        "columns": ["gear"],
                        "types": [5], /* UInt8 */
                        "rows": [ ] },                                                  
      "metadata":{"description":"[RWP]Dali group contained gear list"} }, 
    { "name": "dali/0/group/5",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 1,
                        "columns": ["gear"],
                        "types": [5], /* UInt8 */
                        "rows": [ ] },                                                  
      "metadata":{"description":"[RWP]Dali group contained gear list"} }, 
    { "name": "dali/0/group/6",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 1,
                        "columns": ["gear"],
                        "types": [5], /* UInt8 */
                        "rows": [ ] },                                                  
      "metadata":{"description":"[RWP]Dali group contained gear list"} }, 
    { "name": "dali/0/group/7",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 1,
                        "columns": ["gear"],
                        "types": [5], /* UInt8 */
                        "rows": [ ] },                                                  
      "metadata":{"description":"[RWP]Dali group contained gear list"} }, 
    { "name": "dali/0/group/8",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 1,
                        "columns": ["gear"],
                        "types": [5], /* UInt8 */
                        "rows": [ ] },                                                  
      "metadata":{"description":"[RWP]Dali group contained gear list"} }, 
    { "name": "dali/0/group/9",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 1,
                        "columns": ["gear"],
                        "types": [5], /* UInt8 */
                        "rows": [ ] },                                                  
      "metadata":{"description":"[RWP]Dali group contained gear list"} }, 
    { "name": "dali/0/group/10",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 1,
                        "columns": ["gear"],
                        "types": [5], /* UInt8 */
                        "rows": [ ] },                                                  
      "metadata":{"description":"[RWP]Dali group contained gear list"} }, 
    { "name": "dali/0/group/11",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 1,
                        "columns": ["gear"],
                        "types": [5], /* UInt8 */
                        "rows": [ ] },                                                  
      "metadata":{"description":"[RWP]Dali group contained gear list"} }, 
    { "name": "dali/0/group/12",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 1,
                        "columns": ["gear"],
                        "types": [5], /* UInt8 */
                        "rows": [ ] },                                                  
      "metadata":{"description":"[RWP]Dali group contained gear list"} }, 
    { "name": "dali/0/group/13",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 1,
                        "columns": ["gear"],
                        "types": [5], /* UInt8 */
                        "rows": [ ] },                                                  
      "metadata":{"description":"[RWP]Dali group contained gear list"} }, 
    { "name": "dali/0/group/14",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 1,
                        "columns": ["gear"],
                        "types": [5], /* UInt8 */
                        "rows": [ ] },                                                  
      "metadata":{"description":"[RWP]Dali group contained gear list"} }, 
    { "name": "dali/0/group/15",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 1,
                        "columns": ["gear"],
                        "types": [5], /* UInt8 */
                        "rows": [ ] },                                                  
      "metadata":{"description":"[RWP]Dali group contained gear list"} }, 
   
    /* Control gear metrics */
    /* dali/{bus}/gear/{gear}  */  
    { "name": "dali/0/gear/0/id",                       "dataType": 12/* String */,  "string_value": "0000-1121",        "metadata":{"description":"[R]Gear id stored in memory bank 0"} },
    { "name": "dali/0/gear/0/identify",                 "dataType": 11/* Boolean */, "boolean_value": false,             "metadata":{"description":"[W]Start gear 10s identification procedure"} },
    { "name": "dali/0/gear/0/type",                     "dataType": 12/* String */,  "string_value": "LED",              "metadata":{"description":"[R]Gear type, values = ['NONE', 'FLUORESCENT', 'EMERGENCY', 'HID', 'HALOGEN', 'INCANDESCENT', 'CONVERTOR', 'LED', 'RELAY', 'COLOR'], can be multiple types at the same time ('LED|COLOR')"} }, 
    { "name": "dali/0/gear/0/features",                 "dataType": 12/* String */,  "string_value": "",                 "metadata":{"description":"[R]Gear color type features, values = ['XY', 'TEMPERATURE', 'RGBWAF'], can be multiple features at the same time ('XY|RGBWAF')"} }, 
    { "name": "dali/0/gear/0/status",                   "dataType": 12/* String */,  "string_value": "ok",               "metadata":{"description":"[R]Control gear status, values = ['ok', 'control-failure', 'lamp-failure', 'short-circuit', 'open-circuit', 'current-protector', 'thermal-shutdown', 'thermal-overload', 'fading'], can be multiple status at the same time ('lamp-failure|open-circuit')"} }, 
    { "name": "dali/0/gear/0/level",
      "dataType": 19, /* Template */
      "template_value":{ "version": "level",
                         "is_definition": false,
                         "template_ref": "ref/dali/level",
                         "metrics":[
                          { "name": "dim", "dataType": 5   /* UInt8 */, "int_value": 0, 
                            "properties":{ "keys": ["phy","min","max"], "values": [{"type": 5, "int_value":78},{"type": 5, "int_value":100},{"type": 5, "int_value":254}] },
                            "metadata": {"description":"Gear dim level, values = [0-255], value 255(MASK) stop running fade"} }
                        ] }, 
      "metadata":{"description":"[RW]Gear current level"} },

    { "name": "dali/0/gear/0/level/powerOn",
      "dataType": 19, /* Template */
      "template_value":{ "version": "level",
                         "is_definition": false,
                         "template_ref": "ref/dali/level",
                         "metrics":[
                          { "name": "dim",  "dataType": 5   /* UInt8 */, "int_value": 254, 
                            "metadata": {"description":"Gear dim level, values = [0-255], value 255(MASK) stop running fade"} }
                        ] }, 
      "metadata":{"description":"[RWP]Gear power on level, value 255(MASK) equal last light level"} },

    { "name": "dali/0/gear/0/level/failure",
      "dataType": 19, /* Template */
      "template_value":{ "version": "level",
                         "is_definition": false,
                         "template_ref": "ref/dali/level",
                         "metrics":[
                          { "name": "dim",  "dataType": 5   /* UInt8 */, "int_value": 254, 
                            "metadata": {"description":"Gear dim level, values = [0-255], value 255(MASK) stop running fade"} }
                        ] }, 
      "metadata":{"description":"[RWP]Gear bus failure dim level, value 255(MASK) disable react to bus failure"} },      

    { "name": "dali/0/gear/0/fade",    
      "dataType": 19 /* Template */,
      "template_value":{  "version": "fade",
                          "is_definition": false,
                          "template_ref": "ref/dali/fade",
                          "metrics":[
                            { "name": "time", "dataType": 5  /* UInt8 */, "int_value": 1,
                              "metadata":{"description":"Gear fade time, values = [0-15]"}},
                            { "name": "rate", "dataType": 5  /* UInt8 */, "int_value": 5,
                              "metadata":{"description":"Gear fade rate, values = [1-15]"}} ] },
      "metadata":{"description":"[RWP]Gear fade"} },

    { "name": "dali/0/gear/0/scenes",  
      "dataType": 19 /* Template */,
      "metadata":{"description":"Template definition gear scenes control"},
      "template_value":{ 
      "version": "scenes",
      "is_definition": false,
      "template_ref": "ref/dali/scenes",
      "metrics":[
        { "name": "0",        
          "dataType": 19  /* Template */,
          "metadata":{"description":"Scene 0 level"},
          "template_value":{ "version": "level",
                             "is_definition": false,
                             "template_ref": "ref/dali/level",
                             "metrics":[
                              { "name": "dim",  "dataType": 5   /* UInt8 */, "int_value": 254, 
                                "metadata": {"description":"Gear dim level, values = [0-255], value 255(MASK) stop running fade"} } ] }},
        { "name": "1",        
          "dataType": 19  /* Template */,
          "metadata":{"description":"Scene 1 level"},
          "template_value":{ "version": "level",
                             "is_definition": false,
                             "template_ref": "ref/dali/level",
                             "metrics":[
                              { "name": "dim",  "dataType": 5   /* UInt8 */, "int_value": 254, 
                                "metadata": {"description":"Gear dim level, values = [0-255], value 255(MASK) stop running fade"} } ] }},
        { "name": "2",        
          "dataType": 19  /* Template */,
          "metadata":{"description":"Scene 2 level"},
          "template_value":{ "version": "level",
                             "is_definition": false,
                             "template_ref": "ref/dali/level",
                             "metrics":[
                              { "name": "dim",  "dataType": 5   /* UInt8 */, "int_value": 254, 
                                "metadata": {"description":"Gear dim level, values = [0-255], value 255(MASK) stop running fade"} } ] }},
        { "name": "3",        
          "dataType": 19  /* Template */,
          "metadata":{"description":"Scene 3 level"},
          "template_value":{ "version": "level",
                             "is_definition": false,
                             "template_ref": "ref/dali/level",
                             "metrics":[
                              { "name": "dim",  "dataType": 5   /* UInt8 */, "int_value": 254, 
                                "metadata": {"description":"Gear dim level, values = [0-255], value 255(MASK) stop running fade"} } ] }},
        { "name": "4",        
          "dataType": 19  /* Template */,
          "metadata":{"description":"Scene 4 level"},
          "template_value":{ "version": "level",
                             "is_definition": false,
                             "template_ref": "ref/dali/level",
                             "metrics":[
                              { "name": "dim",  "dataType": 5   /* UInt8 */, "int_value": 254, 
                                "metadata": {"description":"Gear dim level, values = [0-255], value 255(MASK) stop running fade"} } ] }},
        { "name": "5",        
          "dataType": 19  /* Template */,
          "metadata":{"description":"Scene 5 level"},
          "template_value":{ "version": "level",
                             "is_definition": false,
                             "template_ref": "ref/dali/level",
                             "metrics":[
                              { "name": "dim",  "dataType": 5   /* UInt8 */, "int_value": 254, 
                                "metadata": {"description":"Gear dim level, values = [0-255], value 255(MASK) stop running fade"} } ] }},
        { "name": "6",        
          "dataType": 19  /* Template */,
          "metadata":{"description":"Scene 6 level"},
          "template_value":{ "version": "level",
                             "is_definition": false,
                             "template_ref": "ref/dali/level",
                             "metrics":[
                              { "name": "dim",  "dataType": 5   /* UInt8 */, "int_value": 254, 
                                "metadata": {"description":"Gear dim level, values = [0-255], value 255(MASK) stop running fade"} } ] }},
        { "name": "7",        
          "dataType": 19  /* Template */,
          "metadata":{"description":"Scene 7 level"},
          "template_value":{ "version": "level",
                             "is_definition": false,
                             "template_ref": "ref/dali/level",
                             "metrics":[
                              { "name": "dim",  "dataType": 5   /* UInt8 */, "int_value": 254, 
                                "metadata": {"description":"Gear dim level, values = [0-255], value 255(MASK) stop running fade"} } ] }},
        { "name": "8",        
          "dataType": 19  /* Template */,
          "metadata":{"description":"Scene 8 level"},
          "template_value":{ "version": "level",
                             "is_definition": false,
                             "template_ref": "ref/dali/level",
                             "metrics":[
                              { "name": "dim",  "dataType": 5   /* UInt8 */, "int_value": 254, 
                                "metadata": {"description":"Gear dim level, values = [0-255], value 255(MASK) stop running fade"} } ] }},
        { "name": "9",        
          "dataType": 19  /* Template */,
          "metadata":{"description":"Scene 9 level"},
          "template_value":{ "version": "level",
                             "is_definition": false,
                             "template_ref": "ref/dali/level",
                             "metrics":[
                              { "name": "dim",  "dataType": 5   /* UInt8 */, "int_value": 254, 
                                "metadata": {"description":"Gear dim level, values = [0-255], value 255(MASK) stop running fade"} } ] }},
        { "name": "10",       
          "dataType": 19  /* Template */,
          "metadata":{"description":"Scene 10 level"},
          "template_value":{ "version": "level",
                             "is_definition": false,
                             "template_ref": "ref/dali/level",
                             "metrics":[
                              { "name": "dim",  "dataType": 5   /* UInt8 */, "int_value": 254, 
                                "metadata": {"description":"Gear dim level, values = [0-255], value 255(MASK) stop running fade"} } ] }},
        { "name": "11",       
          "dataType": 19  /* Template */,
          "metadata":{"description":"Scene 11 level"},
          "template_value":{ "version": "level",
                             "is_definition": false,
                             "template_ref": "ref/dali/level",
                             "metrics":[
                              { "name": "dim",  "dataType": 5   /* UInt8 */, "int_value": 254, 
                                "metadata": {"description":"Gear dim level, values = [0-255], value 255(MASK) stop running fade"} } ] }},
        { "name": "12",       
          "dataType": 19  /* Template */,
          "metadata":{"description":"Scene 12 level"},
          "template_value":{ "version": "level",
                             "is_definition": false,
                             "template_ref": "ref/dali/level",
                             "metrics":[
                              { "name": "dim",  "dataType": 5   /* UInt8 */, "int_value": 254, 
                                "metadata": {"description":"Gear dim level, values = [0-255], value 255(MASK) stop running fade"} } ] }},
        { "name": "13",       
          "dataType": 19  /* Template */,
          "metadata":{"description":"Scene 13 level"},
          "template_value":{ "version": "level",
                             "is_definition": false,
                             "template_ref": "ref/dali/level",
                             "metrics":[
                              { "name": "dim",  "dataType": 5   /* UInt8 */, "int_value": 254, 
                                "metadata": {"description":"Gear dim level, values = [0-255], value 255(MASK) stop running fade"} } ] }},
        { "name": "14",       
          "dataType": 19  /* Template */,
          "metadata":{"description":"Scene 14 level"},
          "template_value":{ "version": "level",
                             "is_definition": false,
                             "template_ref": "ref/dali/level",
                             "metrics":[
                              { "name": "dim",  "dataType": 5   /* UInt8 */, "int_value": 254, 
                                "metadata": {"description":"Gear dim level, values = [0-255], value 255(MASK) stop running fade"} } ] }},
        { "name": "15",       
          "dataType": 19  /* Template */,
          "metadata":{"description":"Scene 15 level"},
          "template_value":{ "version": "level",
                             "is_definition": false,
                             "template_ref": "ref/dali/level",
                             "metrics":[
                              { "name": "dim",  "dataType": 5   /* UInt8 */, "int_value": 254, 
                                "metadata": {"description":"Gear dim level, values = [0-255], value 255(MASK) stop running fade"} } ] }} ] },
      "metadata":{"description":"[RWP]Dali gear scenes"} },

    /*DALI Color Temperature control gear*/
    { "name": "dali/0/gear/1/id",                       "dataType": 12/* String */,  "string_value": "0000-1122",        "metadata":{"description":"[R]Gear id stored in memory bank 0"} },
    { "name": "dali/0/gear/1/identify",                 "dataType": 11/* Boolean */, "boolean_value": false,             "metadata":{"description":"[W]Start gear 10s identification procedure"} },
    { "name": "dali/0/gear/1/type",                     "dataType": 12/* String */,  "string_value": "COLOR",            "metadata":{"description":"[R]Gear type, values = ['NONE', 'FLUORESCENT', 'EMERGENCY', 'HID', 'HALOGEN', 'INCANDESCENT', 'CONVERTOR', 'LED', 'RELAY', 'COLOR'], can be multiple types at the same time ('LED|COLOR')"} }, 
    { "name": "dali/0/gear/1/features",                 "dataType": 12/* String */,  "string_value": "XY|TEMPERATURE",   "metadata":{"description":"[R]Gear color type features, values = ['XY', 'TEMPERATURE', 'RGBWAF'], can be multiple features at the same time ('XY|RGBWAF')"} }, 
    { "name": "dali/0/gear/1/status",                   "dataType": 12/* String */,  "string_value": "ok",               "metadata":{"description":"[R]Control gear status, values = ['ok', 'control-failure', 'lamp-failure', 'short-circuit', 'open-circuit', 'current-protector', 'thermal-shutdown', 'thermal-overload', 'fading'], can be multiple status at the same time ('lamp-failure|open-circuit')"} }, 
    { "name": "dali/0/gear/1/level",
      "dataType": 19, /* Template */
      "template_value":{ "version": "level",
                         "is_definition": false,
                         "template_ref": "ref/dali/level",
                         "metrics":[
                          { "name": "dim", "dataType": 5   /* UInt8 */, "int_value": 0, 
                            "properties":{ "keys": ["phy","min","max"], "values": [{"type": 5, "int_value":78},{"type": 5, "int_value":100},{"type": 5, "int_value":254}] },
                            "metadata": {"description":"Gear dim level, values = [0-255], value 255(MASK) stop running fade"} },
                          { "name": "color",
                            "dataType": 19, /* Template */
                            "metadata":{"description":"Multi template color control metric, allow ref/dali/color/* template types"},
                            "template_value":{ "version": "color",
                                               "is_definition": false,
                                               "template_ref": "ref/dali/color/temperature",
                                               "metrics":[
                                                { "name": "temperature",  "dataType": 6  /* UInt16 */, "int_value": 2700, 
                                                  "properties":{ "keys": ["phy-warmest","warmest","phy-coolest","coolest"], 
                                                    "values": [{"type": 6, "int_value":2300},{"type": 6, "int_value":2300},{"type": 6, "int_value":5000}, {"type": 6, "int_value":5000}] },
                                                  "metadata":{"description":"Gear color temperature"}}
                                              ] } }
                        ] }, 
      "metadata":{"description":"[RW]Gear current level"} },

    { "name": "dali/0/gear/1/level/powerOn",
      "dataType": 19, /* Template */
      "template_value":{ "version": "level",
                         "is_definition": false,
                         "template_ref": "ref/dali/level",
                         "metrics":[
                          { "name": "dim",  "dataType": 5   /* UInt8 */, "int_value": 254,
                            "metadata": {"description":"Gear dim level, values = [0-255], value 255(MASK) stop running fade"}},
                          { "name": "color",
                            "dataType": 19, /* Template */
                            "metadata":{"description":"Multi template color control metric, allow ref/dali/color/* template types"},
                            "template_value":{ "version": "color",
                                               "is_definition": false,
                                               "template_ref": "ref/dali/color/temperature",
                                               "metrics":[
                                                { "name": "temperature", "dataType": 6  /* UInt16 */, "int_value": 2700,
                                                  "metadata":{"description":"Gear color temperature"} }
                                              ] } }
                        ] }, 
      "metadata":{"description":"[RWP]Gear power on level, value 255(MASK) equal last light level"} },

    { "name": "dali/0/gear/1/level/failure",
      "dataType": 19, /* Template */
      "template_value":{ "version": "level",
                         "is_definition": false,
                         "template_ref": "ref/dali/level",
                         "metrics":[
                          { "name": "dim", "dataType": 5   /* UInt8 */, "int_value": 254,
                             "metadata": {"description":"Gear dim level, values = [0-255], value 255(MASK) stop running fade"}},
                          { "name": "color",
                            "dataType": 19, /* Template */
                            "metadata":{"description":"Multi template color control metric, allow ref/dali/color/* template types"},
                            "template_value":{ "version": "color",
                                               "is_definition": false,
                                               "template_ref": "ref/dali/color/temperature",
                                               "metrics":[
                                                { "name": "temperature", "dataType": 6  /* UInt16 */, "int_value": 2700,
                                                  "metadata":{"description":"Gear color temperature"} }
                                              ] }
                                             }

                        ] }, 
      "metadata":{"description":"[RWP]Gear bus failure level, value 255(MASK) disable react to bus failure"} },      

    { "name": "dali/0/gear/1/fade",    
      "dataType": 19 /* Template - ref/dali/fade */,
      "template_value":{  "version": "fade",
                          "is_definition": false,
                          "template_ref": "ref/dali/fade",
                          "metrics":[
                          { "name": "time", "dataType": 5  /* UInt8 */, "int_value": 1, "metadata":{"description":"Gear fade time, values = [0-15]"}},
                          { "name": "rate", "dataType": 5  /* UInt8 */, "int_value": 5, "metadata":{"description":"Gear fade rate, values = [1-15]"}} ] },
      "metadata":{"description":"[RWP]Gear fade"} },

    { "name": "dali/0/gear/1/scenes",  
      "dataType": 19 /* Template - ref/dali/scenes */,
      "metadata":{"description":"Template definition gear scenes control"},
      "template_value":{ "version": "scenes",
                         "is_definition": false,
                         "template_ref": "ref/dali/scenes",
                         "metrics":[
                           { "name": "0",        
                             "dataType": 19  /* Template */,
                             "metadata":{"description":"Scene 0 level"},
                             "template_value":{ "version": "level",
                                                "is_definition": false,
                                                "template_ref": "ref/dali/level",
                                                "metrics":[
                                                  { "name": "dim",  "dataType": 5   /* UInt8 */, "int_value": 254, 
                                                    "metadata": {"description":"Gear dim level, values = [0-255], value 255(MASK) stop running fade"} },
                                                  { "name": "color",
                                                    "dataType": 19, /* Template */
                                                    "metadata":{"description":"Multi template color control metric, allow ref/dali/color/* template types"},
                                                    "template_value":{ "version": "color",
                                                                      "is_definition": false,
                                                                      "template_ref": "ref/dali/color/temperature",
                                                                      "metrics":[
                                                                        { "name": "temperature", "dataType": 6  /* UInt16 */, "int_value": 2700,
                                                                          "metadata":{"description":"Gear color temperature"} }
                                                                     ] } } 
                                                             ] }},
                           /* 1...14 repeated */ 
                           { "name": "15",       
                             "dataType": 19  /* Template */,
                             "metadata":{"description":"Scene 15 level"},
                             "template_value":{ "version": "level",
                                                "is_definition": false,
                                                "template_ref": "ref/dali/level",
                                                "metrics":[
                                                  { "name": "dim",  "dataType": 5   /* UInt8 */, "int_value": 254, 
                                                    "metadata": {"description":"Gear dim level, values = [0-255], value 255(MASK) stop running fade"} },
                                                  { "name": "color",
                                                    "dataType": 19, /* Template */
                                                    "metadata":{"description":"Multi template color control metric, allow ref/dali/color/* template types"},
                                                    "template_value":{ "version": "color",
                                                                      "is_definition": false,
                                                                      "template_ref": "ref/dali/color/temperature",
                                                                      "metrics":[
                                                                        { "name": "temperature", "dataType": 6  /* UInt16 */, "int_value": 2700,
                                                                          "metadata":{"description":"Gear color temperature"}}
                                                                     ] } } 
                                                             ] }} ] },
                         "metadata":{"description":"[RWP]Dali gear scenes"} },

    /*DALI Color RGBWAF control gear*/
    { "name": "dali/0/gear/2/id",                       "dataType": 12/* String */,  "string_value": "0000-1123",        "metadata":{"description":"[R]Gear id stored in memory bank 0"} },
    { "name": "dali/0/gear/2/identify",                 "dataType": 11/* Boolean */, "boolean_value": false,             "metadata":{"description":"[W]Start gear 10s identification procedure"} },
    { "name": "dali/0/gear/2/type",                     "dataType": 12/* String */,  "string_value": "COLOR",            "metadata":{"description":"[R]Gear type, values = ['NONE', 'FLUORESCENT', 'EMERGENCY', 'HID', 'HALOGEN', 'INCANDESCENT', 'CONVERTOR', 'LED', 'RELAY', 'COLOR'], can be multiple types at the same time ('LED|COLOR')"} }, 
    { "name": "dali/0/gear/2/features",                 "dataType": 12/* String */,  "string_value": "RGBWAF",           "metadata":{"description":"[R]Gear color type features, values = ['XY', 'TEMPERATURE', 'RGBWAF'], can be multiple features at the same time ('XY|RGBWAF')"} }, 
    { "name": "dali/0/gear/2/status",                   "dataType": 12/* String */,  "string_value": "ok",               "metadata":{"description":"[R]Control gear status, values = ['ok', 'control-failure', 'lamp-failure', 'short-circuit', 'open-circuit', 'current-protector', 'thermal-shutdown', 'thermal-overload', 'fading'], can be multiple status at the same time ('lamp-failure|open-circuit')"} }, 
    { "name": "dali/0/gear/2/level",
      "dataType": 19, /* Template */
      "template_value":{ "version": "level",
                         "is_definition": false,
                         "template_ref": "ref/dali/level",
                         "metrics":[
                          { "name": "dim", "dataType": 5   /* UInt8 */, "int_value": 0, 
                            "properties":{ "keys": ["phy","min","max"], "values": [{"type": 5, "int_value":78},{"type": 5, "int_value":100},{"type": 5, "int_value":254}] },
                            "metadata": {"description":"Gear dim level, values = [0-255], value 255(MASK) stop running fade"}},
                          { "name": "color",
                            "dataType": 19, /* Template */
                            "metadata":{"description":"Multi template color control metric, allow ref/dali/color/* template types"},
                            "template_value":{ "version": "color",
                                               "is_definition": false,
                                               "template_ref": "ref/dali/color/rgbwaf",
                                               "metrics":[
                                                { "name": "red",   "dataType": 5  /* UInt8 */, "int_value": 254,
                                                  "metadata":{"description":"Gear red color"}   },
                                                { "name": "green", "dataType": 5  /* UInt8 */, "int_value": 0  ,
                                                  "metadata":{"description":"Gear green color"} },
                                                { "name": "blue",  "dataType": 5  /* UInt8 */, "int_value": 0  ,
                                                  "metadata":{"description":"Gear blue color"}  },
                                                { "name": "white", "dataType": 5  /* UInt8 */, "int_value": 0  ,
                                                  "metadata":{"description":"Gear white color"} },
                                                { "name": "amber", "dataType": 5  /* UInt8 */, "int_value": 0  ,
                                                  "metadata":{"description":"Gear amber color"} },
                                                { "name": "free",  "dataType": 5  /* UInt8 */, "int_value": 0  ,
                                                  "metadata":{"description":"Gear free color"}  }
                                              ] } }
                        ] }, 
      "metadata":{"description":"[RW]Gear current level, values = [0-255], value 255(MASK) stop running fade"} },

    { "name": "dali/0/gear/2/level/powerOn",
      "dataType": 19, /* Template */
      "template_value":{ "version": "level",
                         "is_definition": false,
                         "template_ref": "ref/dali/level",
                         "metrics":[
                          { "name": "dim", "dataType": 5   /* UInt8 */, "int_value": 254,
                            "metadata": {"description":"Gear dim level, values = [0-255], value 255(MASK) stop running fade"} },
                          { "name": "color",
                            "dataType": 19, /* Template */
                            "metadata":{"description":"Multi template color control metric, allow ref/dali/color/* template types"},
                            "template_value":{ "version": "color",
                                               "is_definition": false,
                                               "template_ref": "ref/dali/color/rgbwaf",
                                               "metrics":[
                                                { "name": "red",   "dataType": 5  /* UInt8 */, "int_value": 254,
                                                  "metadata":{"description":"Gear red color"}   },
                                                { "name": "green", "dataType": 5  /* UInt8 */, "int_value": 0  ,
                                                  "metadata":{"description":"Gear green color"} },
                                                { "name": "blue",  "dataType": 5  /* UInt8 */, "int_value": 0  ,
                                                  "metadata":{"description":"Gear blue color"}  },
                                                { "name": "white", "dataType": 5  /* UInt8 */, "int_value": 0  ,
                                                  "metadata":{"description":"Gear white color"} },
                                                { "name": "amber", "dataType": 5  /* UInt8 */, "int_value": 0  ,
                                                  "metadata":{"description":"Gear amber color"} },
                                                { "name": "free",  "dataType": 5  /* UInt8 */, "int_value": 0  ,
                                                  "metadata":{"description":"Gear free color"}  }
                                              ] } }
                        ] }, 
      "metadata":{"description":"[RWP]Gear power on level, value 255(MASK) equal last light level"} },

    { "name": "dali/0/gear/2/level/failure",
      "dataType": 19, /* Template */
      "template_value":{ "version": "level",
                         "is_definition": false,
                         "template_ref": "ref/dali/level",
                         "metrics":[
                          { "name": "dim", "dataType": 5   /* UInt8 */, "int_value": 254, 
                            "metadata": {"description":"Gear dim level, values = [0-255], value 255(MASK) stop running fade"}},
                          { "name": "color",
                            "dataType": 19, /* Template */
                            "metadata":{"description":"Multi template color control metric, allow ref/dali/color/* template types"},
                            "template_value":{ "version": "color",
                                               "is_definition": false,
                                               "template_ref": "ref/dali/color/rgbwaf",
                                               "metrics":[
                                                { "name": "red",   "dataType": 5  /* UInt8 */,  "int_value": 254,
                                                  "metadata":{"description":"Gear red color"}   },
                                                { "name": "green", "dataType": 5  /* UInt8 */,  "int_value": 0  ,
                                                  "metadata":{"description":"Gear green color"} },
                                                { "name": "blue",  "dataType": 5  /* UInt8 */,  "int_value": 0  ,
                                                  "metadata":{"description":"Gear blue color"}  },
                                                { "name": "white", "dataType": 5  /* UInt8 */,  "int_value": 0  ,
                                                  "metadata":{"description":"Gear white color"} },
                                                { "name": "amber", "dataType": 5  /* UInt8 */,  "int_value": 0  ,
                                                  "metadata":{"description":"Gear amber color"} },
                                                { "name": "free",  "dataType": 5  /* UInt8 */,  "int_value": 0  ,
                                                  "metadata":{"description":"Gear free color"}  }
                                              ] } }

                        ] }, 
      "metadata":{"description":"[RWP]Gear bus failure level, value 255(MASK) disable react to bus failure"} },      

    { "name": "dali/0/gear/2/fade",    
      "dataType": 19 /* Template - ref/dali/fade */,
      "template_value":{  "version": "fade",
                          "is_definition": false,
                          "template_ref": "ref/dali/fade",
                          "metrics":[
                          { "name": "time", "dataType": 5  /* UInt8 */, "int_value": 1, "metadata":{"description":"Gear fade time, values = [0-15]"}},
                          { "name": "rate", "dataType": 5  /* UInt8 */, "int_value": 5, "metadata":{"description":"Gear fade rate, values = [1-15]"}} ] },
      "metadata":{"description":"[RWP]Gear fade"} },

    { "name": "dali/0/gear/2/scenes",  
      "dataType": 19 /* Template - ref/dali/scenes */,
      "metadata":{"description":"Template definition gear scenes control"},
      "template_value":{ "version": "scenes",
                         "is_definition": false,
                         "template_ref": "ref/dali/scenes",
                         "metrics":[
                           { "name": "0",        
                             "dataType": 19  /* Template */,
                             "metadata":{"description":"Scene 0 level"},
                             "template_value":{ "version": "level",
                                                "is_definition": false,
                                                "template_ref": "ref/dali/level",
                                                "metrics":[
                                                  { "name": "dim",  "dataType": 5   /* UInt8 */, "int_value": 254, 
                                                    "metadata": {"description":"Gear dim level, values = [0-255], value 255(MASK) stop running fade"} },
                                                  { "name": "color",
                                                    "dataType": 19, /* Template */
                                                    "metadata":{"description":"Multi template color control metric, allow ref/dali/color/* template types"},
                                                    "template_value":{ "version": "color",
                                                                      "is_definition": false,
                                                                      "template_ref": "ref/dali/color/rgbwaf",
                                                                      "metrics":[
                                                                        { "name": "red",   "dataType": 5  /* UInt8 */, "int_value": 254, 
                                                                          "metadata":{"description":"Gear red color"}   },
                                                                        { "name": "green", "dataType": 5  /* UInt8 */, "int_value": 0  , 
                                                                          "metadata":{"description":"Gear green color"} },
                                                                        { "name": "blue",  "dataType": 5  /* UInt8 */, "int_value": 0  , 
                                                                          "metadata":{"description":"Gear blue color"}  },
                                                                        { "name": "white", "dataType": 5  /* UInt8 */, "int_value": 0  , 
                                                                          "metadata":{"description":"Gear white color"} },
                                                                        { "name": "amber", "dataType": 5  /* UInt8 */, "int_value": 0  , 
                                                                          "metadata":{"description":"Gear amber color"} },
                                                                        { "name": "free",  "dataType": 5  /* UInt8 */, "int_value": 0  , 
                                                                          "metadata":{"description":"Gear free color"}  }
                                                                      ] } }
                                                             ] }},
                           /* 1...14 repeated */ 
                           { "name": "15",       
                             "dataType": 19  /* Template */,
                             "metadata":{"description":"Scene 15 level"},
                             "template_value":{ "version": "level",
                                                "is_definition": false,
                                                "template_ref": "ref/dali/level",
                                                "metrics":[
                                                  { "name": "dim",  "dataType": 5   /* UInt8 */, "int_value": 254, 
                                                    "metadata": {"description":"Gear dim level, values = [0-255], value 255(MASK) stop running fade"} },
                                                  { "name": "color",
                                                    "dataType": 19, /* Template */
                                                    "metadata":{"description":"Multi template color control metric, allow ref/dali/color/* template types"},
                                                    "template_value":{ "version": "color",
                                                                      "is_definition": false,
                                                                      "template_ref": "ref/dali/color/rgbwaf",
                                                                      "metrics":[
                                                                        { "name": "red",   "dataType": 5  /* UInt8 */, "int_value": 254, 
                                                                          "metadata":{"description":"Gear red color"}   },
                                                                        { "name": "green", "dataType": 5  /* UInt8 */, "int_value": 0  , 
                                                                          "metadata":{"description":"Gear green color"} },
                                                                        { "name": "blue",  "dataType": 5  /* UInt8 */, "int_value": 0  , 
                                                                          "metadata":{"description":"Gear blue color"}  },
                                                                        { "name": "white", "dataType": 5  /* UInt8 */, "int_value": 0  , 
                                                                          "metadata":{"description":"Gear white color"} },
                                                                        { "name": "amber", "dataType": 5  /* UInt8 */, "int_value": 0  , 
                                                                          "metadata":{"description":"Gear amber color"} },
                                                                        { "name": "free",  "dataType": 5  /* UInt8 */, "int_value": 0  , 
                                                                          "metadata":{"description":"Gear free color"}  }
                                                                      ] } }
                                                             ] }} ] },
      "metadata":{"description":"[RWP]Dali gear scenes"} },


    /* Control device metrics */
    /* dali/{bus}/device/{device}/instance/{instance}  */ 
    { "name": "dali/0/device/0/id",                           "dataType": 12/* String */,  "string_value": "0000-0121",               "metadata":{"description":"[R]Device id stored in memory bank 0"} },
    { "name": "dali/0/device/0/identify",                     "dataType": 11/* Boolean */, "boolean_value": false,                    "metadata":{"description":"[W]Start device 10s identification procedure"} },
    { "name": "dali/0/device/0/instance/0/type",              "dataType": 12/* String */,  "string_value": "PUSH-BUTTON",             "metadata":{"description":"[R]Device instance type, values = ['GENERIC', 'PUSH-BUTTON', 'ABSOLUTE-INPUT-DEVICE', 'OCCUPANCY-SENSOR', 'LIGHT-SENSOR']"} },
    { "name": "dali/0/device/0/instance/0/enable",            "dataType": 11/* Boolean */, "boolean_value": true,                     "metadata":{"description":"[RWP]Device instance enabled/disabled"} },
    { "name": "dali/0/device/0/instance/0/value",             "dataType": 12/* String */,  "string_value": "released",                "metadata":{"description":"[R]Last button event, values = ['released', 'pressed', 'short-press','double-press', 'long-press-start','long-press-repeat','long-press-stop','stuck','free']"} },
    { "name": "dali/0/device/0/instance/0/filter",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 8,
                        "columns": ["released", "pressed", "short-press","double-press","long-press-start","long-press-repeat","long-press-stop","stuck/free"],
                        "types": [11,11,11,11,11,11,11,11], /* Boolean, Boolean, Boolean, Boolean, Boolean, Boolean, Boolean, Boolean */
                        "rows": [ {"elements":[{"boolean_value": false,"boolean_value": false,"boolean_value": true,"boolean_value": true,"boolean_value": true,"boolean_value": false,"boolean_value": true,"boolean_value": false}]} ] }, 
      "metadata":{"description":"[RWP]Dali device enabled states"} }, 
    { "name": "dali/0/device/0/instance/0/timer/short",       "dataType": 5/* UInt8 */,    "int_value": 0,                            "metadata":{"description":"[RWP]Time which differentiates a short press from a long press"} },  
    { "name": "dali/0/device/0/instance/0/timer/double",      "dataType": 5/* UInt8 */,    "int_value": 0,                            "metadata":{"description":"[RWP]Time which differentiates a single (short) press from a double press"} },  
    { "name": "dali/0/device/0/instance/0/timer/repeat",      "dataType": 5/* UInt8 */,    "int_value": 0,                            "metadata":{"description":"[RWP]Repetition interval of long press repeat events"} },  
    { "name": "dali/0/device/0/instance/0/timer/stuck",       "dataType": 5/* UInt8 */,    "int_value": 0,                            "metadata":{"description":"[RWP]Time when button is pressed or bouncing"} },
    { "name": "dali/0/device/0/instance/1/type",              "dataType": 12/* String */,  "string_value": "ABSOLUTE-INPUT-DEVICE",   "metadata":{"description":"[R]Device instance type, values = ['GENERIC', 'PUSH-BUTTON', 'ABSOLUTE-INPUT-DEVICE', 'OCCUPANCY-SENSOR', 'LIGHT-SENSOR']"} },
    { "name": "dali/0/device/0/instance/1/enable",            "dataType": 11/* Boolean */, "boolean_value": true,                     "metadata":{"description":"[RWP]Device instance enabled/disabled"} },
    { "name": "dali/0/device/0/instance/1/value",             "dataType": 6/* UInt16 */,   "int_value": 0,                            "metadata":{"description":"[R]Dali input device position"} },
    { "name": "dali/0/device/0/instance/1/filter",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 1,
                        "columns": ["position"],
                        "types": [11], /* Boolean */
                        "rows": [ {"elements":[{"boolean_value": true}]} ] }, 
      "metadata":{"description":"[RWP]Dali device enabled states"} },    
    { "name": "dali/0/device/0/instance/1/timer/deadtime",    "dataType": 5/* UInt8 */,    "int_value": 0,                            "metadata":{"description":"[RWP]If the deadtime timer is set, the instance shall not send out an event until the deadtime timer has expired"} },  
    { "name": "dali/0/device/0/instance/1/timer/report",      "dataType": 5/* UInt8 */,    "int_value": 0,                            "metadata":{"description":"[RWP]If the report timer is set, it shall trigger an event every tReport even if the value has not changed"} },  

    { "name": "dali/0/device/1/id",                           "dataType": 12/* String */,  "string_value": "0000-0122",               "metadata":{"description":"[R]Device id stored in memory bank 0"} },
    { "name": "dali/0/device/1/instance/0/type",              "dataType": 12/* String */,  "string_value": "OCCUPANCY-SENSOR",        "metadata":{"description":"[R]Device instance type, values = ['GENERIC', 'PUSH-BUTTON', 'ABSOLUTE-INPUT-DEVICE', 'OCCUPANCY-SENSOR', 'LIGHT-SENSOR']"} },
    { "name": "dali/0/device/1/instance/0/enable",            "dataType": 11/* Boolean */, "boolean_value": true,                     "metadata":{"description":"[RWP]Device instance enabled/disabled"} },
    { "name": "dali/0/device/1/instance/0/value",             "dataType": 12/* String */,  "string_value": "vacant",                  "metadata":{"description":"[R]Last occupancy event, values = ['vacant', 'occupied']"} },
    { "name": "dali/0/device/1/instance/0/filter",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 5,
                        "columns": ["occupied", "vacant", "repeat", "movement", "no-movement"],
                        "types": [11,11,11,11,11], /* Boolean, Boolean, Boolean, Boolean, Boolean */
                        "rows": [ {"elements":[{"boolean_value": true,"boolean_value": false,"boolean_value": true,"boolean_value": true,"boolean_value": true}]} ] }, 
      "metadata":{"description":"[RWP]Dali device enabled states"} },        
    { "name": "dali/0/device/1/instance/0/timer/deadtime",    "dataType": 5/* UInt8 */,    "int_value": 0,                            "metadata":{"description":"[RWP]If the deadtime timer is set, the instance shall not send out an event until the deadtime timer has expired"} },  
    { "name": "dali/0/device/1/instance/0/timer/report",      "dataType": 5/* UInt8 */,    "int_value": 0,                            "metadata":{"description":"[RWP]If the report timer is set, it shall trigger an event every tReport even if the value has not changed"} },  
    { "name": "dali/0/device/1/instance/0/timer/hold",        "dataType": 5/* UInt8 */,    "int_value": 0,                            "metadata":{"description":"[RWP]Timeout value, which shall be (re)started each time movement is detected"} },
    { "name": "dali/0/device/1/instance/1/type",              "dataType": 12/* String */,  "string_value": "LIGHT-SENSOR",            "metadata":{"description":"[R]Device instance type, values = ['GENERIC', 'PUSH-BUTTON', 'ABSOLUTE-INPUT-DEVICE', 'OCCUPANCY-SENSOR', 'LIGHT-SENSOR']"} },
    { "name": "dali/0/device/1/instance/1/enable",            "dataType": 11/* Boolean */, "boolean_value": true,                     "metadata":{"description":"[RWP]Device instance enabled/disabled"} },
    { "name": "dali/0/device/1/instance/1/value",             "dataType": 6/* UInt16 */,   "int_value": 0,                            "metadata":{"description":"[R]Dali light sensor illuminance value"} },
    { "name": "dali/0/device/1/instance/1/filter",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 1,
                        "columns": ["illuminance"],
                        "types": [11], /* Boolean */
                        "rows": [ {"elements":[{"boolean_value": true}]} ] }, 
      "metadata":{"description":"[RWP]Dali device enabled states"} },        
    { "name": "dali/0/device/1/instance/1/timer/deadtime",    "dataType": 5/* UInt8 */,    "int_value": 0,                            "metadata":{"description":"[RWP]If the deadtime timer is set, the instance shall not send out an event until the deadtime timer has expired"} },  
    { "name": "dali/0/device/1/instance/1/timer/report",      "dataType": 5/* UInt8 */,    "int_value": 0,                            "metadata":{"description":"[RWP]If the report timer is set, it shall trigger an event every tReport even if the value has not changed"} },
    { "name": "dali/0/device/1/instance/1/hysteresis",        "dataType": 5/* UInt8 */,    "int_value": 0,                            "metadata":{"description":"[RWP]Percentage from value when illuminance was updated, max value = 25%"} },
    { "name": "dali/0/device/1/instance/1/hysteresisMin",     "dataType": 5/* UInt8 */,    "int_value": 0,                            "metadata":{"description":"[RWP]Absolute value when illuminance was updated"} }
  ]
}
```

## BOX device dali death example
> spBv1.0/box/DDEATH/abba2020/deba0006 

```json
{
"timestamp": 1486144502122,
"metrics": [  
    { "name": "bdSeq",                                  "dataType": 8/* Uint64 */,   "long_value": 0,                    "metadata":{"description":"[R]Birth-death sequence, 'online' - [DBIRTH > DDEATH], 'offline' - [DBIRTH <= DDEATH]"} },  
]
}
```