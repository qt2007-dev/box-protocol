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


    { "name": "ref/control/velocity",
      "dataType": 19, /* Template */
      "template_value":{ "version": "velocity",
                         "is_definition": true,
                         "metrics":[
                              { "name": "velocity",     "dataType": 3/* Int32 */,    "metadata":{"description":"[RWP]Motor velocity"} },         
                              { "name": "enable",       "dataType": 11/* Boolean */, "metadata":{"description":"[RWP]Enable motor driver, send 'true' for enable"} },     
                        ] }, 
      "metadata":{"description":"Template definition of motor velocity mode"} },

    { "name": "ref/control/position",
      "dataType": 19, /* Template */
      "template_value":{ "version": "position",
                         "is_definition": true,
                         "metrics":[
                              { "name": "search",       "dataType": 12/* String */,  "metadata":{"description":"[W]Search motor home position, values = ['set', 'cw', ccw]"} },
                              { "name": "home",         "dataType": 12/* String */,  "metadata":{"description":"[RWP]Motor home sensor trigger, values = ['rising', 'falling']"} },
                              { "name": "encoder",      "dataType": 11/* Boolean */, "metadata":{"description":"[RWP]Use motor encoder"} },
                              { "name": "position",     "dataType": 3/* Int32 */,    "metadata":{"description":"[RWP]Motor position"} },                        
                              { "name": "enable",       "dataType": 11/* Boolean */, "metadata":{"description":"[RWP]Enable motor driver, send 'true' for enable"} },              
                        ] }, 
      "metadata":{"description":"Template definition of motor position mode"} },

    { "name": "ref/settings/current",
      "dataType": 19, /* Template */
      "template_value":{ "version": "current",
                         "is_definition": true,
                         "metrics":[
                              { "name": "boost",        "dataType": 5/* UInt8 */,    "metadata":{"description":"[RWP]Motor boost current [0-254] 254 - max current (100%)"} },  
                              { "name": "drive",        "dataType": 5/* UInt8 */,    "metadata":{"description":"[RWP]Motor drive current [0-254] 254 - max current (100%)"} },  
                              { "name": "hold",         "dataType": 5/* UInt8 */,    "metadata":{"description":"[RWP]Motor hold current [0-254] 254 - max current (100%)"} },             
                        ] }, 
      "metadata":{"description":"Template definition of motor current settings"} },

    { "name": "ref/settings/ramp/s-shape",
      "dataType": 19, /* Template */
      "template_value":{ "version": "s-shape",
                         "is_definition": true,
                         "metrics":[
                              { "name": "acceleration", "dataType": 7/* UInt32 */,   "metadata":{"description":"[RWP]Maximum motor acceleration value"} },                     
                              { "name": "deceleration", "dataType": 7/* UInt32 */,   "metadata":{"description":"[RWP]Maximum motor deceleration value"} },                     
                              { "name": "bow/1",        "dataType": 7/* UInt32 */,   "metadata":{"description":"[RWP]Determines the value which increases the absolute acceleration value"} },                     
                              { "name": "bow/2",        "dataType": 7/* UInt32 */,   "metadata":{"description":"[RWP]Determines the value which decreases the absolute acceleration value"} },  
                              { "name": "bow/3",        "dataType": 7/* UInt32 */,   "metadata":{"description":"[RWP]Determines the value which increases the absolute deceleration value"} },  
                              { "name": "bow/4",        "dataType": 7/* UInt32 */,   "metadata":{"description":"[RWP]Determines the value which decreases the absolute deceleration value"} },      
                        ] }, 
      "metadata":{"description":"Template definition of motor ramp settings"} },


    { "name": "motor/0/temperature",                    "dataType": 1/* Int8 */,     "int_value": 22,                    "metadata":{"description":"[R]Temperature sensor in motor driver, value in Celsius"} },    
    { "name": "motor/0/current",
      "dataType": 19, /* Template */
      "template_value":{ "version": "current",
                         "is_definition": false,
                         "template_ref": "ref/settings/current",
                         "metrics":[
                              { "name": "boost",        "int_value": 160,},
                              { "name": "drive",        "int_value": 128 },                        
                              { "name": "hold",         "int_value": 128  },    
                        ] }, 
      "metadata":{"description":"[RWP]Motor current settings, 'template_ref' values = 'ref/settings/current'"} },

    { "name": "motor/0/ramp",
      "dataType": 19, /* Template */
      "template_value":{ "version": "s-shape",
                         "is_definition": false,
                         "template_ref": "ref/settings/ramp/s-shape",
                         "metrics":[
                              { "name": "acceleration", "int_value": 80000 },                     
                              { "name": "deceleration", "int_value": 120000 },                     
                              { "name": "bow/1",        "int_value": 40000 },                     
                              { "name": "bow/2",        "int_value": 20000 },  
                              { "name": "bow/3",        "int_value": 20000 },  
                              { "name": "bow/4",        "int_value": 40000 },   
                        ] }, 
      "metadata":{"description":"[RWP]Motor ramp settings, 'template_ref' values = 'ref/settings/ramp/..'"} },

    { "name": "motor/0/control",
      "dataType": 19, /* Template */
      "template_value":{ "version": "velocity",
                         "is_definition": false,
                         "template_ref": "ref/control/velocity",
                         "metrics":[
                              { "name": "velocity",    "int_value": 100000 },                        
                              { "name": "enable",      "boolean_value": true }
                        ] }, 
      "metadata":{"description":"[RWP]Motor control, 'template_ref' values = 'ref/control/..'"} },

    { "name": "motor/1/temperature",                    "dataType": 1/* Int8 */,     "int_value": 22,                    "metadata":{"description":"[R]Temperature sensor in motor driver, value in Celsius"} },
    { "name": "motor/1/current",
      "dataType": 19, /* Template */
      "template_value":{ "version": "current",
                         "is_definition": false,
                         "template_ref": "ref/settings/current",
                         "metrics":[
                              { "name": "boost",        "int_value": 160,},
                              { "name": "drive",        "int_value": 128 },                        
                              { "name": "hold",         "int_value": 128  },    
                        ] }, 
      "metadata":{"description":"[RWP]Motor current settings, 'template_ref' values = 'ref/settings/current'"} },

    { "name": "motor/1/ramp",
      "dataType": 19, /* Template */
      "template_value":{ "version": "s-shape",
                         "is_definition": false,
                         "template_ref": "ref/settings/ramp/s-shape",
                         "metrics":[
                              { "name": "acceleration", "int_value": 80000 },                     
                              { "name": "deceleration", "int_value": 120000 },                     
                              { "name": "bow/1",        "int_value": 40000 },                     
                              { "name": "bow/2",        "int_value": 20000 },  
                              { "name": "bow/3",        "int_value": 20000 },  
                              { "name": "bow/4",        "int_value": 40000 },   
                        ] }, 
      "metadata":{"description":"[RWP]Motor ramp settings, 'template_ref' values = 'ref/settings/ramp/..'"} },

    { "name": "motor/1/control",
      "dataType": 19, /* Template */
      "template_value":{ "version": "position",
                         "is_definition": false,
                         "template_ref": "ref/control/position",
                         "metrics":[
                              { "name": "search",       "string_value": "" },
                              { "name": "home",         "string_value": "falling" },
                              { "name": "encoder",      "boolean_value": true },  
                              { "name": "position",     "int_value": 100000 },                        
                              { "name": "enable",       "boolean_value": true },    
                        ] }, 
      "metadata":{"description":"[RWP]Motor control, 'template_ref' values = 'ref/control/..'"} },      
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