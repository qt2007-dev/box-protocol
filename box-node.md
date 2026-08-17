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
    { "name": "control/host",                        "dataType": 12/* String */,  "string_value": "",                   "metadata":{"description":"[RWP]Primary host id, node sends its birth if the specified host or host 'ALL' comes online"} },
 
    { "name": "info/hardware/vendor",                "dataType": 12/* String */,  "string_value": "QuintTech",          "metadata":{"description":"[R]Vendor name, hardcoded by vendor"} },
    { "name": "info/hardware/model",                 "dataType": 12/* String */,  "string_value": "rpi4",               "metadata":{"description":"[R]Mcu model, hardcoded by vendor"} },
    { "name": "info/firmware/version",               "dataType": 12/* String */,  "string_value": "0.1.220527",         "metadata":{"description":"[R]Firmware version, MAJOR.MINOR.buildOrCommit"} },
    { "name": "info/type",                           "dataType": 12/* String */,  "string_value": "BOX",                "metadata":{"description":"[R]Device type, hardcoded by vendor"} },
    { "name": "info/id",                             "dataType": 12/* String */,  "string_value": "abba2020",           "metadata":{"description":"[R]Short device id"} },
    { "name": "info/error",                          "dataType": 12/* String */,  "string_value": "",                   "metadata":{"description":"[R]Last error message"} },
    { "name": "info/daytime",                        "dataType": 12/* String */,  "string_value": "day",                "metadata":{"description":"[R]Current daytime, values = ['day','night']"} },

    { "name": "sensors/temperature",                 "dataType": 1 /* Int8 */,     "int_value": 22,                     "metadata":{"description":"[R]Temperature sensor in mcu, value in Celsius"}, "properties":{ "keys": ["threshold"], "values": [{"type": 6, "int_value": 2}]} },
    { "name": "sensors/system/voltage",              "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[R]System voltage, value in mV"}, "properties":{ "keys": ["threshold"], "values": [{"type": 6, "int_value": 10}]} },
    { "name": "sensors/system/current",              "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[R]System current, value in mA"}, "properties":{ "keys": ["threshold"], "values": [{"type": 6, "int_value": 2}]} },  
    { "name": "sensors/modules/voltage",             "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[R]Modules voltage, value in mV"}, "properties":{ "keys": ["threshold"], "values": [{"type": 6, "int_value": 10}]} },
    { "name": "sensors/modules/current",             "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[R]Modules current, value in mA"}, "properties":{ "keys": ["threshold"], "values": [{"type": 6, "int_value": 2}]} },  
    { "name": "sensors/bus/voltage",                 "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[R]Bus voltage, value in mV"}, "properties":{ "keys": ["threshold"], "values": [{"type": 6, "int_value": 10}]} },
    { "name": "sensors/bus/current",                 "dataType": 6 /* UInt16 */,   "int_value": 22,                     "metadata":{"description":"[R]Bus current, value in mA"}, "properties":{ "keys": ["threshold"], "values": [{"type": 6, "int_value": 2}]} },    

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

    { "name": "connection/type",                     "dataType": 12/* String */,  "string_value": "ethernet",           "metadata":{"description":"[RWP]Active connection type, list of values = ['ethernet', 'modem']"} },

    { "name": "connection/static",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 8,
                        "columns": ["address", "mask", "gateway", "dns-0", "dns-1"],
                        "types": [12, 12, 12, 12, 12], /* String, String, String, String, String */
                        "rows": [ {"elements":[{"string_value":"192.168.10.10"},{"string_value":"255.255.255.0"},{"string_value":"192.168.10.1"},{"string_value":"1.1.1.1"},{"string_value":"8.8.8.8"}]} ] }, 
      "metadata":{"description":"[RWP]Static ip address, if dhcp failed, set static ip"} },

    { "name": "connection/server",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 8,
                        "columns": ["address", "port", "tls", "ca-certificate", "client-certificate", "client-key", "username", "password"],
                        "types": [12, 6, 11 , 12, 12, 12, 12, 12], /* String, UInt16, Boolean, String, String, String, String, String   */
                        "rows": [ {"elements":[{"string_value":"some.broker.com"},{"int_value":1883},{"boolean_value":true},{"string_value":"cert"},{"string_value":"cert"},{"string_value":"key"},{"string_value":"mqtt-username"},{"string_value":"mqtt-password"}]} ] }, 
      "metadata":{"description":"[RWP]mqtt broker"} },

    { "name": "connection/modem/operator",           "dataType": 12/* String */,  "string_value": "Beeline",            "metadata":{"description":"[R]Operator name"} },  
    { "name": "connection/modem/iccid",              "dataType": 12/* String */,  "string_value": "897010269709192239", "metadata":{"description":"[R]Show sim card iccid number"} },
    { "name": "connection/modem/rssi",               "dataType": 3 /* Int32 */,    "string_value": -60,                 "metadata":{"description":"[R]Cellular signal strength"}, "properties":{ "keys": ["threshold"], "values": [{"type": 6, "int_value": 2}]} },
    { "name": "schedule",                            "dataType": 12/* String */, "string_value": "on",                  "metadata":{"description":"[RWP]Schedule control metric, list of values = ['on', 'off', 'set', 'get'], schedule set and get in properties"} }, 
    { "name": "scenario/add",                        "dataType": 12/* String */, "string_value":"", "is_null": true,    "metadata":{"description":"[W]Scenario add to list, value = scenario name, scenario sent in properties"} },
    { "name": "scenario/execute",                    "dataType": 12/* String */, "string_value":"", "is_null": true,    "metadata":{"description":"[RW]Execute scenario, value = scenario name, after execution the value is reset to null"} },
    { "name": "scenario/delete",                     "dataType": 12/* String */, "string_value":"", "is_null": true,    "metadata":{"description":"[W]Scenario delete from list. Special value '_all' delete all scenario from list"} }, 
    { "name": "scenario/get",                        "dataType": 12/* String */, "string_value":"", "is_null": true,    "metadata":{"description":"[W]Read scenario from list, scenario sent in properties"} }, 
    { "name": "scenario/enable",                     "dataType": 12/* String */, "string_value":"", "is_null": true,    "metadata":{"description":"[W]Enable scenario, enabled scenario do actions on execute"} }, 
    { "name": "scenario/disable",                    "dataType": 12/* String */, "string_value":"", "is_null": true,    "metadata":{"description":"[W]Disable scenario, disabled scenario don't do any actions on execute"} },   
    { "name": "scenario/debug/url",                        "dataType": 12/* String */,  "string_value": "",                   "metadata":{"description":"[R]The ide's url"} },
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

    { "name": "virtual/add",                        "dataType": 16/* DataSet */,
      "dataset_value":{ "num_of_columns": 4,
                        "columns": ["id", "name", "dataType", "description"],
                        "types": [12, 12, 7, 12], /* String, String, Uint32, String */
                        "rows": [] 
                      },"is_null": true,   
      "metadata":{"description":"[W]Add virtual metric to specific device or node"} },
    { "name": "virtual/delete",                     "dataType": 16/* DataSet */,
      "dataset_value":{ "num_of_columns": 2,
                        "columns": ["id", "name"],
                        "types": [12, 12], /* String, String*/
                        "rows": [] },  
                        "is_null": true,   
      "metadata":{"description":"[W]Delete virtual metric from specific device or node"} }  
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