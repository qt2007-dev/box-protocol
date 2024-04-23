## BOX device io birth example
> spBv1.0/box/DBIRTH/abba2020/deba0004  

```json
{
"timestamp": 1486144502122,
"seq": 0,
"metrics": [
    { "name": "bdSeq",                    "dataType": 8/* Uint64 */,   "long_value": 0,                    "metadata":{"description":"[R]Birth-death sequence, 'online' - [BIRTH > DEATH], 'offline' - [BIRTH <= DEATH]  "} },
    { "name": "control/reboot",           "dataType": 11/* Boolean */, "boolean_value": false,             "metadata":{"description":"[W]Software reboot device, send 'true' for reboot"} },
    { "name": "control/rebirth",          "dataType": 11/* Boolean */, "boolean_value": false,             "metadata":{"description":"[W]Rebirth device, send 'true' for receive birth message again"} },
    { "name": "control/firmware/new",     "dataType": 17/* Bytes */,   "bytes_value":"", "is_null": true,  "metadata":{"description":"[W]Receive new device firmware, firmware send in Base64 format, in birth always null"} },
    { "name": "control/metrics/save",     "dataType": 11/* Boolean */, "boolean_value": true,              "metadata":{"description":"[RWP]Save metrics states after reboot, send 'true' for enable"} },
    { "name": "control/metrics/metadata", "dataType": 11/* Boolean */, "boolean_value": true,              "metadata":{"description":"[RWP]Show metrics metadata in birth, send 'true' for enable"} },
    { "name": "control/group",            "dataType": 12/* String */,  "string_value": "io",               "metadata":{"description":"[RWP]Global group for device, can be used instead id in topics and scenarios"} },

    { "name": "info/hardware/vendor",     "dataType": 12/* String */,  "string_value": "QuintTech" ,       "metadata":{"description":"[R]Vendor name, hardcoded by vendor"} },
    { "name": "info/hardware/model",      "dataType": 12/* String */,  "string_value": "stm32g474ce",      "metadata":{"description":"[R]Mcu model, hardcoded by vendor"} },
    { "name": "info/firmware/version",    "dataType": 12/* String */,  "string_value": "0.1.220527.84852", "metadata":{"description":"[R]Firmware version, MAJOR.MINOR.YYMMDD.SSSSS"} },
    { "name": "info/type",                "dataType": 12/* String */,  "string_value": "8 IO",             "metadata":{"description":"[R]Device type, hardcoded by vendor"} },
    { "name": "info/id",                  "dataType": 12/* String */,  "string_value": "deba0004",         "metadata":{"description":"[R]Short id calculated by a hash from mcu uid"} },
    { "name": "info/error",               "dataType": 12/* String */,  "string_value": "",                 "metadata":{"description":"[R]Last error message"} },

    { "name": "sensors/temperature",      "dataType": 1/* Int8 */,     "int_value": 22,                    "metadata":{"description":"[R]Temperature sensor in mcu, value in Celsius"} },

    { "name": "pid",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 2, 
                        "columns": ["in-channel", "out-channel", "target", "Kp", "Ki", "Kd", "direction"],
                        "types": [5, 5, 10, 10, 10, 10, 12], /* UInt8, UInt8, Double, Double, Double, Double, String */
                        "rows": [ {"elements":[{"int_value": 0,"int_value": 1,"double_value":40,"double_value":10,"double_value":2,"double_value":3,"string_value":"direct"}]},   /* PID Channel 0 */
                                  {"elements":[{"int_value": 2,"int_value": 3,"double_value":50,"double_value":10,"double_value":2,"double_value":3,"string_value":"inverse"}]},  /* PID Channel 1 */
                                  {"elements":[{"int_value": 4,"int_value": 5,"double_value":60,"double_value":10,"double_value":2,"double_value":3,"string_value":"direct"}]},   /* PID Channel 2 */
                                  {"elements":[{"int_value": 6,"int_value": 7,"double_value":70,"double_value":10,"double_value":2,"double_value":3,"string_value":"inverse"}]},  /* PID Channel 3 */ ] },

      "metadata":{"description":"[RWP] PID controller for "} },


    { "name": "ref/io/high-impedance",
      "dataType": 19, /* Template */
      "template_value":{ "version": "1",
                         "is_definition": true,
                         "metrics":[
                          { "name": "pulldown",  "dataType": 11/* Boolean */,  "metadata":{"description":"[RWP]Enable 200kOhm pulldown resistor"} },
                        ] }, 
      "metadata":{"description":"Template definition of high impedance mode"} },

    { "name": "ref/io/voltage-output",
      "dataType": 19, /* Template */
      "template_value":{ "version": "1",
                         "is_definition": true,
                         "metrics":[
                          { "name": "value",     "dataType": 7/* UInt32 */,    "metadata":{"description":"[RW]IO pin state, range of values - [0 - 10000] mV"} },
                          { "name": "current",   "dataType": 3/* Int32 */,     "metadata":{"description":"[R]Voltage output current consumption, values = [-25000 - 25000] uA"} },
                          { "name": "limit",     "dataType": 12/* String */,   "metadata":{"description":"[RWP]Voltage output current limit, values = ['30mA', '7.5mA']"} },
                          { "name": "slew",      "dataType": 12/* String */,   "metadata":{"description":"[RWP]Voltage output slew time, values = ['off','38.6us','40.1us','73.6us','75.8us','113us',
                                                                                                                                                  '259us','280us','459us','520us','858us','1ms',
                                                                                                                                                  '1.1ms','2ms','4ms','17ms','31.7ms']"} },
                          { "name": "error",     "dataType": 12/* String */,   "metadata":{"description":"[R]IO pin error conditions, values = ['none', 'over-current']"} }        
                        ] }, 
      "metadata":{"description":"Template definition of voltage output mode"} },

    { "name": "ref/io/current-output",
      "dataType": 19, /* Template */
      "template_value":{ "version": "1",
                         "is_definition": true,
                         "metrics":[
                          { "name": "value",     "dataType": 7/* UInt32 */,    "metadata":{"description":"[RW]IO pin state, range of values - [0 - 25000] uA"} },
                          { "name": "voltage",   "dataType": 3/* Int32 */,     "metadata":{"description":"[R]Current output voltage, values = [0 - 10000] mV"} },
                          { "name": "hart",      "dataType": 11/* Boolean */,  "metadata":{"description":"[RWP]HART compatibility mode enable"} },
                          { "name": "error",     "dataType": 12/* String */,   "metadata":{"description":"[R]IO pin error conditions, values = ['none', 'open-circuit']"} }        
                        ] }, 
      "metadata":{"description":"Template definition of current output mode"} },

    { "name": "ref/io/voltage-input",
      "dataType": 19, /* Template */
      "template_value":{ "version": "1",
                         "is_definition": true,
                         "metrics":[
                          { "name": "value",     "dataType": 3/* Int32 */,     "metadata":{"description":"[R]IO pin state, range of values - [0 - 10000] mV, [0 - 2500] mV, [-2500 - 2500] mV, [-104000 - 104000] uV"} },
                          { "name": "range",     "dataType": 12/* String */,   "metadata":{"description":"[RWP]Voltage input range select, list of values = ['auto','0V to 10V','0V to 2.5V','-2.5V to 2.5V','-104mV to 104mV']"} },          
                          { "name": "pulldown",  "dataType": 11/* Boolean */,  "metadata":{"description":"[RWP]Voltage input 200kOhm pulldown resistor"} },
                          { "name": "error",     "dataType": 12/* String */,   "metadata":{"description":"[R]IO pin error conditions, values = ['none', 'over-voltage']"} },        
                        ] }, 
      "metadata":{"description":"Template definition of voltage input mode"} },

     { "name": "ref/io/current-input",
      "dataType": 19, /* Template */
      "template_value":{ "version": "1",
                         "is_definition": true,
                         "metrics":[
                          { "name": "value",     "dataType": 7/* UInt32 */,    "metadata":{"description":"[R]IO pin state, range of values - [0 - 25000] uA"} },
                          { "name": "hart",      "dataType": 11/* Boolean */,  "metadata":{"description":"[RWP]HART compatibility mode enable"} },
                          { "name": "error",     "dataType": 12/* String */,   "metadata":{"description":"[R]IO pin error conditions, values = ['none', 'over-current']"} },
                        ] }, 
      "metadata":{"description":"Template definition of current input mode, external powered"} },        
      
      { "name": "ref/io/current-input-loop",
      "dataType": 19, /* Template */
      "template_value":{ "version": "1",
                         "is_definition": true,
                         "metrics":[
                          { "name": "value",     "dataType": 7/* UInt32 */,    "metadata":{"description":"[R]IO pin state, range of values - [0 - 25000] uA"} },
                          { "name": "current",   "dataType": 3/* Int32 */,     "metadata":{"description":"[RWP]Current limit from io, values = [0 - 25000] uA"} },
                          { "name": "hart",      "dataType": 11/* Boolean */,  "metadata":{"description":"[RWP]HART compatibility mode enable"} },
                          { "name": "error",     "dataType": 12/* String */,   "metadata":{"description":"[R]IO pin error conditions, values = ['none', 'over-current']"} },
                        ] }, 
      "metadata":{"description":"Template definition of current input mode, loop powered"} },         

     { "name": "ref/io/resistance-input",
       "dataType": 19, /* Template */
       "template_value":{ "version": "1",
                         "is_definition": true,
                         "metrics":[
                          { "name": "value",     "dataType": 7/* UInt32 */,    "metadata":{"description":"[R]IO pin state, range of values - [0 - 1000000] Ohm"} }
                        ] }, 
      "metadata":{"description":"Template definition of resistance measure mode"} },     

     { "name": "ref/io/digital-input",
       "dataType": 19, /* Template */
       "template_value":{ "version": "1",
                         "is_definition": true,
                         "metrics":[
                          { "name": "value",     "dataType": 11/* Boolean */,  "metadata":{"description":"[R]IO pin state, range of values - ['true' - if input is high, 'false' - if input is low]"} },
                          { "name": "threshold", "dataType": 12/* String */,   "metadata":{"description":"[RWP]Digital input high threshold voltage, list of value = ['0.4','1.2','2','2.8',...,'25.2'] V"} },
                          { "name": "debounce",  "dataType": 12/* String */,   "metadata":{"description":"[RWP]Digital input debounce time, list of value = ['bypass','0.013','0.018','0.024','0.032','0.042','0.056','0.075',
                                                                                                                                                            '0.1','0.13','0.18','0.24','0.32','0.42','0.56','0.75',
                                                                                                                                                            '1','1.3','1.8','2.4','3.2','4.2','5.6','7.5',
                                                                                                                                                            '10','13','18','24','32','42','56','75'] ms"} },
                          { "name": "sink",      "dataType": 12/* String */,   "metadata":{"description":"[RWP]Digital input sink current, values = ['2.4mA','7mA']"} }
                        ] }, 
      "metadata":{"description":"Template definition of digital input mode"} },     

     { "name": "ref/io/digital-output",
       "dataType": 19, /* Template */
       "template_value":{ "version": "1",
                         "is_definition": true,
                         "metrics":[
                          { "name": "value",     "dataType": 11/* Boolean */,  "metadata":{"description":"[RW]IO pin state, range of values - ['true' - if input is high, 'false' - if input is low]"} },                          ,
                          { "name": "error",     "dataType": 12/* String */,   "metadata":{"description":"[R]IO pin error conditions, values = ['none', 'over-current']"} },
                        ] }, 
      "metadata":{"description":"Template definition of digital output mode"} },  

     { "name": "ref/io/temperature",
       "dataType": 19, /* Template */
       "template_value":{ "version": "1",
                         "is_definition": true,
                         "metrics":[
                          { "name": "value",    "dataType": 10/* Double */,    "metadata":{"description":"[R]IO pin state, range of values - [-200.0 - 2000.0] Celsius"} },
                          { "name": "type",     "dataType": 12/* String */,    "metadata":{"description":"[RWP]Temperature RTD type, values = ['PT100','PT1000',
                                                                                                                                               'TC-TYPE-B','TC-TYPE-E','TC-TYPE-J','TC-TYPE-K',
                                                                                                                                               'TC-TYPE-N','TC-TYPE-R','TC-TYPE-S','TC-TYPE-T']"} }
                        ] }, 
      "metadata":{"description":"Template definition of temperature probe input mode"} },     

   
    { "name": "io/0",
      "dataType": 19, /* Template */
      "template_value":{ "version": "1",
                         "is_definition": false,
                         "template_ref": "ref/io/high-impedance",
                         "metrics":[
                          { "name": "pulldown",  "boolean_value": true }
                        ] } },

    { "name": "io/1",
      "dataType": 19, /* Template */
      "template_value":{ "version": "1",
                         "is_definition": false,
                         "template_ref": "ref/io/voltage-output",
                         "metrics":[
                          { "name": "value",     "int_value": 1332 },
                          { "name": "current",   "int_value": 3000 },
                          { "name": "limit",     "string_value": "30mA" },
                          { "name": "slew",      "string_value": "4ms" },
                          { "name": "error",     "string_value": "none" }        
                        ] } },

    { "name": "io/2",
      "dataType": 19, /* Template */
      "template_value":{ "version": "1",
                         "is_definition": false,
                         "template_ref": "ref/io/current-output",
                         "metrics":[
                          { "name": "value",     "int_value": 1332 },
                          { "name": "voltage",   "int_value": 3000 },
                          { "name": "hart",  "boolean_value": false },
                          { "name": "error",     "string_value": "none" }
                        ] } },

    { "name": "io/3",
      "dataType": 19, /* Template */
      "template_value":{ "version": "1",
                         "is_definition": false,
                         "template_ref": "ref/io/voltage-input",
                         "metrics":[
                          { "name": "value",     "int_value": 1332 },
                          { "name": "range",     "string_value": "auto" },          
                          { "name": "pulldown",  "boolean_value": false },
                          { "name": "error",     "string_value": "none" }
                        ] } },

    { "name": "io/4",
      "dataType": 19, /* Template */
      "template_value":{ "version": "1",
                         "is_definition": false,
                         "template_ref": "ref/io/current-input",
                         "metrics":[
                          { "name": "value",     "int_value": 1332 },
                          { "name": "hart",      "boolean_value": false },
                          { "name": "error",     "string_value": "none" }
                        ] } },

    { "name": "io/5",
      "dataType": 19, /* Template */
      "template_value":{ "version": "1",
                         "is_definition": false,
                         "template_ref": "ref/io/resistance-input",
                         "metrics":[
                          { "name": "value",     "int_value": 120000 }
                        ] } },

    { "name": "io/6",
      "dataType": 19, /* Template */
      "template_value":{ "version": "1",
                         "is_definition": false,
                         "template_ref": "ref/io/digital-input",
                         "metrics":[
                          { "name": "value",     "boolean_value": false },
                          { "name": "threshold", "string_value": "8.4" },
                          { "name": "debounce",  "string_value": "10" },
                          { "name": "sink",      "string_value": "2.4mA" }
                        ] } },

    { "name": "io/7",
      "dataType": 19, /* Template */
      "template_value":{ "version": "1",
                         "is_definition": false,
                         "template_ref": "ref/io/digital-output",
                         "metrics":[
                          { "name": "value",     "boolean_value": false},
                          { "name": "error",     "string_value": "none" }
                        ] } }                

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