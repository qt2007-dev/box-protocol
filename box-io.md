## BOX device io birth example
> spBv1.0/box/DBIRTH/abba2020/deba0004  

```json
{
"timestamp": 1486144502122,
"seq": 0,
"metrics": [
    { "name": "bdSeq",                    "dataType": 8/* Uint64 */,   "long_value": 0,                    "metadata":{"description":"[R]Birth-death sequence, 'online' - [BIRTH > DEATH], 'offline' - [BIRTH <= DEATH]"} },
    { "name": "control/reboot",           "dataType": 11/* Boolean */, "boolean_value": false,             "metadata":{"description":"[W]Software reboot, send 'true' for reboot"} },
    { "name": "control/rebirth",          "dataType": 11/* Boolean */, "boolean_value": false,             "metadata":{"description":"[W]Rebirth, send 'true' for receive birth message again"} },
    { "name": "control/firmware/new",     "dataType": 17/* Bytes */,   "bytes_value":"", "is_null": true,  "metadata":{"description":"[W]Receive new firmware, firmware send in Base64 format, in birth always null"} },
    { "name": "control/metrics/save",     "dataType": 11/* Boolean */, "boolean_value": true,              "metadata":{"description":"[RWP]Save metrics states after reboot, send 'true' for enable"} },
    { "name": "control/metrics/metadata", "dataType": 11/* Boolean */, "boolean_value": true,              "metadata":{"description":"[RWP]Show metrics metadata in birth, send 'true' for enable"} },
    { "name": "control/group",            "dataType": 12/* String */,  "string_value": "io",               "metadata":{"description":"[RWP]Global group, can be used instead id in topics and scenarios"} },

    { "name": "info/hardware/vendor",     "dataType": 12/* String */,  "string_value": "QuintTech" ,       "metadata":{"description":"[R]Vendor name, hardcoded by vendor"} },
    { "name": "info/hardware/model",      "dataType": 12/* String */,  "string_value": "stm32g474ce",      "metadata":{"description":"[R]Mcu model, hardcoded by vendor"} },
    { "name": "info/firmware/version",    "dataType": 12/* String */,  "string_value": "0.1.220527", "metadata":{"description":"[R]Firmware version, MAJOR.MINOR.buildOrCommit"} },
    { "name": "info/type",                "dataType": 12/* String */,  "string_value": "8 IO",             "metadata":{"description":"[R]Device type, hardcoded by vendor"} },
    { "name": "info/id",                  "dataType": 12/* String */,  "string_value": "deba0004",         "metadata":{"description":"[R]Short device id"} },
    { "name": "info/error",               "dataType": 12/* String */,  "string_value": "",                 "metadata":{"description":"[R]Last error message"} },

    { "name": "sensors/temperature",      "dataType": 1/* Int8 */,     "int_value": 22,                    "metadata":{"description":"[R]Temperature sensor in mcu, value in Celsius"} },

    { "name": "diagnostic/0/agnd",        "dataType": 9/* Float */, "float_value":0.1,                  "metadata":{"description":"[R]Voltage AGND afe ch 0, value in mV"} },      
    { "name": "diagnostic/0/temperature", "dataType": 9/* Float */, "float_value":25.7,                 "metadata":{"description":"[R]Temperature sensor afe ch 0, value in Celsius"} },      
    { "name": "diagnostic/0/avdd",        "dataType": 9/* Float */, "float_value":3.30,                 "metadata":{"description":"[R]Voltage AVDD afe ch 0, value in mV"} },      
    { "name": "diagnostic/0/avss",        "dataType": 9/* Float */, "float_value":0.01,                 "metadata":{"description":"[R]Voltage AVSS afe ch 0, value in mV"} },      
    { "name": "diagnostic/0/refout",      "dataType": 9/* Float */, "float_value":1.83,                 "metadata":{"description":"[R]Voltage REFOUT afe ch 0, value in mV"} },      
    { "name": "diagnostic/0/aldo5v",      "dataType": 9/* Float */, "float_value":5.08,                 "metadata":{"description":"[R]Voltage ALDO5V afe ch 0, value in mV"} },      
    { "name": "diagnostic/0/aldo1v8",     "dataType": 9/* Float */, "float_value":1.83,                 "metadata":{"description":"[R]Voltage ALDO1V8 afe ch 0, value in mV"} },      
    { "name": "diagnostic/0/dldo1v8",     "dataType": 9/* Float */, "float_value":1.82,                 "metadata":{"description":"[R]Voltage DLDO1V8 afe ch 0, value in mV"} },      
    { "name": "diagnostic/0/dvcc",        "dataType": 9/* Float */, "float_value":3.35,                 "metadata":{"description":"[R]Voltage DVCC afe ch 0, value in mV"} },      
    { "name": "diagnostic/0/iovdd",       "dataType": 9/* Float */, "float_value":3.31,                 "metadata":{"description":"[R]Voltage IOVDD afe ch 0, value in mV"} },      
    { "name": "diagnostic/0/lvin",        "dataType": 9/* Float */, "float_value":1.81,                 "metadata":{"description":"[R]Voltage LVIN afe ch 0, value in mV"} },      

    { "name": "diagnostic/1/agnd",        "dataType": 9/* Float */, "float_value":0.1,                  "metadata":{"description":"[R]Voltage AGND afe ch 1, value in mV"} },      
    { "name": "diagnostic/1/temperature", "dataType": 9/* Float */, "float_value":25.7,                 "metadata":{"description":"[R]Temperature sensor afe ch 1, value in Celsius"} },      
    { "name": "diagnostic/1/avdd",        "dataType": 9/* Float */, "float_value":3.30,                 "metadata":{"description":"[R]Voltage AVDD afe ch 1, value in mV"} },      
    { "name": "diagnostic/1/avss",        "dataType": 9/* Float */, "float_value":0.01,                 "metadata":{"description":"[R]Voltage AVSS afe ch 1, value in mV"} },      
    { "name": "diagnostic/1/refout",      "dataType": 9/* Float */, "float_value":1.83,                 "metadata":{"description":"[R]Voltage REFOUT afe ch 1, value in mV"} },      
    { "name": "diagnostic/1/aldo5v",      "dataType": 9/* Float */, "float_value":5.08,                 "metadata":{"description":"[R]Voltage ALDO5V afe ch 1, value in mV"} },      
    { "name": "diagnostic/1/aldo1v8",     "dataType": 9/* Float */, "float_value":1.83,                 "metadata":{"description":"[R]Voltage ALDO1V8 afe ch 1, value in mV"} },      
    { "name": "diagnostic/1/dldo1v8",     "dataType": 9/* Float */, "float_value":1.82,                 "metadata":{"description":"[R]Voltage DLDO1V8 afe ch 1, value in mV"} },      
    { "name": "diagnostic/1/dvcc",        "dataType": 9/* Float */, "float_value":3.35,                 "metadata":{"description":"[R]Voltage DVCC afe ch 1, value in mV"} },      
    { "name": "diagnostic/1/iovdd",       "dataType": 9/* Float */, "float_value":3.31,                 "metadata":{"description":"[R]Voltage IOVDD afe ch 1, value in mV"} },      
    { "name": "diagnostic/1/lvin",        "dataType": 9/* Float */, "float_value":1.81,                 "metadata":{"description":"[R]Voltage LVIN afe ch 1, value in mV"} },      

    { "name": "ref/pid",
      "dataType": 19, /* Template */
      "template_value":{ "version": "1",
                         "is_definition": true,
                         "metrics":[
                          { "name": "enable",      "dataType": 11/* Boolean */,  "metadata":{"description":"[RWP]Enable PID for specified channels"} },
                          { "name": "in",          "dataType": 5/* UInt8 */,     "metadata":{"description":"[RWP]Input io channel, values = [0-7]"} },
                          { "name": "out",         "dataType": 5/* UInt8 */,     "metadata":{"description":"[RWP]Control io channel, values = [0-7]"} },
                          { "name": "target",      "dataType": 9/* Float */,     "metadata":{"description":"[RWP]Target value, PID will try reach this value on in channel"} },
                          { "name": "Kp",          "dataType": 9/* Float */,     "metadata":{"description":"[RWP]Proportional coefficient of PID"} },
                          { "name": "Ki",          "dataType": 9/* Float */,     "metadata":{"description":"[RWP]Integral coefficient of PID"} },
                          { "name": "Kd",          "dataType": 9/* Float */,     "metadata":{"description":"[RWP]Differential coefficient of PID"} },                          
                          { "name": "direction",   "dataType": 12/* String */,   "metadata":{"description":"[RWP]Direction of PID regulation, values=['direct','inverse']"} }                
                        ] }, 
      "metadata":{"description":"Template definition of PID"} },

    { "name": "ref/io/high-impedance",
      "dataType": 19, /* Template */
      "template_value":{ "version": "1",
                         "is_definition": true,
                         "metrics":[
                          { "name": "pulldown",  "dataType": 11/* Boolean */,  "metadata":{"description":"[RWP]Enable 200kOhm pulldown resistor"} }
                        ] }, 
      "metadata":{"description":"Template definition of high impedance mode"} },

    { "name": "ref/io/voltage-output",
      "dataType": 19, /* Template */
      "template_value":{ "version": "1",
                         "is_definition": true,
                         "metrics":[
                          { "name": "value",     "dataType": 9/* Float */,     "metadata":{"description":"[RW]IO pin state, range of values - [0 - 10000.0] mV"} },
                          { "name": "current",   "dataType": 9/* Float */,     "metadata":{"description":"[R]Voltage output current consumption, values = [-25.0 - 25.0] mA"} },
                          { "name": "limit",     "dataType": 12/* String */,   "metadata":{"description":"[RWP]Voltage output current limit, values = ['30mA', '7.5mA']"} },
                          { "name": "slew",      "dataType": 12/* String */,   "metadata":{"description":"[RWP]Voltage output slew time, values = ['off','38.6us','40.1us','73.6us','75.8us','113us','259us','280us','459us','520us','858us','1ms','1.1ms','2ms','4ms','17ms','31.7ms']"} },
                          { "name": "error",     "dataType": 12/* String */,   "metadata":{"description":"[R]IO pin error conditions, values = ['none', 'over-current']"} }        
                        ] }, 
      "metadata":{"description":"Template definition of voltage output mode"} },

    { "name": "ref/io/current-output",
      "dataType": 19, /* Template */
      "template_value":{ "version": "1",
                         "is_definition": true,
                         "metrics":[
                          { "name": "value",     "dataType": 9/* Float */,     "metadata":{"description":"[RW]IO pin state, range of values - [0 - 25.0] mA"} },
                          { "name": "voltage",   "dataType": 9/* Float */,     "metadata":{"description":"[R]Current output voltage, values = [0 - 10000.0] mV"} },
                          { "name": "hart",      "dataType": 11/* Boolean */,  "metadata":{"description":"[RWP]HART compatibility mode enable"} },
                          { "name": "error",     "dataType": 12/* String */,   "metadata":{"description":"[R]IO pin error conditions, values = ['none', 'open-circuit']"} }        
                        ] }, 
      "metadata":{"description":"Template definition of current output mode"} },

    { "name": "ref/io/voltage-input",
      "dataType": 19, /* Template */
      "template_value":{ "version": "1",
                         "is_definition": true,
                         "metrics":[
                          { "name": "value",     "dataType": 9/* Float */,     "metadata":{"description":"[R]IO pin state, range of values - [-2500.0 - 10000.0] mV"} },
                          { "name": "range",     "dataType": 12/* String */,   "metadata":{"description":"[RWP]Voltage input range select, list of values = ['0V to 10V','-2.5V to 2.5V','-104mV to 104mV']"} },          
                          { "name": "pulldown",  "dataType": 11/* Boolean */,  "metadata":{"description":"[RWP]Voltage input 200kOhm pulldown resistor"} },
                          { "name": "error",     "dataType": 12/* String */,   "metadata":{"description":"[R]IO pin error conditions, values = ['none', 'over-voltage']"} }        
                        ] }, 
      "metadata":{"description":"Template definition of voltage input mode"} },

     { "name": "ref/io/current-input",
      "dataType": 19, /* Template */
      "template_value":{ "version": "1",
                         "is_definition": true,
                         "metrics":[
                          { "name": "value",     "dataType": 9/* Float */,     "metadata":{"description":"[R]IO pin state, range of values - [0 - 25.0] mA"} },
                          { "name": "hart",      "dataType": 11/* Boolean */,  "metadata":{"description":"[RWP]HART compatibility mode enable"} },
                          { "name": "error",     "dataType": 12/* String */,   "metadata":{"description":"[R]IO pin error conditions, values = ['none', 'over-current']"} }
                        ] }, 
      "metadata":{"description":"Template definition of current input mode, external powered"} },        
      
      { "name": "ref/io/current-input-loop",
      "dataType": 19, /* Template */
      "template_value":{ "version": "1",
                         "is_definition": true,
                         "metrics":[
                          { "name": "value",     "dataType": 9/* Float */,     "metadata":{"description":"[R]IO pin state, range of values - [0 - 25.0] mA"} },
                          { "name": "limit",     "dataType": 9/* Float */,     "metadata":{"description":"[RWP]Current limit from io, values = [0 - 25.0] mA"} },
                          { "name": "error",     "dataType": 12/* String */,   "metadata":{"description":"[R]IO pin error conditions, values = ['none', 'over-current']"} }
                        ] }, 
      "metadata":{"description":"Template definition of current input mode, loop powered"} },         

      { "name": "ref/io/current-input-loop-hart",
      "dataType": 19, /* Template */
      "template_value":{ "version": "1",
                         "is_definition": true,
                         "metrics":[
                          { "name": "value",     "dataType": 9/* Float */,     "metadata":{"description":"[R]IO pin state, range of values - [0 - 25.0] mA"} },
                          { "name": "error",     "dataType": 12/* String */,   "metadata":{"description":"[R]IO pin error conditions, values = ['none', 'over-current']"} }
                        ] }, 
      "metadata":{"description":"Template definition of current input mode, loop powered with HART compatibility"} },   

     { "name": "ref/io/resistance-input",
       "dataType": 19, /* Template */
       "template_value":{ "version": "1",
                         "is_definition": true,
                         "metrics":[
                          { "name": "value",     "dataType": 9/* Float */,    "metadata":{"description":"[R]IO pin state, range of values - [0 - 1000000.0] Ohm"} }
                        ] }, 
      "metadata":{"description":"Template definition of resistance measure mode"} },     

     { "name": "ref/io/digital-input",
       "dataType": 19, /* Template */
       "template_value":{ "version": "1",
                         "is_definition": true,
                         "metrics":[
                          { "name": "value",     "dataType": 11/* Boolean */,  "metadata":{"description":"[R]IO pin state, range of values - ['true' - if input is high, 'false' - if input is low]"} },
                          { "name": "threshold", "dataType": 9/* Float */,     "metadata":{"description":"[RWP]Digital input high threshold voltage, values = [0 - 16000] mV"} },
                          { "name": "debounce",  "dataType": 9/* Float */,     "metadata":{"description":"[RWP]Digital input debounce time, values = [0 - 75.0] ms"} }
                        ] }, 
      "metadata":{"description":"Template definition of digital input mode"} },     

     { "name": "ref/io/digital-output",
       "dataType": 19, /* Template */
       "template_value":{ "version": "1",
                         "is_definition": true,
                         "metrics":[
                          { "name": "value",     "dataType": 11/* Boolean */,  "metadata":{"description":"[RW]IO pin state, range of values - ['true' - if input is high, 'false' - if input is low]"} }, 
                          { "name": "error",     "dataType": 12/* String */,   "metadata":{"description":"[R]IO pin error conditions, values = ['none', 'over-current']"} }
                        ] }, 
      "metadata":{"description":"Template definition of digital output mode"} },  

     { "name": "ref/io/temperature",
       "dataType": 19, /* Template */
       "template_value":{ "version": "1",
                         "is_definition": true,
                         "metrics":[
                          { "name": "value",    "dataType": 9/* Float */,      "metadata":{"description":"[R]IO pin state, range of values - [-200.0 - 2000.0] Celsius"} },
                          { "name": "type",     "dataType": 12/* String */,    "metadata":{"description":"[RWP]Temperature RTD type, values = ['PT100','PT1000','TC-TYPE-B','TC-TYPE-E','TC-TYPE-J','TC-TYPE-K','TC-TYPE-N','TC-TYPE-R','TC-TYPE-S','TC-TYPE-T']"} },
                          { "name": "error",     "dataType": 12/* String */,   "metadata":{"description":"[R]IO pin error conditions, values = ['none', 'out-of-range']"} }
                        ] }, 
      "metadata":{"description":"Template definition of temperature probe input mode"} },     
   
    { "name": "pid/0",
      "dataType": 19, /* Template */
      "template_value":{ "version": "1",
                         "is_definition": false,
                         "template_ref": "ref/pid",
                         "metrics":[
                          { "name": "enable",     "boolean_value": false },
                          { "name": "in",         "int_value": 0 },
                          { "name": "out",        "int_value": 1 },
                          { "name": "target",     "float_value": 100 },
                          { "name": "Kp",         "float_value": 1 },
                          { "name": "Ki",         "float_value": 1 },
                          { "name": "Kd",         "float_value": 1 },
                          { "name": "direction",  "string_value": "direct" }
                        ] }, 
      "metadata":{"description":"PID controller channel 0"} },

    { "name": "pid/1",
      "dataType": 19, /* Template */
      "template_value":{ "version": "1",
                         "is_definition": false,
                         "template_ref": "ref/pid",
                         "metrics":[
                          { "name": "enable",     "boolean_value": false },
                          { "name": "in",         "int_value": 2 },
                          { "name": "out",        "int_value": 3 },
                          { "name": "target",     "float_value": 100 },
                          { "name": "Kp",         "float_value": 1 },
                          { "name": "Ki",         "float_value": 1 },
                          { "name": "Kd",         "float_value": 1 },
                          { "name": "direction",  "string_value": "direct" }
                        ] }, 
      "metadata":{"description":"PID controller channel 1"} },

    { "name": "pid/2",
      "dataType": 19, /* Template */
      "template_value":{ "version": "1",
                         "is_definition": false,
                         "template_ref": "ref/pid",
                         "metrics":[
                          { "name": "enable",     "boolean_value": false },
                          { "name": "in",         "int_value": 4 },
                          { "name": "out",        "int_value": 5 },
                          { "name": "target",     "float_value": 100 },
                          { "name": "Kp",         "float_value": 1 },
                          { "name": "Ki",         "float_value": 1 },
                          { "name": "Kd",         "float_value": 1 },
                          { "name": "direction",  "string_value": "reverse" }
                        ] }, 
      "metadata":{"description":"PID controller channel 2"} },

    { "name": "pid/3",
      "dataType": 19, /* Template */
      "template_value":{ "version": "1",
                         "is_definition": false,
                         "template_ref": "ref/pid",
                         "metrics":[
                          { "name": "enable",     "boolean_value": false },
                          { "name": "in",         "int_value": 6 },
                          { "name": "out",        "int_value": 7 },
                          { "name": "target",     "float_value": 100 },
                          { "name": "Kp",         "float_value": 1 },
                          { "name": "Ki",         "float_value": 1 },
                          { "name": "Kd",         "float_value": 1 },
                          { "name": "direction",  "string_value": "reverse" }
                        ] }, 
      "metadata":{"description":"PID controller channel 3"} },

    { "name": "io/0",
      "dataType": 19, /* Template */
      "template_value":{ "version": "1",
                         "is_definition": false,
                         "template_ref": "ref/io/high-impedance",
                         "metrics":[
                          { "name": "pulldown",  "boolean_value": true }
                        ] }, 
      "metadata":{"description":"[RWP]Multifunctional IO pin 0, 'template_ref' values = 'ref/io/..'"} },

    { "name": "io/1",
      "dataType": 19, /* Template */
      "template_value":{ "version": "1",
                         "is_definition": false,
                         "template_ref": "ref/io/voltage-output",
                         "metrics":[
                          { "name": "value",     "float_value": 1332 },
                          { "name": "current",   "float_value": 12.5 },
                          { "name": "limit",     "string_value": "30mA" },
                          { "name": "slew",      "string_value": "4ms" },
                          { "name": "error",     "string_value": "none" }        
                        ] }, 
      "metadata":{"description":"[RWP]Multifunctional IO pin 1, 'template_ref' values = 'ref/io/..'"} },

    { "name": "io/2",
      "dataType": 19, /* Template */
      "template_value":{ "version": "1",
                         "is_definition": false,
                         "template_ref": "ref/io/current-output",
                         "metrics":[
                          { "name": "value",     "float_value": 13.32 },
                          { "name": "voltage",   "float_value": 5000 },
                          { "name": "hart",      "boolean_value": false },
                          { "name": "error",     "string_value": "none" }
                        ] }, 
      "metadata":{"description":"[RWP]Multifunctional IO pin 2, 'template_ref' values = 'ref/io/..'"} },

    { "name": "io/3",
      "dataType": 19, /* Template */
      "template_value":{ "version": "1",
                         "is_definition": false,
                         "template_ref": "ref/io/voltage-input",
                         "metrics":[
                          { "name": "value",     "float_value": 1332 },
                          { "name": "range",     "string_value": "auto" },          
                          { "name": "pulldown",  "boolean_value": false },
                          { "name": "error",     "string_value": "none" }
                        ] }, 
      "metadata":{"description":"[RWP]Multifunctional IO pin 3, 'template_ref' values = 'ref/io/..'"} },

    { "name": "io/4",
      "dataType": 19, /* Template */
      "template_value":{ "version": "1",
                         "is_definition": false,
                         "template_ref": "ref/io/current-input",
                         "metrics":[
                          { "name": "value",     "float_value": 13.32 },
                          { "name": "hart",      "boolean_value": false },
                          { "name": "error",     "string_value": "none" }
                        ] }, 
      "metadata":{"description":"[RWP]Multifunctional IO pin 4, 'template_ref' values = 'ref/io/..'"} },

    { "name": "io/5",
      "dataType": 19, /* Template */
      "template_value":{ "version": "1",
                         "is_definition": false,
                         "template_ref": "ref/io/resistance-input",
                         "metrics":[
                          { "name": "value",     "float_value": 120.000 }
                        ] }, 
      "metadata":{"description":"[RWP]Multifunctional IO pin 5, 'template_ref' values = 'ref/io/..'"} },

    { "name": "io/6",
      "dataType": 19, /* Template */
      "template_value":{ "version": "1",
                         "is_definition": false,
                         "template_ref": "ref/io/digital-input",
                         "metrics":[
                          { "name": "value",     "boolean_value": false },
                          { "name": "threshold", "float_value": 8.4 },
                          { "name": "debounce",  "float_value": 9 }
                        ] }, 
      "metadata":{"description":"[RWP]Multifunctional IO pin 6, 'template_ref' values = 'ref/io/..'"} },

    { "name": "io/7",
      "dataType": 19, /* Template */
      "template_value":{ "version": "1",
                         "is_definition": false,
                         "template_ref": "ref/io/digital-output",
                         "metrics":[
                          { "name": "value",     "boolean_value": false},
                          { "name": "error",     "string_value": "none" }
                        ] }, 
      "metadata":{"description":"[RWP]Multifunctional IO pin 7, 'template_ref' values = 'ref/io/..'"} }                

  ]
}
```

## BOX device io death example
> spBv1.0/box/DDEATH/abba2020/deba0004  

```json
{
"timestamp": 1486144502122,
"metrics": [  
    { "name": "bdSeq",                    "dataType": 8/* Uint64 */,   "long_value": 0,           "metadata":{"description":"[R]Birth-death sequence, 'online' - [BIRTH > DEATH], 'offline' - [BIRTH <= DEATH]"} },  
]
}
```