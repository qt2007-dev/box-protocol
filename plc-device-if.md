## PLC device interface birth example
> spBv1.0/plc/DBIRTH/abba2020/deba0004 

```json
{
  "timestamp": 1486144502122,
  "seq": 0,
  "metrics": [
      { "name": "control/reboot",
        "timestamp": 1486144502122,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
      
      { "name": "control/rebirth",
        "timestamp": 1486144502122,
        "dataType": 11, /* Boolean */
        "boolean_value": false},

      { "name": "control/firmware/new",
        "timestamp": 1486144502122,
        "dataType": 17, /* Bytes" */
        "bytes_value": "Base64 formatted firmware"},     

      { "name": "control/metrics/save",
        "timestamp": 1486144502122,
        "dataType": 11, /* Boolean */
        "boolean_value": true /* save metrics values after reboot */},

      { "name": "control/alias",
        "timestamp": 1479123452194,
        "dataType": 12, /* String */
        "string_value": "Interfaces"},              

      { "name": "info/hardware/vendor",
        "timestamp": 1479123452194,
        "dataType": 12, /* String */
        "string_value": "QuintTech"},
        
      { "name": "info/hardware/model",
        "timestamp": 1479123452194,
        "dataType": 12, /* String */
        "string_value": "hardware model"},
        
      { "name": "info/firmware/version",
        "timestamp": 1479123452194,
        "dataType": 12, /* String */
        "string_value": "0.1.012345678"},
      
      { "name": "info/type",
        "timestamp": 1479123452194,
        "dataType": 12, /* String */
        "string_value": "Interfaces"},

      { "name": "info/id",
        "timestamp": 1479123452194,
        "dataType": 12, /* String */
        "string_value": "deba0004"},     

      { "name": "info/error",
        "timestamp": 1479123452194,
        "dataType": 12, /* String */
        "is_null": true},    
        
      { "name": "RS485/1/settings/baudrate",        
        "timestamp": 1479123452194,
        "dataType": 7,  /* UInt32*/
        "int_value": 115200  /* values = 1200,2400,4800,9600,14400,19200,28800,38400,57600,115200,230400,460800,921600 */ },
        
      { "name": "RS485/1/settings/databits",       
        "timestamp": 1479123452194,
        "dataType": 7,  /* UInt32*/
        "int_value": 8  /* values = 7,8,9 */},
        
      { "name": "RS485/1/settings/stopbits", 
        "timestamp": 1479123452194,
        "dataType": 9,  /* Float */
        "float_value": 1 /* values = 1,1.5,2 */},
      
      { "name": "RS485/1/settings/parity",
        "timestamp": 1479123452194,
        "dataType": 12, /* String */
        "string_value": "none" /* values = "none","even","odd" */},
      
      { "name": "RS485/1/settings/timeout",
        "timestamp": 1479123452194,
        "dataType": 7,  /* UInt32*/
        "int_value": 0 /* value in ms, wait time after last byte received */},
        
      { "name": "RS485/1/settings/terminator",
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": true /* enable/disable terminator on bus */},
        
      { "name": "RS485/1/in",
        "timestamp": 1479123452194,
        "dataType": 17, /* Bytes" */
        "bytes_value": "Base64 formatted string"},
        
      { "name": "RS485/1/out", 
        "timestamp": 1479123452194,
        "dataType": 17, /* Bytes */
        "bytes_value": "Base64 formatted string"},

      { "name": "RS485/2/settings/baudrate",        
        "timestamp": 1479123452194,
        "dataType": 7,  /* UInt32*/
        "int_value": 115200  /* values = 1200,2400,4800,9600,14400,19200,28800,38400,57600,115200,230400,460800,921600 */ },
        
      { "name": "RS485/2/settings/databits",       
        "timestamp": 1479123452194,
        "dataType": 7,  /* UInt32*/
        "int_value": 8  /* values = 7,8,9 */},
        
      { "name": "RS485/2/settings/stopbits", 
        "timestamp": 1479123452194,
        "dataType": 9,  /* Float */
        "float_value": 1 /* values = 1,1.5,2 */},
      
      { "name": "RS485/2/settings/parity",
        "timestamp": 1479123452194,
        "dataType": 12, /* String */
        "string_value": "none" /* values = "none","even","odd" */},
      
      { "name": "RS485/2/settings/timeout",
        "timestamp": 1479123452194,
        "dataType": 7,  /* UInt32*/
        "int_value": 0 /* value in ms, wait time after last byte received */},
        
      { "name": "RS485/2/settings/terminator",
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": true /* enable/disable terminator on bus */},
        
      { "name": "RS485/2/in",
        "timestamp": 1479123452194,
        "dataType": 17, /* Bytes" */
        "bytes_value": "Base64 formatted string"},
        
      { "name": "RS485/2/out", 
        "timestamp": 1479123452194,
        "dataType": 17, /* Bytes */
        "bytes_value": "Base64 formatted string"},
        
      { "name": "RS232/settings/baudrate",        
        "timestamp": 1479123452194,
        "dataType": 7,  /* UInt32*/
        "int_value": 115200  /* values = 1200,2400,4800,9600,14400,19200,28800,38400,57600,115200,230400,460800,921600 */ },
        
      { "name": "RS232/settings/databits",       
        "timestamp": 1479123452194,
        "dataType": 7,  /* UInt32*/
        "int_value": 8  /* values = 7,8,9 */},
        
      { "name": "RS232/settings/stopbits", 
        "timestamp": 1479123452194,
        "dataType": 9,  /* Float */
        "float_value": 1 /* values = 1,1.5,2 */},
      
      { "name": "RS232/settings/parity",
        "timestamp": 1479123452194,
        "dataType": 12, /* String */
        "string_value": "none" /* values = "none","even","odd" */},
      
      { "name": "RS232/settings/timeout",
        "timestamp": 1479123452194,
        "dataType": 7,  /* UInt32*/
        "int_value": 0 /* value in ms, wait time after last byte received */},
        
      { "name": "RS232/in",
        "timestamp": 1479123452194,
        "dataType": 17, /* Bytes" */
        "bytes_value": "Base64 formatted string"},
        
      { "name": "RS232/out", 
        "timestamp": 1479123452194,
        "dataType": 17, /* Bytes */
        "bytes_value": "Base64 formatted string"}                
         ]
}
```