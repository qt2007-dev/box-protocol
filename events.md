# Events metrics

## **event/list**
Отображает лист заданных событий ноды

```json
{  
"metrics": [
    { "name": "event/list",              
      "dataType": 16/* DataSet */, 
      "dataset_value":{ "num_of_columns": 3,
                        "columns": ["name", "version", "enabled"],
                        "types": [12, 7, 11], /* String, Uint32, Boolean */
                        "rows": [ {"elements":[{"string_value":"eventName1"},{"type": 7, "int_value": 1},{"boolean_value": true} ]},
                                  {"elements":[{"string_value":"eventName2"},{"type": 7, "int_value": 1},{"boolean_value": false} ]}  ] }, 
      "metadata":{"description":"[R]List of events names exist in node"} } ]  
}
```      
          

## **event/add**
Добавляет события описанное в поле "properties" метрики, с id равным value (значению метрики).
При успешном добавлении сценария обновляется метрика "event/list"


```json
{
"metrics": [
  { "name": "event/add",
    "dataType": 12, /* String */
    "string_value": "eventName1",
    "properties":{  "keys": ["version", "scenario", "enabled", "deadtime", "triggers", "logic", "conditions"],
                    "values": [ {"type": 7, "int_value": 1},
                                {"type":12, "string_value": "ScenarioName1"},
                                {"type":11, "boolean_value": true},
                                {"type":7,  "int_value": 200}, /* time between start scenario in ms, round to 100ms */
                                {"type":21, "propertysets_value":
                                    { "propertyset": [  /* Triggers array for start check conditions */
                                        { "keys": ["device", "metric"],
                                          "values":[ {"type":12, "string_value": "1245abcd"},
                                                     {"type":12, "string_value": "metricName1"} ] },   
                                                                
                                        { "keys": ["device", "metric"],
                                          "values":[ {"type":12, "string_value": "1245abcd"},
                                                     {"type":12, "string_value": "metricName2"} ] } 
                                ] } },

                                {"type":12, "string_value": "and"}, /* If several conditions are added, logic between them, values = ['and', 'or'] */
                                {"type":21, "propertysets_value":
                                    { "propertyset": [  /* Conditions array for start scenario */
                                        { "keys": ["device", "metric", "compare", "target"],
                                          "values":[ {"type":12, "string_value": "1245abcd"},
                                                     {"type":12, "string_value": "metricName1"}, 
                                                     {"type":12, "string_value": ">"},   /* values = ['=','<','>','>=','<=','!='] */
                                                     {"type":7, "int_value": 128} ] },   
                                                                
                                        { "keys": ["device", "metric", "compare", "target"],
                                          "values":[ {"type":12, "string_value": "1245abcd"},
                                                     {"type":12, "string_value": "metricName2"}, 
                                                     {"type":12, "string_value": "="},   /* values = ['=','<','>','>=','<=','!='] */
                                                     {"type":11, "boolean_value": true} ] } 
                                ] } } 
    ] } } 
          ]
}
```

>Пример событий для включения\включения света по одной кнопке

```json
{
"metrics": [
  { "name": "event/add",
    "dataType": 12, /* String */
    "string_value": "eventButtonLightON",
    "properties":{  "keys": ["version", "scenario", "enabled", "deadtime", "triggers", "logic", "conditions"],
                    "values": [ {"type": 7, "int_value": 1},
                                {"type":12, "string_value": "scenarioDaliON"},
                                {"type":11, "boolean_value": true},
                                {"type":7,  "int_value": 200}, 
                                {"type":21, "propertysets_value":
                                    { "propertyset": [  
                                        { "keys": ["device", "metric"],
                                          "values":[ {"type":12, "string_value": "deba0006"},
                                                     {"type":12, "string_value": "dali/0/device/0/instance/0/value"} ] }
                                ] } },

                                {"type":12, "string_value": "and"}, 
                                {"type":21, "propertysets_value":
                                    { "propertyset": [  
                                        { "keys": ["device", "metric", "compare", "target"],
                                          "values":[ {"type":12, "string_value": "deba0006"},
                                                     {"type":12, "string_value": "dali/0/device/0/instance/0/value"}, 
                                                     {"type":12, "string_value": "="},  
                                                     {"type":7, "string_value": "short-press"} ] },   
                                                                
                                        { "keys": ["device", "metric", "compare", "target"],
                                          "values":[ {"type":12, "string_value": "deba0006"},
                                                     {"type":12, "string_value": "dali/0/gear/0/dim"}, 
                                                     {"type":12, "string_value": "="},   
                                                     {"type":11, "int_value": 0} ] } 
                                ] } } 
    ] } } 
          ]
}
```

```json
{
"metrics": [
  { "name": "event/add",
    "dataType": 12, /* String */
    "string_value": "eventButtonLightOFF",
    "properties":{  "keys": ["version", "scenario", "enabled", "deadtime", "triggers", "logic", "conditions"],
                    "values": [ {"type": 7, "int_value": 1},
                                {"type":12, "string_value": "scenarioDaliOFF"},
                                {"type":11, "boolean_value": true},
                                {"type":7,  "int_value": 200}, 
                                {"type":12, "string_value": "and"}, 
                                {"type":21, "propertysets_value":
                                    { "propertyset": [  
                                        { "keys": ["device", "metric"],
                                          "values":[ {"type":12, "string_value": "deba0006"},
                                                     {"type":12, "string_value": "dali/0/device/0/instance/0/value"} ] }
                                ] } },

                                {"type":12, "string_value": "and"}, 
                                {"type":21, "propertysets_value":
                                    { "propertyset": [  
                                        { "keys": ["device", "metric", "compare", "target"],
                                          "values":[ {"type":12, "string_value": "deba0006"},
                                                     {"type":12, "string_value": "dali/0/device/0/instance/0/value"}, 
                                                     {"type":12, "string_value": "="},  
                                                     {"type":7, "string_value": "short-press"} ] },   
                                                                
                                        { "keys": ["device", "metric", "compare", "target"],
                                          "values":[ {"type":12, "string_value": "deba0006"},
                                                     {"type":12, "string_value": "dali/0/gear/0/dim"}, 
                                                     {"type":12, "string_value": "!="},   
                                                     {"type":11, "int_value": 0} ] } 
                                ] } }
    ] } } 
          ]
}
```
