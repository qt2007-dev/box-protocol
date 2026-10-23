## BOX device energymeter birth example
> spBv1.0/box/DBIRTH/abba2020/deba0007 

```json
{
"timestamp": 1486144502122,
"seq": 0,
"metrics": [
    { "name": "bdSeq",                          "dataType": 8/* Uint64 */,   "long_value": 0,                    "metadata":{"description":"[R]Birth-death sequence, 'online' - [BIRTH > DEATH], 'offline' - [BIRTH <= DEATH]"} },
    { "name": "control/reboot",                 "dataType": 11/* Boolean */, "boolean_value": false,             "metadata":{"description":"[W]Software reboot, send 'true' for reboot"} },
    { "name": "control/rebirth",                "dataType": 11/* Boolean */, "boolean_value": false,             "metadata":{"description":"[W]Rebirth, send 'true' for receive birth message again"} },
    { "name": "control/firmware/new",           "dataType": 17/* Bytes */,   "bytes_value":"", "is_null": true,  "metadata":{"description":"[W]Receive new firmware, firmware send in Base64 format, in birth always null"} },
    { "name": "control/metrics/save",           "dataType": 11/* Boolean */, "boolean_value": true,              "metadata":{"description":"[RWP]Save metrics states after reboot, send 'true' for enable"} },
    { "name": "control/metrics/metadata",       "dataType": 11/* Boolean */, "boolean_value": true,              "metadata":{"description":"[RWP]Show metrics metadata in birth, send 'true' for enable"} },
    { "name": "control/alias",                  "dataType": 12/* String */,  "string_value": "em",               "metadata":{"description":"[RWP]Global alias, can be used instead id in topics and scenarios"} },

    { "name": "info/hardware/vendor",           "dataType": 12/* String */,  "string_value": "QuintTech" ,       "metadata":{"description":"[R]Vendor name, hardcoded by vendor"} },
    { "name": "info/hardware/model",            "dataType": 12/* String */,  "string_value": "stm32g474ce",      "metadata":{"description":"[R]Mcu model, hardcoded by vendor"} },
    { "name": "info/firmware/version",          "dataType": 12/* String */,  "string_value": "0.1.220527.84852", "metadata":{"description":"[R]Firmware version, MAJOR.MINOR.buildOrCommit"} },
    { "name": "info/type",                      "dataType": 12/* String */,  "string_value": "Energymeter",      "metadata":{"description":"[R]Device type, hardcoded by vendor"} },
    { "name": "info/id",                        "dataType": 12/* String */,  "string_value": "deba0007",         "metadata":{"description":"[R]Short device id"} },
    { "name": "info/error",                     "dataType": 12/* String */,  "string_value": "",                 "metadata":{"description":"[R]Last error message"} },
    { "name": "info/warning",                   "dataType": 12/* String */,  "string_value": "",                 "metadata":{"description":"[R]Last warning message"} },

    { "name": "sensors/temperature",            "dataType": 1/* Int8 */,     "int_value": 22,                    "metadata":{"description":"[R]Temperature sensor in mcu, value in Celsius"} },

    { "name": "settings/transformer",           "dataType": 7/* UInt32 */,    "int_value": 2000,                  "metadata":{"description":"[RWP]Current transformer ratio"} },

    { "name": "ref/phase",
      "dataType": 19, /* Template */
      "template_value":{ "version": "phase",
                         "is_definition": true,
                         "metrics":[
                          { "name": "voltage",            "dataType": 9/* Float */,     "metadata":{"description":"[R]Phase A rms voltage, value in V"},        "properties":{ "keys": ["threshold"], "values": [{"type": 9, "float_value": 0.5}]} },
                          { "name": "current",            "dataType": 9/* Float */,     "metadata":{"description":"[R]Phase A rms current, value in A"},        "properties":{ "keys": ["threshold"], "values": [{"type": 9, "float_value": 0.01}]} },
                          { "name": "frequency",          "dataType": 9/* Float */,     "metadata":{"description":"[R]Phase A frequency, value in Hz"},         "properties":{ "keys": ["threshold"], "values": [{"type": 9, "float_value": 0.1}]} },
                    
                          { "name": "power/active",       "dataType": 9/* Float */,     "metadata":{"description":"[R]Phase A active power, value in W"},       "properties":{ "keys": ["threshold"], "values": [{"type": 9, "float_value": 1}]} },
                          { "name": "power/reactive",     "dataType": 9/* Float */,     "metadata":{"description":"[R]Phase A reactive power, value in VAR"},   "properties":{ "keys": ["threshold"], "values": [{"type": 9, "float_value": 1}]} },
                          { "name": "power/apparent",     "dataType": 9/* Float */,     "metadata":{"description":"[R]Phase A apparent power, value in VA"},    "properties":{ "keys": ["threshold"], "values": [{"type": 9, "float_value": 1}]} },
                          { "name": "power/factor",       "dataType": 9/* Float */,     "metadata":{"description":"[R]Phase A power factor"},                   "properties":{ "keys": ["threshold"], "values": [{"type": 9, "float_value": 0.01}]} },

                          { "name": "energy/active",      "dataType": 10/* Double */,   "metadata":{"description":"[RWP]Phase A active energy, value in Wh"},     "properties":{ "keys": ["threshold"], "values": [{"type": 9, "float_value": 1}]} },
                          { "name": "energy/reactive",    "dataType": 10/* Double */,   "metadata":{"description":"[RWP]Phase A reactive energy, value in VARh"}, "properties":{ "keys": ["threshold"], "values": [{"type": 9, "float_value": 1}]} },
                          { "name": "energy/apparent",    "dataType": 10/* Double */,   "metadata":{"description":"[RWP]Phase A apparent energy, value in VAh"},  "properties":{ "keys": ["threshold"], "values": [{"type": 9, "float_value": 1}]} },

                          { "name": "distortion/voltage", "dataType": 9/* Float */,     "metadata":{"description":"[R]Phase A voltage total harmonic distortion, value in %"},  "properties":{ "keys": ["threshold"], "values": [{"type": 9, "float_value": 0.5}]} },
                          { "name": "distortion/current", "dataType": 9/* Float */,     "metadata":{"description":"[R]Phase A current total harmonic distortion, value in %"},  "properties":{ "keys": ["threshold"], "values": [{"type": 9, "float_value": 0.5}]} }
                                  
                        ] }, 
      "metadata":{"description":"Template definition of phase measurements"} },

    { "name": "phase/a",
      "dataType": 19, /* Template */
      "template_value":{ "version": "phase",
                         "is_definition": false,
                         "template_ref": "ref/phase",
                         "metrics":[
                          { "name": "voltage", "dataType": 9/* Float */, "float_value": 220.4, "metadata":{"description":"[R]Phase A rms voltage, value in V"},
                            "properties":{ "keys": ["threshold"], "values": [{"type": 9, "float_value": 0.5}]} },
                          { "name": "current", "dataType": 9/* Float */, "float_value": 10.4, "metadata":{"description":"[R]Phase A rms current, value in A"},     
                            "properties":{ "keys": ["threshold"], "values": [{"type": 9, "float_value": 0.01}]} },                          
                          { "name": "frequency", "dataType": 9/* Float */, "float_value": 50.0, "metadata":{"description":"[R]Phase A frequency, value in Hz"},      
                            "properties":{ "keys": ["threshold"], "values": [{"type": 9, "float_value": 0.1}]} },

                          { "name": "power/active", "dataType": 9/* Float */, "float_value": 2000.4, "metadata":{"description":"[R]Phase A active power, value in W"},   
                            "properties":{ "keys": ["threshold"], "values": [{"type": 9, "float_value": 1}]} },
                          { "name": "power/reactive", "dataType": 9/* Float */, "float_value": 100.3, "metadata":{"description":"[R]Phase A reactive power, value in VAR"},   
                            "properties":{ "keys": ["threshold"], "values": [{"type": 9, "float_value": 1}]} },
                          { "name": "power/apparent", "dataType": 9/* Float */, "float_value": 50.7, "metadata":{"description":"[R]Phase A apparent power, value in VA"},    
                            "properties":{ "keys": ["threshold"], "values": [{"type": 9, "float_value": 1}]} },
                          { "name": "power/factor", "dataType": 9/* Float */, "float_value": 2200.8, "metadata":{"description":"[R]Phase A power factor"},  
                            "properties":{ "keys": ["threshold"], "values": [{"type": 9, "float_value": 0.01}]} },

                          { "name": "energy/active", "dataType": 10/* Double */, "double_value": 712340.4, "metadata":{"description":"[RWP]Phase A active energy, value in Wh"},
                            "properties":{ "keys": ["threshold"], "values": [{"type": 9, "float_value": 1}]} },
                          { "name": "energy/reactive", "dataType": 10/* Double */, "double_value": 1057.4, "metadata":{"description":"[RWP]Phase A reactive energy, value in VARh"}, 
                            "properties":{ "keys": ["threshold"], "values": [{"type": 9, "float_value": 1}]} },
                          { "name": "energy/apparent", "dataType": 10/* Double */, "double_value": 564.4, "metadata":{"description":"[RWP]Phase A apparent energy, value in VAh"},  
                            "properties":{ "keys": ["threshold"], "values": [{"type": 9, "float_value": 1}]} },

                          { "name": "distortion/voltage", "dataType": 9/* Float */, "float_value": 3.2, "metadata":{"description":"[R]Phase A voltage total harmonic distortion, value in %"},     
                            "properties":{ "keys": ["threshold"], "values": [{"type": 9, "float_value": 0.5}]} },
                          { "name": "distortion/current", "dataType": 9/* Float */, "float_value": 5.1, "metadata":{"description":"[R]Phase A current total harmonic distortion, value in %"},     
                            "properties":{ "keys": ["threshold"], "values": [{"type": 9, "float_value": 0.5}]} }
                                  
                        ] }, 
      "metadata":{"description":"[R]Phase A, 'template_ref' values = 'ref/phase'"} },

    { "name": "phase/b",
      "dataType": 19, /* Template */
      "template_value":{ "version": "phase",
                         "is_definition": false,
                         "template_ref": "ref/phase",
                         "metrics":[
                          { "name": "voltage",       "dataType": 9/* Float */,    "float_value": 220.4,  "metadata":{"description":"[R]Phase A rms voltage, value in V"},  
                            "properties":{ "keys": ["threshold"], "values": [{"type": 9, "float_value": 0.5}]} },
                          { "name": "current",       "dataType": 9/* Float */,    "float_value": 10.4,   "metadata":{"description":"[R]Phase A rms current, value in A"},  
                            "properties":{ "keys": ["threshold"], "values": [{"type": 9, "float_value": 0.01}]} },                         
                          { "name": "frequency",     "dataType": 9/* Float */,    "float_value": 50.0,   "metadata":{"description":"[R]Phase A frequency, value in Hz"},   
                            "properties":{ "keys": ["threshold"], "values": [{"type": 9, "float_value": 0.1}]} },

                          { "name": "power/active",   "dataType": 9/* Float */,    "float_value": 2000.4, "metadata":{"description":"[R]Phase A active power, value in W"},       
                            "properties":{ "keys": ["threshold"], "values": [{"type": 9, "float_value": 1}]} },
                          { "name": "power/reactive", "dataType": 9/* Float */,    "float_value": 100.3,  "metadata":{"description":"[R]Phase A reactive power, value in VAR"},   
                            "properties":{ "keys": ["threshold"], "values": [{"type": 9, "float_value": 1}]} },
                          { "name": "power/apparent", "dataType": 9/* Float */,    "float_value": 50.7,   "metadata":{"description":"[R]Phase A apparent power, value in VA"},    
                            "properties":{ "keys": ["threshold"], "values": [{"type": 9, "float_value": 1}]} },
                          { "name": "power/factor",   "dataType": 9/* Float */,    "float_value": 2200.8, "metadata":{"description":"[R]Phase A power factor"},                   
                            "properties":{ "keys": ["threshold"], "values": [{"type": 9, "float_value": 0.01}]} },

                          { "name": "energy/active",   "dataType": 10/* Double */,  "double_value": 712340.4, "metadata":{"description":"[RWP]Phase A active energy, value in Wh"},     
                            "properties":{ "keys": ["threshold"], "values": [{"type": 9, "float_value": 1}]} },
                          { "name": "energy/reactive", "dataType": 10/* Double */,  "double_value": 1057.4,   "metadata":{"description":"[RWP]Phase A reactive energy, value in VARh"}, 
                            "properties":{ "keys": ["threshold"], "values": [{"type": 9, "float_value": 1}]} },
                          { "name": "energy/apparent", "dataType": 10/* Double */,  "double_value": 564.4,    "metadata":{"description":"[RWP]Phase A apparent energy, value in VAh"},  
                            "properties":{ "keys": ["threshold"], "values": [{"type": 9, "float_value": 1}]} },

                          { "name": "distortion/voltage", "dataType": 9/* Float */,  "float_value": 3.2,  "metadata":{"description":"[R]Phase A voltage total harmonic distortion, value in %"},   
                            "properties":{ "keys": ["threshold"], "values": [{"type": 9, "float_value": 0.5}]} },
                          { "name": "distortion/current", "dataType": 9/* Float */,  "float_value": 5.1,  "metadata":{"description":"[R]Phase A current total harmonic distortion, value in %"},   
                            "properties":{ "keys": ["threshold"], "values": [{"type": 9, "float_value": 0.5}]} }
                                  
                        ] }, 
      "metadata":{"description":"[R]Phase B, 'template_ref' values = 'ref/phase'"} },

    { "name": "phase/c",
      "dataType": 19, /* Template */
      "template_value":{ "version": "phase",
                         "is_definition": false,
                         "template_ref": "ref/phase",
                         "metrics":[
                          { "name": "voltage",          "dataType": 9/* Float */,   "float_value": 220.4,  "metadata":{"description":"[R]Phase A rms voltage, value in V"},   
                            "properties":{ "keys": ["threshold"], "values": [{"type": 9, "float_value": 0.5}]} },
                          { "name": "current",          "dataType": 9/* Float */,   "float_value": 10.4,   "metadata":{"description":"[R]Phase A rms current, value in A"},   
                            "properties":{ "keys": ["threshold"], "values": [{"type": 9, "float_value": 0.01}]} },                         
                          { "name": "frequency",        "dataType": 9/* Float */,   "float_value": 50.0,   "metadata":{"description":"[R]Phase A frequency, value in Hz"},    
                            "properties":{ "keys": ["threshold"], "values": [{"type": 9, "float_value": 0.1}]} },
 
                          { "name": "power/active",     "dataType": 9/* Float */,   "float_value": 2000.4,  "metadata":{"description":"[R]Phase A active power, value in W"},      
                            "properties":{ "keys": ["threshold"], "values": [{"type": 9, "float_value": 1}]} },
                          { "name": "power/reactive",   "dataType": 9/* Float */,   "float_value": 100.3,   "metadata":{"description":"[R]Phase A reactive power, value in VAR"},  
                            "properties":{ "keys": ["threshold"], "values": [{"type": 9, "float_value": 1}]} },
                          { "name": "power/apparent",   "dataType": 9/* Float */,   "float_value": 50.7,    "metadata":{"description":"[R]Phase A apparent power, value in VA"},   
                            "properties":{ "keys": ["threshold"], "values": [{"type": 9, "float_value": 1}]} },
                          { "name": "power/factor",     "dataType": 9/* Float */,   "float_value": 2200.8,  "metadata":{"description":"[R]Phase A power factor"},                  
                            "properties":{ "keys": ["threshold"], "values": [{"type": 9, "float_value": 0.01}]} },
 
                          { "name": "energy/active",    "dataType": 10/* Double */,  "double_value": 712340.4, "metadata":{"description":"[RWP]Phase A active energy, value in Wh"},     
                            "properties":{ "keys": ["threshold"], "values": [{"type": 9, "float_value": 1}]} },
                          { "name": "energy/reactive",  "dataType": 10/* Double */,  "double_value": 1057.4,   "metadata":{"description":"[RWP]Phase A reactive energy, value in VARh"}, 
                            "properties":{ "keys": ["threshold"], "values": [{"type": 9, "float_value": 1}]} },
                          { "name": "energy/apparent",  "dataType": 10/* Double */,  "double_value": 564.4,    "metadata":{"description":"[RWP]Phase A apparent energy, value in VAh"},  
                            "properties":{ "keys": ["threshold"], "values": [{"type": 9, "float_value": 1}]} },
 
                          { "name": "distortion/voltage", "dataType": 9/* Float */,  "float_value": 3.2,   "metadata":{"description":"[R]Phase A voltage total harmonic distortion, value in %"},  
                            "properties":{ "keys": ["threshold"], "values": [{"type": 9, "float_value": 0.5}]} },
                          { "name": "distortion/current", "dataType": 9/* Float */,  "float_value": 5.1,   "metadata":{"description":"[R]Phase A current total harmonic distortion, value in %"},  
                            "properties":{ "keys": ["threshold"], "values": [{"type": 9, "float_value": 0.5}]} }
                                  
                        ] }, 
      "metadata":{"description":"[R]Phase C, 'template_ref' values = 'ref/phase'"} },

    { "name": "neutral/current",  "dataType": 9/* Float */,    "float_value": 5.1,      "properties":{ "keys": ["threshold"], "values": [{"type": 9, "float_value": 0.01}]}, "metadata":{"description":"[R]Neutral rms current, value in A"} },

    { "name": "out/0",            "dataType": 11/* Boolean */, "boolean_value": false,  "metadata":{"description":"[RWP]Solid state relay output 0 control"} },
    { "name": "out/1",            "dataType": 11/* Boolean */, "boolean_value": false,  "metadata":{"description":"[RWP]Solid state relay output 1 control"} },

    { "name": "in/0",             "dataType": 11/* Boolean */, "boolean_value": false,  "metadata":{"description":"[R]Digital input 0 state"} },
    { "name": "in/1",             "dataType": 11/* Boolean */, "boolean_value": false,  "metadata":{"description":"[R]Digital input 1 state"} }

  ]
}

```

## BOX device energymeter death example
> spBv1.0/box/DDEATH/abba2020/deba0007 

```json
{
"timestamp": 1486144502122,
"metrics": [  
    { "name": "bdSeq",                          "dataType": 8/* Uint64 */,   "long_value": 0,                    "metadata":{"description":"[R]Birth-death sequence, 'online' - [DBIRTH > DDEATH], 'offline' - [DBIRTH <= DDEATH]  "} },  
]
}
```
