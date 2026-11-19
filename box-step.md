## BOX device step birth example
> spBv1.0/box/DBIRTH/abba2020/deba0008 

```json
{
"timestamp": 1486144502122,
"seq": 0,
"metrics": [
    { "name": "bdSeq",                                  "dataType": 4/* Int64 */,    "long_value": 0,                    "metadata":{"description":"[R]Birth-death sequence, 'online' - [BIRTH > DEATH], 'offline' - [BIRTH <= DEATH]"} },
    { "name": "control/reboot",                         "dataType": 11/* Boolean */, "boolean_value": false,             "metadata":{"description":"[W]Software reboot, send 'true' for reboot"} },
    { "name": "control/rebirth",                        "dataType": 11/* Boolean */, "boolean_value": false,             "metadata":{"description":"[W]Rebirth, send 'true' for receive birth message again"} },
    { "name": "control/firmware/new",                   "dataType": 17/* Bytes */,   "bytes_value":"", "is_null": true,  "metadata":{"description":"[W]Receive new firmware, firmware send in Base64 format, in birth always null"} },
    { "name": "control/metrics/save",                   "dataType": 11/* Boolean */, "boolean_value": true,              "metadata":{"description":"[RWP]Save metrics states after reboot, send 'true' for enable"} },
    { "name": "control/metrics/metadata",               "dataType": 11/* Boolean */, "boolean_value": true,              "metadata":{"description":"[RWP]Show metrics metadata in birth, send 'true' for enable"} },
    { "name": "control/alias",                          "dataType": 12/* String */,  "string_value": "step",             "metadata":{"description":"[RWP]Global alias, can be used instead id in topics and scenarios"} },

    { "name": "info/hardware/vendor",                   "dataType": 12/* String */,  "string_value": "QuintTech" ,       "metadata":{"description":"[R]Vendor name, hardcoded by vendor"} },
    { "name": "info/hardware/model",                    "dataType": 12/* String */,  "string_value": "stm32g474ce",      "metadata":{"description":"[R]Mcu model, hardcoded by vendor"} },
    { "name": "info/firmware/version",                  "dataType": 12/* String */,  "string_value": "0.1.220527",       "metadata":{"description":"[R]Firmware version, MAJOR.MINOR.buildOrCommit"} },
    { "name": "info/type",                              "dataType": 12/* String */,  "string_value": "STEP 2",           "metadata":{"description":"[R]Device type, hardcoded by vendor"} },
    { "name": "info/id",                                "dataType": 12/* String */,  "string_value": "deba0008",         "metadata":{"description":"[R]Short device id"} },
    { "name": "info/error",                             "dataType": 12/* String */,  "string_value": "",                 "metadata":{"description":"[R]Last error message"} },
    { "name": "info/warning",                           "dataType": 12/* String */,  "string_value": "",                 "metadata":{"description":"[R]Last warning message"} },

    { "name": "sensors/temperature",                    "dataType": 1/* Int8 */,     "int_value": 22,                    "metadata":{"description":"[R]Temperature sensor in mcu, value in Celsius"} },


    { "name": "ref/control/velocity",
      "dataType": 19, /* Template */
      "template_value":{ "version": "control",
                         "is_definition": true,
                         "metrics":[
                              { "name": "target",       "dataType": 3/* Int32 */,    "int_value": 0,         "metadata":{"description":"[RW]Motor target velocity"} }, 
                              { "name": "velocity",     "dataType": 3/* Int32 */,    "int_value": 0,         "metadata":{"description":"[R]Motor current velocity"} },           
                              { "name": "enable",       "dataType": 11/* Boolean */, "boolean_value": false, "metadata":{"description":"[RW]Enable motor driver, send 'true' for enable"} }    
                        ] }, 
      "metadata":{"description":"Template definition of motor velocity mode"} },

    { "name": "ref/control/position",
      "dataType": 19, /* Template */
      "template_value":{ "version": "control",
                         "is_definition": true,
                         "metrics":[
                              { "name": "homing",       "dataType": 12/* String */,                           "metadata":{"description":"[W]Search motor home position, values = ['set', 'search']"} },     
                              { "name": "speed",        "dataType": 7/* UInt32 */,   "int_value": 0,          "metadata":{"description":"[RWP]Motor speed"} },
                              { "name": "target",       "dataType": 3/* Int32 */,    "int_value": 0,          "metadata":{"description":"[RW]Motor target position"} },
                              { "name": "position",     "dataType": 3/* Int32 */,    "int_value": 0,          "metadata":{"description":"[R]Motor position"} },         
                              { "name": "stop",         "dataType": 11/* Boolean */, "is_null": true,         "metadata":{"description":"[W]Stop motor, send 'true' for soft stop"} },               
                              { "name": "enable",       "dataType": 11/* Boolean */, "boolean_value": false,  "metadata":{"description":"[RW]Enable motor driver, send 'true' for enable"} }             
                        ] }, 
      "metadata":{"description":"Template definition of motor position mode"} },

    { "name": "ref/settings",
      "dataType": 19, /* Template */
      "template_value":{ "version": "settings",
                         "is_definition": true,
                         "metrics":[
                              { "name": "encoder",      "dataType": 11/* Boolean */, "boolean_value": false,  "metadata":{"description":"[RWP]Use motor encoder"} },
                              { "name": "ppr",          "dataType": 7/* UInt32 */,   "int_value": 1000,       "metadata":{"description":"[RWP]Encoder pulses per revolution"} },                                   
                              { "name": "tolerance",    "dataType": 7/* UInt32 */,   "int_value": 500,        "metadata":{"description":"[RWP]Encoder tolerance between encoder and internal position"} },                
                              { "name": "fullsteps",    "dataType": 7/* UInt32 */,   "int_value": 200,        "metadata":{"description":"[RWP]Motor steps per revolution"} },
                              { "name": "microsteps",   "dataType": 7/* UInt32 */,   "int_value": 256,        "metadata":{"description":"[RWP]Motor microsteps mode"} }
                        ] }, 
      "metadata":{"description":"Template definition of motor settings"} },

    { "name": "ref/settings/home",
      "dataType": 19, /* Template */
      "template_value":{ "version": "home",
                         "is_definition": true,
                         "metrics":[
                              
                              { "name": "polarity",   "dataType": 12/* String */,  "string_value": "high",     "metadata":{"description":"[RWP]Motor home sensor polarity in home, values = ['high', 'low']"} },
                              { "name": "edge",       "dataType": 12/* String */,  "string_value": "rising",   "metadata":{"description":"[RWP]Motor home sensor edge, values = ['rising', 'falling']"} },
                              { "name": "direction",  "dataType": 12/* String */,  "string_value": "positive", "metadata":{"description":"[RWP]Motor home search direction, values = ['negative', 'positive']"} },
                              { "name": "offset",     "dataType": 3/* Int32 */,    "int_value": 0,             "metadata":{"description":"[RWP]Motor home sensor position offset"} },
                              { "name": "escape",     "dataType": 3/* Int32 */,    "int_value": 0,             "metadata":{"description":"[RWP]Motor home escape before start search"} },
                              { "name": "speed",      "dataType": 7/* UInt32 */,   "int_value": 0,             "metadata":{"description":"[RWP]Motor home search speed"} }

                        ] }, 
      "metadata":{"description":"Template definition of home sensor settings"} },

    { "name": "ref/settings/current",
      "dataType": 19, /* Template */
      "template_value":{ "version": "current",
                         "is_definition": true,
                         "metrics":[
                              { "name": "boost",   "dataType": 5/* UInt8 */, "int_value": 20,   "metadata":{"description":"[RWP]Motor boost current [0-254] 254 - max current (100%)"} },  
                              { "name": "drive",   "dataType": 5/* UInt8 */, "int_value": 20,   "metadata":{"description":"[RWP]Motor drive current [0-254] 254 - max current (100%)"} },  
                              { "name": "hold",    "dataType": 5/* UInt8 */, "int_value": 10,   "metadata":{"description":"[RWP]Motor hold current [0-254] 254 - max current (100%)"} }             
                        ] }, 
      "metadata":{"description":"Template definition of motor current settings"} },

    { "name": "ref/settings/ramp/s-shape",
      "dataType": 19, /* Template */
      "template_value":{ "version": "ramp",
                         "is_definition": true,
                         "metrics":[
                              { "name": "acceleration", "dataType": 7/* UInt32 */,  "int_value": 5000000,   "metadata":{"description":"[RWP]Maximum motor acceleration value"} },                     
                              { "name": "deceleration", "dataType": 7/* UInt32 */,  "int_value": 1000000,   "metadata":{"description":"[RWP]Maximum motor deceleration value"} },                     
                              { "name": "bow/1",        "dataType": 7/* UInt32 */,  "int_value": 1000000,   "metadata":{"description":"[RWP]Determines the value which increases the absolute acceleration value"} },                     
                              { "name": "bow/2",        "dataType": 7/* UInt32 */,  "int_value": 4000000,   "metadata":{"description":"[RWP]Determines the value which decreases the absolute acceleration value"} },  
                              { "name": "bow/3",        "dataType": 7/* UInt32 */,  "int_value": 1000000,   "metadata":{"description":"[RWP]Determines the value which increases the absolute deceleration value"} },  
                              { "name": "bow/4",        "dataType": 7/* UInt32 */,  "int_value": 250000,    "metadata":{"description":"[RWP]Determines the value which decreases the absolute deceleration value"} }      
                        ] }, 
      "metadata":{"description":"Template definition of motor ramp settings"} },


    { "name": "motor/0/temperature",   "dataType": 1/* Int8 */,     "int_value": 22,          "metadata":{"description":"[R]Temperature sensor in motor driver, value in Celsius"} },    
    { "name": "motor/0/state",         "dataType": 12/* String */,  "string_value": "idle",   "metadata":{"description":"[R]Motor state, values = ['idle', 'rotating', 'stopping' 'positioning', 'positioned', 'homing']"} },
    { "name": "motor/0/status",        "dataType": 12/* String */,  "string_value": "ok",     "metadata":{"description":"[R]Motor status, values = ['ok', 'stall', 'encoder-fail' 'over-temperature', 'short-to-ground', 'open-load']"} },


    { "name": "motor/0/settings",
      "dataType": 19, /* Template */
      "template_value":{ "version": "settings",
                         "is_definition": false,
                         "template_ref": "ref/settings",
                         "metrics":[
                              { "name": "encoder",    "dataType": 11/* Boolean */, "boolean_value": false, "metadata":{"description":"[RWP]Use motor encoder"} },
                              { "name": "ppr",        "dataType": 7/* UInt32 */,   "int_value": 1000,      "metadata":{"description":"[RWP]Encoder pulses per revolution"} },          
                              { "name": "tolerance",  "dataType": 7/* UInt32 */,   "int_value": 500,       "metadata":{"description":"[RWP]Tolerance between internal and encoder position"} },    
                              { "name": "fullsteps",  "dataType": 7/* UInt32 */,   "int_value": 200,       "metadata":{"description":"[RWP]Motor steps per revolution"} },
                              { "name": "microsteps",   "dataType": 7/* UInt32 */, "int_value": 256,       "metadata":{"description":"[RWP]Motor microsteps mode"} }                              
                        ] }, 
      "metadata":{"description":"[RWP]Motor settings, 'template_ref' values = 'ref/settings'"} },

    { "name": "motor/0/home",
      "dataType": 19, /* Template */
      "template_value":{ "version": "home",
                         "is_definition": false,
                         "template_ref": "ref/settings/home",
                         "metrics":[
                              { "name": "polarity",  "dataType": 12/* String */,  "string_value": "high",     "metadata":{"description":"[RWP]Motor home sensor polarity in home, values = ['high', 'low']"} },
                              { "name": "edge",      "dataType": 12/* String */,  "string_value": "rising",   "metadata":{"description":"[RWP]Motor home sensor edge, values = ['rising', 'falling']"} },
                              { "name": "direction", "dataType": 12/* String */,  "string_value": "positive", "metadata":{"description":"[RWP]Motor home search direction, values = ['negative', 'positive']"} },
                              { "name": "offset",    "dataType": 3/* Int32 */,    "int_value": 0,             "metadata":{"description":"[RWP]Motor home sensor position offset"} },
                              { "name": "escape",    "dataType": 3/* Int32 */,    "int_value": 0,             "metadata":{"description":"[RWP]Motor home escape before start search"} },
                              { "name": "speed",     "dataType": 7/* UInt32 */,   "int_value": 0,             "metadata":{"description":"[RWP]Motor home search speed"} }
                        ] }, 
      "metadata":{"description":"Template definition of home sensor settings"} },

    { "name": "motor/0/current",
      "dataType": 19, /* Template */
      "template_value":{ "version": "current",
                         "is_definition": false,
                         "template_ref": "ref/settings/current",
                         "metrics":[
                              { "name": "boost",   "dataType": 5/* UInt8 */,  "int_value": 20, "metadata":{"description":"[RWP]Motor boost current [0-254] 254 - max current (100%)"} },  
                              { "name": "drive",   "dataType": 5/* UInt8 */,  "int_value": 20, "metadata":{"description":"[RWP]Motor drive current [0-254] 254 - max current (100%)"} },                          
                              { "name": "hold",    "dataType": 5/* UInt8 */,  "int_value": 10, "metadata":{"description":"[RWP]Motor hold current [0-254] 254 - max current (100%)"} }      
                        ] }, 
      "metadata":{"description":"[RWP]Motor current settings, 'template_ref' values = 'ref/settings/current'"} },

    { "name": "motor/0/ramp",
      "dataType": 19, /* Template */
      "template_value":{ "version": "ramp",
                         "is_definition": false,
                         "template_ref": "ref/settings/ramp/s-shape",
                         "metrics":[
                              { "name": "acceleration", "dataType": 7/* UInt32 */, "int_value": 5000000 , "metadata":{"description":"[RWP]Maximum motor acceleration value"} },                                          
                              { "name": "deceleration", "dataType": 7/* UInt32 */, "int_value": 1000000 , "metadata":{"description":"[RWP]Maximum motor deceleration value"} },                                          
                              { "name": "bow/1",        "dataType": 7/* UInt32 */, "int_value": 1000000 , "metadata":{"description":"[RWP]Determines the value which increases the absolute acceleration value"} },                       
                              { "name": "bow/2",        "dataType": 7/* UInt32 */, "int_value": 4000000 , "metadata":{"description":"[RWP]Determines the value which decreases the absolute acceleration value"} },    
                              { "name": "bow/3",        "dataType": 7/* UInt32 */, "int_value": 1000000 , "metadata":{"description":"[RWP]Determines the value which increases the absolute deceleration value"} },    
                              { "name": "bow/4",        "dataType": 7/* UInt32 */, "int_value": 250000  , "metadata":{"description":"[RWP]Determines the value which decreases the absolute deceleration value"} }   
                        ] }, 
      "metadata":{"description":"[RWP]Motor ramp settings, 'template_ref' values = 'ref/settings/ramp/..'"} },

    { "name": "motor/0/control",
      "dataType": 19, /* Template */
      "template_value":{ "version": "control",
                         "is_definition": false,
                         "template_ref": "ref/control/velocity",
                         "metrics":[
                              { "name": "target",   "dataType": 3/* Int32 */,    "int_value": 0,         "metadata":{"description":"[RW]Motor target velocity"} },
                              { "name": "velocity", "dataType": 3/* Int32 */,    "int_value": 0,         "metadata":{"description":"[R]Motor current velocity"} },                                 
                              { "name": "enable",   "dataType": 11/* Boolean */, "boolean_value": false, "metadata":{"description":"[RW]Enable motor driver, send 'true' for enable"} } 
                        ] }, 
      "metadata":{"description":"[RWP]Motor control, 'template_ref' values = 'ref/control/..'"} },

    { "name": "motor/1/temperature",   "dataType": 1/* Int8 */,     "int_value": 22,          "metadata":{"description":"[R]Temperature sensor in motor driver, value in Celsius"} },
    { "name": "motor/1/state",         "dataType": 12/* String */,  "string_value": "idle",   "metadata":{"description":"[R]Motor state, values = ['idle', 'rotating', 'stopping' 'positioning', 'positioned', 'homing']"} },
    { "name": "motor/1/status",        "dataType": 12/* String */,  "string_value": "ok",     "metadata":{"description":"[R]Motor status, values = ['ok', 'stall', 'encoder-fail' 'over-temperature', 'short-to-ground', 'open-load']"} },

    { "name": "motor/1/settings",
      "dataType": 19, /* Template */
      "template_value":{ "version": "settings",
                         "is_definition": false,
                         "template_ref": "ref/settings",
                         "metrics":[
                              { "name": "encoder",   "dataType": 11/* Boolean */,  "boolean_value": false ,"metadata":{"description":"[RWP]Use motor encoder"} },
                              { "name": "ppr",       "dataType": 7/* UInt32 */,    "int_value": 1000      ,"metadata":{"description":"[RWP]Encoder pulses per revolution"} },      
                              { "name": "tolerance", "dataType": 7/* UInt32 */,    "int_value": 500       ,"metadata":{"description":"[RWP]Encoder tolerance between encoder and internal position"} },           
                              { "name": "fullsteps", "dataType": 7/* UInt32 */,    "int_value": 200       ,"metadata":{"description":"[RWP]Motor steps per revolution"} },
                              { "name": "microsteps","dataType": 7/* UInt32 */,    "int_value": 256       ,"metadata":{"description":"[RWP]Motor microsteps mode"} }                            
                        ] }, 
      "metadata":{"description":"[RWP]Motor settings, 'template_ref' values = 'ref/settings'"} },

    { "name": "motor/1/home",
      "dataType": 19, /* Template */
      "template_value":{ "version": "home",
                         "is_definition": false,
                         "template_ref": "ref/settings/home",
                         "metrics":[
                              { "name": "polarity",  "dataType": 12/* String */,  "string_value": "high"     , "metadata":{"description":"[RWP]Motor home sensor polarity in home, values = ['high', 'low']"} },
                              { "name": "edge",      "dataType": 12/* String */,  "string_value": "rising"   , "metadata":{"description":"[RWP]Motor home sensor edge, values = ['rising', 'falling']"} },
                              { "name": "direction", "dataType": 12/* String */,  "string_value": "positive" , "metadata":{"description":"[RWP]Motor home search direction, values = ['negative', 'positive']"} },
                              { "name": "offset",    "dataType": 3/* Int32 */,    "int_value": 0             , "metadata":{"description":"[RWP]Motor home sensor position offset"} },
                              { "name": "escape",    "dataType": 3/* Int32 */,    "int_value": 0             , "metadata":{"description":"[RWP]Motor home escape before start search"} },
                              { "name": "speed",     "dataType": 7/* UInt32 */,   "int_value": 0             , "metadata":{"description":"[RWP]Motor home search speed"} }
                        ] }, 
      "metadata":{"description":"Template definition of home sensor settings"} },

    { "name": "motor/1/current",
      "dataType": 19, /* Template */
      "template_value":{ "version": "current",
                         "is_definition": false,
                         "template_ref": "ref/settings/current",
                         "metrics":[
                              { "name": "boost",  "dataType": 5/* UInt8 */,  "int_value": 20, "metadata":{"description":"[RWP]Motor boost current [0-254] 254 - max current (100%)"} },  
                              { "name": "drive",  "dataType": 5/* UInt8 */,  "int_value": 20, "metadata":{"description":"[RWP]Motor drive current [0-254] 254 - max current (100%)"} },                         
                              { "name": "hold",   "dataType": 5/* UInt8 */,  "int_value": 10, "metadata":{"description":"[RWP]Motor hold current [0-254] 254 - max current (100%)"} }      
                        ] }, 
      "metadata":{"description":"[RWP]Motor current settings, 'template_ref' values = 'ref/settings/current'"} },

    { "name": "motor/1/ramp",
      "dataType": 19, /* Template */
      "template_value":{ "version": "ramp",
                         "is_definition": false,
                         "template_ref": "ref/settings/ramp/s-shape",
                         "metrics":[
                              { "name": "acceleration", "dataType": 7/* UInt32 */, "int_value": 5000000, "metadata":{"description":"[RWP]Maximum motor acceleration value"} },                      
                              { "name": "deceleration", "dataType": 7/* UInt32 */, "int_value": 1000000, "metadata":{"description":"[RWP]Maximum motor deceleration value"} },                      
                              { "name": "bow/1",        "dataType": 7/* UInt32 */, "int_value": 1000000, "metadata":{"description":"[RWP]Determines the value which increases the absolute acceleration value"} },                      
                              { "name": "bow/2",        "dataType": 7/* UInt32 */, "int_value": 4000000, "metadata":{"description":"[RWP]Determines the value which decreases the absolute acceleration value"} },   
                              { "name": "bow/3",        "dataType": 7/* UInt32 */, "int_value": 1000000, "metadata":{"description":"[RWP]Determines the value which increases the absolute deceleration value"} },   
                              { "name": "bow/4",        "dataType": 7/* UInt32 */, "int_value": 250000 , "metadata":{"description":"[RWP]Determines the value which decreases the absolute deceleration value"} }    
                        ] }, 
      "metadata":{"description":"[RWP]Motor ramp settings, 'template_ref' values = 'ref/settings/ramp/..'"} },

    { "name": "motor/1/control",
      "dataType": 19, /* Template */
      "template_value":{ "version": "control",
                         "is_definition": false,
                         "template_ref": "ref/control/position",
                         "metrics":[
                              { "name": "homing",   "dataType": 12/* String */,    "string_value": "",       "metadata":{"description":"[W]Search motor home position, values = ['set', 'search']"} },       
                              { "name": "speed",    "dataType": 7/* UInt32 */,     "int_value": 0,           "metadata":{"description":"[RWP]Motor speed"} },    
                              { "name": "target",   "dataType": 3/* Int32 */,      "int_value": 0,           "metadata":{"description":"[RW]Motor target position"} },    
                              { "name": "position", "dataType": 3/* Int32 */,      "int_value": 0,           "metadata":{"description":"[R]Motor position"} },   
                              { "name": "stop",     "dataType": 11/* Boolean */,   "is_null": true,          "metadata":{"description":"[W]Stop motor, send 'true' for soft stop"} },                                                 
                              { "name": "enable",   "dataType": 11/* Boolean */,   "boolean_value": false,   "metadata":{"description":"[RW]Enable motor driver, send 'true' for enable"} }                  
                        ] }, 
      "metadata":{"description":"[RWP]Motor control, 'template_ref' values = 'ref/control/..'"} }     
  ]
         
}
```

## BOX device step death example
> spBv1.0/box/DDEATH/abba2020/deba0008 

```json
{
"timestamp": 1486144502122,
"metrics": [  
    { "name": "bdSeq",                                  "dataType": 8/* Uint64 */,   "long_value": 0,                    "metadata":{"description":"[R]Birth-death sequence, 'online' - [BIRTH > DEATH], 'offline' - [BIRTH <= DEATH]"} },  
]
}
```