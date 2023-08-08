# sparkPlug topics name schema
>NODE 
>- spBv1.0/**{groupType}**/**{messageType}**/**{nodeID}**  

> DEVICE 
>- spBv1.0/**{groupType}**/**{messageType}**/**{nodeID}**/**{deviceID}**

>example  
>- spBv1.0/box/NBIRTH/abba2020
>- spBv1.0/box/DDATA/abba2020/deba0001

## **{groupType}**
1. box - QuintTech controller

## **{messageType}**
1. NBIRTH - node birth message, first message after connection to mqtt broker
2. DBIRTH - device birth message
3. NDEATH - node death message, last will message from broker, send after node disconnect 
4. DDEATH - device death message, device not response in time, send by node
5. NDATA - node data, from node to broker
6. DDATA - device data, from device to broker
7. NCMD - node command, from broker to node
8. DCMD - device command, from broker to device

## **{nodeID}**
32bit value in hex form low case
>example 
>- **nodeID** = abba2020 

## **{deviceID}**
32bit value in hex form low case
>example  
>- **deviceID** = deba0000
						            
# MQTT message payload in protobuf2
## Metrics
for details - [protobuf](standart.proto)
>metric elements
>- **name** - name of metric, can be group by `/`  
>- **alias** - number for use instead name in cmd\data
>- **timestamp** - time mark of metric
>- **properties** - metric properties used for schedule\scenario
>- **dataType** - value type
>>- Int8 = 1
>>- Int16 = 2
>>- Int32 = 3
>>- Int64 = 4
>>- UInt8 = 5
>>- UInt16 = 6
>>- UInt32 = 7
>>- UInt64 = 8
>>- Float = 9
>>- Double = 10
>>- Boolean = 11
>>- String = 12
>>- DateTime = 13
>>- Text = 14
>>- UUID = 15
>>- DataSet = 16
>>- Bytes = 17
>>- File = 18
>>- Template = 19
>- **value** - specific field for each type
>>- int_value
>>- long_value
>>- float_value
>>- double_value
>>- boolean_value
>>- string_value
>>- bytes_value
>>- dataset_value

>example
>```json
>{ "name": "name1/name2/name3", 
>  "alias": 123,
>  "timestamp": 1486144502122,
>  "dataType": 12, 
>  "properties":{/* metric properties*/},
>  "string_value": "value"
>}  
>```
>For all examples 'alias' and 'timestamp' are omitted 

## Node types
1. [Box Node](plc-node.md)

## Device types
1. [16 Digital outputs](box-do.md)
2. [16 Digital inputs](box-di.md)
3. [8 Relay output](box-ro.md)
4. [8 Multifunctional input-output](box-io.md)
5. [Interfaces](box-if.md)
6. [2 channel Dali](box-dali.md)
7. [3-phase Energymeter](box-em.md)
8. [2 channel Step motor driver](box-em.md)
9. [3 channel Termocontroller](box-tc.md)
10. [2 channel Wiegand](box-wiegand.md)


## [Scenario description and examples](scenario.md)
## [Schedule description and examples](schedule.md)
## [Events description and examples](events.md)
## [Change server description and examples](change-server.md)