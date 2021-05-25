## PLC device dali birth example
> spBv1.0/plc/DBIRTH/abba2020/deba0001 

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
    { "name": "control/alias",                          "dataType": 12, "string_value": "DALI"},                /* String */
    { "name": "info/hardware/vendor",                   "dataType": 12, "string_value": "QuintTech"},           /* String */
    { "name": "info/hardware/model",                    "dataType": 12, "string_value": "model"},               /* String */
    { "name": "info/firmware/version",                  "dataType": 12, "string_value": "0.1.012345678"},       /* String */
    { "name": "info/type",                              "dataType": 12, "string_value": "DALI 128"},            /* String */
    { "name": "info/id",                                "dataType": 12, "string_value": "deba0001"},            /* String */
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
      
    { "name": "dali/1/command/code",                    "dataType": 6,  "int_value": 0},                        /* UInt16 */  
    { "name": "dali/1/command/address",                 "dataType": 5,  "int_value": 0},                        /* UInt8 */
    { "name": "dali/1/command/value",                   "dataType": 5,  "int_value": 0},                        /* UInt8 */
    { "name": "dali/1/command/answer",                  "dataType": 5,  "int_value": 0},                        /* UInt8 */
  

         
  ]
}
```