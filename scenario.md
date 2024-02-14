# Scenario metrics

## **scenario/list**
Отображает лист заданных сценариев ноды

```json
{  
"metrics": [
    { "name": "scenario/list",              
      "dataType": 16/* DataSet */, 
      "dataset_value":{ "num_of_columns": 3,
                        "columns": ["name", "version", "enabled"],
                        "types": [12, 7, 11], /* String, Uint32, Boolean */
                        "rows": [ {"elements":[{"string_value":"scenarioName1"},{"type": 7, "int_value": 1},{"boolean_value": true} ]},
                                  {"elements":[{"string_value":"scenarioName2"},{"type": 7, "int_value": 1},{"boolean_value": false} ]}  ] },                                  
      "metadata":{"description":"[R]List of scenario names exist in node"} } ]
}
```      
                            
## **scenario/add**
Добавляет сценарий описанный в поле "properties" метрики, с id равным value (значению метрики).
При успешном добавлении сценария обновляется метрика "scenario/list"   

- ***actions*** - поле описания действий может быть двух типов
    - **String** - в этом случае ожидается python скрипт управления   
    - **PropertySetList** - лист с последовательными действиями   

- ***object*** - объект управления
    - **scenario** - запускает сценарий с именем **{name}** с количеством повторений **{value}**
    - **event** - ждет срабатывание события с именем **{name}** указанное время в **{value}** в миллисекундах
    - **time** - объект с именем "delay" ждет время указанное в **{value}** в миллисекундах
    - **{groupName}** - изменяет метрику с именем **{name}** на значение указанное в **{value}**, во всех устройствах состоящих в группе **{groupName}**
    - **{deviceID}** - изменяет метрику с именем **{name}** на значение указанное в **{value}**, устройства с ID **{deviceID}**
    - **{nodeID}** - изменяет метрику с именем **{name}** на значение указанное в **{value}**, устройства с ID **{nodeID}**

- ***name*** - при управлении метрикой может быть двух типов
    - **String** - имя метрики
    - **Uint32** - alias метрики

### Примеры
0. Общий прием добавления сценария  
- Сценарий описанный скриптом  
```json
{   
"metrics": [
  { "name": "scenario/add",
    "dataType": 12, /* String */ 
    "string_value": "ScenarioName1", /* scenarioName */ 
    "properties":{  "keys": ["version", "precision", "enabled", "actions"],
                    "values": [ {"type": 7, "int_value": 1},
                                {"type":12, "string_value":"100ms"},                                 
                                {"type":11, "boolean_value": true},
                                {"type":12, "string_value": "m1 = Metric('deviceId1', 'metricName1')
                                                             m2 = Metric('deviceId2', 'metricName2')
                                                             if m1.value == 'some_value':
                                                              m2.value = 'some_value2'"}
  ] } }        
        ]                            
}
```    
- Сценарий описанный последовательными действиями
```json
{   
"metrics": [
  { "name": "scenario/add",
    "dataType": 12, /* String */ 
    "string_value": "ScenarioName1", /* scenarioName */ 
    "properties":{  "keys": ["version", "precision", "enabled", "actions"],
                    "values": [ {"type": 7, "int_value": 1},
                                {"type":12, "string_value":"100ms"},                                
                                {"type":11, "boolean_value": true},
                                {"type":21, "propertysets_value": 
                                    { "propertyset":[   /* Actions array START */
                                    
                                      { "keys":["object", "name", "value"],
                                        "values":[ {"type": 12, "string_value": "time"}, {"type": 12, "string_value": "delay"}, {"type": 7, "int_value": 100}  ] },

                                      { "keys":["object", "name", "value"],
                                        "values":[ {"type": 12, "string_value": "1245abcd"}, {"type": 12, "string_value": "metricName1"}, {"type": 12, "string_value": "some_value"}  ] },

                                    ] }  /* Actions array END */      
                                }
  ] } }        
        ]                            
}
```    

