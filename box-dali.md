## BOX device dali birth example
> spBv1.0/box/DBIRTH/abba2020/deba0006 

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

    { "name": "ref/dali/color/xy",
      "dataType": 19, /* Template */
      "template_value":{ "version": "color",
                         "is_definition": true,
                         "metrics":[
                          { "name": "x",            "dataType": 6  /* UInt16 */, "metadata":{"description":"[RW]Gear x color, dali cmd 'STORE ACTUAL LEVEL IN THE DTR', 'REPORT COLOUR TYPE', 'REPORT COLOUR VALUE', 'QUERY COLOUR STATUS', 'SET TEMPORARY x-COORDINATE', 'ACTIVATE '"}},
                          { "name": "y",            "dataType": 6  /* UInt16 */, "metadata":{"description":"[RW]Gear y color, dali cmd 'STORE ACTUAL LEVEL IN THE DTR', 'REPORT COLOUR TYPE', 'REPORT COLOUR VALUE', 'QUERY COLOUR STATUS', 'SET TEMPORARY y-COORDINATE', 'ACTIVATE '"}}
                        ] }, 
        "metadata":{"description":"Template definition xy color type"} },

    { "name": "ref/dali/color/temperature",
      "dataType": 19, /* Template */
      "template_value":{ "version": "color",
                         "is_definition": true,
                         "metrics":[
                          { "name": "temperature",  "dataType": 6  /* UInt16 */, "properties":{ "keys": ["phy-warmest","warmest","phy-coolest","coolest"], "values": [{"type":6, "int_value": 0},{"type":6, "int_value": 0},{"type":6, "int_value": 65535},{"type":6, "int_value": 65535}] }, 
                            "metadata":{"description":"[RW]Gear color, columns depends on color type, dali cmd 'STORE ACTUAL LEVEL IN THE DTR', 'REPORT COLOUR TYPE', 'REPORT COLOUR VALUE', 'QUERY COLOUR STATUS', 'SET TEMPORARY COLOUR TEMPERATURE', 'ACTIVATE ', 'QUERY COLOUR VALUE', 'STORE COLOUR TEMPERATURE TC LIMIT'"}}
                        ] }, 
        "metadata":{"description":"Template definition temperature color type"} },

    { "name": "ref/dali/color/rgbwaf",
      "dataType": 19, /* Template */
      "template_value":{ "version": "color",
                         "is_definition": true,
                         "metrics":[
                          { "name": "red",          "dataType": 5  /* UInt8 */, "metadata":{"description":"[RW]Gear red color, dali cmd 'STORE ACTUAL LEVEL IN THE DTR', 'REPORT COLOUR TYPE', 'REPORT COLOUR VALUE', 'QUERY COLOUR STATUS', 'SET TEMPORARY RGB DIMLEVEL','ACTIVATE '"} },
                          { "name": "green",        "dataType": 5  /* UInt8 */, "metadata":{"description":"[RW]Gear green color, dali cmd 'STORE ACTUAL LEVEL IN THE DTR', 'REPORT COLOUR TYPE', 'REPORT COLOUR VALUE', 'QUERY COLOUR STATUS', 'SET TEMPORARY RGB DIMLEVEL','ACTIVATE '"} },
                          { "name": "blue",         "dataType": 5  /* UInt8 */, "metadata":{"description":"[RW]Gear blue color, dali cmd 'STORE ACTUAL LEVEL IN THE DTR', 'REPORT COLOUR TYPE', 'REPORT COLOUR VALUE', 'QUERY COLOUR STATUS', 'SET TEMPORARY RGB DIMLEVEL','ACTIVATE '"} },
                          { "name": "white",        "dataType": 5  /* UInt8 */, "metadata":{"description":"[RW]Gear white color, dali cmd 'STORE ACTUAL LEVEL IN THE DTR', 'REPORT COLOUR TYPE', 'REPORT COLOUR VALUE', 'QUERY COLOUR STATUS', 'SET TEMPORARY WAF DIMLEVEL','ACTIVATE '"} },
                          { "name": "amber",        "dataType": 5  /* UInt8 */, "metadata":{"description":"[RW]Gear amber color, dali cmd 'STORE ACTUAL LEVEL IN THE DTR', 'REPORT COLOUR TYPE', 'REPORT COLOUR VALUE', 'QUERY COLOUR STATUS', 'SET TEMPORARY WAF DIMLEVEL','ACTIVATE '"} },
                          { "name": "free",         "dataType": 5  /* UInt8 */, "metadata":{"description":"[RW]Gear free color, dali cmd 'STORE ACTUAL LEVEL IN THE DTR', 'REPORT COLOUR TYPE', 'REPORT COLOUR VALUE', 'QUERY COLOUR STATUS', 'SET TEMPORARY WAF DIMLEVEL','ACTIVATE '"} }
                        ] }, 
        "metadata":{"description":"Template definition rgbwaf color type"} },                   

    { "name": "ref/dali/level",
      "dataType": 19, /* Template */
      "template_value":{ "version": "level",
                         "is_definition": true,
                         "metrics":[
                          { "name": "dim",          "dataType": 5   /* UInt8 */, "properties":{ "keys": ["phy","min","max"], "values": [{"type":5, "int_value": 0},{"type":5, "int_value": 0},{"type":5, "int_value": 254}] },
                                                    "metadata": {"description":""}},
                          { "name": "color",        "dataType": 19  /* Template - ref/dali/color/... */, 
                            "template_value": {
                              "version" : "color",
                              "template_ref": "ref/dali/color/temperature",
                              "is_definition": false,
                              "metrics": []
                            },
                            "metadata":{"description":""}}
                        ] }, 
        "metadata":{"description":"Template definition driver current levels"} },

    { "name": "ref/dali/fade",
      "dataType": 19, /* Template */
      "template_value":{ "version": "fade",
                         "is_definition": true,
                         "metrics":[
                          { "name": "time",        "dataType": 5  /* UInt8 */, "metadata":{"description":"[RWP]Gear fade time, dali cmd 'SET FADE TIME', 'QUERY FADE TIME/FADE RATE', values = [0-15]"} },
                          { "name": "rate",        "dataType": 5  /* UInt8 */, "metadata":{"description":"[RWP]Gear fade rate, dali cmd 'SET FADE RATE', 'QUERY FADE TIME/FADE RATE', values = [0-15]"} }
                        ] }, 
        "metadata":{"description":"Template definition driver fade"} },

    { "name": "ref/dali/scenes",
      "dataType": 19, /* Template */
      "template_value":{ "version": "scenes",
                         "is_definition": true,
                         "metrics":[
                          { "name": "0",        "dataType": 19  /* Template - ref/dali/level */,
                            "template_value": {
                              "version" : "level",
                              "template_ref": "ref/dali/level",
                              "is_definition": false,
                              "metrics": []
                            },
                            "metadata":{"description":"Template definition driver current levels"}},
                          { "name": "1",        "dataType": 19  /* Template - ref/dali/level */, 
                            "template_value": {
                              "version" : "level",
                              "template_ref": "ref/dali/level",
                              "is_definition": false,
                              "metrics": []
                            },
                            "metadata":{"description":"Template definition driver current levels"}},
                          { "name": "2",        "dataType": 19  /* Template - ref/dali/level */,
                            "template_value": {
                              "version" : "level",
                              "template_ref": "ref/dali/level",
                              "is_definition": false,
                              "metrics": []
                            },
                            "metadata":{"description":"Template definition driver current levels"}},
                          { "name": "3",        "dataType": 19  /* Template - ref/dali/level */,
                            "template_value": {
                              "version" : "level",
                              "template_ref": "ref/dali/level",
                              "is_definition": false,
                              "metrics": []
                            },
                            "metadata":{"description":"Template definition driver current levels"}},
                          { "name": "4",        "dataType": 19  /* Template - ref/dali/level */,
                            "template_value": {
                              "version" : "level",
                              "template_ref": "ref/dali/level",
                              "is_definition": false,
                              "metrics": []
                            },
                            "metadata":{"description":"Template definition driver current levels"}},
                          { "name": "5",        "dataType": 19  /* Template - ref/dali/level */,
                            "template_value": {
                              "version" : "level",
                              "template_ref": "ref/dali/level",
                              "is_definition": false,
                              "metrics": []
                            },
                            "metadata":{"description":"Template definition driver current levels"}},
                          { "name": "6",        "dataType": 19  /* Template - ref/dali/level */,
                            "template_value": {
                              "version" : "level",
                              "template_ref": "ref/dali/level",
                              "is_definition": false,
                              "metrics": []
                            },
                            "metadata":{"description":"Template definition driver current levels"}},
                          { "name": "7",        "dataType": 19  /* Template - ref/dali/level */,
                            "template_value": {
                              "version" : "level",
                              "template_ref": "ref/dali/level",
                              "is_definition": false,
                              "metrics": []
                            },
                            "metadata":{"description":"Template definition driver current levels"}},
                          { "name": "8",        "dataType": 19  /* Template - ref/dali/level */,
                            "template_value": {
                              "version" : "level",
                              "template_ref": "ref/dali/level",
                              "is_definition": false,
                              "metrics": []
                            },
                            "metadata":{"description":"Template definition driver current levels"}},
                          { "name": "9",        "dataType": 19  /* Template - ref/dali/level */,
                            "template_value": {
                              "version" : "level",
                              "template_ref": "ref/dali/level",
                              "is_definition": false,
                              "metrics": []
                            },
                            "metadata":{"description":"Template definition driver current levels"}},
                          { "name": "10",       "dataType": 19  /* Template - ref/dali/level */,
                            "template_value": {
                              "version" : "level",
                              "template_ref": "ref/dali/level",
                              "is_definition": false,
                              "metrics": []
                            },
                            "metadata":{"description":"Template definition driver current levels"}},
                          { "name": "11",       "dataType": 19  /* Template - ref/dali/level */,
                            "template_value": {
                              "version" : "level",
                              "template_ref": "ref/dali/level",
                              "is_definition": false,
                              "metrics": []
                            },
                            "metadata":{"description":"Template definition driver current levels"}},
                          { "name": "12",       "dataType": 19  /* Template - ref/dali/level */,
                            "template_value": {
                              "version" : "level",
                              "template_ref": "ref/dali/level",
                              "is_definition": false,
                              "metrics": []
                            },
                            "metadata":{"description":"Template definition driver current levels"}},
                          { "name": "13",       "dataType": 19  /* Template - ref/dali/level */,
                            "template_value": {
                              "version" : "level",
                              "template_ref": "ref/dali/level",
                              "is_definition": false,
                              "metrics": []
                            },
                            "metadata":{"description":"Template definition driver current levels"}},
                          { "name": "14",       "dataType": 19  /* Template - ref/dali/level */,
                            "template_value": {
                              "version" : "level",
                              "template_ref": "ref/dali/level",
                              "is_definition": false,
                              "metrics": []
                            },
                            "metadata":{"description":"Template definition driver current levels"}},
                          { "name": "15",       "dataType": 19  /* Template - ref/dali/level */,
                            "template_value": {
                              "version" : "level",
                              "template_ref": "ref/dali/level",
                              "is_definition": false,
                              "metrics": []
                            },
                            "metadata":{"description":"Template definition driver current levels"}}
                        ] }, 
        "metadata":{"description":"Template definition driver scenes"} },

    /* Bus 0 control metrics */
    { "name": "dali/0/source",                          "dataType": 11/* Boolean */, "boolean_value": true,              "metadata":{"description":"[RW]Dali bus power source state, 'true' - enabled, 'false' - disabled"} },    
    { "name": "dali/0/source/shortCurrent",             "dataType": 11/* Boolean */, "boolean_value": false,             "metadata":{"description":"[R]Dali bus power source short current"} },    
    { "name": "dali/0/source/voltage",                  "dataType": 6/* UInt16 */,   "int_value": 5635,                  "metadata":{"description":"[R]Dali bus voltage, value in mV"} },    
    { "name": "dali/0/source/current",                  "dataType": 6/* UInt16 */,   "int_value": 5635,                  "metadata":{"description":"[R]Dali bus current, value in mA"} },    

    { "name": "dali/0/swap",
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
      "metadata":{"description":"[RWP]Dali group contained gear list, dali cmd 'ADD TO GROUP','REMOVE FROM GROUP','QUERY GROUPS'"} }, 
    { "name": "dali/0/group/1",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 1,
                        "columns": ["gear"],
                        "types": [5], /* UInt8 */
                        "rows": [ ] },                                                  
      "metadata":{"description":"[RWP]Dali group contained gear list, dali cmd 'ADD TO GROUP','REMOVE FROM GROUP','QUERY GROUPS'"} }, 
    { "name": "dali/0/group/2",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 1,
                        "columns": ["gear"],
                        "types": [5], /* UInt8 */
                        "rows": [ ] },                                                  
      "metadata":{"description":"[RWP]Dali group contained gear list, dali cmd 'ADD TO GROUP','REMOVE FROM GROUP','QUERY GROUPS'"} }, 
    { "name": "dali/0/group/3",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 1,
                        "columns": ["gear"],
                        "types": [5], /* UInt8 */
                        "rows": [ ] },                                                  
      "metadata":{"description":"[RWP]Dali group contained gear list, dali cmd 'ADD TO GROUP','REMOVE FROM GROUP','QUERY GROUPS'"} }, 
    { "name": "dali/0/group/4",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 1,
                        "columns": ["gear"],
                        "types": [5], /* UInt8 */
                        "rows": [ ] },                                                  
      "metadata":{"description":"[RWP]Dali group contained gear list, dali cmd 'ADD TO GROUP','REMOVE FROM GROUP','QUERY GROUPS'"} }, 
    { "name": "dali/0/group/5",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 1,
                        "columns": ["gear"],
                        "types": [5], /* UInt8 */
                        "rows": [ ] },                                                  
      "metadata":{"description":"[RWP]Dali group contained gear list, dali cmd 'ADD TO GROUP','REMOVE FROM GROUP','QUERY GROUPS'"} }, 
    { "name": "dali/0/group/6",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 1,
                        "columns": ["gear"],
                        "types": [5], /* UInt8 */
                        "rows": [ ] },                                                  
      "metadata":{"description":"[RWP]Dali group contained gear list, dali cmd 'ADD TO GROUP','REMOVE FROM GROUP','QUERY GROUPS'"} }, 
    { "name": "dali/0/group/7",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 1,
                        "columns": ["gear"],
                        "types": [5], /* UInt8 */
                        "rows": [ ] },                                                  
      "metadata":{"description":"[RWP]Dali group contained gear list, dali cmd 'ADD TO GROUP','REMOVE FROM GROUP','QUERY GROUPS'"} }, 
    { "name": "dali/0/group/8",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 1,
                        "columns": ["gear"],
                        "types": [5], /* UInt8 */
                        "rows": [ ] },                                                  
      "metadata":{"description":"[RWP]Dali group contained gear list, dali cmd 'ADD TO GROUP','REMOVE FROM GROUP','QUERY GROUPS'"} }, 
    { "name": "dali/0/group/9",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 1,
                        "columns": ["gear"],
                        "types": [5], /* UInt8 */
                        "rows": [ ] },                                                  
      "metadata":{"description":"[RWP]Dali group contained gear list, dali cmd 'ADD TO GROUP','REMOVE FROM GROUP','QUERY GROUPS'"} }, 
    { "name": "dali/0/group/10",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 1,
                        "columns": ["gear"],
                        "types": [5], /* UInt8 */
                        "rows": [ ] },                                                  
      "metadata":{"description":"[RWP]Dali group contained gear list, dali cmd 'ADD TO GROUP','REMOVE FROM GROUP','QUERY GROUPS'"} }, 
    { "name": "dali/0/group/11",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 1,
                        "columns": ["gear"],
                        "types": [5], /* UInt8 */
                        "rows": [ ] },                                                  
      "metadata":{"description":"[RWP]Dali group contained gear list, dali cmd 'ADD TO GROUP','REMOVE FROM GROUP','QUERY GROUPS'"} }, 
    { "name": "dali/0/group/12",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 1,
                        "columns": ["gear"],
                        "types": [5], /* UInt8 */
                        "rows": [ ] },                                                  
      "metadata":{"description":"[RWP]Dali group contained gear list, dali cmd 'ADD TO GROUP','REMOVE FROM GROUP','QUERY GROUPS'"} }, 
    { "name": "dali/0/group/13",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 1,
                        "columns": ["gear"],
                        "types": [5], /* UInt8 */
                        "rows": [ ] },                                                  
      "metadata":{"description":"[RWP]Dali group contained gear list, dali cmd 'ADD TO GROUP','REMOVE FROM GROUP','QUERY GROUPS'"} }, 
    { "name": "dali/0/group/14",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 1,
                        "columns": ["gear"],
                        "types": [5], /* UInt8 */
                        "rows": [ ] },                                                  
      "metadata":{"description":"[RWP]Dali group contained gear list, dali cmd 'ADD TO GROUP','REMOVE FROM GROUP','QUERY GROUPS'"} }, 
    { "name": "dali/0/group/15",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 1,
                        "columns": ["gear"],
                        "types": [5], /* UInt8 */
                        "rows": [ ] },                                                  
      "metadata":{"description":"[RWP]Dali group contained gear list, dali cmd 'ADD TO GROUP','REMOVE FROM GROUP','QUERY GROUPS'"} }, 
   
    /* Control gear metrics */
    /* dali/{bus}/gear/{gear}  */  
    { "name": "dali/0/gear/0/id",                       "dataType": 12/* String */,  "string_value": "0000-1121",        "metadata":{"description":"[R]Gear id stored in memory bank 0, dali cmd 'READ MEMORY LOCATION'"} },
    { "name": "dali/0/gear/0/identify",                 "dataType": 11/* Boolean */, "boolean_value": false,             "metadata":{"description":"[W]Start gear 10s identification procedure, dali cmd 'IDENTIFY DEVICE'"} },
    { "name": "dali/0/gear/0/type",                     "dataType": 12/* String */,  "string_value": "LED",              "metadata":{"description":"[R]Gear type, dali cmd 'QUERY DEVICE TYPE','QUERY NEXT DEVICE TYPE', values = ['NONE', 'FLUORESCENT', 'EMERGENCY', 'HID', 'HALOGEN', 'INCANDESCENT', 'CONVERTOR', 'LED', 'RELAY', 'COLOR'], can be multiple types at the same time ('LED|COLOR')"} }, 
    { "name": "dali/0/gear/0/status",                   "dataType": 12/* String */,  "string_value": "ok",               "metadata":{"description":"[R]Control gear status, values = ['ok', 'control-failure', 'lamp-failure', 'short-circuit', 'open-circuit', 'current-protector', 'thermal-shutdown', 'thermal-overload', 'fading'], dali cmd 'QUERY STATUS', LED - 'QUERY FAILURE STATUS', can be multiple status at the same time ('lamp-failure|open-circuit')"} }, 
    { "name": "dali/0/gear/0/level",
      "dataType": 19, /* Template - ref/dali/level */
      "template_value":{ "version": "level",
                         "is_definition": false,
                         "template_ref": "ref/dali/level",
                         "metrics":[
                          { "name": "dim",  "int_value": 0, "properties":{ "keys": ["phy","min","max"], "values": [{"int_value":78},{"int_value":78},{"int_value":254}] }, 
                            "metadata":{"description":"Template definition driver current levels"} }
                        ] }, 
      "metadata":{"description":"[RW]Gear dim level, dali cmd 'DAPC', values = [0-255], value 255(MASK) stop running fade, 'QUERY ACTUAL LEVEL', 'QUERY PHYSICAL MINIMUM','QUERY MIN LEVEL', 'SET MIN LEVEL','QUERY MAX LEVEL', 'SET MAX LEVEL'"} },

    { "name": "dali/0/gear/0/level/powerOn",
      "dataType": 19, /* Template - ref/dali/level */
      "template_value":{ "version": "level",
                         "is_definition": false,
                         "template_ref": "ref/dali/level",
                         "metrics":[
                          { "name": "dim",  "int_value": 254 }
                        ] }, 
      "metadata":{"description":"[RWP]Gear power on dim level, dali cmd 'QUERY POWER ON LEVEL', 'SET POWER ON LEVEL', value 255(MASK) equal last light level"} },

    { "name": "dali/0/gear/0/level/failure",
      "dataType": 19, /* Template - ref/dali/level */
      "template_value":{ "version": "level",
                         "is_definition": false,
                         "template_ref": "ref/dali/level",
                         "metrics":[
                          { "name": "dim",  "int_value": 254 }
                        ] }, 
      "metadata":{"description":"[RWP]Gear bus failure dim level, dali cmd 'QUERY SYSTEM FAILURE LEVEL', 'SET SYSTEM FAILURE LEVEL', value 255(MASK) disable react to bus failure"} },      

    { "name": "dali/0/gear/0/fade",    
      "dataType": 19 /* Template - ref/dali/fade */,
      "template_value":{  "version": "fade",
                          "is_definition": false,
                          "template_ref": "ref/dali/fade",
                          "metrics":[
                          { "name": "time",  "int_value": 1},
                          { "name": "rate",  "int_value": 5} ] },
      "metadata":{"description":""} },

    { "name": "dali/0/gear/0/scenes",  "dataType": 19 /* Template - ref/dali/scenes */,
      "template_value":{ "version": "scenes",
      "is_definition": false,
      "template_ref": "ref/dali/scenes",
      "metrics":[
        { "name": "0",        
          "dataType": 19  /* Template - ref/dali/level */,
          "template_value":{ "version": "level",
                             "is_definition": false,
                             "template_ref": "ref/dali/level",
                             "metrics":[
                              { "name": "dim", "int_value": 254 } ] }},
        { "name": "1",        
          "dataType": 19  /* Template - ref/dali/level */,
          "template_value":{ "version": "level",
                             "is_definition": false,
                             "template_ref": "ref/dali/level",
                             "metrics":[
                              { "name": "dim", "int_value": 254 } ] }},
        { "name": "2",        
          "dataType": 19  /* Template - ref/dali/level */,
          "template_value":{ "version": "level",
                             "is_definition": false,
                             "template_ref": "ref/dali/level",
                             "metrics":[
                              { "name": "dim", "int_value": 254 } ] }},
        { "name": "3",        
          "dataType": 19  /* Template - ref/dali/level */,
          "template_value":{ "version": "level",
                             "is_definition": false,
                             "template_ref": "ref/dali/level",
                             "metrics":[
                              { "name": "dim", "int_value": 254 } ] }},
        { "name": "4",        
          "dataType": 19  /* Template - ref/dali/level */,
          "template_value":{ "version": "level",
                             "is_definition": false,
                             "template_ref": "ref/dali/level",
                             "metrics":[
                              { "name": "dim", "int_value": 254 } ] }},
        { "name": "5",        
          "dataType": 19  /* Template - ref/dali/level */,
          "template_value":{ "version": "level",
                             "is_definition": false,
                             "template_ref": "ref/dali/level",
                             "metrics":[
                              { "name": "dim", "int_value": 254 } ] }},
        { "name": "6",        
          "dataType": 19  /* Template - ref/dali/level */,
          "template_value":{ "version": "level",
                             "is_definition": false,
                             "template_ref": "ref/dali/level",
                             "metrics":[
                              { "name": "dim", "int_value": 254 } ] }},
        { "name": "7",        
          "dataType": 19  /* Template - ref/dali/level */,
          "template_value":{ "version": "level",
                             "is_definition": false,
                             "template_ref": "ref/dali/level",
                             "metrics":[
                              { "name": "dim", "int_value": 254 } ] }},
        { "name": "8",        
          "dataType": 19  /* Template - ref/dali/level */,
          "template_value":{ "version": "level",
                             "is_definition": false,
                             "template_ref": "ref/dali/level",
                             "metrics":[
                              { "name": "dim", "int_value": 254 } ] }},
        { "name": "9",        
          "dataType": 19  /* Template - ref/dali/level */,
          "template_value":{ "version": "level",
                             "is_definition": false,
                             "template_ref": "ref/dali/level",
                             "metrics":[
                              { "name": "dim", "int_value": 254 } ] }},
        { "name": "10",       
          "dataType": 19  /* Template - ref/dali/level */,
          "template_value":{ "version": "level",
                             "is_definition": false,
                             "template_ref": "ref/dali/level",
                             "metrics":[
                              { "name": "dim", "int_value": 254 } ] }},
        { "name": "11",       
          "dataType": 19  /* Template - ref/dali/level */,
          "template_value":{ "version": "level",
                             "is_definition": false,
                             "template_ref": "ref/dali/level",
                             "metrics":[
                              { "name": "dim", "int_value": 254 } ] }},
        { "name": "12",       
          "dataType": 19  /* Template - ref/dali/level */,
          "template_value":{ "version": "level",
                             "is_definition": false,
                             "template_ref": "ref/dali/level",
                             "metrics":[
                              { "name": "dim", "int_value": 254 } ] }},
        { "name": "13",       
          "dataType": 19  /* Template - ref/dali/level */,
          "template_value":{ "version": "level",
                             "is_definition": false,
                             "template_ref": "ref/dali/level",
                             "metrics":[
                              { "name": "dim", "int_value": 254 } ] }},
        { "name": "14",       
          "dataType": 19  /* Template - ref/dali/level */,
          "template_value":{ "version": "level",
                             "is_definition": false,
                             "template_ref": "ref/dali/level",
                             "metrics":[
                              { "name": "dim", "int_value": 254 } ] }},
        { "name": "15",       
          "dataType": 19  /* Template - ref/dali/level */,
          "template_value":{ "version": "level",
                             "is_definition": false,
                             "template_ref": "ref/dali/level",
                             "metrics":[
                              { "name": "dim", "int_value": 254 } ] }} ] },
      "metadata":{"description":"[RWP]Dali gear scenes, dali cmd 'QUERY SCENE LEVEL', 'SET SCENE'"} },

    /*DALI Color Temperature control gear*/
    { "name": "dali/0/gear/1/id",                       "dataType": 12/* String */,  "string_value": "0000-1122",        "metadata":{"description":"[R]Gear id stored in memory bank 0, dali cmd 'READ MEMORY LOCATION'"} },
    { "name": "dali/0/gear/1/identify",                 "dataType": 11/* Boolean */, "boolean_value": false,             "metadata":{"description":"[W]Start gear 10s identification procedure, dali cmd 'IDENTIFY DEVICE'"} },
    { "name": "dali/0/gear/1/type",                     "dataType": 12/* String */,  "string_value": "COLOR",            "metadata":{"description":"[R]Gear type, dali cmd 'QUERY DEVICE TYPE','QUERY NEXT DEVICE TYPE', values = ['NONE', 'FLUORESCENT', 'EMERGENCY', 'HID', 'HALOGEN', 'INCANDESCENT', 'CONVERTOR', 'LED', 'RELAY', 'COLOR'], can be multiple types at the same time ('LED|COLOR')"} }, 
    { "name": "dali/0/gear/1/status",                   "dataType": 12/* String */,  "string_value": "ok",               "metadata":{"description":"[R]Control gear status, values = ['ok', 'control-failure', 'lamp-failure', 'short-circuit', 'open-circuit', 'current-protector', 'thermal-shutdown', 'thermal-overload', 'fading'], dali cmd 'QUERY STATUS', LED - 'QUERY FAILURE STATUS', can be multiple status at the same time ('lamp-failure|open-circuit')"} }, 
    { "name": "dali/0/gear/1/level",
      "dataType": 19, /* Template - ref/dali/level */
      "template_value":{ "version": "level",
                         "is_definition": false,
                         "template_ref": "ref/dali/level",
                         "metrics":[
                          { "name": "dim",  "int_value": 0, "properties":{ "keys": ["phy","min","max"], "values": [{"int_value":78},{"int_value":78},{"int_value":254}] } },
                          { "name": "color",
                            "dataType": 19, /* Template  - ref/dali/color/temperature*/
                            "template_value":{ "version": "color",
                                               "is_definition": false,
                                               "template_ref": "ref/dali/color/temperature",
                                               "metrics":[
                                                { "name": "temperature",  "int_value": 2700, "properties":{ "keys": ["phy","warmest","coolest"], "values": [{"int_value":2300},{"int_value":2300},{"int_value":5000}] }}
                                              ] } }
                        ] }, 
      "metadata":{"description":"[RW]Gear dim level, dali cmd 'DAPC', values = [0-255], value 255(MASK) stop running fade, 'QUERY ACTUAL LEVEL', 'QUERY PHYSICAL MINIMUM','QUERY MIN LEVEL', 'SET MIN LEVEL','QUERY MAX LEVEL', 'SET MAX LEVEL'"} },

    { "name": "dali/0/gear/1/level/powerOn",
      "dataType": 19, /* Template - ref/dali/level */
      "template_value":{ "version": "level",
                         "is_definition": false,
                         "template_ref": "ref/dali/level",
                         "metrics":[
                          { "name": "dim",  "int_value": 254 },
                          { "name": "color",
                            "dataType": 19, /* Template  - ref/dali/color/temperature*/
                            "template_value":{ "version": "color",
                                               "is_definition": false,
                                               "template_ref": "ref/dali/color/temperature",
                                               "metrics":[
                                                { "name": "temperature",  "int_value": 2700 }
                                              ] } }
                        ] }, 
      "metadata":{"description":"[RWP]Gear power on dim level, dali cmd 'QUERY POWER ON LEVEL', 'SET POWER ON LEVEL', value 255(MASK) equal last light level"} },

    { "name": "dali/0/gear/1/level/failure",
      "dataType": 19, /* Template - ref/dali/level */
      "template_value":{ "version": "level",
                         "is_definition": false,
                         "template_ref": "ref/dali/level",
                         "metrics":[
                          { "name": "dim",  "int_value": 254 },
                          { "name": "color",
                            "dataType": 19, /* Template  - ref/dali/color/temperature*/
                            "template_value":{ "version": "color",
                                               "is_definition": false,
                                               "template_ref": "ref/dali/color/temperature",
                                               "metrics":[
                                                { "name": "temperature",  "int_value": 2700 }
                                              ] } }

                        ] }, 
      "metadata":{"description":"[RWP]Gear bus failure dim level, dali cmd 'QUERY SYSTEM FAILURE LEVEL', 'SET SYSTEM FAILURE LEVEL', value 255(MASK) disable react to bus failure"} },      

    { "name": "dali/0/gear/1/fade",    
      "dataType": 19 /* Template - ref/dali/fade */,
      "template_value":{  "version": "fade",
                          "is_definition": false,
                          "template_ref": "ref/dali/fade",
                          "metrics":[
                          { "name": "time",  "int_value": 1},
                          { "name": "rate",  "int_value": 5} ] },
      "metadata":{"description":""} },

    { "name": "dali/0/gear/1/scenes",  
      "dataType": 19 /* Template - ref/dali/scenes */,
      "template_value":{ "version": "scenes",
                         "is_definition": false,
                         "template_ref": "ref/dali/scenes",
                         "metrics":[
                           { "name": "0",        
                             "dataType": 19  /* Template - ref/dali/level */,
                             "template_value":{ "version": "level",
                                                "is_definition": false,
                                                "template_ref": "ref/dali/level",
                                                "metrics":[
                                                  { "name": "dim", "int_value": 254 },
                                                  { "name": "color",
                                                    "dataType": 19, /* Template  - ref/dali/color/temperature*/
                                                    "template_value":{ "version": "color",
                                                                      "is_definition": false,
                                                                      "template_ref": "ref/dali/color/temperature",
                                                                      "metrics":[
                                                                        { "name": "temperature",  "int_value": 2700 }
                                                                     ] } } 
                                                             ] }},
                           /* 1...14 repeated */ 
                           { "name": "15",       
                             "dataType": 19  /* Template - ref/dali/level */,
                             "template_value":{ "version": "level",
                                                "is_definition": false,
                                                "template_ref": "ref/dali/level",
                                                "metrics":[
                                                  { "name": "dim", "int_value": 254 },
                                                  { "name": "color",
                                                    "dataType": 19, /* Template  - ref/dali/color/temperature*/
                                                    "template_value":{ "version": "color",
                                                                      "is_definition": false,
                                                                      "template_ref": "ref/dali/color/temperature",
                                                                      "metrics":[
                                                                        { "name": "temperature",  "int_value": 2700 }
                                                                     ] } } 
                                                             ] }} ] },
                         "metadata":{"description":"[RWP]Dali gear scenes, dali cmd 'QUERY SCENE LEVEL', 'SET SCENE'"} },

    /*DALI Color RGBWAF control gear*/
    { "name": "dali/0/gear/2/id",                       "dataType": 12/* String */,  "string_value": "0000-1123",        "metadata":{"description":"[R]Gear id stored in memory bank 0, dali cmd 'READ MEMORY LOCATION'"} },
    { "name": "dali/0/gear/2/identify",                 "dataType": 11/* Boolean */, "boolean_value": false,             "metadata":{"description":"[W]Start gear 10s identification procedure, dali cmd 'IDENTIFY DEVICE'"} },
    { "name": "dali/0/gear/2/type",                     "dataType": 12/* String */,  "string_value": "COLOR",            "metadata":{"description":"[R]Gear type, dali cmd 'QUERY DEVICE TYPE','QUERY NEXT DEVICE TYPE', values = ['NONE', 'FLUORESCENT', 'EMERGENCY', 'HID', 'HALOGEN', 'INCANDESCENT', 'CONVERTOR', 'LED', 'RELAY', 'COLOR'], can be multiple types at the same time ('LED|COLOR')"} }, 
    { "name": "dali/0/gear/2/status",                   "dataType": 12/* String */,  "string_value": "ok",               "metadata":{"description":"[R]Control gear status, values = ['ok', 'control-failure', 'lamp-failure', 'short-circuit', 'open-circuit', 'current-protector', 'thermal-shutdown', 'thermal-overload', 'fading'], dali cmd 'QUERY STATUS', LED - 'QUERY FAILURE STATUS', can be multiple status at the same time ('lamp-failure|open-circuit')"} }, 
    { "name": "dali/0/gear/2/level",
      "dataType": 19, /* Template - ref/dali/level */
      "template_value":{ "version": "level",
                         "is_definition": false,
                         "template_ref": "ref/dali/level",
                         "metrics":[
                          { "name": "dim",  "int_value": 0, "properties":{ "keys": ["phy","min","max"], "values": [{"int_value":78},{"int_value":78},{"int_value":254}] } },
                          { "name": "color",
                            "dataType": 19, /* Template  - ref/dali/color/rgbwaf*/
                            "template_value":{ "version": "color",
                                               "is_definition": false,
                                               "template_ref": "ref/dali/color/rgbwaf",
                                               "metrics":[
                                                { "name": "red",    "int_value": 254},
                                                { "name": "green",  "int_value": 0},
                                                { "name": "blue",   "int_value": 0},
                                                { "name": "white",  "int_value": 0},
                                                { "name": "amber",  "int_value": 0},
                                                { "name": "free",   "int_value": 0}
                                              ] } }
                        ] }, 
      "metadata":{"description":"[RW]Gear dim level, dali cmd 'DAPC', values = [0-255], value 255(MASK) stop running fade, 'QUERY ACTUAL LEVEL', 'QUERY PHYSICAL MINIMUM','QUERY MIN LEVEL', 'SET MIN LEVEL','QUERY MAX LEVEL', 'SET MAX LEVEL'"} },

    { "name": "dali/0/gear/2/level/powerOn",
      "dataType": 19, /* Template - ref/dali/level */
      "template_value":{ "version": "level",
                         "is_definition": false,
                         "template_ref": "ref/dali/level",
                         "metrics":[
                          { "name": "dim",  "int_value": 254 },
                          { "name": "color",
                            "dataType": 19, /* Template  - ref/dali/color/rgbwaf*/
                            "template_value":{ "version": "color",
                                               "is_definition": false,
                                               "template_ref": "ref/dali/color/rgbwaf",
                                               "metrics":[
                                                { "name": "red",    "int_value": 254},
                                                { "name": "green",  "int_value": 0},
                                                { "name": "blue",   "int_value": 0},
                                                { "name": "white",  "int_value": 0},
                                                { "name": "amber",  "int_value": 0},
                                                { "name": "free",   "int_value": 0}
                                              ] } }
                        ] }, 
      "metadata":{"description":"[RWP]Gear power on dim level, dali cmd 'QUERY POWER ON LEVEL', 'SET POWER ON LEVEL', value 255(MASK) equal last light level"} },

    { "name": "dali/0/gear/2/level/failure",
      "dataType": 19, /* Template - ref/dali/level */
      "template_value":{ "version": "level",
                         "is_definition": false,
                         "template_ref": "ref/dali/level",
                         "metrics":[
                          { "name": "dim",  "int_value": 254 },
                          { "name": "color",
                            "dataType": 19, /* Template  - ref/dali/color/rgbwaf*/
                            "template_value":{ "version": "color",
                                               "is_definition": false,
                                               "template_ref": "ref/dali/color/rgbwaf",
                                               "metrics":[
                                                { "name": "red",    "int_value": 254},
                                                { "name": "green",  "int_value": 0},
                                                { "name": "blue",   "int_value": 0},
                                                { "name": "white",  "int_value": 0},
                                                { "name": "amber",  "int_value": 0},
                                                { "name": "free",   "int_value": 0}
                                              ] } }

                        ] }, 
      "metadata":{"description":"[RWP]Gear bus failure dim level, dali cmd 'QUERY SYSTEM FAILURE LEVEL', 'SET SYSTEM FAILURE LEVEL', value 255(MASK) disable react to bus failure"} },      

    { "name": "dali/0/gear/2/fade",    
      "dataType": 19 /* Template - ref/dali/fade */,
      "template_value":{  "version": "fade",
                          "is_definition": false,
                          "template_ref": "ref/dali/fade",
                          "metrics":[
                          { "name": "time",  "int_value": 1},
                          { "name": "rate",  "int_value": 5} ] },
      "metadata":{"description":""} },

    { "name": "dali/0/gear/2/scenes",  
      "dataType": 19 /* Template - ref/dali/scenes */,
      "template_value":{ "version": "scenes",
                         "is_definition": false,
                         "template_ref": "ref/dali/scenes",
                         "metrics":[
                           { "name": "0",        
                             "dataType": 19  /* Template - ref/dali/level */,
                             "template_value":{ "version": "level",
                                                "is_definition": false,
                                                "template_ref": "ref/dali/level",
                                                "metrics":[
                                                  { "name": "dim", "int_value": 254 },
                                                  { "name": "color",
                                                    "dataType": 19, /* Template  - ref/dali/color/rgbwaf*/
                                                    "template_value":{ "version": "color",
                                                                      "is_definition": false,
                                                                      "template_ref": "ref/dali/color/rgbwaf",
                                                                      "metrics":[
                                                                        { "name": "red",    "int_value": 254},
                                                                        { "name": "green",  "int_value": 0},
                                                                        { "name": "blue",   "int_value": 0},
                                                                        { "name": "white",  "int_value": 0},
                                                                        { "name": "amber",  "int_value": 0},
                                                                        { "name": "free",   "int_value": 0}
                                                                      ] } }
                                                             ] }},
                           /* 1...14 repeated */ 
                           { "name": "15",       
                             "dataType": 19  /* Template - ref/dali/level */,
                             "template_value":{ "version": "level",
                                                "is_definition": false,
                                                "template_ref": "ref/dali/level",
                                                "metrics":[
                                                  { "name": "dim", "int_value": 254 },
                                                  { "name": "color",
                                                    "dataType": 19, /* Template  - ref/dali/color/rgbwaf*/
                                                    "template_value":{ "version": "color",
                                                                      "is_definition": false,
                                                                      "template_ref": "ref/dali/color/rgbwaf",
                                                                      "metrics":[
                                                                        { "name": "red",    "int_value": 254},
                                                                        { "name": "green",  "int_value": 0},
                                                                        { "name": "blue",   "int_value": 0},
                                                                        { "name": "white",  "int_value": 0},
                                                                        { "name": "amber",  "int_value": 0},
                                                                        { "name": "free",   "int_value": 0}
                                                                      ] } }
                                                             ] }} ] },
      "metadata":{"description":"[RWP]Dali gear scenes, dali cmd 'QUERY SCENE LEVEL', 'SET SCENE'"} },


    /* Control device metrics */
    /* dali/{bus}/device/{device}/instance/{instance}  */ 
    { "name": "dali/0/device/0/id",                           "dataType": 12/* String */,  "string_value": "0000-0121",               "metadata":{"description":"[R]Device id stored in memory bank 0, dali cmd 'READ MEMORY LOCATION'"} },
    { "name": "dali/0/device/0/identify",                     "dataType": 11/* Boolean */, "boolean_value": false,                    "metadata":{"description":"[W]Start device 10s identification procedure, dali cmd 'IDENTIFY DEVICE'"} },
    { "name": "dali/0/device/0/instance/0/type",              "dataType": 12/* String */,  "string_value": "PUSH-BUTTON",             "metadata":{"description":"[R]Device instance type, dali cmd 'QUERY INSTANCE TYPE', values = ['GENERIC', 'PUSH-BUTTON', 'ABSOLUTE-INPUT-DEVICE', 'OCCUPANCY-SENSOR', 'LIGHT-SENSOR']"} },
    { "name": "dali/0/device/0/instance/0/enable",            "dataType": 11/* Boolean */, "boolean_value": true,                     "metadata":{"description":"[RWP]Device instance enabled/disabled, dali cmd 'ENABLE INSTANCE', 'DISABLE INSTANCE', 'QUERY INSTANCE ENABLED'"} },
    { "name": "dali/0/device/0/instance/0/value",             "dataType": 12/* String */,  "string_value": "released",                "metadata":{"description":"[R]Last button event, values = ['released', 'pressed', 'short-press','double-press', 'long-press-start','long-press-repeat','long-press-stop','stuck','free'], dali cmd 'QUERY INPUT VALUE'"} },
    { "name": "dali/0/device/0/instance/0/filter",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 8,
                        "columns": ["released", "pressed", "short-press","double-press","long-press-start","long-press-repeat","long-press-stop","stuck/free"],
                        "types": [11,11,11,11,11,11,11,11], /* Boolean, Boolean, Boolean, Boolean, Boolean, Boolean, Boolean, Boolean */
                        "rows": [ {"elements":[{"boolean_value": false,"boolean_value": false,"boolean_value": true,"boolean_value": true,"boolean_value": true,"boolean_value": false,"boolean_value": true,"boolean_value": false}]} ] }, 
      "metadata":{"description":"[RWP]Dali device enabled states, dali cmd 'SET EVENT FILTER', 'QUERY EVENT FILTER 0-7'"} }, 
    { "name": "dali/0/device/0/instance/0/timer/short",       "dataType": 5/* UInt8 */,    "int_value": 0,                            "metadata":{"description":"[RWP]Time which differentiates a short press from a long press, dali cmd 'SET SHORT TIMER', 'QUERY SHORT TIMER'"} },  
    { "name": "dali/0/device/0/instance/0/timer/double",      "dataType": 5/* UInt8 */,    "int_value": 0,                            "metadata":{"description":"[RWP]Time which differentiates a single (short) press from a double press, dali cmd 'SET DOUBLE TIMER', 'QUERY DOUBLE TIMER'"} },  
    { "name": "dali/0/device/0/instance/0/timer/repeat",      "dataType": 5/* UInt8 */,    "int_value": 0,                            "metadata":{"description":"[RWP]Repetition interval of long press repeat events, dali cmd 'SET REPEAT TIMER', 'QUERY REPEAT TIMER'"} },  
    { "name": "dali/0/device/0/instance/0/timer/stuck",       "dataType": 5/* UInt8 */,    "int_value": 0,                            "metadata":{"description":"[RWP]Time when button is pressed or bouncing, dali cmd 'SET STUCK TIMER', 'QUERY STUCK TIMER'"} },
    { "name": "dali/0/device/0/instance/1/type",              "dataType": 12/* String */,  "string_value": "ABSOLUTE-INPUT-DEVICE",   "metadata":{"description":"[R]Device instance type, dali cmd 'QUERY INSTANCE TYPE', values = ['GENERIC', 'PUSH-BUTTON', 'ABSOLUTE-INPUT-DEVICE', 'OCCUPANCY-SENSOR', 'LIGHT-SENSOR']"} },
    { "name": "dali/0/device/0/instance/1/enable",            "dataType": 11/* Boolean */, "boolean_value": true,                     "metadata":{"description":"[RWP]Device instance enabled/disabled, dali cmd 'ENABLE INSTANCE', 'DISABLE INSTANCE', 'QUERY INSTANCE ENABLED'"} },
    { "name": "dali/0/device/0/instance/1/value",             "dataType": 6/* UInt16 */,   "int_value": 0,                            "metadata":{"description":"[R]Dali input device position, dali cmd 'QUERY INPUT VALUE'"} },
    { "name": "dali/0/device/0/instance/1/filter",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 1,
                        "columns": ["position"],
                        "types": [11], /* Boolean */
                        "rows": [ {"elements":[{"boolean_value": true}]} ] }, 
      "metadata":{"description":"[RWP]Dali device enabled states, dali cmd 'SET EVENT FILTER', 'QUERY EVENT FILTER 0-7'"} },    
    { "name": "dali/0/device/0/instance/1/timer/deadtime",    "dataType": 5/* UInt8 */,    "int_value": 0,                            "metadata":{"description":"[RWP]If the deadtime timer is set, the instance shall not send out an event until the deadtime timer has expired, dali cmd 'SET DEADTIME TIMER', 'QUERY DEADTIME TIMER'"} },  
    { "name": "dali/0/device/0/instance/1/timer/report",      "dataType": 5/* UInt8 */,    "int_value": 0,                            "metadata":{"description":"[RWP]If the report timer is set, it shall trigger an event every tReport even if the value has not changed, dali cmd 'SET REPORT TIMER', 'QUERY REPORT TIMER'"} },  

    { "name": "dali/0/device/1/id",                           "dataType": 12/* String */,  "string_value": "0000-0122",               "metadata":{"description":"[R]Device id stored in memory bank 0, dali cmd 'READ MEMORY LOCATION'"} },
    { "name": "dali/0/device/1/instance/0/type",              "dataType": 12/* String */,  "string_value": "OCCUPANCY-SENSOR",        "metadata":{"description":"[R]Device instance type, dali cmd 'QUERY INSTANCE TYPE', values = ['GENERIC', 'PUSH-BUTTON', 'ABSOLUTE-INPUT-DEVICE', 'OCCUPANCY-SENSOR', 'LIGHT-SENSOR']"} },
    { "name": "dali/0/device/1/instance/0/enable",            "dataType": 11/* Boolean */, "boolean_value": true,                     "metadata":{"description":"[RWP]Device instance enabled/disabled, dali cmd 'ENABLE INSTANCE', 'DISABLE INSTANCE', 'QUERY INSTANCE ENABLED'"} },
    { "name": "dali/0/device/1/instance/0/value",             "dataType": 12/* String */,  "string_value": "vacant",                  "metadata":{"description":"[R]Last occupancy event, values = ['vacant', 'occupied'], dali cmd 'QUERY INPUT VALUE'"} },
    { "name": "dali/0/device/1/instance/0/filter",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 5,
                        "columns": ["occupied", "vacant", "repeat", "movement", "no-movement"],
                        "types": [11,11,11,11,11], /* Boolean, Boolean, Boolean, Boolean, Boolean */
                        "rows": [ {"elements":[{"boolean_value": true,"boolean_value": false,"boolean_value": true,"boolean_value": true,"boolean_value": true}]} ] }, 
      "metadata":{"description":"[RWP]Dali device enabled states, dali cmd 'SET EVENT FILTER', 'QUERY EVENT FILTER 0-7'"} },        
    { "name": "dali/0/device/1/instance/0/timer/deadtime",    "dataType": 5/* UInt8 */,    "int_value": 0,                            "metadata":{"description":"[RWP]If the deadtime timer is set, the instance shall not send out an event until the deadtime timer has expired, dali cmd 'SET DEADTIME TIMER', 'QUERY DEADTIME TIMER'"} },  
    { "name": "dali/0/device/1/instance/0/timer/report",      "dataType": 5/* UInt8 */,    "int_value": 0,                            "metadata":{"description":"[RWP]If the report timer is set, it shall trigger an event every tReport even if the value has not changed, dali cmd 'SET REPORT TIMER', 'QUERY REPORT TIMER'"} },  
    { "name": "dali/0/device/1/instance/0/timer/hold",        "dataType": 5/* UInt8 */,    "int_value": 0,                            "metadata":{"description":"[RWP]Timeout value, which shall be (re)started each time movement is detected, dali cmd 'SET HOLD TIMER', 'QUERY HOLD TIMER'"} },
    { "name": "dali/0/device/1/instance/1/type",              "dataType": 12/* String */,  "string_value": "LIGHT-SENSOR",            "metadata":{"description":"[R]Device instance type, dali cmd 'QUERY INSTANCE TYPE', values = ['GENERIC', 'PUSH-BUTTON', 'ABSOLUTE-INPUT-DEVICE', 'OCCUPANCY-SENSOR', 'LIGHT-SENSOR']"} },
    { "name": "dali/0/device/1/instance/1/enable",            "dataType": 11/* Boolean */, "boolean_value": true,                     "metadata":{"description":"[RWP]Device instance enabled/disabled, dali cmd 'ENABLE INSTANCE', 'DISABLE INSTANCE', 'QUERY INSTANCE ENABLED'"} },
    { "name": "dali/0/device/1/instance/1/value",             "dataType": 6/* UInt16 */,   "int_value": 0,                            "metadata":{"description":"[R]Dali light sensor illuminance value, dali cmd 'QUERY INPUT VALUE'"} },
    { "name": "dali/0/device/1/instance/1/filter",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 1,
                        "columns": ["illuminance"],
                        "types": [11], /* Boolean */
                        "rows": [ {"elements":[{"boolean_value": true}]} ] }, 
      "metadata":{"description":"[RWP]Dali device enabled states, dali cmd 'SET EVENT FILTER', 'QUERY EVENT FILTER 0-7'"} },        
    { "name": "dali/0/device/1/instance/1/timer/deadtime",    "dataType": 5/* UInt8 */,    "int_value": 0,                            "metadata":{"description":"[RWP]If the deadtime timer is set, the instance shall not send out an event until the deadtime timer has expired, dali cmd 'SET DEADTIME TIMER', 'QUERY DEADTIME TIMER'"} },  
    { "name": "dali/0/device/1/instance/1/timer/report",      "dataType": 5/* UInt8 */,    "int_value": 0,                            "metadata":{"description":"[RWP]If the report timer is set, it shall trigger an event every tReport even if the value has not changed, dali cmd 'SET REPORT TIMER', 'QUERY REPORT TIMER'"} },
    { "name": "dali/0/device/1/instance/1/hysteresis",        "dataType": 5/* UInt8 */,    "int_value": 0,                            "metadata":{"description":"[RWP]Percentage from value when illuminance was updated, max value = 25%, dali cmd 'SET HYSTERESIS', 'QUERY HYSTERESIS'"} },
    { "name": "dali/0/device/1/instance/1/hysteresisMin",     "dataType": 5/* UInt8 */,    "int_value": 0,                            "metadata":{"description":"[RWP]Absolute value when illuminance was updated, dali cmd 'SET HYSTERESIS MIN', 'QUERY HYSTERESIS MIN'"} },

    { "name": "dali/0/device/1/instance/2/type",              "dataType": 12/* String */,  "string_value": "GENERIC",                 "metadata":{"description":"[R]Device instance type, dali cmd 'QUERY INSTANCE TYPE', values = ['GENERIC', 'PUSH-BUTTON', 'ABSOLUTE-INPUT-DEVICE', 'OCCUPANCY-SENSOR', 'LIGHT-SENSOR']"} },
    { "name": "dali/0/device/1/instance/2/enable",            "dataType": 11/* Boolean */, "boolean_value": true,                     "metadata":{"description":"[RWP]Device instance enabled/disabled, dali cmd 'ENABLE INSTANCE', 'DISABLE INSTANCE', 'QUERY INSTANCE ENABLED'"} },
    { "name": "dali/0/device/1/instance/2/value",             "dataType": 6/* UInt16 */,   "int_value": 0,                            "metadata":{"description":"[R]Instance generic value, dali cmd 'QUERY INPUT VALUE'"} }
  ]
}
```

## BOX device dali death example
> spBv1.0/box/DDEATH/abba2020/deba0006 

```json
{
"timestamp": 1486144502122,
"metrics": [  
    { "name": "bdSeq",                                  "dataType": 8/* Uint64 */,   "long_value": 0,                    "metadata":{"description":"[R]Birth-death sequence, 'online' - [DBIRTH > DDEATH], 'offline' - [DBIRTH <= DDEATH]  "} },  
]
}
```