 # Metrics for setup virtual metrics    

>Пример создания виртуальной метрики
Создание метрики вызовет перерождение устройства, на котором была создана метрика

```json
{
"metrics": [
    { "name": "virtual/add",              
      "dataType": 16/* DataSet */, 
      "dataset_value":{ "num_of_columns": 4,
                        "columns": ["id", "name", "dataType", "description"],
                        "types": [12, 12, 7, 12], /* String, String, Uint32, String */
                        "rows": [ {"elements":[{"string_value":"deba0006"}, /* nodeId or deviceId for add virtual metric */
                                               {"string_value": "virtual/name1"}, /* virtual metric name, name must begin with 'virtual/' */
                                               {"int_value": 12}  /* metric data type */
                                               {"string_value": "Virtual metric description"} ]},
                                   ] }, 
      "metadata":{"description":"[W]Add virtual metric to specific device or node"} }
          ]
}
```

>Пример удаления виртуальной метрики
Удаление метрики вызовет перерождение устройства, на котором была удалена метрика

```json
{
"metrics": [      
    { "name": "virtual/delete",              
      "dataType": 16/* DataSet */, 
      "dataset_value":{ "num_of_columns": 2,
                        "columns": ["id", "name"],
                        "types": [12, 12], /* String, String*/
                        "rows": [ {"elements":[{"string_value":"deba0006"}, /* nodeId or deviceId for delete virtual metric */
                                               {"string_value": "virtual/name1"} /* virtual metric name, name must begin with 'virtual/' */ ]},
                                   ] }, 
      "metadata":{"description":"[W]Delete virtual metric from specific device or node"} }
      
          ]
}
```      