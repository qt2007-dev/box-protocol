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

    { "name": "ref/dmx/slot",
      "dataType": 19, /* Template */
      "template_value":{ "version": "slot",
                         "is_definition": true,
                         "metrics":[
                            { "name": "value",            "dataType": 5/* UInt8 */,    "metadata":{"description":"[RW]Simple 8-bit value"} }, 
                            { "name": "description",      "dataType": 12/* String */,  "metadata":{"description":"[R]Slot description"} }, 
                        ] }, 
      "metadata":{"description":"Template definition of slot"} },

    { "name": "ref/dmx/control",
      "dataType": 19, /* Template */
      "template_value":{ "version": "control",
                         "is_definition": true,
                         "metrics":[
                            { "name": "0",                "dataType": 19, /* Template */  "metadata":{"description":"[RW]Slot 0 control"} },
                            { "name": "1",                "dataType": 19, /* Template */  "metadata":{"description":"[RW]Slot 1 control"} },
                            { "name": "2",                "dataType": 19, /* Template */  "metadata":{"description":"[RW]Slot 2 control"} }, 
                            { "name": "3",                "dataType": 19, /* Template */  "metadata":{"description":"[RW]Slot 3 control"} }, 
                            { "name": "4",                "dataType": 19, /* Template */  "metadata":{"description":"[RW]Slot 4 control"} }, 
                            { "name": "5",                "dataType": 19, /* Template */  "metadata":{"description":"[RW]Slot 5 control"} }, 
                            { "name": "6",                "dataType": 19, /* Template */  "metadata":{"description":"[RW]Slot 6 control"} }, 
                            { "name": "7",                "dataType": 19, /* Template */  "metadata":{"description":"[RW]Slot 7 control"} },  
                        ] }, 
      "metadata":{"description":"Template definition of control"} },      


    { "name": "RS485/0/settings/mode",          "dataType": 12/* String */,  "string_value": "raw",              "metadata":{"description":"[RWP]Mode, list of values = ['raw', 'dmx']"} }, 
    { "name": "RS485/0/settings/baudrate",      "dataType": 7/* UInt32*/,    "int_value": 9600,                  "metadata":{"description":"[RWP]Baudrate, specified values = [1200,2400,4800,9600,14400,19200,28800,38400,57600,115200,230400,460800,921600]"} },
    { "name": "RS485/0/settings/databits",      "dataType": 7/* UInt32*/,    "int_value": 8,                     "metadata":{"description":"[RWP]Databits, specified values = [7,8,9]"} },
    { "name": "RS485/0/settings/stopbits",      "dataType": 9/* Float */,    "float_value": 1,                   "metadata":{"description":"[RWP]Stopbits, specified values = [1,1.5,2]"} },                      
    { "name": "RS485/0/settings/parity",        "dataType": 12/* String */,  "string_value": "none",             "metadata":{"description":"[RWP]Parity, list of values = ['none','even','odd']"} },                
    { "name": "RS485/0/settings/timeout",       "dataType": 7/* UInt32*/,    "int_value": 0,                     "metadata":{"description":"[RWP]Timeout, wait time after last byte received before send to metric, value in ms"} },                         
    { "name": "RS485/0/settings/terminator",    "dataType": 11/* Boolean */, "boolean_value": true,              "metadata":{"description":"[RWP]Bus terminator control"} }, 

    { "name": "RS485/0/raw/in",                     "dataType": 17/* Bytes */,   "bytes_value": "",                  "metadata":{"description":"[R]Received message in base64 format. Max frame 1024"} },       
    { "name": "RS485/0/raw/out",                    "dataType": 17/* Bytes */,   "bytes_value": "",                  "metadata":{"description":"[W]Send message in base64 format. Max frame 1024"} },    


    { "name": "RS485/1/settings/mode",          "dataType": 12/* String */,  "string_value": "dmx",              "metadata":{"description":"[RWP]Mode, list of values = ['raw', 'dmx']"} },                        
    { "name": "RS485/1/settings/terminator",    "dataType": 11/* Boolean */, "boolean_value": true,              "metadata":{"description":"[RWP]Bus terminator control"} }, 

    { "name": "RS485/1/dmx/universe",                 "dataType": 17/* Bytes */,   "bytes_value": "",      "metadata":{"description":"[W]Send message in base64 format. Max frame 512"} },  
    { "name": "RS485/1/dmx/scan",                     "dataType": 12/* String */,  "string_value": "",     "metadata":{"description":"[W]Scan fixtures, values=['all', 'new', 'update']"} },  

    { "name": "RS485/1/dmx/fixture/beef00000001/manufacturer",    "dataType": 12/* String */, "string_value": "Manufacturer",   "metadata":{"description":"[R]Manufacturer name"} }, 
    { "name": "RS485/1/dmx/fixture/beef00000001/model",           "dataType": 12/* String */, "string_value": "Model",          "metadata":{"description":"[R]Device model"} },                              
    { "name": "RS485/1/dmx/fixture/beef00000001/category",        "dataType": 12/* String */, "string_value": "Simple",         "metadata":{"description":"[R]Device category"} },  
    
    { "name": "RS485/1/dmx/fixture/beef00000001/start-address",   "dataType": 6/* UInt16 */,  "int_value": 0,  "metadata":{"description":"[RW]Number of consecutive occupied addresses"} },  
    { "name": "RS485/1/dmx/fixture/beef00000001/footprint",       "dataType": 6/* UInt16 */,  "int_value": 1,  "metadata":{"description":"[R]Number of consecutive occupied addresses"} },  

    { "name": "RS485/1/dmx/fixture/beef00000001/identify",        "dataType": 11/* Boolean */,"boolean_value": false, "metadata":{"description":"[W]Identify device"} },
    { "name": "RS485/1/dmx/fixture/beef00000001/control",         
      "dataType": 19/* Template */,
      "template_value":{  "version": "control",
                          "is_definition": false,
                          "template_ref": "ref/dmx512/control",
                          "metrics":[
                            { "name": "0",  
                              "dataType": 19, /* Template */  
                              "template_value":{  "version": "slot",
                                                  "is_definition": false,
                                                  "template_ref": "ref/dmx512/slot",  
                                                  "metrics":[
                                                    { "name": "value",            "dataType": 5/* UInt8 */,   "int_value": 0,     "metadata":{"description":"[RW]Simple 8-bit value"} }
                                                  ] },                             
                              "metadata":{"description":"[RW]Slot 0 control"} },
                      ] }, 
      "metadata":{"description":"[RW]Control values"} },

    { "name": "RS485/1/dmx/fixture/beef00000002/manufacturer",    "dataType": 12/* String */, "string_value": "Manufacturer",   "metadata":{"description":"[R]Manufacturer name"} }, 
    { "name": "RS485/1/dmx/fixture/beef00000002/model",           "dataType": 12/* String */, "string_value": "Model",          "metadata":{"description":"[R]Device model"} },                              
    { "name": "RS485/1/dmx/fixture/beef00000002/category",        "dataType": 12/* String */, "string_value": "RGBW",           "metadata":{"description":"[R]Device category"} },  
    
    { "name": "RS485/1/dmx/fixture/beef00000002/start-address",   "dataType": 6/* UInt16 */,  "int_value": 1,  "metadata":{"description":"[RW]Number of consecutive occupied addresses"} },  
    { "name": "RS485/1/dmx/fixture/beef00000002/footprint",       "dataType": 6/* UInt16 */,  "int_value": 4,  "metadata":{"description":"[R]Number of consecutive occupied addresses"} },  

    { "name": "RS485/1/dmx/fixture/beef00000002/identify",        "dataType": 11/* Boolean */,"boolean_value": false, "metadata":{"description":"[W]Identify device"} }, 
    { "name": "RS485/1/dmx/fixture/beef00000002/control",         
      "dataType": 19/* Template */,
      "template_value":{  "version": "control",
                          "is_definition": false,
                          "template_ref": "ref/dmx512/control",
                          "metrics":[
                            { "name": "0",  
                              "dataType": 19, /* Template */  
                              "template_value":{  "version": "slot",
                                                  "is_definition": false,
                                                  "template_ref": "ref/dmx512/slot",  
                                                  "metrics":[
                                                    { "name": "value",            "dataType": 5/* UInt8 */,   "int_value": 0,     "metadata":{"description":"[RW]Simple 8-bit value"} }, 
                                                    { "name": "description",      "dataType": 12/* String */, "string_value": "", "metadata":{"description":"[R]Slot description"} }, 
                                                  ] },                             
                              "metadata":{"description":"[RW]Slot 0 control"} },
                            { "name": "1",  
                              "dataType": 19, /* Template */  
                              "template_value":{  "version": "slot",
                                                  "is_definition": false,
                                                  "template_ref": "ref/dmx512/slot",  
                                                  "metrics":[
                                                    { "name": "value",            "dataType": 5/* UInt8 */,   "int_value": 0,     "metadata":{"description":"[RW]Simple 8-bit value"} }, 
                                                    { "name": "description",      "dataType": 12/* String */, "string_value": "", "metadata":{"description":"[R]Slot description"} }, 
                                                  ] },                             
                              "metadata":{"description":"[RW]Slot 1 control"} },
                            { "name": "2",  
                              "dataType": 19, /* Template */  
                              "template_value":{  "version": "slot",
                                                  "is_definition": false,
                                                  "template_ref": "ref/dmx512/slot",  
                                                  "metrics":[
                                                    { "name": "value",            "dataType": 5/* UInt8 */,   "int_value": 0,     "metadata":{"description":"[RW]Simple 8-bit value"} }, 
                                                    { "name": "description",      "dataType": 12/* String */, "string_value": "", "metadata":{"description":"[R]Slot description"} }, 
                                                  ] },                             
                              "metadata":{"description":"[RW]Slot 2 control"} },
                            { "name": "3",  
                              "dataType": 19, /* Template */  
                              "template_value":{  "version": "slot",
                                                  "is_definition": false,
                                                  "template_ref": "ref/dmx512/slot",  
                                                  "metrics":[
                                                    { "name": "value",            "dataType": 5/* UInt8 */,   "int_value": 0,     "metadata":{"description":"[RW]Simple 8-bit value"} }, 
                                                    { "name": "description",      "dataType": 12/* String */, "string_value": "", "metadata":{"description":"[R]Slot description"} }, 
                                                  ] },                             
                              "metadata":{"description":"[RW]Slot 3 control"} },      

                      ] }, 
      "metadata":{"description":"[RW]Control values"} },


    { "name": "RS232/settings/mode",            "dataType": 12/* String */,  "string_value": "raw",              "metadata":{"description":"[RWP]Mode, list of values = ['raw']"} }, 
    { "name": "RS232/settings/baudrate",        "dataType": 7/* UInt32*/,    "int_value": 9600,                  "metadata":{"description":"[RWP]Baudrate, specified values = [1200,2400,4800,9600,14400,19200,28800,38400,57600,115200,230400,460800,921600]"} },
    { "name": "RS232/settings/databits",        "dataType": 7/* UInt32*/,    "int_value": 8,                     "metadata":{"description":"[RWP]Databits, specified values = [7,8,9]"} },
    { "name": "RS232/settings/stopbits",        "dataType": 9/* Float */,    "float_value": 1,                   "metadata":{"description":"[RWP]Stopbits, specified values = [1,1.5,2]"} },                         
    { "name": "RS232/settings/parity",          "dataType": 12/* String */,  "string_value": "none",             "metadata":{"description":"[RWP]Parity, list of values = ['none','even','odd']"} },                
    { "name": "RS232/settings/timeout",         "dataType": 7/* UInt32*/,    "int_value": 0,                     "metadata":{"description":"[RWP]Timeout, wait time after last byte received before send to metric, value in ms"} },                        
    { "name": "RS232/raw/in",                   "dataType": 17/* Bytes */,   "bytes_value": "",                  "metadata":{"description":"[R]Received message in base64 format. Max frame 1024"} },
    { "name": "RS232/raw/out",                  "dataType": 17/* Bytes */,   "bytes_value": "",                  "metadata":{"description":"[W]Send message in base64 format. Max frame 1024"} },  

    { "name": "CAN/settings/mode",              "dataType": 12/* String */,  "string_value": "raw",              "metadata":{"description":"[RWP]Mode, list of values = ['raw']"} }, 
    { "name": "CAN/settings/baudrate",          "dataType": 7/* UInt32*/,    "int_value": 500,                   "metadata":{"description":"[RWP]Baudrate, specified values = [50, 100, 125, 250, 500, 1000] kbps"} },
    { "name": "CAN/settings/terminator",        "dataType": 11/* Boolean */, "boolean_value": true,              "metadata":{"description":"[RWP]Bus terminator control"} },   

    { "name": "CAN/raw/in/identifier",              "dataType": 7/* UInt32*/,    "int_value": 8,                     "metadata":{"description":"[R]Received identifier of the data frame"} },  
    { "name": "CAN/raw/in/identifier/extended",     "dataType": 11/* Boolean */, "boolean_value": true,              "metadata":{"description":"[R]Received identifier format, 'true' - 29-bit format, 'false' - 11-bit format"} },  
    { "name": "CAN/raw/in/rtr",                     "dataType": 11/* Boolean */, "boolean_value": true,              "metadata":{"description":"[R]Received remote transmission request, define the frame type"} },                     
    { "name": "CAN/raw/in",                         "dataType": 17/* Bytes */,   "bytes_value": "",                  "metadata":{"description":"[R]Received data in base64 format"} },

    { "name": "CAN/raw/out/identifier",             "dataType": 7/* UInt32*/,    "int_value": 8,                     "metadata":{"description":"[RW]Set identifier of the data frame"} },  
    { "name": "CAN/raw/out/identifier/extended",    "dataType": 11/* Boolean */, "boolean_value": true,              "metadata":{"description":"[RW]Set identifier format, 'true' - 29-bit format, 'false' - 11-bit format"} },  
    { "name": "CAN/raw/out/rtr",                    "dataType": 11/* Boolean */, "boolean_value": true,              "metadata":{"description":"[RW]Set remote transmission request, define the frame type"} },                 
    { "name": "CAN/raw/out",                        "dataType": 17/* Bytes */,   "bytes_value": "",                  "metadata":{"description":"[W]Send message in base64 format"} }
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
