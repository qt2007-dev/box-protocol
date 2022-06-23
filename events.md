# Metrics for setup events


```json
{
"metrics": [
  { "name": "event/add",
    "dataType": 12, /* String */
    "string_value": "eventName1",
    "properties":{  "keys": ["scenario", "delay", "logic", "triggers"],
                    "values": [ {"type":12, "string_value": "ScenarioName1"},
                                {"type":7,  "int_value": 0}, /* delay before start scenario */
                                {"type":12, "string_value": "and"}, /* If several trigger are added, logic beetwen them, values = ['and', 'or'] */
                                {"type":21, "propertysets_value":
                                    { "propertyset": [  /* Triggers array for start scenario */
                                        { "keys": ["device", "metric", "compare", "target"],
                                          "values":[ {"type":12, "string_value": "1245abcd"},
                                                     {"type":12, "string_value": "metricName1"}, 
                                                     {"type":12, "string_value": ">"},   /* values = ['=','<','>','>=','<='] */
                                                     {"type":7, "int_value": 128} ] },   
                                                                
                                        { "keys": ["device", "metric", "compare", "target"],
                                          "values":[ {"type":12, "string_value": "1245abcd"},
                                                     {"type":12, "string_value": "metricName1"}, 
                                                     {"type":12, "string_value": "="},   /* values = ['=','<','>','>=','<='] */
                                                     {"type":11, "boolean_value": true} ] } 
                                ] } } 
    ] } } 
          ]
}
```
