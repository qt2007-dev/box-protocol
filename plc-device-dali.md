## PLC device dali birth example
> spBv1.0/plc/DBIRTH/abba2020/deba0006 

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
    { "name": "control/alias",                          "dataType": 12, "string_value": "dali"},                /* String */
    { "name": "info/hardware/vendor",                   "dataType": 12, "string_value": "QuintTech"},           /* String */
    { "name": "info/hardware/model",                    "dataType": 12, "string_value": "model"},               /* String */
    { "name": "info/firmware/version",                  "dataType": 12, "string_value": "0.1.012345678"},       /* String */
    { "name": "info/type",                              "dataType": 12, "string_value": "DALI 128"},            /* String */
    { "name": "info/id",                                "dataType": 12, "string_value": "deba0006"},            /* String */
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

    /* dali/{bus}/{device}  */    

    /* Bus control metrics */
    /* Bus status values=['online','dublicate','short-current','error','offline']*/
    { "name": "dali/1/status",                          "dataType": 12, "string_value": "online"},              /* String */
    /* Address devices values=['all', 'new', 'dublicate'] */
    { "name": "dali/1/scan",                            "dataType": 12, "string_value": "all"},                 /* String */
    { "name": "dali/1/update",                          "dataType": 11, "boolean_value": false},                /* Boolean */
    
    { "name": "dali/1/dim",                             "dataType": 5,  "int_value": 0},                        /* UInt8 */
    { "name": "dali/1/scene",                           "dataType": 5,  "int_value": 0},                        /* UInt8 */
    
    /* Group control metrics */
    /* Group 1/16 on bus 1*/
    { "name": "dali/1/group/1",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 1,
                        "columns": ["devices"],
                        "types": [8], /* UInt8 */
                        "rows": [ {"elements":[{"int_value": 0}]},
                                  {"elements":[{"int_value": 1}]},
                                  {"elements":[{"int_value": 2}]},
                                  {"elements":[{"int_value": 3}]},
                                  {"elements":[{"int_value": 4}]},
                                  {"elements":[{"int_value": 5}]}  ] } },
    { "name": "dali/1/group/1/dim",                     "dataType": 5,  "int_value": 0},                        /* UInt8 */
    { "name": "dali/1/group/1/scene",                   "dataType": 5,  "int_value": 0},                        /* UInt8 */ 

    /* Group 2/16 on bus 1*/
    { "name": "dali/1/group/2",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 1, 
                        "columns": ["devices"],
                        "types": [8], /* UInt8 */
                        "rows": [ ] } },
    { "name": "dali/1/group/2/dim",                     "dataType": 5,  "int_value": 0},                        /* UInt8 */
    { "name": "dali/1/group/2/scene",                   "dataType": 5,  "int_value": 0},                        /* UInt8 */ 
    
    /* ...................*/
    /* Group 16/16 on bus 1*/
    { "name": "dali/1/group/16",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 1, 
                        "columns": ["devices"],
                        "types": [8], /* UInt8 */
                        "rows": [ ] } },
    { "name": "dali/1/group/16/dim",                     "dataType": 5,  "int_value": 0},                       /* UInt8 */
    { "name": "dali/1/group/16/scene",                   "dataType": 5,  "int_value": 0},                       /* UInt8 */ 
    
    /* Device control metrics */
    /* Device 1 on bus 1*/
    { "name": "dali/1/device/1/type",                   "dataType": 12, "string_value": "LED"},                 /* String */
    { "name": "dali/1/device/1/id",                     "dataType": 12, "string_value": "0000-1121"},           /* String */
   
    { "name": "dali/1/device/1/dim",                    "dataType": 5,  "int_value": 0},                        /* UInt8 */
    { "name": "dali/1/device/1/dim/phyMin",             "dataType": 5,  "int_value": 0},                        /* UInt8 */
    { "name": "dali/1/device/1/dim/min",                "dataType": 5,  "int_value": 0},                        /* UInt8 */
    { "name": "dali/1/device/1/dim/max",                "dataType": 5,  "int_value": 0},                        /* UInt8 */
    { "name": "dali/1/device/1/dim/powerOn",            "dataType": 5,  "int_value": 0},                        /* UInt8 */
    { "name": "dali/1/device/1/dim/failure",            "dataType": 5,  "int_value": 0},                        /* UInt8 */
    
    { "name": "dali/1/device/1/fade/time",              "dataType": 5,  "int_value": 0},                        /* UInt8 */
    { "name": "dali/1/device/1/fade/rate",              "dataType": 5,  "int_value": 0},                        /* UInt8 */    

    { "name": "dali/1/device/1/gear/controlFailure",    "dataType": 11, "boolean_value": false},                /* Boolean */
    { "name": "dali/1/device/1/gear/lampFailure",       "dataType": 11, "boolean_value": false},                /* Boolean */
    { "name": "dali/1/device/1/gear/lampOn",            "dataType": 11, "boolean_value": true},                 /* Boolean */
    { "name": "dali/1/device/1/gear/limitError",        "dataType": 11, "boolean_value": false},                /* Boolean */
    { "name": "dali/1/device/1/gear/fadeRunning",       "dataType": 11, "boolean_value": false},                /* Boolean */
    { "name": "dali/1/device/1/gear/resetState",        "dataType": 11, "boolean_value": false},                /* Boolean */
    { "name": "dali/1/device/1/gear/powerCycle",        "dataType": 11, "boolean_value": false},                /* Boolean */ 

    { "name": "dali/1/device/1/scene/1",                "dataType": 5,  "int_value": 0},                        /* UInt8 */
    { "name": "dali/1/device/1/scene/2",                "dataType": 5,  "int_value": 0},                        /* UInt8 */
    { "name": "dali/1/device/1/scene/3",                "dataType": 5,  "int_value": 0},                        /* UInt8 */
    { "name": "dali/1/device/1/scene/4",                "dataType": 5,  "int_value": 0},                        /* UInt8 */
    { "name": "dali/1/device/1/scene/5",                "dataType": 5,  "int_value": 0},                        /* UInt8 */
    { "name": "dali/1/device/1/scene/6",                "dataType": 5,  "int_value": 0},                        /* UInt8 */
    { "name": "dali/1/device/1/scene/7",                "dataType": 5,  "int_value": 0},                        /* UInt8 */
    { "name": "dali/1/device/1/scene/8",                "dataType": 5,  "int_value": 0},                        /* UInt8 */
    { "name": "dali/1/device/1/scene/9",                "dataType": 5,  "int_value": 0},                        /* UInt8 */
    { "name": "dali/1/device/1/scene/10",               "dataType": 5,  "int_value": 0},                        /* UInt8 */
    { "name": "dali/1/device/1/scene/11",               "dataType": 5,  "int_value": 0},                        /* UInt8 */
    { "name": "dali/1/device/1/scene/12",               "dataType": 5,  "int_value": 0},                        /* UInt8 */
    { "name": "dali/1/device/1/scene/13",               "dataType": 5,  "int_value": 0},                        /* UInt8 */
    { "name": "dali/1/device/1/scene/14",               "dataType": 5,  "int_value": 0},                        /* UInt8 */
    { "name": "dali/1/device/1/scene/15",               "dataType": 5,  "int_value": 0},                        /* UInt8 */
    { "name": "dali/1/device/1/scene/16",               "dataType": 5,  "int_value": 0},                        /* UInt8 */

    /* Bus control metrics */    
    { "name": "dali/2/status",                          "dataType": 12, "string_value": "online"},              /* String */
    { "name": "dali/2/scan",                            "dataType": 12, "string_value": "all"},                 /* String */
    { "name": "dali/2/update",                          "dataType": 11, "boolean_value": false},                /* Boolean */
    
    { "name": "dali/2/dim",                             "dataType": 5,  "int_value": 0},                        /* UInt8 */
    { "name": "dali/2/scene",                           "dataType": 5,  "int_value": 0},                        /* UInt8 */
    
    /* Group control metrics */
    /* Group 1/16 on bus 2*/
    { "name": "dali/2/group/1",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 1,
                        "columns": ["devices"],
                        "types": [8], /* UInt8 */
                        "rows": [ {"elements":[{"int_value": 0}]},
                                  {"elements":[{"int_value": 1}]},
                                  {"elements":[{"int_value": 2}]},
                                  {"elements":[{"int_value": 3}]},
                                  {"elements":[{"int_value": 4}]},
                                  {"elements":[{"int_value": 5}]}  ] } },
    { "name": "dali/2/group/1/dim",                     "dataType": 5,  "int_value": 0},                        /* UInt8 */
    { "name": "dali/2/group/1/scene",                   "dataType": 5,  "int_value": 0},                        /* UInt8 */ 

    /* Group 2/16 on bus 1*/
    { "name": "dali/2/group/2",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 1, 
                        "columns": ["devices"],
                        "types": [8], /* UInt8 */
                        "rows": [ ] } },
    { "name": "dali/2/group/2/dim",                     "dataType": 5,  "int_value": 0},                        /* UInt8 */
    { "name": "dali/2/group/2/scene",                   "dataType": 5,  "int_value": 0},                        /* UInt8 */ 
    
    /* ...................*/
    /* Group 16/16 on bus 1*/
    { "name": "dali/2/group/16",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 1, 
                        "columns": ["devices"],
                        "types": [8], /* UInt8 */
                        "rows": [ ] } },
    { "name": "dali/2/group/16/dim",                     "dataType": 5,  "int_value": 0},                       /* UInt8 */
    { "name": "dali/2/group/16/scene",                   "dataType": 5,  "int_value": 0},                       /* UInt8 */ 
    
    /* Device control metrics */
    /* Device 1 on bus 1*/
    { "name": "dali/2/device/1/type",                   "dataType": 12, "string_value": "LED"},                 /* String */
    { "name": "dali/2/device/1/id",                     "dataType": 12, "string_value": "0000-1121"},           /* String */
   
    { "name": "dali/2/device/1/dim",                    "dataType": 5,  "int_value": 0},                        /* UInt8 */
    { "name": "dali/2/device/1/dim/phyMin",             "dataType": 5,  "int_value": 0},                        /* UInt8 */
    { "name": "dali/2/device/1/dim/min",                "dataType": 5,  "int_value": 0},                        /* UInt8 */
    { "name": "dali/2/device/1/dim/max",                "dataType": 5,  "int_value": 0},                        /* UInt8 */
    { "name": "dali/2/device/1/dim/powerOn",            "dataType": 5,  "int_value": 0},                        /* UInt8 */
    { "name": "dali/2/device/1/dim/failure",            "dataType": 5,  "int_value": 0},                        /* UInt8 */
    
    { "name": "dali/2/device/1/fade/time",              "dataType": 5,  "int_value": 0},                        /* UInt8 */
    { "name": "dali/2/device/1/fade/rate",              "dataType": 5,  "int_value": 0},                        /* UInt8 */    

    { "name": "dali/2/device/1/gear/controlFailure",    "dataType": 11, "boolean_value": false},                /* Boolean */
    { "name": "dali/2/device/1/gear/lampFailure",       "dataType": 11, "boolean_value": false},                /* Boolean */
    { "name": "dali/2/device/1/gear/lampOn",            "dataType": 11, "boolean_value": true},                 /* Boolean */
    { "name": "dali/2/device/1/gear/limitError",        "dataType": 11, "boolean_value": false},                /* Boolean */
    { "name": "dali/2/device/1/gear/fadeRunning",       "dataType": 11, "boolean_value": false},                /* Boolean */
    { "name": "dali/2/device/1/gear/resetState",        "dataType": 11, "boolean_value": false},                /* Boolean */
    { "name": "dali/2/device/1/gear/powerCycle",        "dataType": 11, "boolean_value": false},                /* Boolean */ 

    { "name": "dali/2/device/1/scene/1",                "dataType": 5,  "int_value": 0},                        /* UInt8 */
    { "name": "dali/2/device/1/scene/2",                "dataType": 5,  "int_value": 0},                        /* UInt8 */
    { "name": "dali/2/device/1/scene/3",                "dataType": 5,  "int_value": 0},                        /* UInt8 */
    { "name": "dali/2/device/1/scene/4",                "dataType": 5,  "int_value": 0},                        /* UInt8 */
    { "name": "dali/2/device/1/scene/5",                "dataType": 5,  "int_value": 0},                        /* UInt8 */
    { "name": "dali/2/device/1/scene/6",                "dataType": 5,  "int_value": 0},                        /* UInt8 */
    { "name": "dali/2/device/1/scene/7",                "dataType": 5,  "int_value": 0},                        /* UInt8 */
    { "name": "dali/2/device/1/scene/8",                "dataType": 5,  "int_value": 0},                        /* UInt8 */
    { "name": "dali/2/device/1/scene/9",                "dataType": 5,  "int_value": 0},                        /* UInt8 */
    { "name": "dali/2/device/1/scene/10",               "dataType": 5,  "int_value": 0},                        /* UInt8 */
    { "name": "dali/2/device/1/scene/11",               "dataType": 5,  "int_value": 0},                        /* UInt8 */
    { "name": "dali/2/device/1/scene/12",               "dataType": 5,  "int_value": 0},                        /* UInt8 */
    { "name": "dali/2/device/1/scene/13",               "dataType": 5,  "int_value": 0},                        /* UInt8 */
    { "name": "dali/2/device/1/scene/14",               "dataType": 5,  "int_value": 0},                        /* UInt8 */
    { "name": "dali/2/device/1/scene/15",               "dataType": 5,  "int_value": 0},                        /* UInt8 */
    { "name": "dali/2/device/1/scene/16",               "dataType": 5,  "int_value": 0},                        /* UInt8 */

         
  ]
}
```

## PLC device dali death example
> spBv1.0/plc/DDEATH/abba2020/deba0006 

```json
{
"timestamp": 1486144502122,
"seq": 0
}
```