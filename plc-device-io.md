## PLC device io birth example
> spBv1.0/plc/DBIRTH/abba2020/deba0008  

```json
{
"timestamp": 1486144502122,
"seq": 0,
"metrics": [
    { "name": "control/reboot",                         "dataType": 11/* Boolean */, "boolean_value": false,             "metadata":{"description":"Sofrware reboot device, send 'true' for reboot"} },
    { "name": "control/rebirth",                        "dataType": 11/* Boolean */, "boolean_value": false,             "metadata":{"description":"Rebirth device, send 'true' for receive dbirth message again"} },
    { "name": "control/firmware/new",                   "dataType": 17/* Bytes */,   "bytes_value":"", "is_null": true,  "metadata":{"description":"Receive new device firmware, firmware send in Base64 format, in birth always null"} },
    { "name": "control/metrics/save",                   "dataType": 11/* Boolean */, "boolean_value": true,              "metadata":{"description":"Save metrics states after reboot, send 'true' for enable"} },
    { "name": "control/group",                          "dataType": 12/* String */,  "string_value": "io",               "metadata":{"description":"Global group for device, can be used instead id in topics and scenarios"} },

    { "name": "info/hardware/vendor",                   "dataType": 12/* String */,  "string_value": "QuintTech" ,       "metadata":{"description":"Vendor name, hardcoded by vendor"} },
    { "name": "info/hardware/model",                    "dataType": 12/* String */,  "string_value": "stm32g474ce",      "metadata":{"description":"Mcu model, hardcoded by vendor"} },
    { "name": "info/firmware/version",                  "dataType": 12/* String */,  "string_value": "0.1.220527.84852", "metadata":{"description":"Firmware version, MAJOR.MINOR.YYMMDD.SSSSS"} },
    { "name": "info/type",                              "dataType": 12/* String */,  "string_value": "8 IO",             "metadata":{"description":"Device type, hardcoded by vendor"} },
    { "name": "info/id",                                "dataType": 12/* String */,  "string_value": "deba0008",         "metadata":{"description":"Short id calculated by a hash from mcu uid"} },
    { "name": "info/error",                             "dataType": 12/* String */,  "string_value": "",                 "metadata":{"description":"Last error message"} },

    { "name": "sensors/temperature",                    "dataType": 1/* Int8 */,     "int_value": 22,                    "metadata":{"description":"Temperature sensor in mcu, value in Celsius"} },

    { "name": "io/0/mode",                              "dataType": 12/* String */,  "string_value": "high-impedance",   "metadata":{"description":"IO pin mode, list of values = ['high-impedance', 'voltage-output',
                                                                                                                                                                                   'current-output', 'voltage-input',
                                                                                                                                                                                   'current-input',  'resistance-input',
                                                                                                                                                                                   'digital-input',  'digital-output']
                                                                                                                                                    change value execute rebirth of device with new metrics"} },

    { "name": "io/0/error",                             "dataType": 12/* String */,  "string_value": "none",             "metadata":{"description":"IO pin error conditions"} },


    { "name": "io/1/mode",                              "dataType": 12, "string_value": "voltage-output"},      /* String */
    /* value voltage - [0 - 10000] mV */ 
    { "name": "io/1",                                   "dataType": 7,  "int_value": 5635},                     /* UInt32 */
    /* current limit value = ['30mA', '7.5mA'] */ 
    { "name": "io/1/current/limit",                     "dataType": 12, "string_value": "30mA"},                /* String */    
    /* value current - [-25000 - 25000] uA */ 
    { "name": "io/1/current",                           "dataType": 3,  "int_value": 20},                       /* Int32 */
    /* slew = ['off','38.6us','40.1us','73.6us','75.8us','113us','259us','280us','459us',
               '520us','858us','1ms','1.1ms','2ms','4ms','17ms','31.7ms'] */      
    { "name": "io/1/slew",                              "dataType": 12, "string_value": "1ms"},                 /* String */ 
    /* error value = ['none', 'over-current']  */   
    { "name": "io/1/error",                             "dataType": 12, "string_value": "none"},                /* String */  


    { "name": "io/2/mode",                              "dataType": 12, "string_value": "current-output"},      /* String */
    /* value current - [0 - 25000] uA */ 
    { "name": "io/2",                                   "dataType": 7,  "int_value": 5635},                     /* UInt32 */
    /* value voltage - [0 - 10000] mV */ 
    { "name": "io/2/voltage",                           "dataType": 7,  "int_value": 5635},                     /* UInt32 */
    /* error value = ['none', 'open-circuit']  */   
    { "name": "io/2/error",                             "dataType": 12, "string_value": "none"},                /* String */  


    { "name": "io/3/mode",                              "dataType": 12, "string_value": "voltage-input"},       /* String */
    /* value voltage - [0 - 10000] mV, [0 - 2500] mV, [-2500 - 2500] mV, [-104000 - 104000] uV */ 
    { "name": "io/3",                                   "dataType": 3,  "int_value": 5635},                     /* Int32 */
    /* enable/disable 200kOhm pulldown resistor */ 
    { "name": "io/3/pulldown",                         "dataType": 11, "boolean_value": false},                 /* Boolean */
    /* range = ['0V to 10V','0V to 2.5V','-2.5V to 2.5V','-104mV to 104mV'] */ 
    { "name": "io/3/range",                            "dataType": 12, "string_value": "0V to 10V"},            /* String */
    /* threshold value for auto update  */      
    { "name": "io/3/threshold",                         "dataType": 7,  "int_value": 200}                       /* UInt32 */   
    /* error value = ['none', 'over-voltage']  */   
    { "name": "io/3/error",                             "dataType": 12, "string_value": "none"},                /* String */  


    { "name": "io/4/mode",                              "dataType": 12, "string_value": "current-input"},       /* String */
    /* value current - [0 - 25000] uA */ 
    { "name": "io/4",                                   "dataType": 7,  "int_value": 5635},                     /* UInt32 */
    /* threshold value for auto update  */      
    { "name": "in/4/threshold",                         "dataType": 7,  "int_value": 200}                       /* UInt32 */   
    /* error value = ['none', 'short-circuit']  */   
    { "name": "io/4/error",                             "dataType": 12, "string_value": "none"},                /* String */  


    { "name": "io/5/mode",                              "dataType": 12, "string_value": "resistance-input"},    /* String */
    /* value current - [0 - 1000000] Ohm */ 
    { "name": "io/5",                                   "dataType": 7,  "int_value": 5635},                     /* UInt32 */
    /* threshold value for auto update  */      
    { "name": "io/5/threshold",                         "dataType": 7,  "int_value": 200}                       /* UInt32 */   
    /* error value = ['none']  */   
    { "name": "io/5/error",                             "dataType": 12, "string_value": "none"},                /* String */  


    { "name": "io/6/mode",                              "dataType": 12, "string_value": "digital-input"},       /* String */
    /* value state */ 
    { "name": "io/6",                                   "dataType": 11, "boolean_value": false},                /* Boolean */
    /* threshold for logic high - ['0.4','1.2','2','2.8',...,'25.2'] V */      
    { "name": "io/6/threshold",                         "dataType": 12, "string_value": "8.4"},                 /* String */ 
    /* debounce = ['bypass','0.013','0.018','0.024','0.032','0.042','0.056','0.075',
                   '0.1','0.13','0.18','0.24','0.32','0.42','0.56','0.75',
                   '1','1.3','1.8','2.4','3.2','4.2','5.6','7.5',
                   '10','13','18','24','32','42','56','75'] ms */      
    { "name": "io/6/debounce",                          "dataType": 12, "string_value": "bypass"},              /* String */ 
    /* sink current = ['2.4mA','7mA'] */
    { "name": "io/6/sink",                              "dataType": 12, "string_value": "2.4mA"},               /* String */ 
    /* error value = ['none']  */   
    { "name": "io/6/error",                             "dataType": 12, "string_value": "none"},                /* String */  


    { "name": "io/7/mode",                              "dataType": 12, "string_value": "digital-output"},      /* String */
    /* value state */ 
    { "name": "io/7",                                   "dataType": 11, "boolean_value": false},                /* Boolean */
    /* error value = ['none']  */   
    { "name": "io/7/error",                             "dataType": 12, "string_value": "none"},                /* String */  

    


    /* for update in values - send true */
    { "name": "io/update",                              "dataType": 11, "boolean_value": false},                /* Boolean */
    /* in update time in seconds, 0 - disable update*/
    { "name": "io/update/time",                         "dataType": 7,  "int_value": 0},                        /* UInt32 */
   
  ]
}
```

## PLC device io death example
> spBv1.0/plc/DDEATH/abba2020/deba0008  

```json
{
"timestamp": 1486144502122,
"seq": 0
}
```