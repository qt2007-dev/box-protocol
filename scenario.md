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

>>Пример группового сценария на базе двух релейных выходов c двумя точками переключения.
```json
{   
"metrics": [
  { "name": "scenario/add",
    "dataType": 12, /* String */ 
    "string_value": "name1", /* scenarioName */ 
    "properties":{  "keys": ["precision", "devices"],
                     "values": [ {"type":12, "string_value":"100ms"},
                                 {"type":21, "propertysets_value":   
                                    { "propertyset":[   /* Device array with actions START */
                                        { "keys":["id", "type", "actions"],
                                          "values":[  {"type": 7, "int_value": 1},
                                                      {"type": 12, "string_value": "16 Digital Output"},
                                                      {"type": 21, "propertysets_value":
                                                        { "propertyset":[   /* Device actions array */
                                                            { "keys": ["duration","out/0","out/1","out/2","out/3","out/4","out/5","out/6","out/7","out/8","out/9","out/10","out/11","out/12","out/13","out/14","out/15"],
                                                              "values":[ {"type": 7, "int_value": 5000},
                                                                         {"type": 11, "boolean_value": true},{"type": 11, "boolean_value": false},{"type": 11, "boolean_value": false},{"type": 11, "boolean_value": false},
                                                                         {"type": 11, "boolean_value": true},{"type": 11, "boolean_value": false},{"type": 11, "boolean_value": false},{"type": 11, "boolean_value": false},
                                                                         {"type": 11, "boolean_value": true},{"type": 11, "boolean_value": false},{"type": 11, "boolean_value": false},{"type": 11, "boolean_value": false},
                                                                         {"type": 11, "boolean_value": true},{"type": 11, "boolean_value": false},{"type": 11, "boolean_value": false},{"type": 11, "boolean_value": false}] },
                                                                                            
                                                            { "keys": ["duration","out/0","out/1","out/2","out/3","out/4","out/5","out/6","out/7","out/8","out/9","out/10","out/11","out/12","out/13","out/14","out/15"],
                                                              "values":[ {"type": 7, "int_value": 10000},
                                                                         {"type": 11, "boolean_value": false},{"type": 11, "boolean_value": false},{"type": 11, "boolean_value": true},{"type": 11, "boolean_value": false},
                                                                         {"type": 11, "boolean_value": false},{"type": 11, "boolean_value": false},{"type": 11, "boolean_value": true},{"type": 11, "boolean_value": false},
                                                                         {"type": 11, "boolean_value": false},{"type": 11, "boolean_value": false},{"type": 11, "boolean_value": true},{"type": 11, "boolean_value": false},
                                                                         {"type": 11, "boolean_value": false},{"type": 11, "boolean_value": false},{"type": 11, "boolean_value": true},{"type": 11, "boolean_value": false}] }
                                                                        ]
                                        } } ] },
                                        { "keys":["id", "type", "actions"],
                                          "values":[  {"type": 7, "int_value": 2},
                                                      {"type": 12, "string_value": "16 Digital Output"},
                                                      {"type": 21, "propertysets_value":
                                                        { "propertyset":[   /* Device actions array */
                                                            { "keys": ["duration","out/0","out/1","out/2","out/3","out/4","out/5","out/6","out/7","out/8","out/9","out/10","out/11","out/12","out/13","out/14","out/15"],
                                                              "values":[ {"type": 7, "int_value": 5000},
                                                                         {"type": 11, "boolean_value": true},{"type": 11, "boolean_value": false},{"type": 11, "boolean_value": false},{"type": 11, "boolean_value": false},
                                                                         {"type": 11, "boolean_value": true},{"type": 11, "boolean_value": false},{"type": 11, "boolean_value": false},{"type": 11, "boolean_value": false},
                                                                         {"type": 11, "boolean_value": true},{"type": 11, "boolean_value": false},{"type": 11, "boolean_value": false},{"type": 11, "boolean_value": false},
                                                                         {"type": 11, "boolean_value": true},{"type": 11, "boolean_value": false},{"type": 11, "boolean_value": false},{"type": 11, "boolean_value": false}] },
                                                                                            
                                                            { "keys": ["duration","out/0","out/1","out/2","out/3","out/4","out/5","out/6","out/7","out/8","out/9","out/10","out/11","out/12","out/13","out/14","out/15"],
                                                              "values":[ {"type": 7, "int_value": 10000},
                                                                         {"type": 11, "boolean_value": false},{"type": 11, "boolean_value": false},{"type": 11, "boolean_value": true},{"type": 11, "boolean_value": false},
                                                                         {"type": 11, "boolean_value": false},{"type": 11, "boolean_value": false},{"type": 11, "boolean_value": true},{"type": 11, "boolean_value": false},
                                                                         {"type": 11, "boolean_value": false},{"type": 11, "boolean_value": false},{"type": 11, "boolean_value": true},{"type": 11, "boolean_value": false},
                                                                         {"type": 11, "boolean_value": false},{"type": 11, "boolean_value": false},{"type": 11, "boolean_value": true},{"type": 11, "boolean_value": false}] } 
                                                                        ]
                                        } } ] } 
                                                    ]  /* Device array with actions END */
                                } }
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
    "properties":{  "keys": ["precision", "devices"],
                    "values": [ {"type":12, "string_value":"100ms"},
                                {"type":21, "propertysets_value":   
                                    { "propertyset":[   /* Device array with actions START */
                                        { "keys":["id", "type", "actions"],
                                          "values":[  {"type": 7, "int_value": 10012002},
                                                      {"type": 12, "string_value": "dali"},
                                                      {"type": 21, "propertysets_value":
                                                          { "propertyset":[   /* Device actions array */
                                                              { "keys": ["duration", "dali/0/gear/0/dim", "dali/0/gear/0/fade/time"],
                                                                "values": [{"type": 7, "int_value": 0},{"type": 5, "int_value": 254},{"type": 5, "int_value": 5}] } ] 
                                                                                      } } ] } 
                                                     ]  /* Device array with actions END */
                                } }
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
    "properties":{  "keys": ["precision", "devices"],
                    "values": [ {"type":12, "string_value":"100ms"},
                                {"type":21, "propertysets_value":   
                                    { "propertyset":[   /* Device array with actions START */
                                        { "keys":["id", "type", "actions"],
                                          "values":[  {"type": 7, "int_value": 10012002},
                                                      {"type": 12, "string_value": "dali"},
                                                      {"type": 21, "propertysets_value":
                                                          { "propertyset":[   /* Device actions array */
                                                              { "keys": ["duration", "dali/0/gear/0/dim", "dali/0/gear/0/fade/time"],
                                                                "values": [{"type": 7, "int_value": 0},{"type": 5, "int_value": 0},{"type": 5, "int_value": 5}] } ] 
                                                                                      } } ] } 
                                                     ]  /* Device array with actions END */
                                } }
  ] } }        
        ]                            
}
```   


## **scenario/delete**
>Удаляет сценарий с id равным value (значению метрики).
>При успешном удалении сценария обновляется метрика "scenario/list"
>При отправки специального значение "_all" удаляет все сценарии 

>>Пример
```json
{
"metrics": [
  {"name": "scenario/delete", "dataType": 12, "string_value": "scenarioName1"}/* String */ 
  ]
}
```

>>Пример удаления всех сценариев
```json
{
"metrics": [
  {"name": "scenario/delete", "dataType": 12, "string_value": "_all"}/* String */ 
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
