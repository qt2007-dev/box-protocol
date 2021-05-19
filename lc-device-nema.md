## Ligth controller device birth example with analog driver
> spBv1.0/lc/DBIRTH/baab2020/deba0001  

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
    { "name": "control/alias",                          "dataType": 12, "string_value": "NEMA"},                /* String */
    { "name": "info/hardware/vendor",                   "dataType": 12, "string_value": "QuintTech"},           /* String */
    { "name": "info/hardware/model",                    "dataType": 12, "string_value": "model"},               /* String */
    { "name": "info/firmware/version",                  "dataType": 12, "string_value": "0.1.012345678"},       /* String */
    { "name": "info/type",                              "dataType": 12, "string_value": "NEMA"},                /* String */
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
     
    { "name": "meter/voltage",                          "dataType": 7,  "int_value": 220000},                   /* UInt32 */
    { "name": "meter/current",                          "dataType": 7,  "int_value": 865},                      /* UInt32 */
    { "name": "meter/power/active",                     "dataType": 3,  "int_value": 7852},                     /* Int32 */
    { "name": "meter/power/reactive",                   "dataType": 7,  "int_value": 865},                      /* UInt32 */
    { "name": "meter/power/apparent",                   "dataType": 7,  "int_value": 8000},                     /* UInt32 */
    { "name": "meter/power/factor",                     "dataType": 3,  "int_value": 865},                      /* Int32 */
    /* meter update time in seconds, 0 - disable update*/
    { "name": "meter/update/time",                      "dataType": 7,  "int_value": 0},                        /* UInt32 */
    /* enabled/disabled update */                
    { "name": "meter/update/voltage",                   "dataType": 11, "boolean_value": false},                /* Boolean */
    { "name": "meter/update/current",                   "dataType": 11, "boolean_value": false},                /* Boolean */
    { "name": "meter/update/power/active",              "dataType": 11, "boolean_value": false},                /* Boolean */
    { "name": "meter/update/power/reactive",            "dataType": 11, "boolean_value": false},                /* Boolean */
    { "name": "meter/update/power/apparent",            "dataType": 11, "boolean_value": false},                /* Boolean */
    { "name": "meter/update/power/factor",              "dataType": 11, "boolean_value": false},                /* Boolean */
    /* update threshold value for auto update  */      
    { "name": "meter/update/voltage/threshold",         "dataType": 7,  "int_value": 300},                      /* UInt32 */   
    { "name": "meter/update/current/threshold",         "dataType": 7,  "int_value": 100},                      /* UInt32 */   
    { "name": "meter/update/power/active/threshold",    "dataType": 7,  "int_value": 100},                      /* UInt32 */   
    { "name": "meter/update/power/reactive/threshold",  "dataType": 7,  "int_value": 100},                      /* UInt32 */   
    { "name": "meter/update/power/apparent/threshold",  "dataType": 7,  "int_value": 100},                      /* UInt32 */   
    { "name": "meter/update/power/factor/threshold",    "dataType": 7,  "int_value": 100},                      /* UInt32 */   
        
    { "name": "load",                                   "dataType": 11, "boolean_value": false},                /* Boolean */
     /* driver selection metric, values = ['analog', 'pwm', 'dali'], change triggers rebirth*/
    { "name": "driver",                                 "dataType": 12, "string_value": "analog"},              /* String */

    { "name": "analog/dim",                             "dataType": 6,  "int_value": 125},                      /* UInt16 */
    { "name": "analog/dim/min",                         "dataType": 6,  "int_value": 0},                        /* UInt16 */
    { "name": "analog/dim/max",                         "dataType": 6,  "int_value": 1000},                     /* UInt16 */    
  ]
}
//TODO: merge meter and sensors   
```

## Ligth controller device birth example with pwm driver
> spBv1.0/lc/DBIRTH/baab2020/deba0001  

```json
{
"timestamp": 1486144502122,
"seq": 0,
"metrics": [
    /* ..... before 'driver' metric all metrics are same ...... */
    { "name": "driver",                                 "dataType": 12, "string_value": "pwm"},                 /* String */

    { "name": "pwm/dim",                                "dataType": 6,  "int_value": 125},                      /* UInt16 */
    { "name": "pwm/dim/min",                            "dataType": 6,  "int_value": 0},                        /* UInt16 */
    { "name": "pwm/dim/max",                            "dataType": 6,  "int_value": 1000},                     /* UInt16 */    
  ]
}
```

## Ligth controller device birth example with dali driver
> spBv1.0/lc/DBIRTH/baab2020/deba0001  

```json
{
"timestamp": 1486144502122,
"seq": 0,
"metrics": [
    /* ..... before 'driver' metric all metrics are same ...... */
    { "name": "driver",                                 "dataType": 12, "string_value": "dali"},                /* String */

    { "name": "dali/0/dim",                             "dataType": 5,  "int_value": 225},                      /* UInt8 */
    { "name": "dali/0/dim/phyMin",                      "dataType": 5,  "int_value": 160},                      /* UInt8 */
    { "name": "dali/0/dim/min",                         "dataType": 5,  "int_value": 160},                      /* UInt8 */
    { "name": "dali/0/dim/max",                         "dataType": 5,  "int_value": 254},                      /* UInt8 */
    { "name": "dali/0/dim/powerOn",                     "dataType": 5,  "int_value": 254},                      /* UInt8 */
    { "name": "dali/0/dim/failure",                     "dataType": 5,  "int_value": 254},                      /* UInt8 */
    { "name": "dali/0/fade/rate",                       "dataType": 5,  "int_value": 5},                        /* UInt8 */
    { "name": "dali/0/fade/time",                       "dataType": 5,  "int_value": 5},                        /* UInt8 */
    { "name": "dali/0/gear/controlFailure",             "dataType": 11, "boolean_value": false},                /* Boolean */
    { "name": "dali/0/gear/lampFailure",                "dataType": 11, "boolean_value": false},                /* Boolean */
    { "name": "dali/0/gear/lampOn",                     "dataType": 11, "boolean_value": true},                /* Boolean */
    { "name": "dali/0/gear/limitError",                 "dataType": 11, "boolean_value": false},                /* Boolean */
    { "name": "dali/0/gear/fadeRunning",                "dataType": 11, "boolean_value": false},                /* Boolean */
    { "name": "dali/0/gear/resetState",                 "dataType": 11, "boolean_value": false},                /* Boolean */
    { "name": "dali/0/gear/shortAddressMissing",        "dataType": 11, "boolean_value": false},                /* Boolean */
    { "name": "dali/0/gear/powerCycle",                 "dataType": 11, "boolean_value": false},                /* Boolean */
  ]
}
```
