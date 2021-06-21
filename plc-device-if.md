## PLC device interface birth example
> spBv1.0/plc/DBIRTH/abba2020/deba0004 

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
    { "name": "control/alias",                          "dataType": 12, "string_value": "if"},                  /* String */
    { "name": "info/hardware/vendor",                   "dataType": 12, "string_value": "QuintTech"},           /* String */
    { "name": "info/hardware/model",                    "dataType": 12, "string_value": "stm32g474ce"},         /* String */
    { "name": "info/firmware/version",                  "dataType": 12, "string_value": "0.1.012345678"},       /* String */
    { "name": "info/type",                              "dataType": 12, "string_value": "Interfaces"},          /* String */
    { "name": "info/id",                                "dataType": 12, "string_value": "deba0004"},            /* String */
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

    /* baudrate values = [1200,2400,4800,9600,14400,19200,28800,38400,57600,115200,230400,460800,921600] */
    { "name": "RS485/1/settings/baudrate",              "dataType": 7,  "int_value": 9600},                     /* UInt32*/
    /* databits values = [7,8,9] */
    { "name": "RS485/1/settings/databits",              "dataType": 7,  "int_value": 8},                        /* UInt32*/
    /* stopbits values = [1,1.5,2]*/
    { "name": "RS485/1/settings/stopbits",              "dataType": 9,  "float_value": 1},                      /* Float */
    /* parity values = ['none','even','odd'] */
    { "name": "RS485/1/settings/parity",                "dataType": 12, "string_value": "none"},                /* String */
    /* value in ms, wait time after last byte received */
    { "name": "RS485/1/settings/timeout",               "dataType": 7,  "int_value": 0},                        /* UInt32*/
    /* enable/disable terminator on bus */    
    { "name": "RS485/1/settings/terminator",            "dataType": 11, "boolean_value": true },                /* Boolean */
    { "name": "RS485/1/in",                             "dataType": 17, "bytes_value": "Base64 string"},        /* Bytes" */
    { "name": "RS485/1/out",                            "dataType": 17, "bytes_value": "Base64 string"},        /* Bytes" */
    
    { "name": "RS485/2/settings/baudrate",              "dataType": 7,  "int_value": 9600},                     /* UInt32*/
    { "name": "RS485/2/settings/databits",              "dataType": 7,  "int_value": 8},                        /* UInt32*/
    { "name": "RS485/2/settings/stopbits",              "dataType": 9,  "float_value": 1},                      /* Float */
    { "name": "RS485/2/settings/parity",                "dataType": 12, "string_value": "none"},                /* String */
    { "name": "RS485/2/settings/timeout",               "dataType": 7,  "int_value": 0},                        /* UInt32*/
    { "name": "RS485/2/settings/terminator",            "dataType": 11, "boolean_value": true },                /* Boolean */
    { "name": "RS485/2/in",                             "dataType": 17, "bytes_value": "Base64 string"},        /* Bytes" */
    { "name": "RS485/2/out",                            "dataType": 17, "bytes_value": "Base64 string"},        /* Bytes" */

    { "name": "RS232/settings/baudrate",                "dataType": 7,  "int_value": 9600},                     /* UInt32*/
    { "name": "RS232/settings/databits",                "dataType": 7,  "int_value": 8},                        /* UInt32*/
    { "name": "RS232/settings/stopbits",                "dataType": 9,  "float_value": 1},                      /* Float */
    { "name": "RS232/settings/parity",                  "dataType": 12, "string_value": "none"},                /* String */
    { "name": "RS232/settings/timeout",                 "dataType": 7,  "int_value": 0},                        /* UInt32*/
    { "name": "RS232/in",                               "dataType": 17, "bytes_value": "Base64 string"},        /* Bytes" */
    { "name": "RS232/out",                              "dataType": 17, "bytes_value": "Base64 string"}         /* Bytes" */   
  ]
}

//TODO: add CAN metrics
```

## PLC device interface death example
> spBv1.0/plc/DDEATH/abba2020/deba0004 

```json
{
"timestamp": 1486144502122,
"seq": 0
}
```
