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

    { "name": "RS485/0/settings/baudrate",      "dataType": 7/* UInt32*/,    "int_value": 9600,                  "metadata":{"description":"[RWP]RS485 baudrate, specified values = [1200,2400,4800,9600,14400,19200,28800,38400,57600,115200,230400,460800,921600]"} },
    { "name": "RS485/0/settings/databits",      "dataType": 7/* UInt32*/,    "int_value": 8,                     "metadata":{"description":"[RWP]RS485 databits, specified values = [7,8,9]"} },
    { "name": "RS485/0/settings/stopbits",      "dataType": 9/* Float */,    "float_value": 1,                   "metadata":{"description":"[RWP]RS485 stopbits, specified values = [1,1.5,2]"} },                      
    { "name": "RS485/0/settings/parity",        "dataType": 12/* String */,  "string_value": "none",             "metadata":{"description":"[RWP]RS485 parity, list of values = ['none','even','odd']"} },                
    { "name": "RS485/0/settings/timeout",       "dataType": 7/* UInt32*/,    "int_value": 0,                     "metadata":{"description":"[RWP]RS485 timeout, wait time after last byte received before send to metric, value in ms"} },                         
    { "name": "RS485/0/settings/terminator",    "dataType": 11/* Boolean */, "boolean_value": true,              "metadata":{"description":"[RWP]RS485 bus terminator control"} }, 
    { "name": "RS485/0/settings/mode",          "dataType": 12/* String */,  "string_value": "raw",              "metadata":{"description":"[RWP]RS485 mode, list of values = ['raw', 'modbus', 'osdp', 'dmx512']"} }, 
    { "name": "RS485/0/in",                     "dataType": 17/* Bytes */,   "bytes_value": "",                  "metadata":{"description":"[R]Received message from RS485, in base64 format"} },       
    { "name": "RS485/0/out",                    "dataType": 17/* Bytes */,   "bytes_value": "",                  "metadata":{"description":"[W]Send message to RS485, in base64 format"} },        
    
    { "name": "RS485/1/settings/baudrate",      "dataType": 7/* UInt32*/,    "int_value": 9600,                  "metadata":{"description":"[RWP]RS485 baudrate, specified values = [1200,2400,4800,9600,14400,19200,28800,38400,57600,115200,230400,460800,921600]"} },
    { "name": "RS485/1/settings/databits",      "dataType": 7/* UInt32*/,    "int_value": 8,                     "metadata":{"description":"[RWP]RS485 databits, specified values = [7,8,9]"} },
    { "name": "RS485/1/settings/stopbits",      "dataType": 9/* Float */,    "float_value": 1,                   "metadata":{"description":"[RWP]RS485 stopbits, specified values = [1,1.5,2]"} },                      
    { "name": "RS485/1/settings/parity",        "dataType": 12/* String */,  "string_value": "none",             "metadata":{"description":"[RWP]RS485 parity, list of values = ['none','even','odd']"} },                
    { "name": "RS485/1/settings/timeout",       "dataType": 7/* UInt32*/,    "int_value": 0,                     "metadata":{"description":"[RWP]RS485 timeout, wait time after last byte received before send to metric, value in ms"} },                         
    { "name": "RS485/1/settings/terminator",    "dataType": 11/* Boolean */, "boolean_value": true,              "metadata":{"description":"[RWP]RS485 bus terminator control"} },
    { "name": "RS485/1/settings/mode",          "dataType": 12/* String */,  "string_value": "raw",              "metadata":{"description":"[RWP]RS485 mode, list of values = ['raw', 'modbus', 'osdp', 'dmx512']"} },                 
    { "name": "RS485/1/in",                     "dataType": 17/* Bytes */,   "bytes_value": "",                  "metadata":{"description":"[R]Received message from RS485, in base64 format"} },       
    { "name": "RS485/1/out",                    "dataType": 17/* Bytes */,   "bytes_value": "",                  "metadata":{"description":"[W]Send message to RS485, in base64 format"} },  

    { "name": "RS232/settings/baudrate",        "dataType": 7/* UInt32*/,    "int_value": 9600,                  "metadata":{"description":"[RWP]RS232 baudrate, specified values = [1200,2400,4800,9600,14400,19200,28800,38400,57600,115200,230400,460800,921600]"} },
    { "name": "RS232/settings/databits",        "dataType": 7/* UInt32*/,    "int_value": 8,                     "metadata":{"description":"[RWP]RS232 databits, specified values = [7,8,9]"} },
    { "name": "RS232/settings/stopbits",        "dataType": 9/* Float */,    "float_value": 1,                   "metadata":{"description":"[RWP]RS232 stopbits, specified values = [1,1.5,2]"} },                         
    { "name": "RS232/settings/parity",          "dataType": 12/* String */,  "string_value": "none",             "metadata":{"description":"[RWP]RS232 parity, list of values = ['none','even','odd']"} },                
    { "name": "RS232/settings/timeout",         "dataType": 7/* UInt32*/,    "int_value": 0,                     "metadata":{"description":"[RWP]RS232 timeout, wait time after last byte received before send to metric, value in ms"} },                        
    { "name": "RS232/in",                       "dataType": 17/* Bytes */,   "bytes_value": "",                  "metadata":{"description":"[R]Received message from RS232, in base64 format"} },
    { "name": "RS232/out",                      "dataType": 17/* Bytes */,   "bytes_value": "",                  "metadata":{"description":"[W]Send message to RS232, in base64 format"} },  

    { "name": "CAN/settings/baudrate",          "dataType": 7/* UInt32*/,    "int_value": 500,                   "metadata":{"description":"[RWP]CAN baudrate, specified values = [50, 100, 125, 250, 500, 1000] kbps"} },
    { "name": "CAN/settings/terminator",        "dataType": 11/* Boolean */, "boolean_value": true,              "metadata":{"description":"[RWP]CAN bus terminator control"} },    
    { "name": "CAN/in/identifier",             "dataType": 7/* UInt32*/,    "int_value": 8,                     "metadata":{"description":"[R]Received identifier of the data frame"} },  
    { "name": "CAN/in/identifier/extended",    "dataType": 11/* Boolean */, "boolean_value": true,              "metadata":{"description":"[R]Received identifier format, 'true' - 29-bit format, 'false' - 11-bit format"} },  
    { "name": "CAN/in/rtr",                     "dataType": 11/* Boolean */, "boolean_value": true,              "metadata":{"description":"[R]Received remote transmission request, define the frame type"} },                     
    { "name": "CAN/in",                         "dataType": 17/* Bytes */,   "bytes_value": "",                  "metadata":{"description":"[R]Received data from CAN, in base64 format"} },
    { "name": "CAN/out/identifier",            "dataType": 7/* UInt32*/,    "int_value": 8,                     "metadata":{"description":"[RW]Set identifier of the data frame"} },  
    { "name": "CAN/out/identifier/extended",   "dataType": 11/* Boolean */, "boolean_value": true,              "metadata":{"description":"[RW]Set identifier format, 'true' - 29-bit format, 'false' - 11-bit format"} },  
    { "name": "CAN/out/rtr",                    "dataType": 11/* Boolean */, "boolean_value": true,              "metadata":{"description":"[RW]Set remote transmission request, define the frame type"} },                 
    { "name": "CAN/out",                        "dataType": 17/* Bytes */,   "bytes_value": "",                  "metadata":{"description":"[W]Send message to CAN, in base64 format"} }
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
