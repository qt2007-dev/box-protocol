Расписание -> Сценарий (расписание запускает сценарии)

## Metrics for setup scenario

**Scenario list**
  Отображает лист(id и имен) заданных сценариев ноды

```json
								

{
  "timestamp": 1486144502122,
  "seq": 0,
  "metrics": [
      { "name": "scenario/list",
        "timestamp": 1479123452194,
        "dataType": 16, /* DataSet */
        "dataset_value":{ "num_of_columns": 3,
                          "columns": ["name", "last", "next"],
                          "types": [12, 8, 8], /* String, UInt64, UInt64 */
                          "rows": [ {"elements":[{"string_value":"scenarioName1"},{"long_value":151515151515},{"long_value":151515151515} ]},
                                    {"elements":[{"string_value":"scenarioName2"},{"long_value":151515151515},{"long_value":151515151515} ]}  ] }
                                    /* value = list of scenarioId and names, last - last used time, next - next time to be used */} ]
}
```      
                            
**Scenario add**
  Добавляет сценарий описанный в поле "properties" метрики, с id равным value (значению метрики).
    При успешном добавлении сценария обновляется метрика "scenario/list"

Пример группового сценария на базе двух релейных выходов c двумя точками переключения.

```json
{
  "timestamp": 1486144502122,
  "seq": 0,
  "metrics": [
      { "name": "scenario/add",
        "alias": 1,
        "timestamp": 1479123452194,
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
                                                                                              "values": [ {"type": 7, "int_value": 5000},
                                                                                                          {"type": 11, "boolean_value": true},{"type": 11, "boolean_value": false},{"type": 11, "boolean_value": false},{"type": 11, "boolean_value": false},
                                                                                                          {"type": 11, "boolean_value": true},{"type": 11, "boolean_value": false},{"type": 11, "boolean_value": false},{"type": 11, "boolean_value": false},
                                                                                                          {"type": 11, "boolean_value": true},{"type": 11, "boolean_value": false},{"type": 11, "boolean_value": false},{"type": 11, "boolean_value": false},
                                                                                                          {"type": 11, "boolean_value": true},{"type": 11, "boolean_value": false},{"type": 11, "boolean_value": false},{"type": 11, "boolean_value": false}  ] },
                                                                                            
                                                                                            { "keys": ["duration","out/0","out/1","out/2","out/3","out/4","out/5","out/6","out/7","out/8","out/9","out/10","out/11","out/12","out/13","out/14","out/15"],
                                                                                              "values": [ {"type": 7, "int_value": 10000},
                                                                                                          {"type": 11, "boolean_value": false},{"type": 11, "boolean_value": false},{"type": 11, "boolean_value": true},{"type": 11, "boolean_value": false},
                                                                                                          {"type": 11, "boolean_value": false},{"type": 11, "boolean_value": false},{"type": 11, "boolean_value": true},{"type": 11, "boolean_value": false},
                                                                                                          {"type": 11, "boolean_value": false},{"type": 11, "boolean_value": false},{"type": 11, "boolean_value": true},{"type": 11, "boolean_value": false},
                                                                                                          {"type": 11, "boolean_value": false},{"type": 11, "boolean_value": false},{"type": 11, "boolean_value": true},{"type": 11, "boolean_value": false}  ] } ]
                                                                                      } } ] },
                                                        { "keys":["id", "type", "actions"],
                                                          "values":[  {"type": 7, "int_value": 2},
                                                                      {"type": 12, "string_value": "16 Digital Output"},
                                                                      {"type": 21, "propertysets_value":
                                                                                      { "propertyset":[   /* Device actions array */
                                                                                            { "keys": ["duration","out/0","out/1","out/2","out/3","out/4","out/5","out/6","out/7","out/8","out/9","out/10","out/11","out/12","out/13","out/14","out/15"],
                                                                                              "values": [ {"type": 7, "int_value": 5000},
                                                                                                          {"type": 11, "boolean_value": true},{"type": 11, "boolean_value": false},{"type": 11, "boolean_value": false},{"type": 11, "boolean_value": false},
                                                                                                          {"type": 11, "boolean_value": true},{"type": 11, "boolean_value": false},{"type": 11, "boolean_value": false},{"type": 11, "boolean_value": false},
                                                                                                          {"type": 11, "boolean_value": true},{"type": 11, "boolean_value": false},{"type": 11, "boolean_value": false},{"type": 11, "boolean_value": false},
                                                                                                          {"type": 11, "boolean_value": true},{"type": 11, "boolean_value": false},{"type": 11, "boolean_value": false},{"type": 11, "boolean_value": false}  ] },
                                                                                            
                                                                                            { "keys": ["duration","out/0","out/1","out/2","out/3","out/4","out/5","out/6","out/7","out/8","out/9","out/10","out/11","out/12","out/13","out/14","out/15"],
                                                                                              "values": [ {"type": 7, "int_value": 10000},
                                                                                                          {"type": 11, "boolean_value": false},{"type": 11, "boolean_value": false},{"type": 11, "boolean_value": true},{"type": 11, "boolean_value": false},
                                                                                                          {"type": 11, "boolean_value": false},{"type": 11, "boolean_value": false},{"type": 11, "boolean_value": true},{"type": 11, "boolean_value": false},
                                                                                                          {"type": 11, "boolean_value": false},{"type": 11, "boolean_value": false},{"type": 11, "boolean_value": true},{"type": 11, "boolean_value": false},
                                                                                                          {"type": 11, "boolean_value": false},{"type": 11, "boolean_value": false},{"type": 11, "boolean_value": true},{"type": 11, "boolean_value": false}  ] } ]
                                                                                      } } ] } 
                                                                  ]  /* Device array with actions END */
                                                  } }
                                  ] } }        
              ]                            
}
```    

