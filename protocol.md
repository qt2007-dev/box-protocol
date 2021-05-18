# topics name schema
> **nodeID**, **deviceID** = 32bit in hex form low case
>>example  
**nodeID** = abba2020 
## **groupType**
- lc
-plc
-sta
-...


## **messageType**
1. NBIRTH - подключение контроллера
2. DBIRTH - подключение устройства
3. NDEATH - потеря связи с контроллером
4. DDEATH - потеря связи с устройством
5. NDATA - данные контроллера
6. DDATA - данные устройства
7. NCMD - команда контроллеру
8. DCMD - команда устройству
9. STATE - критические сообщения
> spBv1.0/**{groupType}**/**{messageType}**/**{nodeID}**  
> spBv1.0/**{groupType}**/**{messageType}**/**{nodeID}**/**{deviceID}**
>> example
>>
>>- spBv1.0/plc/NBIRTH/abba2020
>>- spBv1.0/lc/DDATA/abba2020/deba0001
						
## Payload in protobuf2
## Node types in info/type
1. *PLC*
2. *LC*


## Device types in info/type
1. *16 Digital outputs*
2. *16 Digital inputs*
3. *16 Analog outputs*
4. *16 Analog inputs*
5. *16 Relay outputs*
6. *Interfaces*
7. *NEMA*
...


## STA node birth example
> spBv1.0/sta/NBIRTH/abba2020

```json
{
  "timestamp": 1486144502122,
  "seq": 0,
  "metrics": [
      { "name": "bdSeq",
        "timestamp": 1486144502122,
        "dataType": 8, /* Uint64 */
        "long_value": 0},
      
      { "name": "control/reboot",
        "timestamp": 1486144502122,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
      
      { "name": "control/rebirth",
        "timestamp": 1486144502122,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
        
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
        "string_value": "STA"},

      { "name": "thread/name",
        "timestamp": 1479123452194,
        "dataType": 12, /* String */
        "string_value": "OpenThreadName"},      

      { "name": "thread/panid",
        "timestamp": 1479123452194,
        "dataType": 12, /* String */
        "string_value": "dead"},  

      { "name": "thread/expanid",
        "timestamp": 1479123452194,
        "dataType": 12, /* String */
        "string_value": "dead00beef00cafe1"},  

      { "name": "thread/mac",
        "timestamp": 1479123452194,
        "dataType": 12, /* String */
        "string_value": "f1f1f1f1f1"},  

      { "name": "thread/channel",
        "timestamp": 1479123452194,
        "dataType": 7, /* UInt32 */
        "int_value": 15},  

      { "name": "thread/connections",
        "alias": 2,
        "timestamp": 1479123452194,
        "dataType": 16, /* DataSet */
        "dataset_value":{ "num_of_columns": 5,
                          "columns": ["id", "rloc16", "age", "avgRSSI", "lastRSSI"],
                          "types": [7, 7, 7, 3, 3], /* UInt32, UInt32, UInt32, Int32, Int32 */
                          "rows": [ {"elements":[{"int_value":12}, {"int_value":4545}, {"int_value":20}, {"int_value":-30}, {"int_value":-35}]},
                                    {"elements":[{"int_value":15}, {"int_value":4583}, {"int_value":20}, {"int_value":-30}, {"int_value":-35}] } ] } },  
        
      { "name": "coordinates/latitude",
        "alias": 6,
        "timestamp": 1479123452194,
        "dataType": 10, /* Double */
        "double_value": 55.751244}, 
        
      { "name": "coordinates/longitude",
        "alias": 7,
        "timestamp": 1479123452194,
        "dataType": 10, /* Double */
        "double_value": 37.618423},     
        
      { "name": "coordinates/update/time",
        "alias": 8,
        "timestamp": 1479123452194,
        "dataType": 7, /* UInt32 */
        "int_value": 0} /* Value 0 disable update */ ]
}
```


## PLC node birth example
> spBv1.0/plc/NBIRTH/abba2020

