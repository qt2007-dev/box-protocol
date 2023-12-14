# Events metrics


```json
{
"metrics": [
  { "name": "event/add",
    "dataType": 12, /* String */
    "string_value": "eventName1",
    "properties":{  "keys": ["scenario", "enabled", "deadtime", "logic", "triggers"],
                    "values": [ {"type":12, "string_value": "ScenarioName1"},
                                {"type":11, "boolean_value": true},
                                {"type":7,  "int_value": 200}, /* time between start scenario in ms, round to 100ms */
                                {"type":12, "string_value": "and"}, /* If several trigger are added, logic beetwen them, values = ['and', 'or'] */
                                {"type":21, "propertysets_value":
                                    { "propertyset": [  /* Triggers array for start scenario */
                                        { "keys": ["device", "metric", "compare", "target"],
                                          "values":[ {"type":12, "string_value": "1245abcd"},
                                                     {"type":12, "string_value": "metricName1"}, 
                                                     {"type":12, "string_value": ">"},   /* values = ['=','<','>','>=','<=','!='] */
                                                     {"type":7, "int_value": 128} ] },   
                                                                
                                        { "keys": ["device", "metric", "compare", "target"],
                                          "values":[ {"type":12, "string_value": "1245abcd"},
                                                     {"type":12, "string_value": "metricName1"}, 
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
    "properties":{  "keys": ["scenario", "enabled", "deadtime", "logic", "triggers"],
                    "values": [ {"type":12, "string_value": "scenarioDaliON"},
                                {"type":11, "boolean_value": true},
                                {"type":7,  "int_value": 200}, 
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
    "properties":{  "keys": ["scenario", "enabled", "deadtime", "logic", "triggers"],
                    "values": [ {"type":12, "string_value": "scenarioDaliOFF"},
                                {"type":11, "boolean_value": true},
                                {"type":7,  "int_value": 200}, 
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