Пример сценариев для димирования dali светильниом.

```json
{
  "timestamp": 1486144502122,
  "seq": 0,
  "metrics": [
      { "name": "scenario/add",
        "alias": 1,
        "timestamp": 1479123452194,
        "dataType": 12, /* String */ 
        "string_value": "daliLampON", /* scenarioName */ 
        "properties":{  "keys": ["precision", "devices"],
                        "values": [ {"type":12, "string_value":"100ms"},
                                    {"type":21, "propertysets_value":   
                                                  { "propertyset":[   /* Device array with actions START */
                                                        { "keys":["id", "type", "actions"],
                                                          "values":[  {"type": 7, "int_value": 10012002},
                                                                      {"type": 12, "string_value": "NEMA"},
                                                                      {"type": 21, "propertysets_value":
                                                                                      { "propertyset":[   /* Device actions array */
                                                                                            { "keys": ["duration", "dali/0/dim", "dali/0/fade/time"],
                                                                                              "values": [ {"type": 7, "int_value": 0},
                                                                                                          {"type": 5, "int_value": 254},{"type": 5, "int_value": 5} ] } ] 
                                                                                      } } ] } 
                                                                  ]  /* Device array with actions END */
                                                  } }
                                  ] } }        
              ]                            
}
```   

```json
{
  "timestamp": 1486144502122,
  "seq": 0,
  "metrics": [
      { "name": "scenario/add",
        "alias": 1,
        "timestamp": 1479123452194,
        "dataType": 12, /* String */ 
        "string_value": "daliLampOFF", /* scenarioName */ 
        "properties":{  "keys": [ "precision", "devices"],
                        "values": [ {"type":12, "string_value":"100ms"},
                                    {"type":21, "propertysets_value":   
                                                  { "propertyset":[   /* Device array with actions START */
                                                        { "keys":["id", "type", "actions"],
                                                          "values":[  {"type": 7, "int_value": 10012002},
                                                                      {"type": 12, "string_value": "NEMA"},
                                                                      {"type": 21, "propertysets_value":
                                                                                      { "propertyset":[   /* Device actions array */
                                                                                            { "keys": ["duration", "dali/0/dim", "dali/0/fade/time"],
                                                                                              "values": [ {"type": 7, "int_value": 0},
                                                                                                          {"type": 5, "int_value": 0},{"type": 5, "int_value": 5} ] } ] 
                                                                                      } } ] } 
                                                                  ]  /* Device array with actions END */
                                                  } }
                                  ] } }        
              ]                            
}
```


**Scenario delete**
  Удаляет сценарий с id равным value (значению метрики).
    При успешном удалении сценария обновляется метрика "scenario/list"

```json
{
  "timestamp": 1486144502122,
  "seq": 0,
  "metrics": [
      { "name": "scenario/delete",
        "alias": 1,
        "timestamp": 1479123452194,
        "dataType": 12, /* String */ 
        "string_value": "name1" /* scenarioName */  } ]
}
```

**Scenario get**
  Запрашивает описания сценария с id равным value (значению метрики).
    Если такой сценарий записан, то возвращает метрику "scenario/get" с описанием сценария в поле "properties", 
        формат описание поля совпадает с задание сценария

```json
{
  "timestamp": 1486144502122,
  "seq": 0,
  "metrics": [
      { "name": "scenario/get",
        "alias": 1,
        "timestamp": 1479123452194,
        "dataType": 12, /* String */ 
        "string_value": "name1" /* scenarioName */ }  ]
}
```    

## Metrics for setup schedule

  Дейсвия в зависимости от значения метрики:
    **on** - включает работу по расписание
    **off** - выключает работу по расписанию
    **set** - устанавливает расписание описанное в поле "properties"
    **get** - запрашивает установленное расписание, возвращает метрику с полем "properties"
    
  Возможные значиения свойства "start":
    **now**  - С нулевым значением означает запуск сразу после получение значения **on**    
    
    **timestamp**   -  Запуск сценария в указаный timestamp, не может быть одновременно с другими полями    
    
    **year**  - Запуск в указаный год, если не указан, то каждый год 
    **month**  - Запуск в указаный месяц, если не указан, то каждый месяц 
    **day**  - Запуск в указаный день, если не указан, то каждый день 
    **weekday**  - Запуск в указаный день недели, если не указан, игнорируется
    **hour**  - Запуск в указаный час, если не указан, то каждый час
    **minute**  - Запуск в указаную минуту, если не указана, то каждую минуту
		
    ** **  -  Пустое поле, означает запуск каждую минуту бесконечно 

