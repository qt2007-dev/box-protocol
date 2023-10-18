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
      "metadata":{"description":"[W]Dali send command to bus, 
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
   


    { "name": "define/dali/color",
      "dataType": 19, /* Template */
      "template_value":{ "version": "v1",
                         "is_definition": true,
                         "metrics":[
                          { "name": "type",         "dataType": 12 /* String */},

                          { "name": "x",            "dataType": 6  /* UInt16 */},
                          { "name": "y",            "dataType": 6  /* UInt16 */},

                          { "name": "temperature",  "dataType": 6  /* UInt16 */, "properties":{ "keys": ["phy","warmest","coolest"], 
                                                                                                "values": [{"type":6},{"type":6},{"type":6}] } },

                          { "name": "red",          "dataType": 5  /* UInt8 */},
                          { "name": "green",        "dataType": 5  /* UInt8 */},
                          { "name": "blue",         "dataType": 5  /* UInt8 */},
                          { "name": "white",        "dataType": 5  /* UInt8 */},
                          { "name": "amber",        "dataType": 5  /* UInt8 */},
                          { "name": "free",         "dataType": 5  /* UInt8 */}
                        ] }, 
        "metadata":{"description":""} },

    { "name": "ref/dali/level",
      "dataType": 19, /* Template */
      "template_value":{ "version": "v1",
                         "is_definition": true,
                         "metrics":[
                          { "name": "dim",          "dataType": 5  /* UInt8 */, "properties":{ "keys": ["phy","min","max"], 
                                                                                                "values": [{"type":5},{"type":5},{"type":5}] } },
                          { "name": "color",        "dataType": 19  /* Template - daliColorTemplate */}
                        ] }, 
        "metadata":{"description":""} },

    { "name": "ref/dali/fade",
      "dataType": 19, /* Template */
      "template_value":{ "version": "v1",
                         "is_definition": true,
                         "metrics":[
                          { "name": "time",        "dataType": 5  /* UInt8 */},
                          { "name": "rate",        "dataType": 5  /* UInt8 */}
                        ] }, 
        "metadata":{"description":""} },


    { "name": "ref/dali/scenes",
      "dataType": 19, /* Template */
      "template_value":{ "version": "v1",
                         "is_definition": true,
                         "metrics":[
                          { "name": "0",        "dataType": 19  /* Template - ref/dali/level */},
                          { "name": "1",        "dataType": 19  /* Template - ref/dali/level */},
                          { "name": "2",        "dataType": 19  /* Template - ref/dali/level */},
                          { "name": "3",        "dataType": 19  /* Template - ref/dali/level */},
                          { "name": "4",        "dataType": 19  /* Template - ref/dali/level */},
                          { "name": "5",        "dataType": 19  /* Template - ref/dali/level */},
                          { "name": "6",        "dataType": 19  /* Template - ref/dali/level */},
                          { "name": "7",        "dataType": 19  /* Template - ref/dali/level */},
                          { "name": "8",        "dataType": 19  /* Template - ref/dali/level */},
                          { "name": "9",        "dataType": 19  /* Template - ref/dali/level */},
                          { "name": "10",       "dataType": 19  /* Template - ref/dali/level */},
                          { "name": "11",       "dataType": 19  /* Template - ref/dali/level */},
                          { "name": "12",       "dataType": 19  /* Template - ref/dali/level */},
                          { "name": "13",       "dataType": 19  /* Template - ref/dali/level */},
                          { "name": "14",       "dataType": 19  /* Template - ref/dali/level */},
                          { "name": "15",       "dataType": 19  /* Template - ref/dali/level */}
                        ] }, 
        "metadata":{"description":""} },


    { "name": "ref/dali/gear",
      "dataType": 19, /* Template */
      "template_value":{ "version": "v1",
                         "is_definition": true,
                         "metrics":[
                          { "name": "status",        "dataType": 12/* String */},
                          { "name": "type",          "dataType": 12/* String */},
                          { "name": "gtin",          "dataType": 12/* String */},
                          { "name": "id",            "dataType": 12/* String */},

                          { "name": "level",         "dataType": 19 /* Template - ref/dali/level */},
                          { "name": "fade",          "dataType": 19 /* Template - ref/dali/fade */},

                          { "name": "powerOn",       "dataType": 19 /* Template - ref/dali/level */},
                          { "name": "failure",       "dataType": 19 /* Template - ref/dali/level */},                          

                          { "name": "scenes",        "dataType": 19 /* Template - ref/dali/scenes */},
                          
                        ] }, 
        "metadata":{"description":""} },

    { "name": "ref/dali/gears",
      "dataType": 19, /* Template */
      "template_value":{ "version": "v1",
                         "is_definition": true,
                         "metrics":[
                          { "name": "0",        "dataType": 19  /* Template - ref/dali/gear */},
                          { "name": "1",        "dataType": 19  /* Template - ref/dali/gear */},
                          { "name": "2",        "dataType": 19  /* Template - ref/dali/gear */},
                          { "name": "3",        "dataType": 19  /* Template - ref/dali/gear */},
                          { "name": "4",        "dataType": 19  /* Template - ref/dali/gear */},
                          { "name": "5",        "dataType": 19  /* Template - ref/dali/gear */},
                          { "name": "6",        "dataType": 19  /* Template - ref/dali/gear */},
                          { "name": "7",        "dataType": 19  /* Template - ref/dali/gear */},
                          { "name": "8",        "dataType": 19  /* Template - ref/dali/gear */},
                          { "name": "9",        "dataType": 19  /* Template - ref/dali/gear */},
                          { "name": "10",       "dataType": 19  /* Template - ref/dali/gear */},
                          { "name": "11",       "dataType": 19  /* Template - ref/dali/gear */},
                          { "name": "12",       "dataType": 19  /* Template - ref/dali/gear */},
                          { "name": "13",       "dataType": 19  /* Template - ref/dali/gear */},
                          { "name": "14",       "dataType": 19  /* Template - ref/dali/gear */},
                          { "name": "15",       "dataType": 19  /* Template - ref/dali/gear */},
                          { "name": "16",       "dataType": 19  /* Template - ref/dali/gear */},
                          { "name": "17",       "dataType": 19  /* Template - ref/dali/gear */},
                          { "name": "18",       "dataType": 19  /* Template - ref/dali/gear */},
                          { "name": "19",       "dataType": 19  /* Template - ref/dali/gear */},
                          { "name": "20",       "dataType": 19  /* Template - ref/dali/gear */},
                          { "name": "21",       "dataType": 19  /* Template - ref/dali/gear */},
                          { "name": "22",       "dataType": 19  /* Template - ref/dali/gear */},
                          { "name": "23",       "dataType": 19  /* Template - ref/dali/gear */},
                          { "name": "24",       "dataType": 19  /* Template - ref/dali/gear */},
                          { "name": "25",       "dataType": 19  /* Template - ref/dali/gear */},
                          { "name": "26",       "dataType": 19  /* Template - ref/dali/gear */},
                          { "name": "27",       "dataType": 19  /* Template - ref/dali/gear */},
                          { "name": "28",       "dataType": 19  /* Template - ref/dali/gear */},
                          { "name": "29",       "dataType": 19  /* Template - ref/dali/gear */},
                          { "name": "30",       "dataType": 19  /* Template - ref/dali/gear */},
                          { "name": "31",       "dataType": 19  /* Template - ref/dali/gear */}
                          
                        ] }, 
        "metadata":{"description":""} },




    { "name": "dali/0/gear",
      "dataType": 19, /* Template */
      "template_value":{ "version": "v1",
                         "is_definition": false,
                         "template_ref": "ref/dali/gears",
                         "metrics":[
                          { "name": "0",  "dataType": 19  /* Template - daliGear */, 
                              "template_value":{ "version": "v1",
                                                 "is_definition": false,
                                                 "template_ref": "ref/dali/gear",
                                                 "metrics":[
                                                  { "name": "status",  "dataType": 12/* String */, "string_value": "ok"},
                                                  { "name": "type",    "dataType": 12/* String */, "string_value": "LED"},
                                                  { "name": "gtin",    "dataType": 12/* String */, "string_value": "12165468465"},
                                                  { "name": "id",      "dataType": 12/* String */, "string_value": "0000-1121"},

                                                  { "name": "level",   "dataType": 19 /* Template - daliLevelTemplate */,
                                                      "template_value":{ "version": "v1",
                                                                         "is_definition": false,
                                                                         "metrics":[
                                                                          { "name": "dim", "dataType": 5  /* UInt8 */, "int_value": 0, 
                                                                            "properties":{ "keys": ["phy","min","max"], 
                                                                                           "values": [{"type":5,"int_value": 80},{"type":5,"int_value": 80},{"type":5,"int_value": 254}] } } ] } },


                                                  { "name": "fade",    "dataType": 19 /* Template - daliFadeTemplate */,
                                                      "template_value":{ "version": "v1",
                                                                         "is_definition": false,
                                                                         "template_ref": "ref/dali/fade",
                                                                         "metrics":[
                                                                          { "name": "time",        "dataType": 5  /* UInt8 */},
                                                                          { "name": "rate",        "dataType": 5  /* UInt8 */} ] } },

                                                  { "name": "powerOn", "dataType": 19 /* Template - daliLevelTemplate */,
                                                      "template_value":{ "version": "v1",
                                                                         "is_definition": false,
                                                                         "template_ref": "ref/dali/level",
                                                                         "metrics":[
                                                                          { "name": "dim", "dataType": 5  /* UInt8 */, "int_value": 254 } ] } },

                                                  { "name": "failure", "dataType": 19 /* Template - daliLevelTemplate */,
                                                      "template_value":{ "version": "v1",
                                                                         "is_definition": false,
                                                                         "template_ref": "ref/dali/level",
                                                                         "metrics":[
                                                                          { "name": "dim", "dataType": 5  /* UInt8 */, "int_value": 254 } ] } },                         

                                                  { "name": "scenes",  "dataType": 19 /* Template - daliScenesTemplate */,
                                                      "template_value":{ "version": "v1",
                                                      "is_definition": false,
                                                      "metrics":[
                                                       { "name": "0",        "dataType": 19  /* Template - ref/dali/level */,
                                                           "template_value":{ "version": "v1",
                                                                              "is_definition": false,
                                                                              "template_ref": "ref/dali/level",
                                                                              "metrics":[
                                                                               { "name": "dim", "dataType": 5  /* UInt8 */, "int_value": 254 } ] }},
                                                       { "name": "1",        "dataType": 19  /* Template - ref/dali/level */,
                                                           "template_value":{ "version": "v1",
                                                                              "is_definition": false,
                                                                              "template_ref": "ref/dali/level",
                                                                              "metrics":[
                                                                               { "name": "dim", "dataType": 5  /* UInt8 */, "int_value": 254 } ] }},
                                                       { "name": "2",        "dataType": 19  /* Template - ref/dali/level */,
                                                           "template_value":{ "version": "v1",
                                                                              "is_definition": false,
                                                                              "template_ref": "ref/dali/level",
                                                                              "metrics":[
                                                                               { "name": "dim", "dataType": 5  /* UInt8 */, "int_value": 254 } ] }},
                                                       { "name": "3",        "dataType": 19  /* Template - ref/dali/level */,
                                                           "template_value":{ "version": "v1",
                                                                              "is_definition": false,
                                                                              "template_ref": "ref/dali/level",
                                                                              "metrics":[
                                                                               { "name": "dim", "dataType": 5  /* UInt8 */, "int_value": 254 } ] }},
                                                       { "name": "4",        "dataType": 19  /* Template - ref/dali/level */,
                                                           "template_value":{ "version": "v1",
                                                                              "is_definition": false,
                                                                              "template_ref": "ref/dali/level",
                                                                              "metrics":[
                                                                               { "name": "dim", "dataType": 5  /* UInt8 */, "int_value": 254 } ] }},
                                                       { "name": "5",        "dataType": 19  /* Template - ref/dali/level */,
                                                           "template_value":{ "version": "v1",
                                                                              "is_definition": false,
                                                                              "template_ref": "ref/dali/level",
                                                                              "metrics":[
                                                                               { "name": "dim", "dataType": 5  /* UInt8 */, "int_value": 254 } ] }},
                                                       { "name": "6",        "dataType": 19  /* Template - ref/dali/level */,
                                                           "template_value":{ "version": "v1",
                                                                              "is_definition": false,
                                                                              "template_ref": "ref/dali/level",
                                                                              "metrics":[
                                                                               { "name": "dim", "dataType": 5  /* UInt8 */, "int_value": 254 } ] }},
                                                       { "name": "7",        "dataType": 19  /* Template - ref/dali/level */,
                                                           "template_value":{ "version": "v1",
                                                                              "is_definition": false,
                                                                              "template_ref": "ref/dali/level",
                                                                              "metrics":[
                                                                               { "name": "dim", "dataType": 5  /* UInt8 */, "int_value": 254 } ] }},
                                                       { "name": "8",        "dataType": 19  /* Template - ref/dali/level */,
                                                           "template_value":{ "version": "v1",
                                                                              "is_definition": false,
                                                                              "template_ref": "ref/dali/level",
                                                                              "metrics":[
                                                                               { "name": "dim", "dataType": 5  /* UInt8 */, "int_value": 254 } ] }},
                                                       { "name": "9",        "dataType": 19  /* Template - ref/dali/level */,
                                                           "template_value":{ "version": "v1",
                                                                              "is_definition": false,
                                                                              "template_ref": "ref/dali/level",
                                                                              "metrics":[
                                                                               { "name": "dim", "dataType": 5  /* UInt8 */, "int_value": 254 } ] }},
                                                       { "name": "10",       "dataType": 19  /* Template - ref/dali/level */,
                                                           "template_value":{ "version": "v1",
                                                                              "is_definition": false,
                                                                              "template_ref": "ref/dali/level",
                                                                              "metrics":[
                                                                               { "name": "dim", "dataType": 5  /* UInt8 */, "int_value": 254 } ] }},
                                                       { "name": "11",       "dataType": 19  /* Template - ref/dali/level */,
                                                           "template_value":{ "version": "v1",
                                                                              "is_definition": false,
                                                                              "template_ref": "ref/dali/level",
                                                                              "metrics":[
                                                                               { "name": "dim", "dataType": 5  /* UInt8 */, "int_value": 254 } ] }},
                                                       { "name": "12",       "dataType": 19  /* Template - ref/dali/level */,
                                                           "template_value":{ "version": "v1",
                                                                              "is_definition": false,
                                                                              "template_ref": "ref/dali/level",
                                                                              "metrics":[
                                                                               { "name": "dim", "dataType": 5  /* UInt8 */, "int_value": 254 } ] }},
                                                       { "name": "13",       "dataType": 19  /* Template - ref/dali/level */,
                                                           "template_value":{ "version": "v1",
                                                                              "is_definition": false,
                                                                              "template_ref": "ref/dali/level",
                                                                              "metrics":[
                                                                               { "name": "dim", "dataType": 5  /* UInt8 */, "int_value": 254 } ] }},
                                                       { "name": "14",       "dataType": 19  /* Template - ref/dali/level */,
                                                           "template_value":{ "version": "v1",
                                                                              "is_definition": false,
                                                                              "template_ref": "ref/dali/level",
                                                                              "metrics":[
                                                                               { "name": "dim", "dataType": 5  /* UInt8 */, "int_value": 254 } ] }},
                                                       { "name": "15",       "dataType": 19  /* Template - ref/dali/level */,
                                                           "template_value":{ "version": "v1",
                                                                              "is_definition": false,
                                                                              "template_ref": "ref/dali/level",
                                                                              "metrics":[
                                                                               { "name": "dim", "dataType": 5  /* UInt8 */, "int_value": 254 } ] }}, ] } }     
                                                 ]} },
                          
                          
                        ] }, 
        "metadata":{"description":""} },










    
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