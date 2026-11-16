## BOX device digital output birth example
> spBv1.0/box/DBIRTH/abba2020/deba0001 

```json
{
"timestamp": 1486144502122,
"seq": 0,
"metrics": [
    { "name": "bdSeq",                          "dataType": 8/* UInt64 */,   "long_value": 0,                      "metadata":{"description":"[R]Birth-death sequence, 'online' - [BIRTH > DEATH], 'offline' - [BIRTH <= DEATH]"} },
    { "name": "control/reboot",                 "dataType": 11/* Boolean */, "boolean_value": false,               "metadata":{"description":"[W]Software reboot, send 'true' for reboot"} },
    { "name": "control/rebirth",                "dataType": 11/* Boolean */, "boolean_value": false,               "metadata":{"description":"[W]Rebirth, send 'true' for receive birth message again"} },
    { "name": "control/firmware/new",           "dataType": 17/* Bytes */,   "bytes_value":"", "is_null": true,    "metadata":{"description":"[W]Receive new firmware, firmware send in Base64 format, in birth always null"} },
    { "name": "control/metrics/save",           "dataType": 11/* Boolean */, "boolean_value": true,                "metadata":{"description":"[RWP]Save metrics states after reboot, send 'true' for enable"} },
    { "name": "control/metrics/metadata",       "dataType": 11/* Boolean */, "boolean_value": true,                "metadata":{"description":"[RWP]Show metrics metadata in birth, send 'true' for enable"} },
    { "name": "control/alias",                  "dataType": 12/* String */,  "string_value": "do",                 "metadata":{"description":"[RWP]Global alias, can be used instead id in topics and scenarios"} },
  
    { "name": "info/hardware/vendor",           "dataType": 12/* String */,  "string_value": "QuintTech" ,         "metadata":{"description":"[R]Vendor name, hardcoded by vendor"} },
    { "name": "info/hardware/model",            "dataType": 12/* String */,  "string_value": "stm32g474ce",        "metadata":{"description":"[R]Mcu model, hardcoded by vendor"} },
    { "name": "info/firmware/version",          "dataType": 12/* String */,  "string_value": "0.1.220527",         "metadata":{"description":"[R]Firmware version, MAJOR.MINOR.buildOrCommit"} },
    { "name": "info/type",                      "dataType": 12/* String */,  "string_value": "16 Digital outputs", "metadata":{"description":"[R]Device type, hardcoded by vendor"} },
    { "name": "info/id",                        "dataType": 12/* String */,  "string_value": "deba0001",           "metadata":{"description":"[R]Short device id"} },
    { "name": "info/error",                     "dataType": 12/* String */,  "string_value": "",                   "metadata":{"description":"[R]Last error message"} },
    { "name": "info/warning",                   "dataType": 12/* String */,  "string_value": "",                   "metadata":{"description":"[R]Last warning message"} },
  
    { "name": "sensors/temperature",            "dataType": 1/* Int8 */,     "int_value": 22,                      "metadata":{"description":"[R]Temperature sensor in mcu, value in Celsius"} },  
  
    { "name": "bitmask",                        "dataType": 6/* UInt16 */,   "int_value": 0,                       "metadata":{"description":"[RWP]Bitmask of digital outputs, [0-15] out"} },  

    { "name": "ref/mode/const",
      "dataType": 19, /* Template */
      "template_value":{ "version": "mode",
                         "is_definition": true,
                         "metrics":[
                          { "name": "polarity",  "dataType": 12/* String */,   "metadata":{"description":"[RWP]Pin polarity, values = ['high','low']"} }
                        ] }, 
      "metadata":{"description":"Template definition of const mode"} },

    { "name": "ref/mode/pulse",
      "dataType": 19, /* Template */
      "template_value":{ "version": "mode",
                         "is_definition": true,
                         "metrics":[
                          { "name": "duration",  "dataType": 7/* UInt32 */,    "metadata":{"description":"[RWP]Pulse duration"} },
                          { "name": "polarity",  "dataType": 12/* String */,   "metadata":{"description":"[RWP]Pulse polarity, values = ['high','low']"} }
                        ] }, 
      "metadata":{"description":"Template definition of pulse mode"} },

    { "name": "ref/mode/pwm",
      "dataType": 19, /* Template */
      "template_value":{ "version": "mode",
                         "is_definition": true,
                         "metrics":[
                          { "name": "period",    "dataType": 7/* UInt32 */,    "metadata":{"description":"[RWP]PWM period, in ms"} },7
                          { "name": "duty",      "dataType": 7/* UInt32 */,    "metadata":{"description":"[RWP]PWM duty, in percent"} },
                          { "name": "polarity",  "dataType": 12/* String */,   "metadata":{"description":"[RWP]PWM polarity, values = ['high','low']"} }
                        ] }, 
      "metadata":{"description":"Template definition of pwm mode"} },

    { "name": "out/0",                          "dataType": 11/* Boolean */, "boolean_value": false,               "metadata":{"description":"[RWP]Digital output 0 control"} },
    { "name": "out/0/mode",
      "dataType": 19, /* Template */
      "template_value":{ "version": "mode",
                         "template_ref": "ref/mode/const",
                         "is_definition": true,
                         "metrics":[
                          { "name": "polarity",  "dataType": 12/* String */, "string_value": "high",               "metadata":{"description":"[RWP]PWM polarity, values = ['high','low']"} }
                        ] }, 
      "metadata":{"description":"Template definition of const mode"} },
    
    { "name": "out/1",                          "dataType": 11/* Boolean */, "boolean_value": false,               "metadata":{"description":"[RWP]Digital output 1 control"} },
    { "name": "out/1/mode",
      "dataType": 19, /* Template */
      "template_value":{ "version": "mode",
                         "template_ref": "ref/mode/pulse",
                         "is_definition": true,
                         "metrics":[
                          { "name": "duration",  "dataType": 7/* UInt32 */,    "metadata":{"description":"[RWP]Pulse duration"} },
                          { "name": "polarity",  "dataType": 12/* String */,   "metadata":{"description":"[RWP]Pulse polarity, values = ['high','low']"} }
                        ] }, 
      "metadata":{"description":"Template definition of pulse mode"} },

    { "name": "out/2",                          "dataType": 11/* Boolean */, "boolean_value": false,               "metadata":{"description":"[RWP]Digital output 2 control"} },
    { "name": "out/2/mode",
      "dataType": 19, /* Template */
      "template_value":{ "version": "mode",
                         "template_ref": "ref/mode/pwm",
                         "is_definition": true,
                         "metrics":[
                          { "name": "period",    "dataType": 7/* UInt32 */,    "metadata":{"description":"[RWP]PWM period, in ms"} },7
                          { "name": "duty",      "dataType": 7/* UInt32 */,    "metadata":{"description":"[RWP]PWM duty, in percent"} },
                          { "name": "polarity",  "dataType": 12/* String */,   "metadata":{"description":"[RWP]PWM polarity, values = ['high','low']"} }
                        ] }, 
      "metadata":{"description":"Template definition of PWM mode"} },

    /* 3...14 repeated */ 
    //{% for do_number in range(1,15) %}
    { "name": "out/${do_number}$",                          "dataType": 11/* Boolean */, "boolean_value": false,               "metadata":{"description":"[RWP]Digital output ${do_number}$ control"} },
    { "name": "out/${do_number}$/mode",
      "dataType": 19, /* Template */
      "template_value":{ "version": "mode",
                         "template_ref": "ref/mode/const",
                         "is_definition": true,
                         "metrics":[
                          { "name": "polarity",  "dataType": 12/* String */, "string_value": "high",               "metadata":{"description":"[RWP]PWM polarity, values = ['high','low']"} }
                        ] }, 
      "metadata":{"description":"Template definition of const mode"} },
    //{% endfor %}

    { "name": "out/15",                          "dataType": 11/* Boolean */, "boolean_value": false,               "metadata":{"description":"[RWP]Digital output 15 control"} },
    { "name": "out/15/mode",
      "dataType": 19, /* Template */
      "template_value":{ "version": "mode",
                         "template_ref": "ref/mode/const",
                         "is_definition": true,
                         "metrics":[
                          { "name": "polarity",  "dataType": 12/* String */, "string_value": "high",               "metadata":{"description":"[RWP]PWM polarity, values = ['high','low']"} }
                        ] }, 
      "metadata":{"description":"Template definition of const mode"} },

    
  ]
}
```

## BOX device digital output death example
> spBv1.0/box/DDEATH/abba2020/deba0001  

```json
{
"timestamp": 1486144502122,
"metrics": [  
    { "name": "bdSeq",                          "dataType": 8/* Uint64 */,   "long_value": 0,                    "metadata":{"description":"[R]Birth-death sequence, 'online' - [BIRTH > DEATH], 'offline' - [BIRTH <= DEATH]  "} },  
]
}
```