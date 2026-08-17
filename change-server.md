# Metric for change server

>>Пример смены брокера tcp
```json
{
"metrics": [
    { "name": "connection/server",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 8,
                        "columns": ["address", "port", "tls"],
                        "types": [12, 6, 11], /* String, UInt16, Boolean   */
                        "rows": [ {"elements":[{"string_value":"some.broker.com"},{"int_value":1883},{"boolean_value":false}]} ] }, 
      "metadata":{"description":"[RWP]mqtt broker"} }
          ]
}
```

>>Пример смены брокера tcp с авторизацией
```json
{
"metrics": [
    { "name": "connection/server",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 8,
                        "columns": ["address", "port", "tls", "username", "password"],
                        "types": [12, 6, 11, 12, 12,], /* String, UInt16, Boolean, String, String  */
                        "rows": [ {"elements":[{"string_value":"some.broker.com"},{"int_value":1883},{"boolean_value":false},
                        {"string_value":"mqtt-username"},{"string_value":"mqtt-password"}]} ] }, 
      "metadata":{"description":"[RWP]mqtt broker"} }
          ]
}
```
>>Пример смены брокера tls с авторизацией
```json
{
"metrics": [
    { "name": "connection/server",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 8,
                        "columns": ["address", "port", "tls", "ca-certificate", "username", "password"],
                        "types": [12, 6, 11, 12, 12, 12], /* String, UInt16, Boolean, String, String, String */
                        "rows": [ {"elements":[{"string_value":"some.broker.com"},{"int_value":1883},{"boolean_value":true},
                        {"string_value":"-----BEGIN CERTIFICATE-----
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
                        {"string_value":"mqtt-username"},{"string_value":"mqtt-password"}]} ] }, 
      "metadata":{"description":"[RWP]mqtt broker"} }
          ]
}
```