1. Сценарий управления 16 выходами модуля цифровых выходов DO  
- Сценарий описанный скриптом  
```python
out = [ Metric('1245abcd', f'out/{i}') for i in range(16)]

delay(100)
for o in out:
  o.value = False

delay(100)
for o in out:
  o.value = True
```
- Сценарий описанный последовательными действиями
```json
{"propertyset":[   /* Actions array START */
                                    
  { "keys":["object", "name", "value"],
    "values":[ {"type": 12, "string_value": "time"}, {"type": 12, "string_value": "delay"}, {"type": 7, "int_value": 100}  ] },

  { "keys":["object", "name", "value"],
    "values":[ {"type": 12, "string_value": "1245abcd"}, {"type": 12, "string_value": "out/0"}, {"type": 11, "boolean_value": false}  ] },

  { "keys":["object", "name", "value"],
    "values":[ {"type": 12, "string_value": "1245abcd"}, {"type": 12, "string_value": "out/1"}, {"type": 11, "boolean_value": false}  ] },

  { "keys":["object", "name", "value"],
    "values":[ {"type": 12, "string_value": "1245abcd"}, {"type": 12, "string_value": "out/2"}, {"type": 11, "boolean_value": false}  ] },

  { "keys":["object", "name", "value"],
    "values":[ {"type": 12, "string_value": "1245abcd"}, {"type": 12, "string_value": "out/3"}, {"type": 11, "boolean_value": false}  ] },

  { "keys":["object", "name", "value"],
    "values":[ {"type": 12, "string_value": "1245abcd"}, {"type": 12, "string_value": "out/4"}, {"type": 11, "boolean_value": false}  ] },

  { "keys":["object", "name", "value"],
    "values":[ {"type": 12, "string_value": "1245abcd"}, {"type": 12, "string_value": "out/5"}, {"type": 11, "boolean_value": false}  ] },

  { "keys":["object", "name", "value"],
    "values":[ {"type": 12, "string_value": "1245abcd"}, {"type": 12, "string_value": "out/6"}, {"type": 11, "boolean_value": false}  ] },

  { "keys":["object", "name", "value"],
    "values":[ {"type": 12, "string_value": "1245abcd"}, {"type": 12, "string_value": "out/7"}, {"type": 11, "boolean_value": false}  ] },

  { "keys":["object", "name", "value"],
    "values":[ {"type": 12, "string_value": "time"}, {"type": 12, "string_value": "delay"}, {"type": 7, "int_value": 100}  ] },

  { "keys":["object", "name", "value"],
    "values":[ {"type": 12, "string_value": "1245abcd"}, {"type": 12, "string_value": "out/8"}, {"type": 11, "boolean_value": true}  ] },

  { "keys":["object", "name", "value"],
    "values":[ {"type": 12, "string_value": "1245abcd"}, {"type": 12, "string_value": "out/9"}, {"type": 11, "boolean_value": true}  ] },

  { "keys":["object", "name", "value"],
    "values":[ {"type": 12, "string_value": "1245abcd"}, {"type": 12, "string_value": "out/10"}, {"type": 11, "boolean_value": true}  ] },

  { "keys":["object", "name", "value"],
    "values":[ {"type": 12, "string_value": "1245abcd"}, {"type": 12, "string_value": "out/11"}, {"type": 11, "boolean_value": true}  ] },

  { "keys":["object", "name", "value"],
    "values":[ {"type": 12, "string_value": "1245abcd"}, {"type": 12, "string_value": "out/12"}, {"type": 11, "boolean_value": true}  ] },

  { "ke/*  */ys":["object", "name", "value"],
    "values":[ {"type": 12, "string_value": "1245abcd"}, {"type": 12, "string_value": "out/13"}, {"type": 11, "boolean_value": true}  ] },

  { "keys":["object", "name", "value"],
    "values":[ {"type": 12, "string_value": "1245abcd"}, {"type": 12, "string_value": "out/14"}, {"type": 11, "boolean_value": true}  ] },

  { "keys":["object", "name", "value"],
    "values":[ {"type": 12, "string_value": "1245abcd"}, {"type": 12, "string_value": "out/15"}, {"type": 11, "boolean_value": true}  ] }
] }  /* Actions array END */   
```    

2. Сценарий димирования на яркость 254 с фейдом 5 dali светильника на шине 0 с адресом 0  
- Сценарий описанный скриптом  
```python
fade = Metric('1245abcd', 'dali/0/gear/0/fade/time')
dim = Metric('1245abcd', 'dali/0/gear/0/dim')
fade.value = 5
dim.value = 254
```
- Сценарий описанный последовательными действиями
```json
{ "propertyset":[   /* Actions array START */
  { "keys":["object", "name", "value"],
    "values":[ {"type": 12, "string_value": "1245abcd"}, {"type": 12, "string_value": "dali/0/gear/0/fade/time"}, {"type": 5, "int_value": 5}  ] },

  { "keys":["object", "name", "value"],
    "values":[ {"type": 12, "string_value": "1245abcd"}, {"type": 12, "string_value": "dali/0/gear/0/dim"}, {"type": 5, "int_value": 254}  ] }                                      
] }  /* Actions array END */     
```   
3. Сценарий димирования на яркость 0 с фейдом 5 dali светильника на шине 0 с адресом 0  
- Сценарий описанный скриптом  
```python
fade = Metric('1245abcd', 'dali/0/gear/0/fade/time')
dim = Metric('1245abcd', 'dali/0/gear/0/dim')
fade.value = 5
dim.value = 0
```
- Сценарий описанный последовательными действиями
```json
{ "propertyset":[   /* Actions array START */
  { "keys":["object", "name", "value"],
    "values":[ {"type": 12, "string_value": "1245abcd"}, {"type": 12, "string_value": "dali/0/gear/0/fade/time"}, {"type": 5, "int_value": 5}  ] },

  { "keys":["object", "name", "value"],
    "values":[ {"type": 12, "string_value": "1245abcd"}, {"type": 12, "string_value": "dali/0/gear/0/dim"}, {"type": 5, "int_value": 0}  ] }                                      
] }  /* Actions array END */     
``` 

