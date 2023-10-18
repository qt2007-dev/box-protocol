## BOX node birth example
> spBv1.0/box/NBIRTH/abba2020

```json
{
"timestamp": 1486144502122,
"seq": 0,
"metrics": [
    { "name": "bdSeq",                               "dataType": 8/* Uint64 */,   "long_value": 0,                      "metadata":{"description":"[R]Birth-death sequence, 'online' - [NBIRTH > NDEATH], 'offline' - [NBIRTH <= NDEATH]  "} },                      
    { "name": "control/reboot",                      "dataType": 11/* Boolean */, "boolean_value": false,               "metadata":{"description":"[W]Software reboot node, send 'true' for reboot"} },
    { "name": "control/rebirth",                     "dataType": 11/* Boolean */, "boolean_value": false,               "metadata":{"description":"[W]Rebirth node, send 'true' for receive dbirth message again"} },
    { "name": "control/firmware/new",                "dataType": 17/* Bytes */,   "bytes_value":"", "is_null": true,    "metadata":{"description":"[W]Receive new node firmware, firmware send in Base64 format, in birth always null"} },
    { "name": "control/metrics/save",                "dataType": 11/* Boolean */, "boolean_value": true,                "metadata":{"description":"[RWP]Save metrics states after reboot, send 'true' for enable"} },
    { "name": "control/metrics/metadata",            "dataType": 11/* Boolean */, "boolean_value": true,                "metadata":{"description":"[RWP]Show metrics metadata in birth, send 'true' for enable"} },
    { "name": "control/group",                       "dataType": 12/* String */,  "string_value": "plc",                "metadata":{"description":"[RWP]Global group for node, can be used instead id in topics and scenarios"} },
    { "name": "control/bus/power",                   "dataType": 11/* Boolean */, "boolean_value": true,                "metadata":{"description":"[RWP]Bus enable, enable or disable bus power"} },             
    { "name": "control/timezone",                    "dataType": 12/* String */,  "string_value": "UTC+0",              "metadata":{"description":"[RWP]Current timezone"} },         

    { "name": "info/hardware/vendor",                "dataType": 12/* String */,  "string_value": "QuintTech",          "metadata":{"description":"[R]Vendor name, hardcoded by vendor"} },
    { "name": "info/hardware/model",                 "dataType": 12/* String */,  "string_value": "rpi4",               "metadata":{"description":"[R]Mcu model, hardcoded by vendor"} },
    { "name": "info/firmware/version",               "dataType": 12/* String */,  "string_value": "0.1.220527.84852",   "metadata":{"description":"[R]Firmware version, MAJOR.MINOR.YYMMDD.SSSSS"} },
    { "name": "info/type",                           "dataType": 12/* String */,  "string_value": "BOX",                "metadata":{"description":"[R]Node type, hardcoded by vendor"} },
    { "name": "info/id",                             "dataType": 12/* String */,  "string_value": "abba2020",           "metadata":{"description":"[R]Short id calculated by a hash from mcu uid"} },
    { "name": "info/error",                          "dataType": 12/* String */,  "string_value": "",                   "metadata":{"description":"[R]Last error message"} },
    { "name": "info/date",                           "dataType": 12/* String */,  "string_value": "18.10.2023",         "metadata":{"description":"[R]Current date"} },
    { "name": "info/time",                           "dataType": 12/* String */,  "string_value": "14:50:00",           "metadata":{"description":"[R]Current time"} },
    { "name": "info/daytime",                        "dataType": 12/* String */,  "string_value": "day",                "metadata":{"description":"[R]Current daytime, values = ['day','nigth','sunset','sunrise']"} },

    { "name": "sensors/temperature",                 "dataType": 1 /* Int8 */,     "int_value": 22,                     "metadata":{"description":"[R]Temperature sensor in mcu, value in Celsius"} },
    { "name": "sensors/system/voltage",              "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[R]System voltage, value in mV"} },
    { "name": "sensors/system/current",              "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[R]System current, value in mA"} },  
    { "name": "sensors/modules/voltage",             "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[R]Modules voltage, value in mV"} },
    { "name": "sensors/modules/current",             "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[R]Modules current, value in mA"} },  
    { "name": "sensors/bus/voltage",                 "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[R]Bus voltage, value in mV"} },
    { "name": "sensors/bus/current",                 "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[R]Bus current, value in mA"} },    
   


    { "name": "coordinates/latitude",                "dataType": 10/* Double */,  "double_value": 55.751244,            "metadata":{"description":"[R]GNSS coordinates latitude, value in degree"} },            
    { "name": "coordinates/longitude",               "dataType": 10/* Double */,  "double_value": 37.618423,            "metadata":{"description":"[R]GNSS coordinates longitude, value in degree"} },
    
    { "name": "connection/type",                     "dataType": 12/* String */,  "string_value": "ethernet",           "metadata":{"description":"[RWP]Active connection type, list of values = ['ethernet', 'modem', 'thread']"} },
    { "name": "connection/server",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 4,
                        "columns": ["address", "port", "tls", "ca-certificate", "client-certificate", "client-key", "username", "password"],
                        "types": [12, 6, 11 , 12, 12, 12, 12, 12], /* String, UInt16, Boolean, String, String, String, String, String   */
                        "rows": [ {"elements":[{"string_value":"dev.qtsolar.com"},{"int_value":8883},{"boolean_value":true},{"string_value":"cert"},{"string_value":"cert"},{"string_value":"key"},{"string_value":"mqtt-username"},{"string_value":"mqtt-password"}]} ] }, 
      "metadata":{"description":"[RWP]Current mqtt broker, client-key without password"} },

    { "name": "connection/modem/operator",           "dataType": 12/* String */,  "string_value": "Beeline",            "metadata":{"description":"[R]Operator name"} },  
    { "name": "connection/modem/iccid",              "dataType": 12/* String */,  "string_value": "897010269709192239", "metadata":{"description":"[R]Show sim card iccid number"} },
    { "name": "connection/modem/rssi",               "dataType": 3 /* Int32 */,    "string_value": -60,                 "metadata":{"description":"[R]Cellular signal strenght"} },
   
    { "name": "connection/thread/name",              "dataType": 12/* String */,  "string_value": "ThreadNetworkName",  "metadata":{"description":"[RWP]Thread network name"} },   
    { "name": "connection/thread/panid",             "dataType": 6 /* UInt16 */,   "int_value": 1234,                   "metadata":{"description":"[RWP]Thread network panid"} },                     
    { "name": "connection/thread/channel",           "dataType": 5 /* UInt8 */,    "int_value": 12,                     "metadata":{"description":"[RWP]Thread network channel"} },                       
    { "name": "connection/thread/role",              "dataType": 12/* String */,  "string_value": "leader",             "metadata":{"description":"[R]Node role in thread network, list of values = ['child', 'router', 'leader']"} },            
    { "name": "connection/thread/rloc16",            "dataType": 6 /* UInt16 */,   "int_value": 1234,                   "metadata":{"description":"[R]Node rloc16 in thread network"} },                        
    { "name": "connection/thread/neighbors",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 4,
                        "columns": ["role", "rloc16", "avg-rssi", "last-rssi"],
                        "types": [12, 6, 3, 3 ], /* String, UInt16, Int32, Int32 */
                        "rows": [ {"elements":[{"string_value":"child"},{"int_value":1235},{"int_value":-60},{"int_value":-70} ]},
                                  {"elements":[{"string_value":"router"},{"int_value":1235},{"int_value":-60},{"int_value":-70} ]},
                                  {"elements":[{"string_value":"leader"},{"int_value":1235},{"int_value":-60},{"int_value":-70} ]}  ] }, 
      "metadata":{"description":"[R]Node neighbors list in thread network"} },

    { "name": "schedule",                            "dataType": 12/* String */, "string_value": "on",                  "metadata":{"description":"[RWP]Schedule control metric, list of values = ['on', 'off', 'set', 'get'], schedule set and get in properties"} }, 

    { "name": "scenario/add",                        "dataType": 12/* String */, "string_value":"", "is_null": true,    "metadata":{"description":"[W]Scenario add to list, value = scenario name, scenario sent in properties"} },
    { "name": "scenario/execute",                    "dataType": 12/* String */, "string_value":"", "is_null": true,    "metadata":{"description":"[RW]Execute scenario, value = scenario name, after execution the value is reset to null"} },
    { "name": "scenario/delete",                     "dataType": 12/* String */, "string_value":"", "is_null": true,    "metadata":{"description":"[W]Scenario delete from list. Special value '_all' delete all scenario from list"} }, 
    { "name": "scenario/get",                        "dataType": 12/* String */, "string_value":"", "is_null": true,    "metadata":{"description":"[W]Read scenario from list, scenario sent in properties"} },   
    { "name": "scenario/list",              
      "dataType": 16/* DataSet */, 
      "dataset_value":{ "num_of_columns": 3,
                        "columns": ["name"],
                        "types": [12, 8, 8], /* String */
                        "rows": [ {"elements":[{"string_value":"scenarioName1"} ]},
                                  {"elements":[{"string_value":"scenarioName2"} ]}  ] },                                  
      "metadata":{"description":"[R]List of scenario names exist in node"} },                           

    { "name": "event/add",                           "dataType": 12/* String */, "string_value":"", "is_null": true,    "metadata":{"description":"[W]Event add to list, value = event name, event sent in properties"} },
    { "name": "event/delete",                        "dataType": 12/* String */, "string_value":"", "is_null": true,    "metadata":{"description":"[W]Event delete from list. Special value '_all' delete all event from list"} }, 
    { "name": "event/get",                           "dataType": 12/* String */, "string_value":"", "is_null": true,    "metadata":{"description":"[W]Read event from list, event sent in properties"} }, 
    { "name": "event/list",              
      "dataType": 16/* DataSet */, 
      "dataset_value":{ "num_of_columns": 3,
                        "columns": ["name"],
                        "types": [12], /* String */
                        "rows": [ {"elements":[{"string_value":"eventName1"} ]},
                                  {"elements":[{"string_value":"eventName2"} ]}  ] }, 
      "metadata":{"description":"[R]List of events names exist in node"} },      

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