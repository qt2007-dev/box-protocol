# Schedule metrics

```json
{ "name": "schedule",
  "dataType": 12, /* String */
  "string_value": "set", 
  "properties":{  "keys": ["description", "points"],
                  "values": [ {"type":12, "string_value": "Schedule description"},
                              {"type":21, "propertysets_value": { "propertyset": [ { "keys": ["start", "name", "repeat", "delay"] } ] } } ] },
  "metadata":{"description":"[RWP]Schedule control metric, list of values = ['on', 'off', 'set', 'get'], schedule set and get in properties"} 
}
```
Действия в зависимости от значения метрики:  
- ***on*** - включает работу по расписание  
- ***off*** - выключает работу по расписанию  
- ***set*** - устанавливает расписание описанное в поле "properties"  
- ***get*** - запрашивает установленное расписание, возвращает метрику с полем "properties"  
    
Cвойство ***"start"*** может быть разных типов:  
- ***UInt64*** - Запуск сценария в указанный ***timestamp***  
- ***String*** - [***CRON***](cron.md) строка задания времени  
- ***PropertySet*** - Структура времени     
    - **year**  - Запуск в указанный год, если не указан, то каждый год   
    - **month**  - Запуск в указанный месяц, если не указан, то каждый месяц  
    - **day**  - Запуск в указанный день, если не указан, то каждый день  
    - **weekday**  - Запуск в указанный день недели, если не указан, игнорируется  
    - **hour**  - Запуск в указанный час, если не указан, то каждый час  
    - **minute**  - Запуск в указанную минуту, если не указана, то каждую минуту  
    - ""  -  Пустое поле, означает запуск каждую минуту бесконечно   

## Общий пример установки расписания по времени, по timestamp, и CRON строкой    
```json
{
"metrics": [
  { "name": "schedule",
    "dataType": 12, /* String */
    "string_value": "set", /* value = on/off/set/get */
    "properties":{  "keys": ["description", "points"],
                    "values": [ {"type":12, "string_value": "Super schedule for work"},
                                {"type":21, "propertysets_value":
                                    { "propertyset": [  /* Points array for start scenario */
                                        { "keys": ["start", "name", "repeat", "delay"],
                                          "values":[ {"type":20, "propertyset_value": { 
                                                                    "keys":["hour","minute"], 
                                                                    "values":[{"type":7,"int_value": 15}, {"type":7,"int_value": 30}]} },
                                                     {"type":12, "string_value": "name1"},   /* ScenarioName */
                                                     {"type":3, "int_value": 0},   /* "0" - not repeat, "-1" - repeat forever */
                                                     {"type":7, "int_value": 0}    /* delay before start scenario */ ] },
                                                                
                                        { "keys": ["start", "name", "repeat", "delay"],
                                          "values": [ {"type":8, "long_value": 1545345345345},
                                                      {"type":12, "string_value": "name2"},   /* ScenarioName */
                                                      {"type":3, "int_value": 0},   /* "0" - not repeat, "-1" - repeat forever */
                                                      {"type":7, "int_value": 0}    /* delay before start scenario */ ] },
                                                                
                                        { "keys": ["start", "name", "repeat", "delay"],
                                          "values": [ {"type":12, "string_value": "25 18 1 Jan * 2024"},
                                                      {"type":12, "string_value": "name3"},   /* ScenarioName */
                                                      {"type":3, "int_value": 0},   /* "0" - not repeat, "-1" - repeat forever */
                                                      {"type":7, "int_value": 0}    /* delay before start scenario */ ] }
                                ] } } 
    ] } } 
          ]
}
```

## Пример расписания для светильников dali c двумя точками, с запуском в определенный день, c повтором каждый год
1.  1 января в 15:00 выполняем сценарий "daliLampON"
2.  5 марта в 2:30 выполняем сценарий "daliLampOFF"

```json
{
"metrics": [
  { "name": "schedule",
    "dataType": 12, /* String */
    "string_value": "set", /* value = on/off/set/get */
    "properties":{  "keys": ["description", "points"],
                    "values": [ {"type":12, "string_value": "DaliLampDimSchedule"},
                                {"type":21, "propertysets_value":
                                    { "propertyset": [  /* Points array for start scenario */
                                        { "keys": ["start", "name", "repeat", "delay"],
                                          "values": [ {"type":20, "propertyset_value": { 
                                                                      "keys":["month", "day", "hour", "minute"], 
                                                                      "values":[{"type":7,"int_value": 1}, {"type":7,"int_value": 1}, {"type":7,"int_value": 15}, {"type":7,"int_value": 0}]} },
                                                      {"type":12, "string_value": "daliLampON"},   /* ScenarioName */
                                                      {"type":3, "int_value": 0},   /* "0" - not repeat, "-1" - repeat forever */
                                                      {"type":7, "int_value": 0}    /* delay before start scenario */ ] },

                                        { "keys": ["start", "name", "repeat", "delay"],
                                          "values": [ {"type":20, "propertyset_value": { 
                                                                      "keys":["month", "day", "hour", "minute"], 
                                                                      "values":[{"type":7,"int_value": 3}, {"type":7,"int_value": 5}, {"type":7,"int_value": 2}, {"type":7,"int_value": 30}]} },
                                                      {"type":12, "string_value": "daliLampOFF"},   /* ScenarioName */
                                                      {"type":3, "int_value": 0},   /* "0" - not repeat, "-1" - repeat forever */
                                                      {"type":7, "int_value": 0}    /* delay before start scenario */ ] }                                                                

                                ] } } 
  ] } } 
          ]
}
```

