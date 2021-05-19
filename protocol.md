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

