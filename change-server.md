# Metric for change server

>>Пример смены сервера
```json
{
"metrics": [
  { "name": "connection/server",
    "dataType": 12, /* String */
    "string_value": "NewServerDomainNameOrIpAddress:ServerPort", 
    "properties":{  
        "keys": ["certificate"],
        "values": [ {   "type":12, 
                        "string_value": "-----BEGIN CERTIFICATE-----
                        MIIC1TCCAb2gAwIBAgIJAN5YK5q4bCK7MA0GCSqGSIb3DQEBBQUAMBoxGDAWBgNV
                        BAMTD3d3dy5leGFtcGxlLmNvbTAeFw0yMTA5MDYxNDAwNTBaFw0zMTA5MDQxNDAw
                        NTBaMBoxGDAWBgNVBAMTD3d3dy5leGFtcGxlLmNvbTCCASIwDQYJKoZIhvcNAQEB
                        BQADggEPADCCAQoCggEBANcFO8aSPs1P1Yghm03pRuX3+lIgxenl/eB+/zRHh/NO
                        nMF0xL/OEID+hPVVeIt6HCBPOXdiEWMrhil9XxOti0nf/LpVwphxkd8VwV0AoQd6
                        6bSQgFuf7rbCfmj/yt51cQDfKbp2bneJ0qEWoCh4qOHJPjU/0jirLTDI9tKBbJFW
                        IDNfzB4V961HQN1J9wq/6iIIReoC4OnbwbBP3LJq8XAf9ZWhNOOka+r1PicUyUFk
                        8BVolP5JTEEXMAk956+ZZ01OERT/WLepOaI4t7xhcaxajixQZvuWtYo13CfP2xZF
                        ZqVH0Vv7cqqidC56avAYLEpF8QK2d3b6t9eP/k4xTecCAwEAAaMeMBwwGgYDVR0R
                        BBMwEYIPd3d3LmV4YW1wbGUuY29tMA0GCSqGSIb3DQEBBQUAA4IBAQBCnYZ58rVI
                        pZH1+5AXezlhLDwMeVSeGTDlFTxJe8QPKHd4aqv+pzbhMBhrPzXflYETkWBI0WlG
                        XNx+JmqyXoyAw+/63zi6SOgV3oqOfscfWVdeNP72DcbeE8pMiDaU7kE45vjxQKYh
                        +eXRsVu2FY9bbYpizdrKjI101xjlHsCeE2fi/eOguNzmQPlcF99dR3WebJ9gCKQN
                        1J5LJypFvhBBJSUyCNrUYVTgcGUZV3YQd8oVV4ts3F47/QzJVcIblLJRAeeeg/tZ
                        w9I3hTujeizTBh81h1oiO4d6dbF4Ulxcj++wskQxteCBMpinbqN5/5Qhrn0QKhoE
                        BD2kb0nSiPEs
                        -----END CERTIFICATE-----"},                                
    ] } } 
          ]
}
```

>>После получения команды устройство отключится и попробует подключится к новому серверу, 
если у него не получиться устройство вернется на старый сервер


