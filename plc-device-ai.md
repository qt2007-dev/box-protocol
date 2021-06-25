## PLC device analog input birth example
> spBv1.0/plc/DBIRTH/abba2020/deba0005  

```json
{
"timestamp": 1486144502122,
"seq": 0,
"metrics": [
    { "name": "control/reboot",                         "dataType": 11, "boolean_value": false},                /* Boolean */
    { "name": "control/rebirth",                        "dataType": 11, "boolean_value": false},                /* Boolean */
    /* for receive new firmware in Base64 */
    { "name": "control/firmware/new",                   "dataType": 17, "is_null": true},                       /* Bytes */
    /* save metrics values after reboot */
    { "name": "control/metrics/save",                   "dataType": 11, "boolean_value": true },                /* Boolean */
    /* alias can be used instead id in topics and scenario */    
    { "name": "control/alias",                          "dataType": 12, "string_value": "ai"},                  /* String */
    { "name": "info/hardware/vendor",                   "dataType": 12, "string_value": "QuintTech"},           /* String */
    { "name": "info/hardware/model",                    "dataType": 12, "string_value": "stm32g474ce"},         /* String */
    { "name": "info/firmware/version",                  "dataType": 12, "string_value": "0.1.012345678"},       /* String */
    { "name": "info/type",                              "dataType": 12, "string_value": "16 Analog inputs"},    /* String */
    { "name": "info/id",                                "dataType": 12, "string_value": "deba0005"},            /* String */
    /* metric for last error, in birth always null */       
    { "name": "info/error",                             "dataType": 12, "is_null": true},                       /* String */ 

    { "name": "sensors/temperature",                    "dataType": 1,  "int_value": 22},                       /* Int8 */
    /* for update sensors values - send true */
    { "name": "sensors/update",                         "dataType": 11, "boolean_value": false},                /* Boolean */
    /* sensors update time in seconds, 0 - disable update*/
    { "name": "sensors/update/time",                    "dataType": 7,  "int_value": 0},                        /* UInt32 */
    /* enabled/disabled update */
    { "name": "sensors/update/temperature",             "dataType": 11, "boolean_value": false},                /* Boolean */
    /* update threshold value for auto update  */      
    { "name": "sensors/update/temperature/threshold",   "dataType": 5,  "int_value": 2},                        /* UInt8 */
     
    /* in values in voltage -mV, current - uA*/ 
    { "name": "in/0",                                   "dataType": 7,  "int_value": 5635},                     /* UInt32 */
    /* in mode values = ['voltage', 'current'] */ 
    { "name": "in/0/mode",                              "dataType": 12, "string_value": "voltage"},             /* String */
    /* in max values = ['2.5V', '5V', '10V', '20V', '25mA', 'auto'] */ 
    { "name": "in/0/max",                               "dataType": 12, "string_value": "10V"},                 /* String */
    /* in threshold value for auto update  */      
    { "name": "in/0/threshold",                         "dataType": 7,  "int_value": 200}                       /* UInt32 */   
    /* in error values = ['none', 'adc-out-of-range', 'amp-out-of-range' ]  */      
    { "name": "in/0/error",                             "dataType": 12, "string_value": "none"},                /* String */  
    /* if in/0 < in/0/led then led off, else led on */ 
    { "name": "in/0/led",                               "dataType": 7,  "int_value": 2500},                     /* UInt32 */  
    
    { "name": "in/1",                                   "dataType": 7,  "int_value": 5635},                     /* UInt32 */
    { "name": "in/1/mode",                              "dataType": 12, "string_value": "voltage"},             /* String */
    { "name": "in/1/max",                               "dataType": 12, "string_value": "10V"},                 /* String */
    { "name": "in/1/threshold",                         "dataType": 7,  "int_value": 200}                       /* UInt32 */
    { "name": "in/1/error",                             "dataType": 12, "string_value": "none"},                /* String */ 
    { "name": "in/1/led",                               "dataType": 7,  "int_value": 2500},                     /* UInt32 */  

    { "name": "in/2",                                   "dataType": 7,  "int_value": 5635},                     /* UInt32 */
    { "name": "in/2/mode",                              "dataType": 12, "string_value": "voltage"},             /* String */
    { "name": "in/2/max",                               "dataType": 12, "string_value": "10V"},                 /* String */
    { "name": "in/2/threshold",                         "dataType": 7,  "int_value": 200}                       /* UInt32 */
    { "name": "in/2/error",                             "dataType": 12, "string_value": "none"},                /* String */
    { "name": "in/2/led",                               "dataType": 7,  "int_value": 2500},                     /* UInt32 */  

    { "name": "in/3",                                   "dataType": 7,  "int_value": 5635},                     /* UInt32 */
    { "name": "in/3/mode",                              "dataType": 12, "string_value": "voltage"},             /* String */
    { "name": "in/3/max",                               "dataType": 12, "string_value": "10V"},                 /* String */
    { "name": "in/3/threshold",                         "dataType": 7,  "int_value": 200}                       /* UInt32 */
    { "name": "in/3/error",                             "dataType": 12, "string_value": "none"},                /* String */   
    { "name": "in/3/led",                               "dataType": 7,  "int_value": 2500},                     /* UInt32 */  

    { "name": "in/4",                                   "dataType": 7,  "int_value": 5635},                     /* UInt32 */
    { "name": "in/4/mode",                              "dataType": 12, "string_value": "voltage"},             /* String */
    { "name": "in/4/max",                               "dataType": 12, "string_value": "10V"},                 /* String */
    { "name": "in/4/threshold",                         "dataType": 7,  "int_value": 200}                       /* UInt32 */
    { "name": "in/4/error",                             "dataType": 12, "string_value": "none"},                /* String */  
    { "name": "in/4/led",                               "dataType": 7,  "int_value": 2500},                     /* UInt32 */  

    { "name": "in/5",                                   "dataType": 7,  "int_value": 5635},                     /* UInt32 */
    { "name": "in/5/mode",                              "dataType": 12, "string_value": "voltage"},             /* String */
    { "name": "in/5/max",                               "dataType": 12, "string_value": "10V"},                 /* String */
    { "name": "in/5/threshold",                         "dataType": 7,  "int_value": 200}                       /* UInt32 */ 
    { "name": "in/5/error",                             "dataType": 12, "string_value": "none"},                /* String */  
    { "name": "in/5/led",                               "dataType": 7,  "int_value": 2500},                     /* UInt32 */  
    
    { "name": "in/6",                                   "dataType": 7,  "int_value": 5635},                     /* UInt32 */
    { "name": "in/6/mode",                              "dataType": 12, "string_value": "voltage"},             /* String */
    { "name": "in/6/max",                               "dataType": 12, "string_value": "10V"},                 /* String */
    { "name": "in/6/threshold",                         "dataType": 7,  "int_value": 200}                       /* UInt32 */ 
    { "name": "in/6/error",                             "dataType": 12, "string_value": "none"},                /* String */ 
    { "name": "in/6/led",                               "dataType": 7,  "int_value": 2500},                     /* UInt32 */  

    { "name": "in/7",                                   "dataType": 7,  "int_value": 5635},                     /* UInt32 */
    { "name": "in/7/mode",                              "dataType": 12, "string_value": "voltage"},             /* String */
    { "name": "in/7/max",                               "dataType": 12, "string_value": "10V"},                 /* String */
    { "name": "in/7/threshold",                         "dataType": 7,  "int_value": 200}                       /* UInt32 */ 
    { "name": "in/7/error",                             "dataType": 12, "string_value": "none"},                /* String */  
    { "name": "in/7/led",                               "dataType": 7,  "int_value": 2500},                     /* UInt32 */  
    
    { "name": "in/8",                                   "dataType": 7,  "int_value": 5635},                     /* UInt32 */
    { "name": "in/8/mode",                              "dataType": 12, "string_value": "voltage"},             /* String */
    { "name": "in/8/max",                               "dataType": 12, "string_value": "10V"},                 /* String */
    { "name": "in/8/threshold",                         "dataType": 7,  "int_value": 200}                       /* UInt32 */ 
    { "name": "in/8/error",                             "dataType": 12, "string_value": "none"},                /* String */  
    { "name": "in/8/led",                               "dataType": 7,  "int_value": 2500},                     /* UInt32 */  

    { "name": "in/9",                                   "dataType": 7,  "int_value": 5635},                     /* UInt32 */
    { "name": "in/9/mode",                              "dataType": 12, "string_value": "voltage"},             /* String */
    { "name": "in/9/max",                               "dataType": 12, "string_value": "10V"},                 /* String */
    { "name": "in/9/threshold",                         "dataType": 7,  "int_value": 200}                       /* UInt32 */ 
    { "name": "in/9/error",                             "dataType": 12, "string_value": "none"},                /* String */  
    { "name": "in/9/led",                               "dataType": 7,  "int_value": 2500},                     /* UInt32 */  
   
    { "name": "in/10",                                  "dataType": 7,  "int_value": 5635},                     /* UInt32 */
    { "name": "in/10/mode",                             "dataType": 12, "string_value": "voltage"},             /* String */
    { "name": "in/10/max",                              "dataType": 12, "string_value": "10V"},                 /* String */
    { "name": "in/10/threshold",                        "dataType": 7,  "int_value": 200}                       /* UInt32 */ 
    { "name": "in/10/error",                            "dataType": 12, "string_value": "none"},                /* String */  
    { "name": "in/10/led",                               "dataType": 7,  "int_value": 2500},                     /* UInt32 */  
    
    { "name": "in/11",                                  "dataType": 7,  "int_value": 5635},                     /* UInt32 */
    { "name": "in/11/mode",                             "dataType": 12, "string_value": "voltage"},             /* String */
    { "name": "in/11/max",                              "dataType": 12, "string_value": "10V"},                 /* String */
    { "name": "in/11/threshold",                        "dataType": 7,  "int_value": 200}                       /* UInt32 */ 
    { "name": "in/11/error",                            "dataType": 12, "string_value": "none"},                /* String */  
    { "name": "in/11/led",                               "dataType": 7,  "int_value": 2500},                     /* UInt32 */  
    
    { "name": "in/12",                                  "dataType": 7,  "int_value": 5635},                     /* UInt32 */
    { "name": "in/12/mode",                             "dataType": 12, "string_value": "voltage"},             /* String */
    { "name": "in/12/max",                              "dataType": 12, "string_value": "10V"},                 /* String */
    { "name": "in/12/threshold",                        "dataType": 7,  "int_value": 200}                       /* UInt32 */ 
    { "name": "in/12/error",                            "dataType": 12, "string_value": "none"},                /* String */  
    { "name": "in/12/led",                              "dataType": 7,  "int_value": 2500},                     /* UInt32 */  
    
    { "name": "in/13",                                  "dataType": 7,  "int_value": 5635},                     /* UInt32 */
    { "name": "in/13/mode",                             "dataType": 12, "string_value": "voltage"},             /* String */
    { "name": "in/13/max",                              "dataType": 12, "string_value": "10V"},                 /* String */
    { "name": "in/13/threshold",                        "dataType": 7,  "int_value": 200}                       /* UInt32 */ 
    { "name": "in/13/error",                            "dataType": 12, "string_value": "none"},                /* String */  
    { "name": "in/13/led",                              "dataType": 7,  "int_value": 2500},                     /* UInt32 */  

    { "name": "in/14",                                  "dataType": 7,  "int_value": 5635},                     /* UInt32 */
    { "name": "in/14/mode",                             "dataType": 12, "string_value": "voltage"},             /* String */
    { "name": "in/14/max",                              "dataType": 12, "string_value": "10V"},                 /* String */
    { "name": "in/14/threshold",                        "dataType": 7,  "int_value": 200}                       /* UInt32 */ 
    { "name": "in/14/error",                            "dataType": 12, "string_value": "none"},                /* String */  
    { "name": "in/14/led",                              "dataType": 7,  "int_value": 2500},                     /* UInt32 */  
    
    { "name": "in/15",                                  "dataType": 7,  "int_value": 5635},                     /* UInt32 */
    { "name": "in/15/mode",                             "dataType": 12, "string_value": "voltage"},             /* String */
    { "name": "in/15/max",                              "dataType": 12, "string_value": "10V"},                 /* String */
    { "name": "in/15/threshold",                        "dataType": 7,  "int_value": 200},                      /* UInt32 */ 
    { "name": "in/15/error",                            "dataType": 12, "string_value": "none"},                /* String */  
    { "name": "in/15/led",                              "dataType": 7,  "int_value": 2500},                     /* UInt32 */  

    /* for update in values - send true */
    { "name": "in/update",                              "dataType": 11, "boolean_value": false},                /* Boolean */
    /* in update time in seconds, 0 - disable update*/
    { "name": "in/update/time",                         "dataType": 7,  "int_value": 0},                        /* UInt32 */
   
  ]
}
```

## PLC device analog input death example
> spBv1.0/plc/DDEATH/abba2020/deba0005  

```json
{
"timestamp": 1486144502122,
"seq": 0
}
```