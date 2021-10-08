## Ligth controller node birth example
> spBv1.0/lc/NBIRTH/baab2020

```json
{
"timestamp": 1486144502122,
"seq": 0,
"metrics": [
    /* birth-death-sequence same value in ndeath message */
    { "name": "bdSeq",                                  "dataType": 8,  "long_value": 0},                       /* Uint64 */
    { "name": "control/reboot",                         "dataType": 11, "boolean_value": false},                /* Boolean */
    { "name": "control/rebirth",                        "dataType": 11, "boolean_value": false},                /* Boolean */
    /* for receive new firmware in Base64 */
    { "name": "control/firmware/new",                   "dataType": 17, "is_null": true},                       /* Bytes" */
    /* save metrics values after reboot */
    { "name": "control/metrics/save",                   "dataType": 11, "boolean_value": true },                /* Boolean */
    /* alias can be used instead id in topics and scenario */    
    { "name": "control/alias",                          "dataType": 12, "string_value": "lc"},                  /* String */
    { "name": "info/hardware/vendor",                   "dataType": 12, "string_value": "QuintTech"},           /* String */
    { "name": "info/hardware/model",                    "dataType": 12, "string_value": "model"},               /* String */
    { "name": "info/firmware/version",                  "dataType": 12, "string_value": "0.1.012345678"},       /* String */
    { "name": "info/commit",                            "dataType": 12, "string_value": "4a920e480e6438d272fb69b2aff4e416d0c9a143"}, /* String */
    { "name": "info/type",                              "dataType": 12, "string_value": "LC"},                  /* String */
    { "name": "info/id",                                "dataType": 12, "string_value": "baab2020"},            /* String */
    /* metric for last error, in birth always null */       
    { "name": "info/error",                             "dataType": 12, "is_null": true},                       /* String */    
    /* active connection type metric, values = ['modem', 'thread']  */  
    { "name": "connection/type",                        "dataType": 12, "string_value": "modem"},               /* String */
    { "name": "connection/modem/operator",              "dataType": 12, "string_value": "Beeline"},             /* String */
    { "name": "connection/modem/iccid",                 "dataType": 12, "string_value": "897010269709192239"},  /* String */
    { "name": "connection/modem/rssi",                  "dataType": 3,  "string_value": -60},                   /* Int32 */   
    { "name": "connection/thread/name",                 "dataType": 12, "string_value": "ThreadNetworkName"},   /* String */
    { "name": "connection/thread/panid",                "dataType": 6,  "int_value": 1234},                     /* UInt16 */
    { "name": "connection/thread/channel",              "dataType": 5,  "int_value": 12},                       /* UInt8 */
    /* device role in thread network, values = ['child', 'router', 'leader']  */  
    { "name": "connection/thread/role",                 "dataType": 12, "string_value": "leader"},              /* String */
    { "name": "connection/thread/rloc16",               "dataType": 6,  "int_value": 1234},                     /* UInt16 */
    { "name": "connection/thread/neighbors",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 4,
                        "columns": ["role", "rloc16", "avg-rssi", "last-rssi"],
                        "types": [12, 6, 3, 3], /* String, UInt16, Int32, Int32 */
                        "rows": [ {"elements":[{"string_value":"child"},{"int_value":1235},{"int_value":-60},{"int_value":-70} ]},
                                  {"elements":[{"string_value":"router"},{"int_value":1235},{"int_value":-60},{"int_value":-70} ]},
                                  {"elements":[{"string_value":"leader"},{"int_value":1235},{"int_value":-60},{"int_value":-70} ]}  ] } },
    /* current server, to change send server:port with certificate in properties*/                              
    { "name": "connection/server",                      "dataType": 12, "string_value": "84.201.159.12:1883"},  /* String */                                   

    { "name": "scenario/list",              
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 3,
                        "columns": ["name", "last", "next"],
                        "types": [12, 8, 8], /* String, UInt64, UInt64 */
                        "rows": [ {"elements":[{"string_value":"scenarioName1"},{"long_value":151515151515},{"long_value":151515151515} ]},
                                  {"elements":[{"string_value":"scenarioName2"},{"long_value":151515151515},{"long_value":151515151515} ]}  ] }
                                  /* value = list of scenarioId and names, last - last used time, next - next time to be used */},      
    /* value = scenarioId to add to list, in birth always null */
    { "name": "scenario/add",                           "dataType": 12, "is_null": true},                       /* String */ 
    /* value = scenarioId to delete from list, in birth always null */
    { "name": "scenario/delete",                        "dataType": 12, "is_null": true},                       /* String */ 
    /* value = scenarioId to get from list, in birth always null */
    { "name": "scenario/get",                           "dataType": 12, "is_null": true},                       /* String */     
    /* schedule control metric, values = ['on', 'off', 'set', 'get'] */
    { "name": "schedule",                               "dataType": 12, "string_value": "on"},                  /* String */
    { "name": "schedule/state",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 5,
                        "columns": ["name", "actioNumber", "actionQuantity", "repeatNumber", "repeatQuantity"],
                        "types": [12, 3, 3, 3, 3], /* String, UInt32, UInt32, UInt32 */
                        "rows": [ {"elements":[ {"string_value":"scenarioName1"},{"int_value":2},{"int_value":10},{"int_value":3},{"int_value":25} ]},
                                  {"elements":[ {"string_value":"scenarioName2"},{"int_value":2},{"int_value":10},{"int_value":3},{"int_value":-1} ]}  ] } }, 

    { "name": "sensors/accelerometer/x",                "dataType": 9,  "float_value": 7852},                   /* Float */
    { "name": "sensors/accelerometer/y",                "dataType": 9,  "float_value": 7852},                   /* Float */
    { "name": "sensors/accelerometer/z",                "dataType": 9,  "float_value": 7852},                   /* Float */
    { "name": "sensors/luminosity",                     "dataType": 9,  "float_value": 12.4},                   /* Float */
    { "name": "sensors/temperature",                    "dataType": 1,  "int_value": 22},                       /* Int8 */
    /* for update sensors values - send true */
    { "name": "sensors/update",                         "dataType": 11, "boolean_value": false},                /* Boolean */
    /* sensors update time in seconds, 0 - disable update*/
    { "name": "sensors/update/time",                    "dataType": 7,  "int_value": 0},                        /* UInt32 */
    /* enabled/disabled update */
    { "name": "sensors/update/accelerometer",           "dataType": 11, "boolean_value": false},                /* Boolean */  
    { "name": "sensors/update/luminosity",              "dataType": 11, "boolean_value": false},                /* Boolean */
    { "name": "sensors/update/temperature",             "dataType": 11, "boolean_value": false},                /* Boolean */
    /* update threshold value for auto update  */      
    { "name": "sensors/update/accelerometer/threshold", "dataType": 9,  "float_value": 3},                      /* Float */
    { "name": "sensors/update/luminosity/threshold",    "dataType": 9,  "float_value": 3},                      /* Float */
    { "name": "sensors/update/temperature/threshold",   "dataType": 5,  "int_value": 2},                        /* UInt8 */

    { "name": "coordinates/latitude",                   "dataType": 10, "double_value": 55.751244},             /* Double */
    { "name": "coordinates/longitude",                  "dataType": 10, "double_value": 37.618423},             /* Double */
    { "name": "coordinates/update/time",                "dataType": 7,  "int_value": 0},                        /* UInt32 */
    { "name": "coordinates/update/threshold",           "dataType": 10, "double_value": 0.001}                  /* Double */           
  ]
}
```

```json
> spBv1.0/lc/NDEATH/baab2020
{
"timestamp": 1486144502122,
"metrics": [  
    /* birth-death-sequence same value in nbirth message */
    { "name": "bdSeq",                                  "dataType": 8,  "long_value": 0},                       /* Uint64 */
]
}
```
