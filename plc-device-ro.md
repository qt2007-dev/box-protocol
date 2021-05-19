## PLC device relay output birth example
> spBv1.0/plc/DBIRTH/abba2020/deba0002 

```json
{
"timestamp": 1486144502122,
"seq": 0,
"metrics": [
    { "name": "bdSeq",                                  "dataType": 8,  "long_value": 0},                       /* Uint64 */
    { "name": "control/reboot",                         "dataType": 11, "boolean_value": false},                /* Boolean */
    { "name": "control/rebirth",                        "dataType": 11, "boolean_value": false},                /* Boolean */
    /* for receive new firmware in Base64 */
    { "name": "control/firmware/new",                   "dataType": 17, "is_null": true},                       /* Bytes" */
    /* save metrics values after reboot */
    { "name": "control/metrics/save",                   "dataType": 11, "boolean_value": true },                /* Boolean */
    /* alias can be used instead id in topics and scenario */    
    { "name": "control/alias",                          "dataType": 12, "string_value": "RO"},                  /* String */
    { "name": "info/hardware/vendor",                   "dataType": 12, "string_value": "QuintTech"},           /* String */
    { "name": "info/hardware/model",                    "dataType": 12, "string_value": "model"},               /* String */
    { "name": "info/firmware/version",                  "dataType": 12, "string_value": "0.1.012345678"},       /* String */
    { "name": "info/type",                              "dataType": 12, "string_value": "16 Relay outputs"},    /* String */
    { "name": "info/id",                                "dataType": 12, "string_value": "deba0002"},            /* String */
    /* metric for last error, in birth always null */       
    { "name": "info/error",                             "dataType": 12, "is_null": true},                       /* String */ 

    { "name": "sensors/temperature",                    "dataType": 9,  "float_value": 24.5},                   /* Float */
    /* for update sensors values - send true */
    { "name": "sensors/update",                         "dataType": 11, "boolean_value": false},                /* Boolean */
    /* sensors update time in seconds, 0 - disable update*/
    { "name": "sensors/update/time",                    "dataType": 7,  "int_value": 0},                        /* UInt32 */
    /* enabled/disabled update */
    { "name": "sensors/update/temperature",             "dataType": 11, "boolean_value": false},                /* Boolean */
    /* update threshold value for auto update  */      
    { "name": "sensors/update/temperature/threshold",   "dataType": 9,  "float_value": 3},                      /* Float */
      
    /* value is bitmask 0-7 input */    
    { "name": "out/lsb",                                "dataType": 5,  "int_value": 0},                        /* UInt8 */
    /* value is bitmask 8-15 input */    
    { "name": "out/msb",                                "dataType": 5,  "int_value": 0},                        /* UInt8 */

    { "name": "out/0",                                  "dataType": 11, "boolean_value": false},                /* Boolean */
    { "name": "out/1",                                  "dataType": 11, "boolean_value": false},                /* Boolean */       
    { "name": "out/2",                                  "dataType": 11, "boolean_value": false},                /* Boolean */       
    { "name": "out/3",                                  "dataType": 11, "boolean_value": false},                /* Boolean */       
    { "name": "out/4",                                  "dataType": 11, "boolean_value": false},                /* Boolean */       
    { "name": "out/5",                                  "dataType": 11, "boolean_value": false},                /* Boolean */       
    { "name": "out/6",                                  "dataType": 11, "boolean_value": false},                /* Boolean */       
    { "name": "out/7",                                  "dataType": 11, "boolean_value": false},                /* Boolean */       
    { "name": "out/8",                                  "dataType": 11, "boolean_value": false},                /* Boolean */       
    { "name": "out/9",                                  "dataType": 11, "boolean_value": false},                /* Boolean */       
    { "name": "out/10",                                 "dataType": 11, "boolean_value": false},                /* Boolean */       
    { "name": "out/11",                                 "dataType": 11, "boolean_value": false},                /* Boolean */       
    { "name": "out/12",                                 "dataType": 11, "boolean_value": false},                /* Boolean */       
    { "name": "out/13",                                 "dataType": 11, "boolean_value": false},                /* Boolean */       
    { "name": "out/14",                                 "dataType": 11, "boolean_value": false},                /* Boolean */       
    { "name": "out/15",                                 "dataType": 11, "boolean_value": false}                 /* Boolean */          
  ]
}
```