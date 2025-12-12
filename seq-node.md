## BOX node birth example
> spBv1.0/box/NBIRTH/abba2020

```json
{
"timestamp": 1486144502122,
"seq": 0,
"metrics": [
    { "name": "bdSeq",                               "dataType": 8/* Uint64 */,   "long_value": 0,                      "metadata":{"description":"[R]Birth-death sequence, 'online' - [BIRTH > DEATH], 'offline' - [BIRTH <= DEATH]"} },                      
    { "name": "control/reboot",                      "dataType": 11/* Boolean */, "boolean_value": false,               "metadata":{"description":"[W]Software reboot, send 'true' for reboot"} },
    { "name": "control/rebirth",                     "dataType": 11/* Boolean */, "boolean_value": false,               "metadata":{"description":"[W]Rebirth, send 'true' for receive birth message again"} },
    { "name": "control/firmware/new",                "dataType": 17/* Bytes */,   "bytes_value":"", "is_null": true,    "metadata":{"description":"[W]Receive new firmware, firmware send in Base64 format, in birth always null"} },
    { "name": "control/metrics/save",                "dataType": 11/* Boolean */, "boolean_value": true,                "metadata":{"description":"[RWP]Save metrics states after reboot, send 'true' for enable"} },
    { "name": "control/metrics/metadata",            "dataType": 11/* Boolean */, "boolean_value": true,                "metadata":{"description":"[RWP]Show metrics metadata in birth, send 'true' for enable"} },
    { "name": "control/group",                       "dataType": 12/* String */,  "string_value": "plc",                "metadata":{"description":"[RWP]Global group, can be used instead id in topics and scenarios"} },
 
    { "name": "info/hardware/vendor",                "dataType": 12/* String */,  "string_value": "QuintTech",          "metadata":{"description":"[R]Vendor name, hardcoded by vendor"} },
    { "name": "info/hardware/model",                 "dataType": 12/* String */,  "string_value": "rpi4",               "metadata":{"description":"[R]Mcu model, hardcoded by vendor"} },
    { "name": "info/firmware/version",               "dataType": 12/* String */,  "string_value": "0.1.220527",         "metadata":{"description":"[R]Firmware version, MAJOR.MINOR.buildOrCommit"} },
    { "name": "info/type",                           "dataType": 12/* String */,  "string_value": "SEQ",                "metadata":{"description":"[R]Type, hardcoded by vendor"} },
    { "name": "info/id",                             "dataType": 12/* String */,  "string_value": "abba2020",           "metadata":{"description":"[R]Short id calculated by a hash from mcu uid"} },
    { "name": "info/error",                          "dataType": 12/* String */,  "string_value": "",                   "metadata":{"description":"[R]Last error message"} },
    { "name": "info/daytime",                        "dataType": 12/* String */,  "string_value": "day",                "metadata":{"description":"[R]Current daytime, values = ['day','night']"} },

    { "name": "sensors/temperature/mpu",             "dataType": 1 /* Int8 */,     "int_value": 22,                     "metadata":{"description":"[R]Temperature sensor in mpu, value in Celsius"} },
    { "name": "sensors/temperature/fpga",            "dataType": 1 /* Int8 */,     "int_value": 22,                     "metadata":{"description":"[R]Temperature sensor in fpga, value in Celsius"} },
    { "name": "sensors/temperature/ambient",         "dataType": 1 /* Int8 */,     "int_value": 22,                     "metadata":{"description":"[R]Temperature sensor on motherboard, value in Celsius"} },
    
    { "name": "sensors/voltage/vin",                 "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[R]System input voltage, value in mV"} },
    { "name": "sensors/voltage/vout",                "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[R]System output voltage, value in mV"} },
    { "name": "sensors/voltage/vout5v",              "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[R]System output 5V voltage, value in mV"} },
    { "name": "sensors/voltage/sys5v",               "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[R]System 5V voltage, value in mV"} },
    { "name": "sensors/voltage/sys3v3",              "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[R]System 3.3V voltage, value in mV"} },
    { "name": "sensors/voltage/sys1v8",              "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[R]System 1.8V voltage, value in mV"} },

    { "name": "sensors/current/vin12v",              "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[R]System input current, value in mA"} },
    { "name": "sensors/current/vout12v",             "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[R]System output 12V current, value in mA"} },
    { "name": "sensors/current/vout5v",              "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[R]System output 5V current, value in mA"} },
    { "name": "sensors/current/sys5v",               "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[R]System 5V current, value in mA"} },
    { "name": "sensors/current/sys3v3",              "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[R]System 3.3V current, value in mA"} },
    { "name": "sensors/current/sys1v8",              "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[R]System 1.8V current, value in mA"} },

    { "name": "sensors/fan/0/rpm",                   "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[R]System fan 0 RPM"} },
    { "name": "sensors/fan/1/rpm",                   "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[R]System fan 1 RPM"} },
    { "name": "sensors/fan/2/rpm",                   "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[R]System fan 2 RPM"} },
    { "name": "sensors/fan/3/rpm",                   "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[R]System fan 3 RPM"} },
    { "name": "sensors/fan/4/rpm",                   "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[R]System fan 4 RPM"} },


    { "name": "chip/0/type",                         "dataType": 12/* String */,   "string_value": "ION314",            "metadata":{"description":"[R]Chip type installed on board"} },

    { "name": "chip/0/frame/settings/quantity",      "dataType": 6 /* UInt16 */,   "int_value": 30,                     "metadata":{"description":"[RWP]Quantity of frames to record"} },
    { "name": "chip/0/frame/settings/delay",         "dataType": 6 /* UInt16 */,   "int_value": 0,                      "metadata":{"description":"[RWP]Delay between frames of record"} },
    { "name": "chip/0/frame/record",                 "dataType": 11/* Boolean */,  "is_null": true,                     "metadata":{"description":"[W]Start record frame"} },
    { "name": "chip/0/frame/get",                    "dataType": 11/* Boolean */,  "is_null": true,                     "metadata":{"description":"[W]Request one frame from chip"} },
    { "name": "chip/0/frame",                        "dataType": 17/* Bytes */,    "bytes_value": "",                   "metadata":{"description":"[R]Last frame in base64 format"} }, 

    { "name": "chip/0/sensors/temperature",          "dataType": 1 /* Int8 */,     "int_value": 22,                     "metadata":{"description":"[R]Chip 0 sensor in mcu, value in Celsius"} },
    
    { "name": "chip/0/sensors/voltage/vin",          "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[R]Chip 0 system input voltage, value in mV"} },
    { "name": "chip/0/sensors/voltage/n5v4in",       "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[R]Chip 0 system input voltage for negative 5.4V dcdc, value in mV"} },
    { "name": "chip/0/sensors/voltage/5v3",          "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[R]Chip 0 system 5.3V voltage, value in mV"} },
    { "name": "chip/0/sensors/voltage/3v3",          "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[R]Chip 0 system 3.3V voltage, value in mV"} },
    { "name": "chip/0/sensors/voltage/3v3a",         "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[R]Chip 0 system 5.3VA voltage, value in mV"} },
    { "name": "chip/0/sensors/voltage/3v3ca",        "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[R]Chip 0 system 5.3VCA voltage, value in mV"} },

    { "name": "chip/0/sensors/voltage/v0",           "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[R]Chip 0 system V0 voltage, value in mV"} },
    { "name": "chip/0/sensors/voltage/v1",           "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[R]Chip 0 system V1 voltage, value in mV"} },
    { "name": "chip/0/sensors/voltage/v2",           "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[R]Chip 0 system V2 voltage, value in mV"} },
    { "name": "chip/0/sensors/voltage/v3",           "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[R]Chip 0 system V3 voltage, value in mV"} },
    { "name": "chip/0/sensors/voltage/v4",           "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[R]Chip 0 system V4 voltage, value in mV"} },
    
    { "name": "chip/0/sensors/voltage/vid0",         "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[R]Chip 0 system VID0 voltage, value in mV"} },
    { "name": "chip/0/sensors/voltage/vid1",         "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[R]Chip 0 system VID1 voltage, value in mV"} },
    { "name": "chip/0/sensors/voltage/vid2",         "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[R]Chip 0 system VID2 voltage, value in mV"} },

    { "name": "chip/0/sensors/current/vin",          "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[R]Chip 0 system input current, value in mA"} },
    { "name": "chip/0/sensors/current/n5v4in",       "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[R]Chip 0 system input current for negative 5.4V dcdc, value in mA"} },
    { "name": "chip/0/sensors/current/5v3",          "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[R]Chip 0 system 5.3V current, value in mA"} },
    { "name": "chip/0/sensors/current/3v3",          "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[R]Chip 0 system 3.3V current, value in mA"} },
    { "name": "chip/0/sensors/current/3v3a",         "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[R]Chip 0 system 5.3VA current, value in mA"} },
    { "name": "chip/0/sensors/current/3v3ca",        "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[R]Chip 0 system 5.3VCA current, value in mA"} },

    { "name": "chip/0/settings/v0",                  "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[RWP]Chip 0 V0 voltage, value in mV"} },
    { "name": "chip/0/settings/v1",                  "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[RWP]Chip 0 V1 voltage, value in mV"} },
    { "name": "chip/0/settings/v2",                  "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[RWP]Chip 0 V2 voltage, value in mV"} },
    { "name": "chip/0/settings/v3",                  "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[RWP]Chip 0 V3 voltage, value in mV"} },
    { "name": "chip/0/settings/v4",                  "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[RWP]Chip 0 V4 voltage, value in mV"} },
   
    { "name": "chip/0/settings/vb0",                 "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[RWP]Chip 0 VB0 voltage, value in mV"} },
    { "name": "chip/0/settings/vb1",                 "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[RWP]Chip 0 VB1 voltage, value in mV"} },

    { "name": "chip/0/settings/vref",                "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[RWP]Chip 0 Vref voltage, value in mV"} },

    { "name": "chip/0/amplifier/0",                  "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[RWP]Chip 0 amplifier 0 offset voltage, value in mV"} },
    { "name": "chip/0/amplifier/1",                  "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[RWP]Chip 0 amplifier 1 offset voltage, value in mV"} },
    { "name": "chip/0/amplifier/2",                  "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[RWP]Chip 0 amplifier 2 offset voltage, value in mV"} },
    { "name": "chip/0/amplifier/3",                  "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[RWP]Chip 0 amplifier 3 offset voltage, value in mV"} },

    { "name": "chip/0/driver/0",                     "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[RWP]Chip 0 driver 0 offset voltage, value in mV"} },
    { "name": "chip/0/driver/1",                     "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[RWP]Chip 0 driver 1 offset voltage, value in mV"} },
    { "name": "chip/0/driver/2",                     "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[RWP]Chip 0 driver 2 offset voltage, value in mV"} },
    { "name": "chip/0/driver/3",                     "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[RWP]Chip 0 driver 3 offset voltage, value in mV"} },

    { "name": "chip/0/heater/enable",                "dataType": 11/* Boolean */,  "boolean_value": false,              "metadata":{"description":"[RW]Chip 0 heater state, send 'true' for enable"} },
    { "name": "chip/0/heater/target",                "dataType": 6 /* UInt16 */,   "int_value": 45,                     "metadata":{"description":"[RWP]Chip 0 heater target temperature, value in Celsius"} },
    { "name": "chip/0/heater/current",               "dataType": 9 /* Float */,    "float_value": 22.35,                "metadata":{"description":"[R]Chip 0 heater current temperature, value in Celsius"} },



    { "name": "RS485/0/settings/baudrate",           "dataType": 7/* UInt32*/,     "int_value": 9600,                   "metadata":{"description":"[RWP]Baudrate, specified values = [1200,2400,4800,9600,14400,19200,28800,38400,57600,115200,230400,460800,921600]"} },
    { "name": "RS485/0/settings/databits",           "dataType": 7/* UInt32*/,     "int_value": 8,                      "metadata":{"description":"[RWP]Databits, specified values = [7,8,9]"} },
    { "name": "RS485/0/settings/stopbits",           "dataType": 9/* Float */,     "float_value": 1,                    "metadata":{"description":"[RWP]Stopbits, specified values = [1,1.5,2]"} },                      
    { "name": "RS485/0/settings/parity",             "dataType": 12/* String */,   "string_value": "none",              "metadata":{"description":"[RWP]Parity, list of values = ['none','even','odd']"} },                
    { "name": "RS485/0/settings/timeout",            "dataType": 7/* UInt32*/,     "int_value": 0,                      "metadata":{"description":"[RWP]Timeout, wait time after last byte received before send to metric, value in ms"} },                         
    { "name": "RS485/0/settings/terminator",         "dataType": 11/* Boolean */,  "boolean_value": true,               "metadata":{"description":"[RWP]Bus terminator control"} }, 
    { "name": "RS485/0/settings/mode",               "dataType": 12/* String */,   "string_value": "raw",               "metadata":{"description":"[RWP]Mode, list of values = ['raw']"} }, 
    { "name": "RS485/0/in",                          "dataType": 17/* Bytes */,    "bytes_value": "",                   "metadata":{"description":"[R]Received message in base64 format. Max frame 1024"} },       
    { "name": "RS485/0/out",                         "dataType": 17/* Bytes */,    "bytes_value": "",                   "metadata":{"description":"[W]Send message in base64 format. Max frame 1024"} },        


    { "name": "timezone/auto",                       "dataType": 11/* Boolean */, "boolean_value": true,                "metadata":{"description":"[RWP]Enable/disable auto timezone from coordinates"} },         
    { "name": "timezone",                            "dataType": 12/* String */,  "string_value": "UTC+0",              "metadata":{"description":"[RWP]Current timezone"} },         

    { "name": "datetime/auto",                       "dataType": 11/* Boolean */, "boolean_value": true,                "metadata":{"description":"[RWP]Enable/disable auto date and time update from NTP"} },         
    { "name": "datetime",                            "dataType": 12/* String */,  "string_value": "2023-10-18T14:50:00","metadata":{"description":"[RW]Current date and time in ISO 8601 format"} },  
    
    { "name": "coordinates/auto",                    "dataType": 11/* Boolean */, "boolean_value": true,                "metadata":{"description":"[RWP]Enable/disable read coordinates from GNSS, WAN"} },     
    { "name": "coordinates",              
      "dataType": 16/* DataSet */, 
      "dataset_value":{ "num_of_columns": 2,
                        "columns": ["latitude", "longitude"],
                        "types": [10, 10], /* Double, Double */
                        "rows": [ {"elements":[{"double_value": 55.751244},{"double_value": 37.618423}]} ] },                                  
      "metadata":{"description":"[RWP]GNSS coordinates, values in degree"} },     

    { "name": "connection/type",                     "dataType": 12/* String */,  "string_value": "ethernet",           "metadata":{"description":"[RWP]Active connection type, list of values = ['ethernet', 'modem', 'thread']"} },
    { "name": "connection/server",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 8,
                        "columns": ["address", "port", "tls", "ca-certificate", "client-certificate", "client-key", "username", "password"],
                        "types": [12, 6, 11 , 12, 12, 12, 12, 12], /* String, UInt16, Boolean, String, String, String, String, String   */
                        "rows": [ {"elements":[{"string_value":"some.broker.com"},{"int_value":1883},{"boolean_value":true},{"string_value":"cert"},{"string_value":"cert"},{"string_value":"key"},{"string_value":"mqtt-username"},{"string_value":"mqtt-password"}]} ] }, 
      "metadata":{"description":"[RWP]mqtt broker"} },

    { "name": "schedule",                            "dataType": 12/* String */, "string_value": "on",                  "metadata":{"description":"[RWP]Schedule control metric, list of values = ['on', 'off', 'set', 'get'], schedule set and get in properties"} }, 
    { "name": "schedule/info",              
      "dataType": 16/* DataSet */, 
      "dataset_value":{ "num_of_columns": 3,
                        "columns": ["description", "version", "points"],
                        "types": [12, 7, 7], /* String, Uint32, Uint32 */
                        "rows": [ {"elements":[{"string_value":"scheduleDescription1"},{"type": 7, "int_value": 1},{"int_value": 18} ]} ] },                                  
      "metadata":{"description":"[R]Schedule info metric"} },     

    { "name": "scenario/add",                        "dataType": 12/* String */, "string_value":"", "is_null": true,    "metadata":{"description":"[W]Scenario add to list, value = scenario name, scenario sent in properties"} },
    { "name": "scenario/execute",                    "dataType": 12/* String */, "string_value":"", "is_null": true,    "metadata":{"description":"[RW]Execute scenario, value = scenario name, after execution the value is reset to null"} },
    { "name": "scenario/delete",                     "dataType": 12/* String */, "string_value":"", "is_null": true,    "metadata":{"description":"[W]Scenario delete from list. Special value '_all' delete all scenario from list"} }, 
    { "name": "scenario/get",                        "dataType": 12/* String */, "string_value":"", "is_null": true,    "metadata":{"description":"[W]Read scenario from list, scenario sent in properties"} }, 
    { "name": "scenario/enable",                     "dataType": 12/* String */, "string_value":"", "is_null": true,    "metadata":{"description":"[W]Enable scenario, enabled scenario do actions on execute"} }, 
    { "name": "scenario/disable",                    "dataType": 12/* String */, "string_value":"", "is_null": true,    "metadata":{"description":"[W]Disable scenario, disabled scenario don't do any actions on execute"} },   
    { "name": "scenario/list",              
      "dataType": 16/* DataSet */, 
      "dataset_value":{ "num_of_columns": 3,
                        "columns": ["name", "version", "enabled"],
                        "types": [12, 7, 11], /* String, Uint32, Boolean */
                        "rows": [ {"elements":[{"string_value":"scenarioName1"},{"type": 7, "int_value": 1},{"boolean_value": true} ]},
                                  {"elements":[{"string_value":"scenarioName2"},{"type": 7, "int_value": 1},{"boolean_value": false} ]}  ] },                                  
      "metadata":{"description":"[R]List of scenario names exist in node"} },                           

    { "name": "event/add",                           "dataType": 12/* String */, "string_value":"", "is_null": true,    "metadata":{"description":"[W]Event add to list, value = event name, event sent in properties"} },
    { "name": "event/delete",                        "dataType": 12/* String */, "string_value":"", "is_null": true,    "metadata":{"description":"[W]Event delete from list. Special value '_all' delete all event from list"} }, 
    { "name": "event/get",                           "dataType": 12/* String */, "string_value":"", "is_null": true,    "metadata":{"description":"[W]Read event from list, event sent in properties"} },
    { "name": "event/enable",                        "dataType": 12/* String */, "string_value":"", "is_null": true,    "metadata":{"description":"[W]Enable event, enabled event execute scenario"} }, 
    { "name": "event/disable",                       "dataType": 12/* String */, "string_value":"", "is_null": true,    "metadata":{"description":"[W]Disable event, disabled event don't execute scenario"} },    
    { "name": "event/list",              
      "dataType": 16/* DataSet */, 
      "dataset_value":{ "num_of_columns": 3,
                        "columns": ["name", "version", "enabled"],
                        "types": [12, 7, 11], /* String, Uint32, Boolean */
                        "rows": [ {"elements":[{"string_value":"eventName1"},{"type": 7, "int_value": 1},{"boolean_value": true} ]},
                                  {"elements":[{"string_value":"eventName2"},{"type": 7, "int_value": 1},{"boolean_value": false} ]}  ] }, 
      "metadata":{"description":"[R]List of events names exist in node"} },      

    { "name": "virtual/add",                        "dataType": 16/* DataSet */,"dataset_value":{},  "is_null": true,   "metadata":{"description":"[W]Add virtual metric to specific device or node"} },
    { "name": "virtual/delete",                     "dataType": 16/* DataSet */,"dataset_value":{},  "is_null": true,   "metadata":{"description":"[W]Delete virtual metric from specific device or node"} },  

  ]
}
```

## BOX node death example
```json
> spBv1.0/box/NDEATH/abba2020
{
"timestamp": 1486144502122,
"metrics": [  
    { "name": "bdSeq",                               "dataType": 8/* Uint64 */,   "long_value": 0,                      "metadata":{"description":"[R]Birth-death sequence, 'online' - [NBIRTH > NDEATH], 'offline' - [NBIRTH <= NDEATH]  "} },  
]
}
```