Общий пример расписания по времени и по timestamp   

```json
{
  "timestamp": 1486144502122,
  "seq": 0,
  "metrics": [
      { "name": "schedule",
        "alias": 5,
        "timestamp": 1479123452194,
        "dataType": 12, /* String */
        "string_value": "set", /* value = on/off/set/get */
        "properties":{  "keys": ["description", "points"],
                        "values": [ {"type":12, "string_value": "Super schedule for work"},
                                    {"type":21, "propertysets_value":
                                                  { "propertyset": [  /* Points array for start scenario */
                                                        { "keys": ["start", "name", "repeat", "delay"],
                                                          "values": [
                                                                {"type":20, "propertyset_value": { "keys":["hour","minute"], 
                                                                                                   "values":[{"type":7,"int_value": 15}, {"type":7,"int_value": 30}]} },
                                                                {"type":12, "string_value": "name1"},   /* ScenarioName */
                                                                {"type":3, "int_value": 0},   /* "0" - not repeat, "-1" - repeat forever */
                                                                {"type":7, "int_value": 0}    /* delay before start scenario */ ] },
                                                                
                                                        { "keys": ["start", "name", "repeat", "delay"],
                                                          "values": [
                                                                {"type":20, "propertyset_value": { "keys":["timestamp"], 
                                                                                                   "values":[{"type":8,"long_value": 1545345345345}]} },
                                                                {"type":12, "string_value": "name2"},   /* ScenarioName */
                                                                {"type":3, "int_value": 0},   /* "0" - not repeat, "-1" - repeat forever */
                                                                {"type":7, "int_value": 0}    /* delay before start scenario */ ] }
                                                                    ] } } 
                                  ] } } ]
}
```

Пример расписания для светильниов dali c двумя точками, с запуском в определенный день, c повтором каждый год
  1 января в 15:00 выполняем сценаарий "daliLampON"
  5 марта в 2:30 выполняем сценаарий "daliLampOFF"

```json
{
  "timestamp": 1486144502122,
  "seq": 0,
  "metrics": [
      { "name": "schedule",
        "alias": 5,
        "timestamp": 1479123452194,
        "dataType": 12, /* String */
        "string_value": "set", /* value = on/off/set/get */
        "properties":{  "keys": ["description", "points"],
                        "values": [ {"type":12, "string_value": "DaliLampDimSchedule"},
                                    {"type":21, "propertysets_value":
                                                  { "propertyset": [  /* Points array for start scenario */
                                                        { "keys": ["start", "name", "repeat", "delay"],
                                                          "values": [
                                                                {"type":20, "propertyset_value": { "keys":["month", "day", "hour", "minute"], 
                                                                                                   "values":[{"type":7,"int_value": 1}, {"type":7,"int_value": 1}, {"type":7,"int_value": 15}, {"type":7,"int_value": 0}]} },
                                                                {"type":12, "string_value": "daliLampON"},   /* ScenarioName */
                                                                {"type":3, "int_value": 0},   /* "0" - not repeat, "-1" - repeat forever */
                                                                {"type":7, "int_value": 0}    /* delay before start scenario */ ] },
                                                        { "keys": ["start", "name", "repeat", "delay"],
                                                          "values": [
                                                                {"type":20, "propertyset_value": { "keys":["month", "day", "hour", "minute"], 
                                                                                                   "values":[{"type":7,"int_value": 3}, {"type":7,"int_value": 5}, {"type":7,"int_value": 2}, {"type":7,"int_value": 30}]} },
                                                                {"type":12, "string_value": "daliLampOFF"},   /* ScenarioName */
                                                                {"type":3, "int_value": 0},   /* "0" - not repeat, "-1" - repeat forever */
                                                                {"type":7, "int_value": 0}    /* delay before start scenario */ ] }                                                                

                                                                    ] } } 
                                  ] } } ]
}
```



**Schedule state**

Метрика показывает запущеные сценании их шаги и повторы

**name** - Имя сценария
**actioNumber** - Текущий шаг в сценарии
**actionQuantity** - Количество шагов в сценарии
**repeatNumber** - Текущий повтор сценария
**repeatQuantity** - Количество повторов сценария, "-1" - повторять бесконечно 

```json
{
  "timestamp": 1486144502122,
  "seq": 0,
  "metrics": [
      { "name": "schedule/state",
        "timestamp": 1479123452194,
        "dataType": 16, /* DataSet */
        "dataset_value":{ "num_of_columns": 5,
                          "columns": ["name", "actioNumber", "actionQuantity", "repeatNumber", "repeatQuantity"],
                          "types": [12, 3, 3, 3, 3], /* String, Int32, Int32, Int32, Int32 */
                          "rows": [ {"elements":[ {"string_value":"scenarioName1"},{"int_value":2},{"int_value":10},{"int_value":3},{"int_value":25} ]},
                                    {"elements":[ {"string_value":"scenarioName2"},{"int_value":2},{"int_value":10},{"int_value":3},{"int_value":-1} ]}  ] }
      } ]
}
```