```json
{
  "timestamp": 1486144502122,
  "seq": 0,
  "metrics": [
      { "name": "bdSeq",
        "timestamp": 1486144502122,
        "dataType": 8, /* Uint64 */
        "long_value": 0},
      
      { "name": "control/reboot",
        "timestamp": 1486144502122,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
      
      { "name": "control/rebirth",
        "timestamp": 1486144502122,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
        
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
        "string_value": "PLC"},
      
      { "name": "scenario/list",
        "alias": 2,
        "timestamp": 1479123452194,
        "dataType": 16, /* DataSet */
        "dataset_value":{ "num_of_columns": 3,
                          "columns": ["name", "last", "next"],
                          "types": [12, 8, 8], /* String, UInt64, UInt64 */
                          "rows": [ {"elements":[{"string_value":"scenarioName1"},{"long_value":151515151515},{"long_value":151515151515} ]},
                                    {"elements":[{"string_value":"scenarioName2"},{"long_value":151515151515},{"long_value":151515151515} ]}  ] }
                                    /* value = list of scenarioId and names, last - last used time, next - next time to be used */},
                                      
      { "name": "scenario/add",
        "alias": 2,
        "timestamp": 1479123452194,
        "dataType": 12, /* String */ 
        "is_null": true /* in birth always null */
        /* int_value = scenarioId to add to list */},
      
      { "name": "scenario/delete",
        "alias": 3,
        "timestamp": 1479123452194,
        "dataType": 12, /* String */ 
        "is_null": true /* in birth always null */
        /* int_value = scenarioId to delete from list */},
        
      { "name": "scenario/get",
        "alias": 4,
        "timestamp": 1479123452194,
        "dataType": 12, /* String */ 
        "is_null": true /* in birth always null */
        /* int_value = scenarioId to get from list */},
        
      { "name": "schedule",
        "alias": 5,
        "timestamp": 1479123452194,
        "dataType": 12, /* String */
        "string_value": "on" /* value = on/off/set/get */},

      { "name": "schedule/state",
        "timestamp": 1479123452194,
        "dataType": 16, /* DataSet */
        "dataset_value":{ "num_of_columns": 5,
                          "columns": ["name", "actioNumber", "actionQuantity", "repeatNumber", "repeatQuantity"],
                          "types": [12, 3, 3, 3, 3], /* String, UInt32, UInt32, UInt32 */
                          "rows": [ {"elements":[ {"string_value":"scenarioName1"},{"int_value":2},{"int_value":10},{"int_value":3},{"int_value":25} ]},
                                    {"elements":[ {"string_value":"scenarioName2"},{"int_value":2},{"int_value":10},{"int_value":3},{"int_value":-1} ]}  ] } },         
        
      { "name": "coordinates/latitude",
        "alias": 6,
        "timestamp": 1479123452194,
        "dataType": 10, /* Double */
        "double_value": 55.751244}, 
        
      { "name": "coordinates/longitude",
        "alias": 7,
        "timestamp": 1479123452194,
        "dataType": 10, /* Double */
        "double_value": 37.618423},     
        
      { "name": "coordinates/update/time",
        "alias": 8,
        "timestamp": 1479123452194,
        "dataType": 7, /* UInt32 */
        "int_value": 0} /* Value 0 disable update */ ]
}
```
## PLC device digital output birth example
> spBv1.0/plc/DBIRTH/abba2020/deba0001 

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
        "string_value": "16 Digital outputs"},
        
      { "name": "out/bits/0",
        "alias": 1,
        "timestamp": 1479123452194,
        "dataType": 5, /* UInt8 */
        "int_value": 255    /* value is bitmask 0-7 output */},
      
      { "name": "out/bits/1",
        "alias": 2,
        "timestamp": 1479123452194,
        "dataType": 5, /* UInt8 */
        "int_value": 0      /* value is bitmask 8-15 output */},
        
      { "name": "out/0",
        "alias": 2,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
      
      { "name": "out/1",
        "alias": 3,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
      
      { "name": "out/2",
        "alias": 4,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
        
      { "name": "out/3",
        "alias": 5,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
        
      { "name": "out/4",
        "alias": 6,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
      
      { "name": "out/5",
        "alias": 7,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
      
      { "name": "out/6",
        "alias": 8,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
      
      { "name": "out/7",
        "alias": 9,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
        
      { "name": "out/8",
        "alias": 10,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
        
      { "name": "out/9",
        "alias": 11,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
        
      { "name": "out/10",
        "alias": 12,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
        
      { "name": "out/11",
        "alias": 13,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
      
      { "name": "out/12",
        "alias": 14,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
        
      { "name": "out/13",
        "alias": 15,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
      
      { "name": "out/14",
        "alias": 16,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
      
      { "name": "out/15",
        "alias": 17,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false} ]
}
```


## PLC device relay output birth example
> spBv1.0/plc/DBIRTH/abba2020/deba0002 

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
        
      { "name": "info/hardware/vendor",
        "timestamp": 1479123452194,
        "dataType": 12, /* String */
        "boolean_value": "QuintTech"},
        
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
        "string_value": "16 Relay outputs"},
        
      { "name": "out/bits/0",
        "alias": 1,
        "timestamp": 1479123452194,
        "dataType": 5, /* UInt8 */
        "int_value": 255    /* value is bitmask 0-7 output */},
      
      { "name": "out/bits/1",
        "alias": 2,
        "timestamp": 1479123452194,
        "dataType": 5, /* UInt8 */
        "int_value": 0      /* value is bitmask 8-15 output */},
        
      { "name": "out/0",
        "alias": 2,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
      
      { "name": "out/1",
        "alias": 3,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
      
      { "name": "out/2",
        "alias": 4,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
        
      { "name": "out/3",
        "alias": 5,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
        
      { "name": "out/4",
        "alias": 6,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
      
      { "name": "out/5",
        "alias": 7,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
      
      { "name": "out/6",
        "alias": 8,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
      
      { "name": "out/7",
        "alias": 9,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
        
      { "name": "out/8",
        "alias": 10,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
        
      { "name": "out/9",
        "alias": 11,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
        
      { "name": "out/10",
        "alias": 12,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
        
      { "name": "out/11",
        "alias": 13,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
      
      { "name": "out/12",
        "alias": 14,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
        
      { "name": "out/13",
        "alias": 15,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
      
      { "name": "out/14",
        "alias": 16,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
      
      { "name": "out/15",
        "alias": 17,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false} ]
}
```


## PLC device digital input birth example
> spBv1.0/plc/DBIRTH/abba2020/deba0003  

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
        "string_value": "16 Digital inputs"},
        
      { "name": "in/bits/0",
        "alias": 1,
        "timestamp": 1479123452194,
        "dataType": 5, /* UInt8 */
        "int_value": 255    /* value is bitmask 0-7 input */},
      
      { "name": "in/bits/1",
        "alias": 2,
        "timestamp": 1479123452194,
        "dataType": 5, /* UInt8 */
        "int_value": 0      /* value is bitmask 8-15 input */},
        
      { "name": "in/0",
        "alias": 2,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
      
      { "name": "in/1",
        "alias": 3,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
      
      { "name": "in/2",
        "alias": 4,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
        
      { "name": "in/3",
        "alias": 5,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
        
      { "name": "in/4",
        "alias": 6,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
      
      { "name": "in/5",
        "alias": 7,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
      
      { "name": "in/6",
        "alias": 8,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
      
      { "name": "in/7",
        "alias": 9,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
        
      { "name": "in/8",
        "alias": 10,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
        
      { "name": "in/9",
        "alias": 11,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
        
      { "name": "in/10",
        "alias": 12,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
        
      { "name": "in/11",
        "alias": 13,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
      
      { "name": "in/12",
        "alias": 14,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
        
      { "name": "in/13",
        "alias": 15,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
      
      { "name": "in/14",
        "alias": 16,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
      
      { "name": "in/15",
        "alias": 17,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false} ]
}
```


## PLC device analog input birth example
> spBv1.0/plc/DBIRTH/abba2020/deba0003  

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
        "string_value": "16 Analog inputs"},
        
      { "name": "in/0",
        "alias": 1,
        "timestamp": 1479123452194,
        "dataType": 7, /* UInt32 */
        "int_value": 5635   /* value in mV */ },
      
      { "name": "in/1",
        "alias": 2,
        "timestamp": 1479123452194,
        "dataType": 7, /* UInt32 */
        "int_value": 5635   /* value in mV */ },
      
      { "name": "in/2",
        "alias": 3,
        "timestamp": 1479123452194,
        "dataType": 7, /* UInt32 */
        "int_value": 5635   /* value in mV */ },
        
      { "name": "in/3",
        "alias": 4,
        "timestamp": 1479123452194,
        "dataType": 7, /* UInt32 */
        "int_value": 5635   /* value in mV */ },
        
      { "name": "in/4",
        "alias": 5,
        "timestamp": 1479123452194,
        "dataType": 7, /* UInt32 */
        "int_value": 5635   /* value in mV */ },
      
      { "name": "in/5",
        "alias": 6,
        "timestamp": 1479123452194,
        "dataType": 7, /* UInt32 */
        "int_value": 5635   /* value in mV */ },
      
      { "name": "in/6",
        "alias": 7,
        "timestamp": 1479123452194,
        "dataType": 7, /* UInt32 */
        "int_value": 5635   /* value in mV */ },
      
      { "name": "in/7",
        "alias": 8,
        "timestamp": 1479123452194,
        "dataType": 7, /* UInt32 */
        "int_value": 5635   /* value in mV */ },
        
      { "name": "in/8",
        "alias": 9,
        "timestamp": 1479123452194,
        "dataType": 7, /* UInt32 */
        "int_value": 5635   /* value in mV */ },
        
      { "name": "in/9",
        "alias": 10,
        "timestamp": 1479123452194,
        "dataType": 7, /* UInt32 */
        "int_value": 5635   /* value in mV */ },
        
      { "name": "in/10",
        "alias": 11,
        "timestamp": 1479123452194,
        "dataType": 7, /* UInt32 */
        "int_value": 5635   /* value in mV */ },
        
      { "name": "in/11",
        "alias": 12,
        "timestamp": 1479123452194,
        "dataType": 7, /* UInt32 */
        "int_value": 5635   /* value in mV */ },
      
      { "name": "in/12",
        "alias": 13,
        "timestamp": 1479123452194,
        "dataType": 7, /* UInt32 */
        "int_value": 5635   /* value in mV */ },
        
      { "name": "in/13",
        "alias": 14,
        "timestamp": 1479123452194,
        "dataType": 7, /* UInt32 */
        "int_value": 5635   /* value in mV */ },
      
      { "name": "in/14",
        "alias": 15,
        "timestamp": 1479123452194,
        "dataType": 7, /* UInt32 */
        "int_value": 5635   /* value in mV */ },
      
      { "name": "in/15",
        "alias": 16,
        "timestamp": 1479123452194,
        "dataType": 7, /* UInt32 */
        "int_value": 5635   /* value in mV */ } ]
}
```


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
        
      { "name": "RS485/settings/baudrate",
        "alias": 1,
        "timestamp": 1479123452194,
        "dataType": 7,  /* UInt32*/
        "int_value": 115200  /* values = 1200,2400,4800,9600,14400,19200,28800,38400,57600,115200,230400,460800,921600 */ },
        
      { "name": "RS485/settings/databits",
        "alias": 2,
        "timestamp": 1479123452194,
        "dataType": 7,  /* UInt32*/
        "int_value": 8  /* values = 7,8,9 */},
        
      { "name": "RS485/settings/stopbits",
        "alias": 3,
        "timestamp": 1479123452194,
        "dataType": 9,  /* Float */
        "float_value": 1 /* values = 1,1.5,2 */},
      
      { "name": "RS485/settings/parity",
        "alias": 4,
        "timestamp": 1479123452194,
        "dataType": 12, /* String */
        "string_value": "none" /* values = "none","even","odd" */},
      
      { "name": "RS485/settings/timeout",
        "alias": 5,
        "timestamp": 1479123452194,
        "dataType": 7,  /* UInt32*/
        "int_value": 0 /* value in ms, wait time after last byte received */},
        
      { "name": "RS485/settings/terminator",
        "alias": 6,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": true /* enable/disable terminator on bus */},
        
      { "name": "RS485/in",
        "alias": 7,
        "timestamp": 1479123452194,
        "dataType": 17, /* Bytes" */
        "bytes_value": "Base64 formatted string"},
        
      { "name": "RS485/out", 
        "alias": 8,
        "timestamp": 1479123452194,
        "dataType": 17, /* Bytes */
        "bytes_value": "Base64 formatted string"} ]
}
```


## Ligth controller node birth example
> spBv1.0/lc/NBIRTH/baab2020

```json
{
  "timestamp": 1486144502122,
  "seq": 0,
  "metrics": [
      { "name": "bdSeq",
        "timestamp": 1486144502122,
        "dataType": 8, /* Uint64 */
        "int_value": 0},
      
      { "name": "control/reboot",
        "timestamp": 1486144502122,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
      
      { "name": "control/rebirth",
        "timestamp": 1486144502122,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
        
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
        "string_value": "LC"},
      
      { "name": "scenario/list",
        "alias": 2,
        "timestamp": 1479123452194,
        "dataType": 16, /* DataSet */
        "dataset_value":{ "num_of_columns": 3,
                          "columns": ["name", "last", "next"],
                          "types": [12, 8, 8], /* String, UInt64, UInt64 */
                          "rows": [ {"elements":[{"string_value":"scenarioName1"},{"long_value":151515151515},{"long_value":151515151515} ]},
                                    {"elements":[{"string_value":"scenarioName2"},{"long_value":151515151515},{"long_value":151515151515} ]}  ] }
                                    /* value = list of scenarioId and names, last - last used time, next - next time to be used */},
                                      
      { "name": "scenario/add",
        "alias": 2,
        "timestamp": 1479123452194,
        "dataType": 12, /* String */ 
        "is_null": true /* in birth always null */
        /* int_value = scenarioId to add to list */},
      
      { "name": "scenario/delete",
        "alias": 3,
        "timestamp": 1479123452194,
        "dataType": 12, /* String */ 
        "is_null": true /* in birth always null */
        /* int_value = scenarioId to delete from list */},
        
      { "name": "scenario/get",
        "alias": 4,
        "timestamp": 1479123452194,
        "dataType": 12, /* String */ 
        "is_null": true /* in birth always null */
        /* int_value = scenarioId to get from list */},
        
      { "name": "schedule",
        "alias": 5,
        "timestamp": 1479123452194,
        "dataType": 12, /* String */
        "string_value": "on" /* value = on/off/set/get */},

      { "name": "schedule/state",
        "alias": 6,
        "timestamp": 1479123452194,
        "dataType": 16, /* DataSet */
        "dataset_value":{ "num_of_columns": 5,
                          "columns": ["name", "actioNumber", "actionQuantity", "repeatNumber", "repeatQuantity"],
                          "types": [12, 3, 3, 3, 3], /* String, UInt32, UInt32, UInt32 */
                          "rows": [ {"elements":[ {"string_value":"scenarioName1"},{"int_value":2},{"int_value":10},{"int_value":3},{"int_value":25} ]},
                                    {"elements":[ {"string_value":"scenarioName2"},{"int_value":2},{"int_value":10},{"int_value":3},{"int_value":-1} ]}  ] } }, 
        
      { "name": "sensors/accelerometer/x",
        "alias": 7,
        "timestamp": 1479123452194,
        "dataType": 9, /* Float */
        "float_value": 7852},          
        
      { "name": "sensors/accelerometer/y",
        "alias": 8,
        "timestamp": 1479123452194,
        "dataType": 9, /* Float */
        "float_value": 7852},  
        
      { "name": "sensors/accelerometer/z",
        "alias": 9,
        "timestamp": 1479123452194,
        "dataType": 9, /* Float */
        "float_value": 7852},      
        
      { "name": "sensors/luminosity",
        "alias": 10,
        "timestamp": 1479123452194,
        "dataType": 9, /* Float */
        "float_value": 12.4},  
        
      { "name": "sensors/temperature",
        "alias": 11,
        "timestamp": 1479123452194,
        "dataType": 9, /* Float */
        "float_value": 24},

      { "name": "sensors/update",
        "alias": 12,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false}, /* update now - send true  */

      { "name": "sensors/update/time",
        "alias": 13,
        "timestamp": 1479123452194,
        "dataType": 7, /* UInt32 */
        "int_value": 0}, /* Value 0 disable update */            

      { "name": "sensors/update/accelerometer",
        "alias": 14,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */

      { "name": "sensors/update/accelerometer/threshold",
        "alias": 15,
        "timestamp": 1479123452194,
        "dataType": 9, /* Float */
        "float_value": 300}, /* delta value for auto update  */           
        
      { "name": "sensors/update/luminosity",
        "alias": 16,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false}, /* enabled/disabled  */ 

      { "name": "sensors/update/luminosity/threshold",
        "alias": 17,
        "timestamp": 1479123452194,
        "dataType": 9, /* Float */
        "float_value": 5}, /* delta value for auto update  */         
        
      { "name": "sensors/update/temperature",
        "alias": 18,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false}, /* enabled/disabled  */

      { "name": "sensors/update/temperature/threshold",
        "alias": 19,
        "timestamp": 1479123452194,
        "dataType": 9, /* Float */
        "float_value": 3}, /* delta value for auto update  */           
        
      { "name": "coordinates/latitude",
        "alias": 20,
        "timestamp": 1479123452194,
        "dataType": 10, /* Double */
        "double_value": 55.751244}, 
        
      { "name": "coordinates/longitude",
        "alias": 21,
        "timestamp": 1479123452194,
        "dataType": 10, /* Double */
        "double_value": 37.618423},     
        
      { "name": "coordinates/update/time",
        "alias": 22,
        "timestamp": 1479123452194,
        "dataType": 7, /* UInt32 */
        "int_value": 0}, /* Value 0 disable update */    

      { "name": "coordinates/update/threshold",
        "alias": 23,
        "timestamp": 1479123452194,
        "dataType": 10, /* Double */
        "double_value": 0.001},                  

        ]
}
```

## Ligth controller device birth example with analog driver
> spBv1.0/lc/DBIRTH/baab2020/deba0001  

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
        "string_value": "NEMA"},
      
      { "name": "driver",
        "alias": 1,
        "timestamp": 1479123452194,
        "dataType": 12, /* String */
        "string_value": "analog"},
      
      { "name": "analog/dim",
        "alias": 2,
        "timestamp": 1479123452194,
        "dataType": 6,  /* UInt16 */
        "int_value": 125},
        
      { "name": "analog/dim/min",
        "alias": 3,
        "timestamp": 1479123452194,
        "dataType": 6,  /* UInt16 */
        "int_value": 125},
      
      { "name": "analog/dim/max",
        "alias": 4,
        "timestamp": 1479123452194,
        "dataType": 6,  /* UInt16 */
        "int_value": 125},
      
      { "name": "load",
        "alias": 5,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
        
      { "name": "meter/voltage",
        "alias": 6,
        "timestamp": 1479123452194,
        "dataType": 7, /* UInt32 */
        "int_value": 220000}, /* Value in mV */    
        
      { "name": "meter/current",
        "alias": 7,
        "timestamp": 1479123452194,
        "dataType": 7, /* UInt32 */
        "int_value": 865}, /* Value in mA */    
        
      { "name": "meter/power/active",
        "alias": 8,
        "timestamp": 1479123452194,
        "dataType": 3, /* Int32 */
        "int_value": 7852}, /* Value in mW */         

      { "name": "meter/power/reactive",
        "alias": 9,
        "timestamp": 1479123452194,
        "dataType": 7, /* UInt32 */
        "int_value": 865}, /* Value in mVAR */    
        
      { "name": "meter/power/apparent",
        "alias": 10,
        "timestamp": 1479123452194,
        "dataType": 7, /* UInt32 */
        "int_value": 8000}, /* Value in mVA */  
        
      { "name": "meter/power/factor",
        "alias": 11,
        "timestamp": 1479123452194,
        "dataType": 3, /* Int32 */
        "int_value": 865}, /* Value in metc */     
  
      { "name": "meter/update/time",
        "alias": 12,
        "timestamp": 1479123452194,
        "dataType": 7, /* UInt32 */
        "int_value": 0}, /* Value 0 disable update */          
        
      { "name": "meter/update/voltage",
        "alias": 13,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false}, /* enabled/disabled */   
        
      { "name": "meter/update/current",
        "alias": 14,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false}, /* enabled/disabled  */
        
      { "name": "meter/update/power/active",
        "alias": 15,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false}, /* enabled/disabled  */
        
      { "name": "meter/update/power/reactive",
        "alias": 16,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false}, /* enabled/disabled  */  
        
      { "name": "meter/update/power/apparent",
        "alias": 17,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false}, /* enabled/disabled  */ 
        
      { "name": "meter/update/power/factor",
        "alias": 18,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false} /* enabled/disabled  */         
        ]
}
```

## Ligth controller device birth example with pwm driver
> spBv1.0/lc/DBIRTH/baab2020/deba0001  

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
        "string_value": "NEMA"},
      
      { "name": "driver",
        "alias": 1,
        "timestamp": 1479123452194,
        "dataType": 12, /* String */
        "string_value": "pwm"},
      
      { "name": "pwm/dim",
        "alias": 2,
        "timestamp": 1479123452194,
        "dataType": 6,  /* UInt16 */
        "int_value": 125},
        
      { "name": "pwm/dim/min",
        "alias": 3,
        "timestamp": 1479123452194,
        "dataType": 6,  /* UInt16 */
        "int_value": 125},
      
      { "name": "pwm/dim/max",
        "alias": 4,
        "timestamp": 1479123452194,
        "dataType": 6,  /* UInt16 */
        "int_value": 125},
      
      { "name": "load",
        "alias": 5,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
        
      { "name": "meter/voltage",
        "alias": 6,
        "timestamp": 1479123452194,
        "dataType": 7, /* UInt32 */
        "int_value": 220000}, /* Value in mV */    
        
      { "name": "meter/current",
        "alias": 7,
        "timestamp": 1479123452194,
        "dataType": 7, /* UInt32 */
        "int_value": 865}, /* Value in mA */    
        
      { "name": "meter/power/active",
        "alias": 8,
        "timestamp": 1479123452194,
        "dataType": 3, /* Int32 */
        "int_value": 7852}, /* Value in mW */         

      { "name": "meter/power/reactive",
        "alias": 9,
        "timestamp": 1479123452194,
        "dataType": 7, /* UInt32 */
        "int_value": 865}, /* Value in mVAR */    
        
      { "name": "meter/power/apparent",
        "alias": 10,
        "timestamp": 1479123452194,
        "dataType": 7, /* UInt32 */
        "int_value": 8000}, /* Value in mVA */  
        
      { "name": "meter/power/factor",
        "alias": 11,
        "timestamp": 1479123452194,
        "dataType": 3, /* Int32 */
        "int_value": 865}, /* Value in metc */
        
      { "name": "meter/update/time",
        "alias": 12,
        "timestamp": 1479123452194,
        "dataType": 7, /* UInt32 */
        "int_value": 0}, /* Value 0 disable update */          
        
      { "name": "meter/update/voltage",
        "alias": 13,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false}, /* enabled/disabled */   
        
      { "name": "meter/update/current",
        "alias": 14,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false}, /* enabled/disabled */
        
      { "name": "meter/update/power/active",
        "alias": 15,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false}, /* enabled/disabled */
        
      { "name": "meter/update/power/reactive",
        "alias": 16,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false}, /* enabled/disabled */  
        
      { "name": "meter/update/power/apparent",
        "alias": 17,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false}, /* enabled/disabled */ 
        
      { "name": "meter/update/power/factor",
        "alias": 18,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false} /* enabled/disabled  */         
        ]
}
```

## Ligth controller device birth example with dali driver
> spBv1.0/lc/DBIRTH/baab2020/deba0001  

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
        "string_value": "NEMA"},
      
      { "name": "driver",
        "alias": 1,
        "timestamp": 1479123452194,
        "dataType": 12, /* String */
        "string_value": "dali"},
      
      { "name": "dali/0/dim",
        "alias": 2,
        "timestamp": 1479123452194,
        "dataType": 5,  /* UInt8 */
        "int_value": 125},
        
      { "name": "dali/0/dim/phyMin",
        "alias": 3,
        "timestamp": 1479123452194,
        "dataType": 5,  /* UInt8 */
        "int_value": 125},
      
      { "name": "dali/0/dim/min",
        "alias": 4,
        "timestamp": 1479123452194,
        "dataType": 5,  /* UInt8 */
        "int_value": 125},
        
      { "name": "dali/0/dim/max",
        "alias": 5,
        "timestamp": 1479123452194,
        "dataType": 5,  /* UInt8 */
        "int_value": 125},
        
      { "name": "dali/0/dim/powerOn",
        "alias": 6,
        "timestamp": 1479123452194,
        "dataType": 5,  /* UInt8 */
        "int_value": 125},
        
      { "name": "dali/0/dim/failure",
        "alias": 7,
        "timestamp": 1479123452194,
        "dataType": 5,  /* UInt8 */
        "int_value": 125},          
        
      { "name": "dali/0/fade/rate",
        "alias": 8,
        "timestamp": 1479123452194,
        "dataType": 5,  /* UInt8 */
        "int_value": 5},
        
      { "name": "dali/0/fade/time",
        "alias": 9,
        "timestamp": 1479123452194,
        "dataType": 5,  /* UInt8 */
        "int_value": 5},        
        
      { "name": "dali/0/gear/controlFailure",
        "alias": 10,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
        
      { "name": "dali/0/gear/lampFailure",
        "alias": 11,        
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false},        
        
      { "name": "dali/0/gear/lampOn",
        "alias": 12,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false},        
        
      { "name": "dali/0/gear/limitError",
        "alias": 13,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false},            
   
      { "name": "dali/0/gear/fadeRunning",
        "alias": 14,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
        
      { "name": "dali/0/gear/resetState",
        "alias": 15,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false},        
        
      { "name": "dali/0/gear/shortAddressMissing",
        "alias": 16,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false},        
        
      { "name": "dali/0/gear/powerCycle",
        "alias": 17,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false},       
      
      { "name": "load",
        "alias": 18,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false},
        
      { "name": "meter/voltage",
        "alias": 19,
        "timestamp": 1479123452194,
        "dataType": 7, /* UInt32 */
        "int_value": 220000}, /* Value in mV */    
        
      { "name": "meter/current",
        "alias": 20,
        "timestamp": 1479123452194,
        "dataType": 7, /* UInt32 */
        "int_value": 865}, /* Value in mA */    
        
      { "name": "meter/power/active",
        "alias": 21,
        "timestamp": 1479123452194,
        "dataType": 3, /* Int32 */
        "int_value": 7852}, /* Value in mW */         

      { "name": "meter/power/reactive",
        "alias": 22,
        "timestamp": 1479123452194,
        "dataType": 7, /* UInt32 */
        "int_value": 865}, /* Value in mVAR */    
        
      { "name": "meter/power/apparent",
        "alias": 23,
        "timestamp": 1479123452194,
        "dataType": 7, /* UInt32 */
        "int_value": 8000}, /* Value in mVA */  
        
      { "name": "meter/power/factor",
        "alias": 24,
        "timestamp": 1479123452194,
        "dataType": 3, /* Int32 */
        "int_value": 865}, /* Value in metc */     
        
      { "name": "meter/update/time",
        "alias": 25,
        "timestamp": 1479123452194,
        "dataType": 7, /* UInt32 */
        "int_value": 0}, /* Value 0 disable update */          
        
      { "name": "meter/update/voltage",
        "alias": 26,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false}, /* enabled/disabled  */   
        
      { "name": "meter/update/current",
        "alias": 27,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false}, /* enabled/disabled d */
        
      { "name": "meter/update/power/active",
        "alias": 28,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false}, /* enabled/disabled  */
        
      { "name": "meter/update/power/reactive",
        "alias": 29,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false}, /* enabled/disabled  */  
        
      { "name": "meter/update/power/apparent",
        "alias": 30,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false}, /* enabled/disabled  */ 
        
      { "name": "meter/update/power/factor",
        "alias": 31,
        "timestamp": 1479123452194,
        "dataType": 11, /* Boolean */
        "boolean_value": false} /* enabled/disabled  */          
        
        ]
}
```

<!--stackedit_data:
eyJoaXN0b3J5IjpbODQwMDQ4MDk0XX0=
-->