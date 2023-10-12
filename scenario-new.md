# Metrics for setup scenario

## **scenario/list**
>Отображает лист(id и имен) заданных сценариев ноды

```json
{  
"metrics": [
  { "name": "scenario/list",
    "dataType": 16, /* DataSet */
    "dataset_value":{ "num_of_columns": 3,
                      "columns": ["name", "last", "next"],
                      "types": [12, 8, 8], /* String, UInt64, UInt64 */
                      "rows": [ {"elements":[{"string_value":"scenarioName1"}, {"long_value":151515151515}, {"long_value":151515151515}] },
                                {"elements":[{"string_value":"scenarioName2"}, {"long_value":151515151515}, {"long_value":151515151515}] }  ] }
                                /* value = list of scenarioId and names, last - last used time, next - next time to be used */} ]
}
```      
                            
## **scenario/add**
>Добавляет сценарий описанный в поле "properties" метрики, с id равным value (значению метрики).
>При успешном добавлении сценария обновляется метрика "scenario/list"
**object** - объект управления
>- **scenario** - запускает сценарий с именем **{name}** с количеством повторений **{value}**
>- **event** - ждет срабатывание события с именем **{name}** указаное время в **{value}** в миллисекундах
>- **time** - объект с именем "delay" ждет время указаное в **{value}** в миллисекундах
>- **{groupName}** - изменяет метрику с именем **{name}** на значение указаное в **{value}**, во всех устройствах состоящих в группе **{groupName}**
>- **{deviceID}** - изменяет метрику с именем **{name}** на значение указаное в **{value}**, устройства с ID **{deviceID}**

**name** - при управлении метрикой может быть двух типов
>- **String** - имя метрики
>- **Uint32** - alias метрики


>>Пример группового сценария на базе двух релейных выходов c двумя точками переключения.
```json
{   
"metrics": [
  { "name": "scenario/add",
    "dataType": 12, /* String */ 
    "string_value": "name1", /* scenarioName */ 
    "properties":{  "keys": ["precision", "actions"],
                    "values": [ {"type":12, "string_value":"100ms"},
                                {"type":21, "propertysets_value": 
                                    { "propertyset":[   /* Actions array START */
                                    
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

                                      { "keys":["object", "name", "value"],
                                        "values":[ {"type": 12, "string_value": "1245abcd"}, {"type": 12, "string_value": "out/13"}, {"type": 11, "boolean_value": true}  ] },

                                      { "keys":["object", "name", "value"],
                                        "values":[ {"type": 12, "string_value": "1245abcd"}, {"type": 12, "string_value": "out/14"}, {"type": 11, "boolean_value": true}  ] },

                                      { "keys":["object", "name", "value"],
                                        "values":[ {"type": 12, "string_value": "1245abcd"}, {"type": 12, "string_value": "out/15"}, {"type": 11, "boolean_value": true}  ] },

                                    ] }  /* Actions array END */      
                                }
  ] } }        
        ]                            
}
```    

>>Пример сценариев для димирования dali светильников
```json
{
"metrics": [
  { "name": "scenario/add",
    "dataType": 12, /* String */ 
    "string_value": "daliLampON", /* scenarioName */ 
    "properties":{  "keys": ["precision", "actions"],
                    "values": [ {"type":12, "string_value":"100ms"},
                                {"type":21, "propertysets_value": 
                                    { "propertyset":[   /* Actions array START */
                                      { "keys":["object", "name", "value"],
                                        "values":[ {"type": 12, "string_value": "1245abcd"}, {"type": 12, "string_value": "dali/0/fade/time"}, {"type": 5, "int_value": 5}  ] },

                                      { "keys":["object", "name", "value"],
                                        "values":[ {"type": 12, "string_value": "1245abcd"}, {"type": 12, "string_value": "dali/0/dim"}, {"type": 5, "int_value": 254}  ] }                                      
                                    ] }  /* Actions array END */     
                                }
  ] } }        
        ]                            
}
```   

```json
{
"metrics": [
  { "name": "scenario/add",
    "dataType": 12, /* String */ 
    "string_value": "daliLampOFF", /* scenarioName */ 
    "properties":{  "keys": ["precision", "actions"],
                    "values": [ {"type":12, "string_value":"100ms"},
                                {"type":21, "propertysets_value": 
                                    { "propertyset":[   /* Actions array START */ 
                                      { "keys":["object", "name", "value"],
                                        "values":[ {"type": 12, "string_value": "1245abcd"}, {"type": 12, "string_value": "dali/0/fade/time"}, {"type": 5, "int_value": 5}  ] },

                                      { "keys":["object", "name", "value"],
                                        "values":[ {"type": 12, "string_value": "1245abcd"}, {"type": 12, "string_value": "dali/0/dim"}, {"type": 5, "int_value": 0}  ] }
                                    ] } /* Actions array END */     
                                }
  ] } }        
        ]                            
}
```   

>>Пример сценария для который по выполнению события запускает другие сценарии
```json
{
"metrics": [
  { "name": "scenario/add",
    "dataType": 12, /* String */ 
    "string_value": "daliLampON", /* scenarioName */ 
    "properties":{  "keys": ["precision", "actions"],
                    "values": [ {"type":12, "string_value":"100ms"},
                                {"type":21, "propertysets_value": 
                                    { "propertyset":[   /* Actions array START */
                                      { "keys":["object", "name", "value"],
                                        "values":[ {"type": 12, "string_value": "event"}, {"type": 12, "string_value": "eventName1"}, {"type": 5, "int_value": 200000}  ] },

                                      { "keys":["object", "name", "value"],
                                        "values":[ {"type": 12, "string_value": "scenario"}, {"type": 12, "string_value": "scenarioName1"}, {"type": 5, "int_value": 3}  ] },
                                        
                                      { "keys":["object", "name", "value"],
                                        "values":[ {"type": 12, "string_value": "time"}, {"type": 12, "string_value": "delay"}, {"type": 7, "int_value": 2000}  ] },                                        
                                        
                                       { "keys":["object", "name", "value"],
                                        "values":[ {"type": 12, "string_value": "scenario"}, {"type": 12, "string_value": "scenarioName2"}, {"type": 5, "int_value": 0}  ] },                                       
                                        
                                    ] }  /* Actions array END */     
                                }
  ] } }        
        ]                            
}
```  

## **scenario/execute**
>Запускает сценарий с id равным value (значению метрики).
>После завершения метрика обнуляется, запись нулевого сценария в эту метрику останавливает запущеный сценарий
>>Пример
```json
{
"metrics": [
  {"name": "scenario/execute", "dataType": 12, "string_value": "scenarioName1"}/* String */ 
  ]
}
```


## **scenario/delete**
>Удаляет сценарий с id равным value (значению метрики).
>При успешном удалении сценария обновляется метрика "scenario/list"

>>Пример
```json
{
"metrics": [
  {"name": "scenario/delete", "dataType": 12, "string_value": "scenarioName1"}/* String */ 
  ]
}
```

## **scenario/get**
>Запрашивает описания сценария с id равным value (значению метрики).
>Если такой сценарий записан, то возвращает метрику "scenario/get" с описанием сценария в поле "properties", 
>формат описание поля совпадает с задание сценария

>>Пример
```json
{
"metrics": [
  {"name": "scenario/get", "dataType": 12, "string_value": "scenarioName2"}/* String */ 
  ]
}   