>>Пример смены брокера mtls с авторизацией
```json
{
"metrics": [
    { "name": "connection/server",
      "dataType": 16, /* DataSet */
      "dataset_value":{ "num_of_columns": 8,
                        "columns": ["address", "port", "tls", "ca-certificate", "client-certificate", "client-key", "username", "password"],
                        "types": [12, 6, 11 , 12, 12, 12, 12, 12], /* String, UInt16, Boolean, String, String, String, String, String   */
                        "rows": [ {"elements":[{"string_value":"some.broker.com"},{"int_value":1883},{"boolean_value":true},
                        {"string_value":"-----BEGIN CERTIFICATE-----
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
                        {"string_value":"-----BEGIN CERTIFICATE-----
                          MIIFBTCCAu2gAwIBAgIUcQPrhUjvQf24dBxuSJb7bh3wfZMwDQYJKoZIhvcNAQEL
                          BQAwEjEQMA4GA1UECgwHVGVzdE9yZzAeFw0yNjA4MTQwODU3MzBaFw0yNzA4MTQw
                          ODU3MzBaMBIxEDAOBgNVBAoMB1Rlc3RPcmcwggIiMA0GCSqGSIb3DQEBAQUAA4IC
                          DwAwggIKAoICAQCxIYYJXBWqFH0RrARJjlUceiWrN/b3I11YzgQNGl6KBTY1S2B5
                          RsmH49y2BP1R0BOhzJySQZuTNMTj0iiLgLaneoCBVyDKflq5by3K494yoZPYdjqV
                          fGVt0NaGvJ4+/J4i5cVYE9nrZcrlFSFiWvbeIdK44zTOtHZk9eU1rpnlMDLP+2Wi
                          u2UGO6GqM7b84JumtMoWdioHgCyzy37nEpAKUSAn/e5Ybvv1/q1R5ax1cpwGMpcM
                          837CZQnm55MUXGK+j+DvKklC3wg4R/Aq3pcDCs9MpeY/03a18UXr8XQu55GC6q2h
                          /HoLm/Xuuz9Xv2UYNDG+Hx0qW2BeWCNEDjN20hPNLLVpkdytA0o/hgtLFrbLtCpu
                          CxD007PjBBdUwEDGwko4yk/75ErPv49/8Q2UMnAS51zUKzIWUHgfyq0iMwrDKfWr
                          hpDIv8l7CjqAoU5PDhn5ezQwWYP86xX0NOj6tsihebvD/zB9a8c1jjwhemM4048/
                          7yt9Hkq737jGPgLzj2PaEKud4bFxnypRVOVZCd2CUKY05m+vIMcf/yd6zyPt26iG
                          IcYdyLUlbEWK9s8ChnoSWVP/OLLmWICpDmkz3K8AIlD5Z6A4YCoLETjw2NGdCF02
                          ty+dPUrjNAYDJWNNzyUSJBa3cCVuEFatDpCqlfYqvHTppC1vqZGT8Z8wlwIDAQAB
                          o1MwUTAdBgNVHQ4EFgQUnvL2xdVLNcz4LALD5A0taInBlMkwHwYDVR0jBBgwFoAU
                          nvL2xdVLNcz4LALD5A0taInBlMkwDwYDVR0TAQH/BAUwAwEB/zANBgkqhkiG9w0B
                          AQsFAAOCAgEAeM/F2z1dc+oUvkenvJQ22mf0ogg19BoWJIwn11p6c0DMyjhBueSa
                          Y8W6eeNj9YyLVRmOgG9Py4cz6q5rvJ4rUEuuHOol7WOLBqnckSvm2rBfJvJLfydA
                          PyckhfK9NhzOTrXkFnkd89NYoV9bU6UFu2HZDZ7xQsLn88sc7RPfVzXM8wfmG2yV
                          3YBtr3jA8b7EDnA2fHDL/yRDZEcXPmLBQHUrc7tXX7hjTJXSD0djeo976v7abicf
                          R3Ax/yvqvusrUeTwAMhxQxD/Wi78S6QoN8WGEk4te0K2yygnkCfN6xcBK675rmIq
                          Iqu27jycO2gesBGz8XDz0yVzVAKIpM0mBO7oPFUM75gDzYeXRI/JnQnlXGBuGimv
                          j4dIl9OHzhu+k+NLwlj6WSvKiyKVR5GPASp0GqMKEFNWWn8BZ4Twx+aLE0L174XN
                          z+wMq9ge+R+PMNSQloH/EeTlnTIW+QIbasgqyTK0wZCGNnVRlrbI5/Bzysx/llg7
                          ZvXKf9eHTdB3BxlBfLwgiQHwnX44F7PwByBSUqezlpHtQFfxmWfFusZu30wXi1d8
                          dqYBI4GKyIVCdFOgNLIk1iYjx9+bNCUn5YuxA1uHjE02p7e9d26RpmtDikZ6Ntcu
                          PCcXhssLGZNpST3fnmDzJ7wLATPmjUANXFaIwGqGFRqX9u/CB0YA7K0=
                          -----END CERTIFICATE-----"},
                        {"string_value":"-----BEGIN PRIVATE KEY-----
                          MIIJQwIBADANBgkqhkiG9w0BAQEFAASCCS0wggkpAgEAAoICAQCxIYYJXBWqFH0R
                          rARJjlUceiWrN/b3I11YzgQNGl6KBTY1S2B5RsmH49y2BP1R0BOhzJySQZuTNMTj
                          0iiLgLaneoCBVyDKflq5by3K494yoZPYdjqVfGVt0NaGvJ4+/J4i5cVYE9nrZcrl
                          FSFiWvbeIdK44zTOtHZk9eU1rpnlMDLP+2Wiu2UGO6GqM7b84JumtMoWdioHgCyz
                          y37nEpAKUSAn/e5Ybvv1/q1R5ax1cpwGMpcM837CZQnm55MUXGK+j+DvKklC3wg4
                          R/Aq3pcDCs9MpeY/03a18UXr8XQu55GC6q2h/HoLm/Xuuz9Xv2UYNDG+Hx0qW2Be
                          WCNEDjN20hPNLLVpkdytA0o/hgtLFrbLtCpuCxD007PjBBdUwEDGwko4yk/75ErP
                          v49/8Q2UMnAS51zUKzIWUHgfyq0iMwrDKfWrhpDIv8l7CjqAoU5PDhn5ezQwWYP8
                          6xX0NOj6tsihebvD/zB9a8c1jjwhemM4048/7yt9Hkq737jGPgLzj2PaEKud4bFx
                          nypRVOVZCd2CUKY05m+vIMcf/yd6zyPt26iGIcYdyLUlbEWK9s8ChnoSWVP/OLLm
                          WICpDmkz3K8AIlD5Z6A4YCoLETjw2NGdCF02ty+dPUrjNAYDJWNNzyUSJBa3cCVu
                          EFatDpCqlfYqvHTppC1vqZGT8Z8wlwIDAQABAoICAHE+OH5FZAhfnvIsYnVQTPOu
                          1+RWHEs2TdiXpZlm8WgWGukJrrz6V5/MOvAX0oh6mgKIWNVcooUDaJkqZAeEG8KJ
                          HB0Uwf8Ttxb0kHc1JXqDOI1cUOn/JK2HpY9wiU9FnCg9c+RylJDdfFDnKHfEJi4v
                          u5O+lqVMVKEJYCfo37TaErJLTFg0rErG1v2EoImdY4W58bVYiFhRRsMP56r9gB9I
                          bGGFA9t/4RANaWuBhbd0tXF06IM8LR9FD4aTKMIMqoigXbMp+rqI8q1guJf/xNYK
                          FCwxqDnIDQ4XGZfVv2y5WZs0RBva2YAQjrO4/K8xywUlYWPmanQJBVxrxugcmCNe
                          kW4Rojs7jykro3aUI5Gdyzjv74uLV3H3WPfR+WSrgDvck2W7DtiWTTcVTHQw211T
                          s8sRZQVPrnA2LjHYhnCMagx0jxzm8ckkx8VY88rbKHENtGwf4ttHAvHt7FMGuej8
                          rymgIKWdMsi0zWo9vWloniRoH4d5DRf5lBrQzJ51oVUB2DfH5EDylSgboA1B3Ot6
                          xOgS5UfDQg+lUxYQ3sGiSrqCMmj1pE/4YjgSGc3br6MqVxBmrxzDTf0xOik4H3+2
                          rf+WRnFPiEd69Md8g/CmJ18LEMUyXgJv3C9ndIO0nOQkrZgU3AJQZobCBqSyBBn2
                          W6Nb23jo65Wna2+UqoIBAoIBAQDpVbpDTrdup1th42nDj36qJW2o7PkSnGb72c84
                          3sI+5DDHo2CuYa6dMBPcY3/nZII2lWIemkNLbdD36HkM2sb9XrTu4EPL7ehO5c/y
                          0/wby/o5QTT6srFPUd9b/AfPsWuoSBDI/WJdepqpTyKBfDXnEEVr7j2gJApZ3ZxO
                          +KthAIsgTH/csYbRHTT6d76nsPemiOHh+H8hHYg7aYkNwcEyCA4ffmTc6MvPbqQo
                          ZYNesJGpgXJar2Su25HJVNUjD8TrwB0cy38IZ6st0cQYWowBwudr+lN0skPC8p8c
                          16UbA3KPM+KFAl6Y5xExYTA/irwvCdhqsUTCA8mEmlPpl0GXAoIBAQDCVjBeCCOt
                          /jJcb16G3jsj0vDXE56Jfi5zOMF7L4myCLG82SOmRkZasz9oGKQRtC1OmB4/o/Ha
                          TMFTK3EzrjcxSBE+0cWEIaaxS20oH1tBXoziD0NavyBJrsVIlDIXT0eBdzvCthkP
                          EdjQsTVG1TNAO1FDkYqIPTDsLU8L2cPbO5GNfiwtHxGBdyrwJ3so9D4M0VTSufyq
                          yVt2pJ8NFSHJqQhteBqb3kgmnCUjPJO49O5P+h4M249MuyqmYXOyypvOJqzJxB6b
                          Z/69/3kI/X+hrMQZ2Uc8Ve+Af/LIIy9opBNHzRV6+B/LxScq2RJrJTbYPYfHPBvg
                          yPGQu3PFB2kBAoIBAH1lSNhrMUESR5XvtSMXtqaRvsENuT07OE0Y3LhfXlyWHXDs
                          aETO0hw/fizufApKhX/3/+caWBftSGQyVvuFh3Matnm5pDWwASyFbJ+/NLlrgWnL
                          lUE1Tvylrzer1jbTzlt9fyfEpFxAS2W51X1o1z76C5TZT90EAVwSMLJwCQn0VNBi
                          zEQ6U42F+LayK4/LFww0e9AIz6loSZJEQRdXjQ/qLEzYjDP8F6u+dhIPm+4DTgSe
                          QGpj3+PotAxSvsg87UMU15Bl/Dr0G5ZgKNY9swgvSldJDBimxKu7366MZXqC+8nh
                          xFZe05+wbhjvdhJv6HoO/HM6GQ17I41TsszSMLkCggEBAJ8rEpBhoD+I3FyjBsv1
                          xoBv67xsoEPCqm7KxIWNiPzdbB3dxvoPwt3UxBERZYfuh9FAfD3pnFQM26awBRas
                          ER53BVDrZRf0q9+4hF4BWK+wrjkVATiZI+vVjlYEswYuc8WRD8xJczrJhkhfa+Bp
                          DIIGU2fBE7LEU4aNEZoGMQklv/AgsDQAp0jffraVz6Tabtv2s7+of06ufxAsguyn
                          KzZNEM8AOOMC6xtcdnpmyiMJ0QqGNAiZ58OT5LnDRYzhrzzopkrXK65jPd0GGm8H
                          mXqk0zTMpjC/vdsEcKgFUXYmNHhxe69s/DXcc1j/07sYDtSLiOLg04CHdHrzXT25
                          9QECggEBAJNdlJi4o3mPHHzzzcp6PxEY7jzZoglgaMbeXU1XRpDgB6HWVddnoGEB
                          tf7QRdOiLfpExl6P3o+cJbadNFClsckRlOtk2fGf2ANwVvfSYvzSTZU2qvpK3lCm
                          keUkPBDY6uuuoKzJUOIfWLdiylCIiVf6IDXwzVqRnjEOvIaM6QxspKu/WgA+YsCv
                          2Zir6BpZCpXadrsZKX5/WNx0gEKW9NERZukJhi0zxeSboa2COJAjG1FTPKqtjETV
                          P74DTmFfZaz6wfjkUqOeosWuO5135L5Oqgphn+HwH/57NdZQEn9xciLmDtZBIO59
                          3eDR4eYcmo4XRSPOjy5+rusEt0e+e60=
                          -----END PRIVATE KEY-----"},
                        {"string_value":"mqtt-username"},{"string_value":"mqtt-password"}]} ] }, 
      "metadata":{"description":"[RWP]mqtt broker"} }
          ]
}
```

>>После получения команды устройство отключится и попробует подключится к новому серверу, 
если у него не получиться устройство вернется на старый сервер


