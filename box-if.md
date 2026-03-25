## BOX device interface birth example
> spBv1.0/box/DBIRTH/abba2020/deba0005 

```json
{
"timestamp": 1486144502122,
"seq": 0,
"metrics": [
    { "name": "bdSeq",                          "dataType": 8/* Uint64 */,   "long_value": 0,                    "metadata":{"description":"[R]Birth-death sequence, 'online' - [BIRTH > DEATH], 'offline' - [BIRTH <= DEATH]"} },
    { "name": "control/reboot",                 "dataType": 11/* Boolean */, "boolean_value": false,             "metadata":{"description":"[W]Software reboot, send 'true' for reboot"} },
    { "name": "control/rebirth",                "dataType": 11/* Boolean */, "boolean_value": false,             "metadata":{"description":"[W]Rebirth, send 'true' for receive birth message again"} },
    { "name": "control/firmware/new",           "dataType": 17/* Bytes */,   "bytes_value":"", "is_null": true,  "metadata":{"description":"[W]Receive new firmware, firmware send in Base64 format, in birth always null"} },
    { "name": "control/metrics/save",           "dataType": 11/* Boolean */, "boolean_value": true,              "metadata":{"description":"[RWP]Save metrics states after reboot, send 'true' for enable"} },
    { "name": "control/metrics/metadata",       "dataType": 11/* Boolean */, "boolean_value": true,              "metadata":{"description":"[RWP]Show metrics metadata in birth, send 'true' for enable"} },
    { "name": "control/group",                  "dataType": 12/* String */,  "string_value": "if",               "metadata":{"description":"[RWP]Global group, can be used instead id in topics and scenarios"} },

    { "name": "info/hardware/vendor",           "dataType": 12/* String */,  "string_value": "QuintTech" ,       "metadata":{"description":"[R]Vendor name, hardcoded by vendor"} },
    { "name": "info/hardware/model",            "dataType": 12/* String */,  "string_value": "stm32g474ce",      "metadata":{"description":"[R]Mcu model, hardcoded by vendor"} },
    { "name": "info/firmware/version",          "dataType": 12/* String */,  "string_value": "0.1.220527.84852", "metadata":{"description":"[R]Firmware version, MAJOR.MINOR.buildOrCommit"} },
    { "name": "info/type",                      "dataType": 12/* String */,  "string_value": "Interfaces",       "metadata":{"description":"[R]Device type, hardcoded by vendor"} },
    { "name": "info/id",                        "dataType": 12/* String */,  "string_value": "deba0005",         "metadata":{"description":"[R]Short device id"} },
    { "name": "info/error",                     "dataType": 12/* String */,  "string_value": "",                 "metadata":{"description":"[R]Last error message"} },

    { "name": "sensors/temperature",            "dataType": 1/* Int8 */,     "int_value": 22,                    "metadata":{"description":"[R]Temperature sensor in mcu, value in Celsius"} },


    { "name": "ref/settings",
      "dataType": 19, /* Template */
      "template_value":{ "version": "settings",
                         "is_definition": true,
                         "metrics":[
                            { "name": "baudrate",      "dataType": 7/* UInt32*/,    "metadata":{"description":"[RWP]Baudrate"} },
                            { "name": "databits",      "dataType": 7/* UInt32*/,    "metadata":{"description":"[RWP]Databits, specified values = [7,8,9]"} },
                            { "name": "stopbits",      "dataType": 9/* Float */,    "metadata":{"description":"[RWP]Stopbits, specified values = [1,1.5,2]"} },                      
                            { "name": "parity",        "dataType": 12/* String */,  "metadata":{"description":"[RWP]Parity, list of values = ['none','even','odd']"} },                
                            { "name": "timeout",       "dataType": 7/* UInt32*/,    "metadata":{"description":"[RWP]Timeout, wait time after last byte received before send to metric, value in ms"} },                         
                            { "name": "terminator",    "dataType": 11/* Boolean */, "metadata":{"description":"[RWP]Bus terminator control"} }, 
                        ] }, 
      "metadata":{"description":"Template definition of interface settings"} },

    { "name": "ref/data/raw",
      "dataType": 19, /* Template */
      "template_value":{ "version": "data",
                         "is_definition": true,
                         "metrics":[
                            { "name": "in",                   "dataType": 17/* Bytes */,   "metadata":{"description":"[R]Received message in base64 format. Max frame 1024"} },       
                            { "name": "out",                  "dataType": 17/* Bytes */,   "metadata":{"description":"[W]Send message in base64 format. Max frame 1024"} },  
                        ] }, 
      "metadata":{"description":"Template definition of interface data in raw mode"} },



    { "name": "ref/dmx512/control/simple",
      "dataType": 19, /* Template */
      "template_value":{ "version": "control",
                         "is_definition": true,
                         "metrics":[
                            { "name": "value",                "dataType": 5/* UInt8 */,  "metadata":{"description":"[W]Simple 8-bit value"} },  
                        ] }, 
      "metadata":{"description":"Template definition of simple control"} },

    { "name": "ref/dmx512/control/rgbw",
      "dataType": 19, /* Template */
      "template_value":{ "version": "control",
                         "is_definition": true,
                         "metrics":[
                            { "name": "red",                  "dataType": 5/* UInt8 */,  "metadata":{"description":"[W]Red value"} }, 
                            { "name": "green",                "dataType": 5/* UInt8 */,  "metadata":{"description":"[W]Green value"} },  
                            { "name": "blue",                 "dataType": 5/* UInt8 */,  "metadata":{"description":"[W]Blue value"} },  
                            { "name": "white",                "dataType": 5/* UInt8 */,  "metadata":{"description":"[W]White value"} },   
                        ] }, 
      "metadata":{"description":"Template definition of rgbw control"} },      


    { "name": "ref/dmx512/fixture",
      "dataType": 19, /* Template */
      "template_value":{ "version": "fixture",
                         "is_definition": true,
                         "metrics":[
                            { "name": "uid",                    "dataType": 12/* String */,  "metadata":{"description":"[R]Unique device id, format mmmm:dddddddd"} },  
                            { "name": "manufacturer",           "dataType": 12/* String */,  "metadata":{"description":"[R]Manufacturer name"} }, 
                            { "name": "model",                  "dataType": 12/* String */,  "metadata":{"description":"[R]Device model"} },                              
                            { "name": "category",               "dataType": 12/* String */,  "metadata":{"description":"[R]Device category"} },  
                            
                            { "name": "footprint",              "dataType": 6/* UInt16 */,   "metadata":{"description":"[R]Number of consecutive occupied addresses"} },  

                            { "name": "identify",               "dataType": 11/* Boolean */, "metadata":{"description":"[W]Identify device"} }, 

                            { "name": "control",                "dataType": 19/* Template */,"metadata":{"description":"[RW]Control values"} },
                        ] }, 
      "metadata":{"description":"Template definition of interface data in raw mode"} },


    { "name": "ref/data/dmx512",
      "dataType": 19, /* Template */
      "template_value":{ "version": "data",
                         "is_definition": true,
                         "metrics":[
                            { "name": "universe",               "dataType": 17/* Bytes */,   "metadata":{"description":"[W]Send message in base64 format. Max frame 512"} },  
                            { "name": "scan",                   "dataType": 11/* Boolean */, "metadata":{"description":"[W]Scan and addressing all fixtures"} },  

                            { "name": "fixture/0",              "dataType": 19/* Template */,"metadata":{"description":"[RW]Fixture with start address 0"} },  
                            { "name": "fixture/1",              "dataType": 19/* Template */,"metadata":{"description":"[RW]Fixture with start address 1"} },
                            { "name": "fixture/2",              "dataType": 19/* Template */,"metadata":{"description":"[RW]Fixture with start address 2"} },

                            { "name": "fixture/512",              "dataType": 19/* Template */,"metadata":{"description":"[RW]Fixture with start address 512"} },
                        ] }, 
      "metadata":{"description":"Template definition of interface data in raw mode"} },


    { "name": "RS485/0/settings",
      "dataType": 19, /* Template */
      "template_value":{ "version": "settings",
                         "is_definition": false,
                         "template_ref": "ref/settings",
                         "metrics":[
                            { "name": "baudrate",      "dataType": 7/* UInt32*/,    "int_value": 9600,                  "metadata":{"description":"[RWP]Baudrate, specified values = [1200,2400,4800,9600,14400,19200,28800,38400,57600,115200,230400,250000,460800,921600]"} },
                            { "name": "databits",      "dataType": 7/* UInt32*/,    "int_value": 8,                     "metadata":{"description":"[RWP]Databits, specified values = [7,8,9]"} },
                            { "name": "stopbits",      "dataType": 9/* Float */,    "float_value": 1,                   "metadata":{"description":"[RWP]Stopbits, specified values = [1,1.5,2]"} },                      
                            { "name": "parity",        "dataType": 12/* String */,  "string_value": "none",             "metadata":{"description":"[RWP]Parity, list of values = ['none','even','odd']"} },                
                            { "name": "timeout",       "dataType": 7/* UInt32*/,    "int_value": 0,                     "metadata":{"description":"[RWP]Timeout, wait time after last byte received before send to metric, value in ms"} },                         
                            { "name": "terminator",    "dataType": 11/* Boolean */, "boolean_value": true,              "metadata":{"description":"[RWP]Bus terminator control"} }, 
                        ] }, 
      "metadata":{"description":"RS485 channel 0 settings"} },

    { "name": "RS485/0/data",
      "dataType": 19, /* Template */
      "template_value":{ "version": "data",
                         "is_definition": false,
                         "template_ref": "ref/data/raw",
                         "metrics":[
                            { "name": "in",                     "dataType": 17/* Bytes */,   "bytes_value": "",                  "metadata":{"description":"[R]Received message in base64 format. Max frame 1024"} },       
                            { "name": "out",                    "dataType": 17/* Bytes */,   "bytes_value": "",                  "metadata":{"description":"[W]Send message in base64 format. Max frame 1024"} },  
                        ] }, 
      "metadata":{"description":"RS485 channel 0 data"} },


    { "name": "RS485/1/settings",
      "dataType": 19, /* Template */
      "template_value":{ "version": "settings",
                         "is_definition": false,
                         "template_ref": "ref/settings",
                         "metrics":[
                            { "name": "baudrate",      "dataType": 7/* UInt32*/,    "int_value": 250000,                "metadata":{"description":"[RWP]Baudrate, specified values = [1200,2400,4800,9600,14400,19200,28800,38400,57600,115200,230400,250000,460800,921600]"} },
                            { "name": "databits",      "dataType": 7/* UInt32*/,    "int_value": 8,                     "metadata":{"description":"[RWP]Databits, specified values = [7,8,9]"} },
                            { "name": "stopbits",      "dataType": 9/* Float */,    "float_value": 1,                   "metadata":{"description":"[RWP]Stopbits, specified values = [1,1.5,2]"} },                      
                            { "name": "parity",        "dataType": 12/* String */,  "string_value": "none",             "metadata":{"description":"[RWP]Parity, list of values = ['none','even','odd']"} },                
                            { "name": "timeout",       "dataType": 7/* UInt32*/,    "int_value": 0,                     "metadata":{"description":"[RWP]Timeout, wait time after last byte received before send to metric, value in ms"} },                         
                            { "name": "terminator",    "dataType": 11/* Boolean */, "boolean_value": true,              "metadata":{"description":"[RWP]Bus terminator control"} }, 
                        ] }, 
      "metadata":{"description":"RS485 channel 1 settings"} },

    { "name": "RS485/1/data",
      "dataType": 19, /* Template */
      "template_value":{ "version": "data",
                         "is_definition": false,
                         "template_ref": "ref/data/dmx512",
                         "metrics":[
                            { "name": "universe",               "dataType": 17/* Bytes */,   "bytes_value": "",      "metadata":{"description":"[W]Send message in base64 format. Max frame 512"} },  
                            { "name": "scan",                   "dataType": 11/* Boolean */, "boolean_value": false, "metadata":{"description":"[W]Scan and addressing all fixtures"} },  

                            { "name": "fixture/0",              
                              "dataType": 19/* Template */,
                              "template_value":{  "version": "fixture",
                                                  "is_definition": false,
                                                  "template_ref": "ref/dmx512/fixture",
                                                  "metrics":[
                                                      { "name": "uid",             "dataType": 12/* String */, "string_value": "abcd:01234567" , "metadata":{"description":"[R]Unique device id, format mmmm:dddddddd"} },  
                                                      { "name": "manufacturer",    "dataType": 12/* String */, "string_value": "Manufacturer",   "metadata":{"description":"[R]Manufacturer name"} }, 
                                                      { "name": "model",           "dataType": 12/* String */, "string_value": "Model",          "metadata":{"description":"[R]Device model"} },                              
                                                      { "name": "category",        "dataType": 12/* String */, "string_value": "Simple",         "metadata":{"description":"[R]Device category"} },  
                                                      
                                                      { "name": "footprint",       "dataType": 6/* UInt16 */,  "int_value": 1,  "metadata":{"description":"[R]Number of consecutive occupied addresses"} },  

                                                      { "name": "identify",        "dataType": 11/* Boolean */,"boolean_value": false, "metadata":{"description":"[W]Identify device"} }, 

                                                      { "name": "control",         
                                                        "dataType": 19/* Template */,
                                                        "template_value":{ "version": "control",
                                                                           "is_definition": false,
                                                                           "template_ref": "ref/dmx512/control/simple",
                                                                           "metrics":[
                                                                               { "name": "value",  "dataType": 5/* UInt8 */, "int_value": 0,  "metadata":{"description":"[W]Simple 8-bit value"} },  
                                                                        ] }, 
                                                        "metadata":{"description":"[RW]Control values"} },
                                                  ] }, 
                              "metadata":{"description":"[RW]Fixture with start address 0"} },  

                            { "name": "fixture/1",              
                              "dataType": 19/* Template */,
                              "template_value":{  "version": "fixture",
                                                  "is_definition": false,
                                                  "template_ref": "ref/dmx512/fixture",
                                                  "metrics":[
                                                      { "name": "uid",             "dataType": 12/* String */, "string_value": "abcd:01234567" , "metadata":{"description":"[R]Unique device id, format mmmm:dddddddd"} },  
                                                      { "name": "manufacturer",    "dataType": 12/* String */, "string_value": "Manufacturer",   "metadata":{"description":"[R]Manufacturer name"} }, 
                                                      { "name": "model",           "dataType": 12/* String */, "string_value": "Model",          "metadata":{"description":"[R]Device model"} },                              
                                                      { "name": "category",        "dataType": 12/* String */, "string_value": "RGBW",           "metadata":{"description":"[R]Device category"} },  
                                                       
                                                      { "name": "footprint",       "dataType": 6/* UInt16 */,  "int_value": 4,  "metadata":{"description":"[R]Number of consecutive occupied addresses"} },  

                                                      { "name": "identify",        "dataType": 11/* Boolean */,"boolean_value": false, "metadata":{"description":"[W]Identify device"} }, 

                                                      { "name": "control",         
                                                        "dataType": 19/* Template */,
                                                        "template_value":{ "version": "control",
                                                                           "is_definition": false,
                                                                           "template_ref": "ref/dmx512/control/rgbw",
                                                                           "metrics":[
                                                                                { "name": "red",    "dataType": 5/* UInt8 */,  "metadata":{"description":"[W]Red value"} }, 
                                                                                { "name": "green",  "dataType": 5/* UInt8 */,  "metadata":{"description":"[W]Green value"} },  
                                                                                { "name": "blue",   "dataType": 5/* UInt8 */,  "metadata":{"description":"[W]Blue value"} },  
                                                                                { "name": "white",  "dataType": 5/* UInt8 */,  "metadata":{"description":"[W]White value"} },   
                                                                        ] }, 
                                                        "metadata":{"description":"[RW]Control values"} },
                                                  ] }, 
                              "metadata":{"description":"[RW]Fixture with start address 1"} },  
                        ] }, 
      "metadata":{"description":"RS485 channel 1 data"} },


    { "name": "RS232/settings",
      "dataType": 19, /* Template */
      "template_value":{ "version": "settings",
                         "is_definition": false,
                         "metrics":[
                            { "name": "baudrate",      "dataType": 7/* UInt32*/,    "int_value": 9600,                  "metadata":{"description":"[RWP]Baudrate, specified values = [1200,2400,4800,9600,14400,19200,28800,38400,57600,115200,230400,250000,460800,921600]"} },
                            { "name": "databits",      "dataType": 7/* UInt32*/,    "int_value": 8,                     "metadata":{"description":"[RWP]Databits, specified values = [7,8,9]"} },
                            { "name": "stopbits",      "dataType": 9/* Float */,    "float_value": 1,                   "metadata":{"description":"[RWP]Stopbits, specified values = [1,1.5,2]"} },                      
                            { "name": "parity",        "dataType": 12/* String */,  "string_value": "none",             "metadata":{"description":"[RWP]Parity, list of values = ['none','even','odd']"} },                
                            { "name": "timeout",       "dataType": 7/* UInt32*/,    "int_value": 0,                     "metadata":{"description":"[RWP]Timeout, wait time after last byte received before send to metric, value in ms"} },
                        ] }, 
      "metadata":{"description":"RS232 settings"} },


    { "name": "RS232/data",
      "dataType": 19, /* Template */
      "template_value":{ "version": "data",
                         "is_definition": false,
                         "template_ref": "ref/data/raw",
                         "metrics":[
                            { "name": "in",                     "dataType": 17/* Bytes */,   "bytes_value": "",                  "metadata":{"description":"[R]Received message in base64 format. Max frame 1024"} },       
                            { "name": "out",                    "dataType": 17/* Bytes */,   "bytes_value": "",                  "metadata":{"description":"[W]Send message in base64 format. Max frame 1024"} },  
                        ] }, 
      "metadata":{"description":"RS232 data"} },
                 
    { "name": "CAN/settings",
      "dataType": 19, /* Template */
      "template_value":{ "version": "settings",
                         "is_definition": false,
                         "template_ref": "ref/settings",
                         "metrics":[
                            { "name": "CAN/settings/baudrate",          "dataType": 7/* UInt32*/,    "int_value": 500,                   "metadata":{"description":"[RWP]Baudrate, specified values = [50, 100, 125, 250, 500, 1000] kbps"} },
                            { "name": "CAN/settings/terminator",        "dataType": 11/* Boolean */, "boolean_value": true,              "metadata":{"description":"[RWP]Bus terminator control"} },    
                        ] }, 
      "metadata":{"description":"CAN settings"} },

    { "name": "CAN/in/identifier",             "dataType": 7/* UInt32*/,    "int_value": 8,                     "metadata":{"description":"[R]Received identifier of the data frame"} },  
    { "name": "CAN/in/identifier/extended",    "dataType": 11/* Boolean */, "boolean_value": true,              "metadata":{"description":"[R]Received identifier format, 'true' - 29-bit format, 'false' - 11-bit format"} },  
    { "name": "CAN/in/rtr",                     "dataType": 11/* Boolean */, "boolean_value": true,              "metadata":{"description":"[R]Received remote transmission request, define the frame type"} },                     
    { "name": "CAN/in",                         "dataType": 17/* Bytes */,   "bytes_value": "",                  "metadata":{"description":"[R]Received data in base64 format"} },

    { "name": "CAN/out/identifier",            "dataType": 7/* UInt32*/,    "int_value": 8,                     "metadata":{"description":"[RW]Set identifier of the data frame"} },  
    { "name": "CAN/out/identifier/extended",   "dataType": 11/* Boolean */, "boolean_value": true,              "metadata":{"description":"[RW]Set identifier format, 'true' - 29-bit format, 'false' - 11-bit format"} },  
    { "name": "CAN/out/rtr",                    "dataType": 11/* Boolean */, "boolean_value": true,              "metadata":{"description":"[RW]Set remote transmission request, define the frame type"} },                 
    { "name": "CAN/out",                        "dataType": 17/* Bytes */,   "bytes_value": "",                  "metadata":{"description":"[W]Send message in base64 format"} }
  ]
}

```

## BOX device interface death example
> spBv1.0/box/DDEATH/abba2020/deba0005 

```json
{
"timestamp": 1486144502122,
"metrics": [  
    { "name": "bdSeq",                          "dataType": 8/* Uint64 */,   "long_value": 0,                    "metadata":{"description":"[R]Birth-death sequence, 'online' - [DBIRTH > DDEATH], 'offline' - [DBIRTH <= DDEATH]  "} }  
]
}
```
