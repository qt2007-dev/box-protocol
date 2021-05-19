# sparkPlug topics name schema
> spBv1.0/**{groupType}**/**{messageType}**/**{nodeID}**  
> spBv1.0/**{groupType}**/**{messageType}**/**{nodeID}**/**{deviceID}**

## **{groupType}**
1. lc - light controller
2. plc - programmable logic controller 

## **{messageType}**
1. NBIRTH - node birth message, first message after connection to mqtt broker
2. DBIRTH - device birth message
3. NDEATH - node death message, last will message from broker, send after node disconnect 
4. DDEATH - device death message, device not responce in time, send by node
5. NDATA - node data, from node to broker
6. DDATA - device data, from device to broker
7. NCMD - node command, from broker to node
8. DCMD - device command, from broker to device

## **{nodeID}**
>32bit value in hex form low case
>>example 
**nodeID** = abba2020 

## **{deviceID}**
>32bit value in hex form low case
>>example  
 **deviceID** = deba0000

>> topics example
>>- spBv1.0/plc/NBIRTH/abba2020
>>- spBv1.0/lc/DBIRTH/abba2020/deba0001
						
# MQTT message payload in protobuf2
## Metrics
>for details - [a relative link](standart.proto)
>>metric elements
1. **name** - name of metric, can be group by `/`  
2. **alias** - number for use instead name in cmd\data
3. **timestamp** - time mark of metric
4. **properties** - metric properties used for schedule\scenario
5. **dataType** - value type
>Int8 = 1
>Int16 = 2
>Int32 = 3
>Int64 = 4
>UInt8 = 5
>UInt16 = 6
>UInt32 = 7
>UInt64 = 8
>Float = 9
>Double = 10
>Boolean = 11
>String = 12
>DateTime = 13
>Text = 14
>UUID = 15
>DataSet = 16
>Bytes = 17
>File = 18
>Template = 19
6. **value** - specific field for each type
>int_value
>long_value
>float_value
>double_value
>boolean_value
>string_value
>bytes_value
>dataset_value

>>example metric
```json
{ "name": "name1/name2/name3", 
  "alias": 123,
  "timestamp": 1486144502122,
  "dataType": 12, 
  "properties":{/* metric properties*/},
  "string_value": "value"}  
```

>For all examples 'alias' and 'timestamp' are omitted 
## Node types
1. *PLC* - [a relative link](plc-node.md)
2. *LC* -  [a relative link](lc-node.md)

## Device types
1. *16 Digital outputs* -  [a relative link](plc-device-do.md)
2. *16 Digital inputs*  -  [a relative link](plc-device-di.md)
3. *16 Analog inputs*   -  [a relative link](plc-device-ai.md)
4. *16 Relay outputs*   -  [a relative link](plc-device-ro.md)
5. *Interfaces*         -  [a relative link](plc-device-if.md)
6. *NEMA*               -  [a relative link](lc-device-nema.md)

## Scenario 
> Scenario description and examples - [a relative link](scenario.md)
## Schedule
> Schedule description and examples - [a relative link](schedule.md)
