# Topics
Details in [***SparkPlug***](sparkplug-specification-3.0.0.pdf)
> **NODE** 
>
> spBv1.0/***{groupType}***/***{messageType}***/***{nodeID}***  
>
>> example
>>
>> spBv1.0/box/NBIRTH/abba2020


> **DEVICE** 
>
> spBv1.0/***{groupType}***/***{messageType}***/***{nodeID}***/***{deviceID}***
>>example
>>
>>spBv1.0/box/DDATA/abba2020/deba0001

- ***groupType***
    - ***plc***
    - ***lc***
    - ***box***
    - ***ledef***

- ***messageType***
    - ***NBIRTH*** - node birth message, first message after connection to mqtt broker
    - ***DBIRTH*** - device birth message
    - ***NDEATH*** - node death message, last will message from broker, send after node disconnect 
    - ***DDEATH*** - device death message, device not response in time, send by node
    - ***NDATA*** - node data, from node to broker
    - ***DDATA*** - device data, from device to broker
    - ***NCMD*** - node command, from broker to node
    - ***DCMD*** - device command, from broker to device

- ***nodeID***  - 32bit value in hex form, low case
- ***deviceID*** - 32bit value in hex form, low case

					            
# Payload 
Mqtt message payload in [***protobuf***](standart.proto)

>example
>```json
>{ "timestamp":1486144502122,
>   "seq":1,
>   "uuid":"8c1ade19-6860-4b7f-82d4-b5d8f74cf4ac",
>   "metrics":[ 
>   {   "name": "name1/name2/name3", 
>       "alias": 123,
>       "timestamp": 1486144502122,
>       "dataType": 12, 
>       "properties":{  "keys": ["key1", "key2"],
>                       "values": [ {"type":12, "string_value":"value1"}, {"type":12, "string_value":"value2"} ] },
>       "string_value": "value"}, ]
>}  
>```

## Metrics

- ***"name"*** - name of metric, can be group by `/`  
- ***"alias"*** - number for use instead name in xCMD and xDATA ***messageType***
- ***"timestamp"*** - time mark of metric
- ***"properties"*** - metric properties used for schedule\scenario\events

- ***"dataType"*** - value type
    1. Int8
    2. Int16
    3. Int32
    4. Int64
    5. UInt8
    6. UInt16
    7. UInt32
    8. UInt64
    9. Float
    10. Double 
    11. Boolean
    12. String
    13. DateTime 
    14. Text
    15. UUID
    16. DataSet
    17. Bytes
    18. File
    19. Template

- ***"value"*** - specific field for each type
    - int_value
    - long_value
    - float_value
    - double_value
    - boolean_value
    - string_value
    - bytes_value
    - dataset_value

## Node types
- [Node](box-node.md)

## Device types
- [16 Digital outputs](box-do.md)
- [16 Digital inputs](box-di.md)
- [8 Relay output](box-ro.md)
- [8 Multifunctional input-output](box-io.md)
- [Interfaces](box-if.md)
- [2 channel Dali](box-dali.md)
- [3-phase Energymeter](box-em.md)
- [2 channel Step motor driver](box-em.md)
- [2 channel Thermocontroller](box-tc.md)
- [2 channel Wiegand](box-wiegand.md)

## Functions
- [Scenario description and examples](scenario.md)
- [Schedule description and examples](schedule.md)
- [Events description and examples](events.md)
- [Virtual metrics description and examples](virtual.md)
- [Change server description and examples](change-server.md)