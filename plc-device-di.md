## PLC device digital input birth example
> spBv1.0/plc/DBIRTH/abba2020/deba0003  

```json
{
"timestamp": 1486144502122,
"seq": 0,
"metrics": [
    { "name": "control/reboot",                         "dataType": 11, "boolean_value": false},                /* Boolean */
    { "name": "control/rebirth",                        "dataType": 11, "boolean_value": false},                /* Boolean */
    /* for receive new firmware in Base64 */
    { "name": "control/firmware/new",                   "dataType": 17, "is_null": true},                       /* Bytes" */
    /* save metrics values after reboot */
    { "name": "control/metrics/save",                   "dataType": 11, "boolean_value": true },                /* Boolean */
    /* alias can be used instead id in topics and scenario */    
    { "name": "control/alias",                          "dataType": 12, "string_value": "di"},                  /* String */
    { "name": "info/hardware/vendor",                   "dataType": 12, "string_value": "QuintTech"},           /* String */
    { "name": "info/hardware/model",                    "dataType": 12, "string_value": "model"},               /* String */
    { "name": "info/firmware/version",                  "dataType": 12, "string_value": "0.1.012345678"},       /* String */
    { "name": "info/type",                              "dataType": 12, "string_value": "16 Digital inputs"},   /* String */
    { "name": "info/id",                                "dataType": 12, "string_value": "deba0003"},            /* String */
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

    /* value is bitmask 0-7 input */    
    { "name": "in/lsb",                                 "dataType": 5,  "int_value": 0},                        /* UInt8 */
    /* value is bitmask 8-15 input */    
    { "name": "in/msb",                                 "dataType": 5,  "int_value": 0},                        /* UInt8 */

    { "name": "in/0",                                   "dataType": 11, "boolean_value": false},                /* Boolean */
    { "name": "in/1",                                   "dataType": 11, "boolean_value": false},                /* Boolean */       
    { "name": "in/2",                                   "dataType": 11, "boolean_value": false},                /* Boolean */       
    { "name": "in/3",                                   "dataType": 11, "boolean_value": false},                /* Boolean */       
    { "name": "in/4",                                   "dataType": 11, "boolean_value": false},                /* Boolean */       
    { "name": "in/5",                                   "dataType": 11, "boolean_value": false},                /* Boolean */       
    { "name": "in/6",                                   "dataType": 11, "boolean_value": false},                /* Boolean */       
    { "name": "in/7",                                   "dataType": 11, "boolean_value": false},                /* Boolean */       
    { "name": "in/8",                                   "dataType": 11, "boolean_value": false},                /* Boolean */       
    { "name": "in/9",                                   "dataType": 11, "boolean_value": false},                /* Boolean */       
    { "name": "in/10",                                  "dataType": 11, "boolean_value": false},                /* Boolean */       
    { "name": "in/11",                                  "dataType": 11, "boolean_value": false},                /* Boolean */       
    { "name": "in/12",                                  "dataType": 11, "boolean_value": false},                /* Boolean */       
    { "name": "in/13",                                  "dataType": 11, "boolean_value": false},                /* Boolean */       
    { "name": "in/14",                                  "dataType": 11, "boolean_value": false},                /* Boolean */       
    { "name": "in/15",                                  "dataType": 11, "boolean_value": false},                /* Boolean */     
    
    /* for update in values - send true */
    { "name": "in/update",                              "dataType": 11, "boolean_value": false},                /* Boolean */
    /* in update time in seconds, 0 - disable update*/
    { "name": "in/update/time",                         "dataType": 7,  "int_value": 0}                         /* UInt32 */      
  ]
}
```

## PLC device digital input death example
> spBv1.0/plc/DDEATH/abba2020/deba0003  

```json
{
"timestamp": 1486144502122,
"seq": 0
}
```