4. Сценария димирования на яркость 254 с фейдом 2 группы dali 2  
- Сценарий описанный скриптом 
```python
cmd = Metric('1245abcd', 'dali/0/cmd')
cmd.value = [ ('group', 2, 'fade-time', 2), ('group', 2, 'dim', 254) ]
```

- Сценарий описанный последовательными действиями
```json
{ "propertyset":[   /* Actions array START */
  { "keys":["object", "name", "value"],
    "values":[ {"type": 12, "string_value": "1245abcd"}, 
                {"type": 12, "string_value": "dali/0/cmd"}, 
                {"type": 20, "propertyset_value": { "keys":["addr-type", "addr", "cmd", "value"], 
                                                    "values":[ {"type": 12, "string_value": "group"} 
                                                              {"type":  7, "int_value": 2},
                                                              {"type": 12, "string_value": "fade-time"} 
                                                              {"type":  7, "int_value": 2},
                                                              ]} }  ] },
  { "keys":["object", "name", "value"],
    "values":[ {"type": 12, "string_value": "1245abcd"}, 
                {"type": 12, "string_value": "dali/0/cmd"}, 
                {"type": 20, "propertyset_value": { "keys":["addr-type", "addr", "cmd", "value"], 
                                                    "values":[ {"type": 12, "string_value": "group"} 
                                                              {"type":  7, "int_value": 2},
                                                              {"type": 12, "string_value": "dim"} 
                                                              {"type":  7, "int_value": 254},
                                                              ]} }  ] }                                  
] }  /* Actions array END */ 
```   

5. Сценарий который по выполнению события запускает другие сценарии  
- Сценарий описанный скриптом 
```python
s1 = Scenario('ScenarioName1')
s2 = Scenario('ScenarioName2')
e = Event('eventName1')

if e.wait(200000):
  for i in range(3):
    s1.run()
  delay(2000)
  s2.run()
```
- Сценарий описанный последовательными действиями
```json
{ "propertyset":[   /* Actions array START */
  { "keys":["object", "name", "value"],
    "values":[ {"type": 12, "string_value": "event"}, {"type": 12, "string_value": "eventName1"}, {"type": 7, "int_value": 200000}  ] },

  { "keys":["object", "name", "value"],
    "values":[ {"type": 12, "string_value": "scenario"}, {"type": 12, "string_value": "scenarioName1"}, {"type": 7, "int_value": 3}  ] },
    
  { "keys":["object", "name", "value"],
    "values":[ {"type": 12, "string_value": "time"}, {"type": 12, "string_value": "delay"}, {"type": 7, "int_value": 2000}  ] },                                        
    
    { "keys":["object", "name", "value"],
    "values":[ {"type": 12, "string_value": "scenario"}, {"type": 12, "string_value": "scenarioName2"}, {"type": 7, "int_value": 0}  ] }
] }  /* Actions array END */  
```  

## **scenario/execute**
Запускает сценарий с id равным value (значению метрики).
После завершения метрика обнуляется, запись нулевого сценария в эту метрику останавливает запущенный сценарий
### Пример
```json
{
"metrics": [
  {"name": "scenario/execute", "dataType": 12, "string_value": "scenarioName1"}/* String */ 
  ]
}
```

## **scenario/enable**
Включает сценарий, включенный сценарии выполняют действия при запуске.
### Пример
```json
{
"metrics": [
  {"name": "scenario/enable", "dataType": 12, "string_value": "scenarioName1"}/* String */ 
  ]
}
```
## **scenario/disable**
Выключает сценарий, выключенный сценарии не выполняют действий при запуске.
### Пример
```json
{
"metrics": [
  {"name": "scenario/disable", "dataType": 12, "string_value": "scenarioName1"}/* String */ 
  ]
}
```

## **scenario/delete**
Удаляет сценарий с id равным value (значению метрики).
При успешном удалении сценария обновляется метрика "scenario/list"
### Пример
```json
{
"metrics": [
  {"name": "scenario/delete", "dataType": 12, "string_value": "scenarioName1"}/* String */ 
  ]
}
```

## **scenario/get**
Запрашивает описания сценария с id равным value (значению метрики).
Если такой сценарий записан, то возвращает метрику "scenario/get" с описанием сценария в поле "properties", 
формат описание поля совпадает с задание сценария
### Пример
```json
{
"metrics": [
  {"name": "scenario/get", "dataType": 12, "string_value": "scenarioName2"}/* String */ 
  ]
}   
