## BOX device io birth example
> spBv1.0/box/DBIRTH/abba2020/deba0005  

```json
{
"timestamp": 1486144502122,
"seq": 0,
"metrics": [
    { "name": "bdSeq",                    "dataType": 8/* Uint64 */,   "long_value": 0,                    "metadata":{"description":"[R]Birth-death sequence, 'online' - [DBIRTH > DDEATH], 'offline' - [DBIRTH <= DDEATH]  "} },
    { "name": "control/reboot",           "dataType": 11/* Boolean */, "boolean_value": false,             "metadata":{"description":"[W]Software reboot device, send 'true' for reboot"} },
    { "name": "control/rebirth",          "dataType": 11/* Boolean */, "boolean_value": false,             "metadata":{"description":"[W]Rebirth device, send 'true' for receive dbirth message again"} },
    { "name": "control/firmware/new",     "dataType": 17/* Bytes */,   "bytes_value":"", "is_null": true,  "metadata":{"description":"[W]Receive new device firmware, firmware send in Base64 format, in birth always null"} },
    { "name": "control/metrics/save",     "dataType": 11/* Boolean */, "boolean_value": true,              "metadata":{"description":"[RWP]Save metrics states after reboot, send 'true' for enable"} },
    { "name": "control/metrics/metadata", "dataType": 11/* Boolean */, "boolean_value": true,              "metadata":{"description":"[RWP]Show metrics metadata in birth, send 'true' for enable"} },
    { "name": "control/group",            "dataType": 12/* String */,  "string_value": "io",               "metadata":{"description":"[RWP]Global group for device, can be used instead id in topics and scenarios"} },

    { "name": "info/hardware/vendor",     "dataType": 12/* String */,  "string_value": "QuintTech" ,       "metadata":{"description":"[R]Vendor name, hardcoded by vendor"} },
    { "name": "info/hardware/model",      "dataType": 12/* String */,  "string_value": "stm32g474ce",      "metadata":{"description":"[R]Mcu model, hardcoded by vendor"} },
    { "name": "info/firmware/version",    "dataType": 12/* String */,  "string_value": "0.1.220527.84852", "metadata":{"description":"[R]Firmware version, MAJOR.MINOR.YYMMDD.SSSSS"} },
    { "name": "info/type",                "dataType": 12/* String */,  "string_value": "8 IO",             "metadata":{"description":"[R]Device type, hardcoded by vendor"} },
    { "name": "info/id",                  "dataType": 12/* String */,  "string_value": "deba0005",         "metadata":{"description":"[R]Short id calculated by a hash from mcu uid"} },
    { "name": "info/error",               "dataType": 12/* String */,  "string_value": "",                 "metadata":{"description":"[R]Last error message"} },

    { "name": "sensors/temperature",      "dataType": 1/* Int8 */,     "int_value": 22,                    "metadata":{"description":"[R]Temperature sensor in mcu, value in Celsius"} },


    { "name": "io/0/mode",                "dataType": 12/* String */,  "string_value": "high-impedance",   "metadata":{"description":"[RW]IO pin mode, list of values = ['high-impedance', 'voltage-output',
                                                                                                                                                                     'current-output', 'voltage-input',
                                                                                                                                                                     'current-input',  'resistance-input',
                                                                                                                                                                     'digital-input',  'digital-output']
                                                                                                                                      change value execute rebirth of device with new metrics"} },
    { "name": "io/0/error",               "dataType": 12/* String */,  "string_value": "none",             "metadata":{"description":"[R]IO pin error conditions, values = ['none','over-current','open-circuit','over-voltage','short-circuit']"} },


    { "name": "io/1/mode",                "dataType": 12/* String */,  "string_value": "voltage-output",   "metadata":{"description":"[RW]IO pin mode, list of values = ['high-impedance', 'voltage-output',
                                                                                                                                                                     'current-output', 'voltage-input',
                                                                                                                                                                     'current-input',  'resistance-input',
                                                                                                                                                                     'digital-input',  'digital-output']
                                                                                                                                      change value execute rebirth of device with new metrics"} },  
    { "name": "io/1",                     "dataType": 7/* UInt32 */,   "int_value": 5635,                  "metadata":{"description":"[RW]IO pin state, range of values depends on the operating mode.
                                                                                                                                      'voltage-output' - [0 - 10000] mV,
                                                                                                                                      'current-output' - [0 - 25000] uA,
                                                                                                                                      'voltage-input' - [0 - 10000] mV, [0 - 2500] mV, [-2500 - 2500] mV, [-104000 - 104000] uV,
                                                                                                                                      'current-input  - [0 - 25000] uA,
                                                                                                                                      'resistance-input' - [0 - 1000000] Ohm,
                                                                                                                                      'digital-input' - ['true' - if input is high, 'false' - if input is low],
                                                                                                                                      'digital-output' - ['true' - if output is high, 'false' - if output is low]"} },                   
    { "name": "io/1/current/limit",       "dataType": 12/* String */, "string_value": "30mA",              "metadata":{"description":"[RW]Voltage output current limit, values = ['30mA', '7.5mA']"} },                 
    { "name": "io/1/current",             "dataType": 3/* Int32 */,   "int_value": 20,                     "metadata":{"description":"[R]Voltage output current cunsumption, values = [-25000 - 25000] uA, read-only"} },                        
    { "name": "io/1/slew",                "dataType": 12/* String */, "string_value": "1ms",               "metadata":{"description":"[RW]Voltage output slew time, values = ['off','38.6us','40.1us','73.6us','75.8us','113us',
                                                                                                                                      '259us','280us','459us','520us','858us','1ms','1.1ms','2ms','4ms','17ms','31.7ms']"} },                  
    { "name": "io/1/error",               "dataType": 12/* String */, "string_value": "none",              "metadata":{"description":"[R]IO pin error conditions, values = ['none','over-current','open-circuit','over-voltage','short-circuit']"} },            


    { "name": "io/2/mode",                "dataType": 12/* String */, "string_value": "current-output",    "metadata":{"description":"[RW]IO pin mode, list of values = ['high-impedance', 'voltage-output',
                                                                                                                                                                     'current-output', 'voltage-input',
                                                                                                                                                                     'current-input',  'resistance-input',
                                                                                                                                                                     'digital-input',  'digital-output']
                                                                                                                                      change value execute rebirth of device with new metrics"} },     
    { "name": "io/2",                     "dataType": 7/* UInt32 */,  "int_value": 5635,                   "metadata":{"description":"[RW]IO pin state, range of values depends on the operating mode.
                                                                                                                                      'voltage-output' - [0 - 10000] mV,
                                                                                                                                      'current-output' - [0 - 25000] uA,
                                                                                                                                      'voltage-input' - [0 - 10000] mV, [0 - 2500] mV, [-2500 - 2500] mV, [-104000 - 104000] uV,
                                                                                                                                      'current-input  - [0 - 25000] uA,
                                                                                                                                      'resistance-input' - [0 - 1000000] Ohm,
                                                                                                                                      'digital-input' - ['true' - if input is high, 'false' - if input is low],
                                                                                                                                      'digital-output' - ['true' - if output is high, 'false' - if output is low]"} },                     
    { "name": "io/2/voltage",             "dataType": 7/* UInt32 */,  "int_value": 5635,                   "metadata":{"description":"[R]Current output voltage, values = [0 - 10000] mV, read-only"} },                     
    { "name": "io/2/error",               "dataType": 12/* String */, "string_value": "none",              "metadata":{"description":"[R]IO pin error conditions, values = ['none','over-current','open-circuit','over-voltage','short-circuit']"} },                   


    { "name": "io/3/mode",                "dataType": 12/* String */, "string_value": "voltage-input",     "metadata":{"description":"[RW]IO pin mode, list of values = ['high-impedance', 'voltage-output',
                                                                                                                                                                     'current-output', 'voltage-input',
                                                                                                                                                                     'current-input',  'resistance-input',
                                                                                                                                                                     'digital-input',  'digital-output']
                                                                                                                                      change value execute rebirth of device with new metrics"} },       
    { "name": "io/3",                     "dataType": 3/* Int32 */,   "int_value": 5635,                   "metadata":{"description":"[RW]IO pin state, range of values depends on the operating mode.
                                                                                                                                      'voltage-output' - [0 - 10000] mV,
                                                                                                                                      'current-output' - [0 - 25000] uA,
                                                                                                                                      'voltage-input' - [0 - 10000] mV, [0 - 2500] mV, [-2500 - 2500] mV, [-104000 - 104000] uV,
                                                                                                                                      'current-input  - [0 - 25000] uA,
                                                                                                                                      'resistance-input' - [0 - 1000000] Ohm,
                                                                                                                                      'digital-input' - ['true' - if input is high, 'false' - if input is low],
                                                                                                                                      'digital-output' - ['true' - if output is high, 'false' - if output is low]"} },                    
    { "name": "io/3/pulldown",            "dataType": 11/* Boolean */,"boolean_value": false,              "metadata":{"description":"[RW]Voltage input 200kOhm pulldown resistor"} },                  
    { "name": "io/3/range",               "dataType": 12/* String */, "string_value": "0V to 10V",         "metadata":{"description":"[RW]Voltage input range select, list of values = ['auto','0V to 10V','0V to 2.5V','-2.5V to 2.5V','-104mV to 104mV']"} },          
    { "name": "io/3/error",               "dataType": 12/* String */, "string_value": "none",              "metadata":{"description":"[R]IO pin error conditions, values = ['none','over-current','open-circuit','over-voltage','short-circuit']"} },                


    { "name": "io/4/mode",                "dataType": 12/* String */, "string_value": "current-input",     "metadata":{"description":"[RW]IO pin mode, list of values = ['high-impedance', 'voltage-output',
                                                                                                                                                                     'current-output', 'voltage-input',
                                                                                                                                                                     'current-input',  'resistance-input',
                                                                                                                                                                     'digital-input',  'digital-output']
                                                                                                                                      change value execute rebirth of device with new metrics"} },      
    { "name": "io/4",                     "dataType": 7/* UInt32 */,  "int_value": 5635,                   "metadata":{"description":"[RW]IO pin state, range of values depends on the operating mode.
                                                                                                                                      'voltage-output' - [0 - 10000] mV,
                                                                                                                                      'current-output' - [0 - 25000] uA,
                                                                                                                                      'voltage-input' - [0 - 10000] mV, [0 - 2500] mV, [-2500 - 2500] mV, [-104000 - 104000] uV,
                                                                                                                                      'current-input  - [0 - 25000] uA,
                                                                                                                                      'resistance-input' - [0 - 1000000] Ohm,
                                                                                                                                      'digital-input' - ['true' - if input is high, 'false' - if input is low],
                                                                                                                                      'digital-output' - ['true' - if output is high, 'false' - if output is low]"} },                      
    { "name": "io/4/error",               "dataType": 12/* String */, "string_value": "none",              "metadata":{"description":"[R]IO pin error conditions, values = ['none','over-current','open-circuit','over-voltage','short-circuit']"} },              


    { "name": "io/5/mode",                "dataType": 12/* String */, "string_value": "resistance-input",  "metadata":{"description":"[RW]IO pin mode, list of values = ['high-impedance', 'voltage-output',
                                                                                                                                                                     'current-output', 'voltage-input',
                                                                                                                                                                     'current-input',  'resistance-input',
                                                                                                                                                                     'digital-input',  'digital-output']
                                                                                                                                      change value execute rebirth of device with new metrics"} },    
    { "name": "io/5",                     "dataType": 7/* UInt32 */,  "int_value": 5635,                   "metadata":{"description":"[RW]IO pin state, range of values depends on the operating mode.
                                                                                                                                      'voltage-output' - [0 - 10000] mV,
                                                                                                                                      'current-output' - [0 - 25000] uA,
                                                                                                                                      'voltage-input' - [0 - 10000] mV, [0 - 2500] mV, [-2500 - 2500] mV, [-104000 - 104000] uV,
                                                                                                                                      'current-input  - [0 - 25000] uA,
                                                                                                                                      'resistance-input' - [0 - 1000000] Ohm,
                                                                                                                                      'digital-input' - ['true' - if input is high, 'false' - if input is low],
                                                                                                                                      'digital-output' - ['true' - if output is high, 'false' - if output is low]"} },                     
    { "name": "io/5/error",               "dataType": 12/* String */, "string_value": "none",              "metadata":{"description":"[R]IO pin error conditions, values = ['none','over-current','open-circuit','over-voltage','short-circuit']"} },                 


    { "name": "io/6/mode",                "dataType": 12/* String */, "string_value": "digital-input",     "metadata":{"description":"[RW]IO pin mode, list of values = ['high-impedance', 'voltage-output',
                                                                                                                                                                     'current-output', 'voltage-input',
                                                                                                                                                                     'current-input',  'resistance-input',
                                                                                                                                                                     'digital-input',  'digital-output']
                                                                                                                                      change value execute rebirth of device with new metrics"} },       
    /* value state */ 
    { "name": "io/6",                     "dataType": 11/* Boolean */, "boolean_value": false,             "metadata":{"description":"[RW]IO pin state, range of values depends on the operating mode.
                                                                                                                                      'voltage-output' - [0 - 10000] mV,
                                                                                                                                      'current-output' - [0 - 25000] uA,
                                                                                                                                      'voltage-input' - [0 - 10000] mV, [0 - 2500] mV, [-2500 - 2500] mV, [-104000 - 104000] uV,
                                                                                                                                      'current-input  - [0 - 25000] uA,
                                                                                                                                      'resistance-input' - [0 - 1000000] Ohm,
                                                                                                                                      'digital-input' - ['true' - if input is high, 'false' - if input is low],
                                                                                                                                      'digital-output' - ['true' - if output is high, 'false' - if output is low]"} },                
    { "name": "io/6/threshold",           "dataType": 12/* String */, "string_value": "8.4",               "metadata":{"description":"[RW]Digital input high threshold voltage, list of value = ['0.4','1.2','2','2.8',...,'25.2'] V"} },                 
    { "name": "io/6/debounce",            "dataType": 12/* String */, "string_value": "bypass",            "metadata":{"description":"[RW]Digital input debounce time, list of value = ['bypass','0.013','0.018','0.024','0.032','0.042','0.056','0.075',
                                                                                                                                                                                          '0.1','0.13','0.18','0.24','0.32','0.42','0.56','0.75',
                                                                                                                                                                                          '1','1.3','1.8','2.4','3.2','4.2','5.6','7.5',
                                                                                                                                                                                          '10','13','18','24','32','42','56','75'] ms"} },              
    { "name": "io/6/sink",                "dataType": 12/* String */, "string_value": "2.4mA",             "metadata":{"description":"[RW]Digital input sink current, values = ['2.4mA','7mA']"} },                
    { "name": "io/6/error",               "dataType": 12/* String */, "string_value": "none",              "metadata":{"description":"[R]IO pin error conditions, values = ['none','over-current','open-circuit','over-voltage','short-circuit']"} },                


    { "name": "io/7/mode",                "dataType": 12/* String */, "string_value": "digital-output",    "metadata":{"description":"[RW]IO pin mode, list of values = ['high-impedance', 'voltage-output',
                                                                                                                                                                     'current-output', 'voltage-input',
                                                                                                                                                                     'current-input',  'resistance-input',
                                                                                                                                                                     'digital-input',  'digital-output']
                                                                                                                                      change value execute rebirth of device with new metrics"} },      
    { "name": "io/7",                     "dataType": 11/* Boolean */, "boolean_value": false,             "metadata":{"description":"[RW]IO pin state, range of values depends on the operating mode.
                                                                                                                                      'voltage-output' - [0 - 10000] mV,
                                                                                                                                      'current-output' - [0 - 25000] uA,
                                                                                                                                      'voltage-input' - [0 - 10000] mV, [0 - 2500] mV, [-2500 - 2500] mV, [-104000 - 104000] uV,
                                                                                                                                      'current-input  - [0 - 25000] uA,
                                                                                                                                      'resistance-input' - [0 - 1000000] Ohm,
                                                                                                                                      'digital-input' - ['true' - if input is high, 'false' - if input is low],
                                                                                                                                      'digital-output' - ['true' - if output is high, 'false' - if output is low]"} },                
    { "name": "io/7/error",               "dataType": 12/* String */  , "string_value": "none",            "metadata":{"description":"[R]IO pin error conditions, values = ['none','over-current','open-circuit','over-voltage','short-circuit']"} },                

   
  ]
}
```

## BOX device io death example
> spBv1.0/box/DDEATH/abba2020/deba0005  

```json
{
"timestamp": 1486144502122,
"metrics": [  
    { "name": "bdSeq",                    "dataType": 8/* Uint64 */,   "long_value": 0,                    "metadata":{"description":"[R]Birth-death sequence, 'online' - [DBIRTH > DDEATH], 'offline' - [DBIRTH <= DDEATH]  "} },  
]
}
```