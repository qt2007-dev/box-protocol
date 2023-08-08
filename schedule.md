# Metrics for setup schedule

## **schedule**
>Действия в зависимости от значения метрики:
1. **on** - включает работу по расписание
2. **off** - выключает работу по расписанию
3. **set** - устанавливает расписание описанное в поле "properties"
4. **get** - запрашивает установленное расписание, возвращает метрику с полем "properties"
    
>Возможные значения свойства "start":

1. **now**  - С нулевым значением означает запуск сразу после получение значения **on**    
2. **timestamp**   -  Запуск сценария в указанный timestamp, не может быть одновременно с другими полями    
3. **year**  - Запуск в указанный год, если не указан, то каждый год 
4. **month**  - Запуск в указанный месяц, если не указан, то каждый месяц 
5. **day**  - Запуск в указанный день, если не указан, то каждый день 
6. **weekday**  - Запуск в указанный день недели, если не указан, игнорируется
7. **hour**  - Запуск в указанный час, если не указан, то каждый час
8. **minute**  - Запуск в указанную минуту, если не указана, то каждую минуту
9. * *  -  Пустое поле, означает запуск каждую минуту бесконечно 

>>Общий пример установки расписания по времени и по timestamp   
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
                                          "values": [ {"type":20, "propertyset_value": { 
                                                                      "keys":["timestamp"], 
                                                                      "values":[{"type":8,"long_value": 1545345345345}]} },
                                                      {"type":12, "string_value": "name2"},   /* ScenarioName */
                                                      {"type":3, "int_value": 0},   /* "0" - not repeat, "-1" - repeat forever */
                                                      {"type":7, "int_value": 0}    /* delay before start scenario */ ] }
                                ] } } 
    ] } } 
          ]
}
```

>>Пример расписания для светильников dali c двумя точками, с запуском в определенный день, c повтором каждый год
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

