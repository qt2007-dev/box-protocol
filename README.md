# BOX Protocol

Протокол обмена между контроллерами QuintTech, MQTT-брокером и хостом (SCADA / облако).

Основа — [Sparkplug B 3.0](sparkplug-specification-3.0.0.pdf). Полезная нагрузка ноды и устройств кодируется protobuf (`[standart.proto](standart.proto)`). JSON в этой документации — читаемое представление тех же сообщений, а не формат MQTT-payload. Исключение — топик `STATE`: там хост публикует JSON.

Типичная топология:

```mermaid
flowchart LR
  host[Host] --- mqtt[MQTT]
  mqtt --- node[Node]
  node --- device[Device]
```



Нода держит MQTT-сессию, публикует собственные метрики и проксирует устройства. Устройства появляются как Sparkplug Device у этой ноды.

## Топики

```
spBv1.0/{groupType}/{messageType}/{nodeID}
spBv1.0/{groupType}/{messageType}/{nodeID}/{deviceID}
```

Примеры:

```
spBv1.0/box/NBIRTH/abba2020
spBv1.0/box/DDATA/abba2020/deba0001
```


| Поле        | Описание                                                               |
| ----------- | ---------------------------------------------------------------------- |
| `groupType` | Группа в топике. Допустимые значения: `box`, `plc`, `lc`, `ledef`.     |
| `nodeID`    | Идентификатор ноды: 32-битное число в hex, нижний регистр (`abba2020`) |
| `deviceID`  | Идентификатор устройства: тот же формат (`deba0001`)                   |


`control/group` у ноды и устройства может подставляться вместо id в топиках и сценариях.

### Типы сообщений


| Тип      | Направление         | Когда                                                          |
| -------- | ------------------- | -------------------------------------------------------------- |
| `NBIRTH` | нода → брокер       | Первое сообщение после выхода онлайн: полный набор метрик ноды |
| `DBIRTH` | нода → брокер       | Устройство появилось: полный набор метрик устройства           |
| `NDEATH` | брокер → подписчики | Last Will: нода отключилась или ушла офлайн                    |
| `DDEATH` | нода → брокер       | Устройство не отвечает                                         |
| `NDATA`  | нода → брокер       | Изменение метрик ноды                                          |
| `DDATA`  | нода → брокер       | Изменение метрик устройства                                    |
| `NCMD`   | хост → нода         | Команда ноде                                                   |
| `DCMD`   | хост → устройство   | Команда устройству                                             |


В `NBIRTH` / `DBIRTH` метрики публикуются с `name` и `alias`. В `xCMD` метрику можно указать по `name` или по `alias`. Формат ответа в `xDATA` совпадает с форматом команды: команда с `name` — ответ с `name`, команда с `alias` — ответ с `alias`.

## Выход онлайн

После подключения к брокеру нода **не публикует NBIRTH**, пока хост не объявит себя онлайн.

Хост публикует JSON (не protobuf) в топик Sparkplug 3.0:

```
spBv1.0/STATE/{hostId}
```

`{hostId}` совпадает с метрикой `control/host`. Специальное значение `ALL` — нода ждёт онлайн любого хоста. Сообщение обычно retained.

Онлайн:

```json
{ "online": true, "timestamp": 1486144502122 }
```

После `online: true` нода публикует `NBIRTH`, затем `DBIRTH` устройств.

Офлайн:

```json
{ "online": false, "timestamp": 1486144502122 }
```

После `online: false` нода уходит офлайн: публикуется `NDEATH`, обмен `NDATA` / `DDATA` / приём команд останавливается. Нода снова ждёт `online: true` в том же топике `STATE` и только тогда повторяет birth.

Пока в `STATE` нет `online: true`, нода считается не вышедшей в онлайн.

## Payload

Схема метрик ноды и устройств: `[standart.proto](standart.proto)` (Eclipse Tahu Sparkplug B).

```json
{
  "timestamp": 1486144502122,
  "seq": 1,
  "uuid": "8c1ade19-6860-4b7f-82d4-b5d8f74cf4ac",
  "metrics": [
    {
      "name": "name1/name2/name3",
      "alias": 123,
      "timestamp": 1486144502122,
      "dataType": 12,
      "metadata": {
        "description": "[RWP]Example metric description"
      },
      "properties": {
        "keys": ["key1", "key2"],
        "values": [
          { "type": 12, "string_value": "value1" },
          { "type": 12, "string_value": "value2" }
        ]
      },
      "string_value": "value"
    }
  ]
}
```

Поля сообщения:


| Поле        | Смысл                                |
| ----------- | ------------------------------------ |
| `timestamp` | Время отправки сообщения             |
| `seq`       | Порядковый номер Sparkplug-сообщения |
| `uuid`      | Опциональный идентификатор сообщения |
| `metrics`   | Список метрик                        |


### Метрика


| Поле                   | Смысл                                                                               |
| ---------------------- | ----------------------------------------------------------------------------------- |
| `name`                 | Имя. Уровни разделяются `/` (`control/reboot`, `out/0`)                             |
| `alias`                | Числовой ярлык метрики, назначается в birth. В `xCMD` / `xDATA` можно вместо `name` |
| `timestamp`            | Время значения                                                                      |
| `dataType`             | Тип значения (таблица ниже)                                                         |
| `properties`           | Доп. поля: пороги, сценарии, события, расписание                                    |
| `metadata.description` | Человекочитаемое описание и флаг доступа                                            |


Значение лежит в одном из полей `oneof`: `int_value`, `long_value`, `float_value`, `double_value`, `boolean_value`, `string_value`, `bytes_value`, `dataset_value`, `template_value`.

### Типы данных (`dataType`)


| Код | Тип      | Поле значения    |
| --- | -------- | ---------------- |
| 1   | Int8     | `int_value`      |
| 2   | Int16    | `int_value`      |
| 3   | Int32    | `int_value`      |
| 4   | Int64    | `long_value`     |
| 5   | UInt8    | `int_value`      |
| 6   | UInt16   | `int_value`      |
| 7   | UInt32   | `int_value`      |
| 8   | UInt64   | `long_value`     |
| 9   | Float    | `float_value`    |
| 10  | Double   | `double_value`   |
| 11  | Boolean  | `boolean_value`  |
| 12  | String   | `string_value`   |
| 13  | DateTime | `long_value`     |
| 14  | Text     | `string_value`   |
| 15  | UUID     | `string_value`   |
| 16  | DataSet  | `dataset_value`  |
| 17  | Bytes    | `bytes_value`    |
| 18  | File     | `bytes_value`    |
| 19  | Template | `template_value` |


`DataSet` — таблицы (списки сценариев, ключи Wiegand, координаты). `Template` — повторяемые структуры (фаза счётчика, DALI gear, слот DMX).

### Флаги доступа

В `metadata.description` в квадратных скобках:


| Флаг  | Смысл                                                    |
| ----- | -------------------------------------------------------- |
| `R`   | Только чтение (публикуется в birth/data)                 |
| `W`   | Только запись (команда, в birth обычно `null` / `false`) |
| `RW`  | Чтение и запись                                          |
| `RWP` | Как `RW`, значение сохраняется после перезагрузки        |


## Общие метрики

Есть у ноды и у каждого устройства.


| Метрика                    | Доступ | Назначение                                       |
| -------------------------- | ------ | ------------------------------------------------ |
| `bdSeq`                    | R      | Birth/death sequence. Online, если BIRTH > DEATH |
| `control/reboot`           | W      | Программная перезагрузка (`true`)                |
| `control/rebirth`          | W      | Повторная публикация birth                       |
| `control/firmware/new`     | W      | Прошивка в Base64                                |
| `control/metrics/save`     | RWP    | Сохранять значения метрик после reboot           |
| `control/metrics/metadata` | RWP    | Включать metadata в birth                        |
| `control/group`            | RWP    | Группа вместо id в топиках и сценариях           |
| `info/hardware/vendor`     | R      | Производитель                                    |
| `info/hardware/model`      | R      | Модель MCU                                       |
| `info/firmware/version`    | R      | Версия прошивки                                  |
| `info/type`                | R      | Тип устройства                                   |
| `info/id`                  | R      | Короткий id                                      |
| `info/error`               | R      | Последняя ошибка                                 |
| `sensors/temperature`      | R      | Температура MCU, °C                              |


У ноды дополнительно: `control/host` (id Primary Host для топика `STATE`), MQTT (`connection/server`), модем, GNSS, NTP, timezone, сценарии, события, расписание.

## Типы нод


| `info/type` | Файл                       | Платформа                            |
| ----------- | -------------------------- | ------------------------------------ |
| `BOX`       | [box-node.md](box-node.md) | Raspberry Pi 4, шлюз линейки BOX     |
| `SEQ`       | [seq-node.md](seq-node.md) | Zynq, расширенный мониторинг питания |


## Типы устройств


| `info/type`          | Файл                             | Каналы                        |
| -------------------- | -------------------------------- | ----------------------------- |
| `16 Digital outputs` | [box-do.md](box-do.md)           | 16 дискретных выходов         |
| `16 Digital inputs`  | [box-di.md](box-di.md)           | 16 дискретных входов          |
| `8 Relay outputs`    | [box-ro.md](box-ro.md)           | 2 механических реле + 6 SSR   |
| `8 IO`               | [box-io.md](box-io.md)           | 8 многофункциональных IO, PID |
| `Interfaces`         | [box-if.md](box-if.md)           | RS485: raw и DMX512           |
| `DALI 2`             | [box-dali.md](box-dali.md)       | 2 шины DALI                   |
| `Energymeter`        | [box-em.md](box-em.md)           | Трёхфазный счётчик            |
| `STEP 2`             | [box-step.md](box-step.md)       | 2 шаговых двигателя           |
| `Thermocontroller 2` | [box-tc.md](box-tc.md)           | 2 канала термоконтроля        |
| `Wiegand 2`          | [box-wiegand.md](box-wiegand.md) | 2 канала СКУД Wiegand         |


Профиль устройства — пример `DBIRTH`: полный список метрик, типы и флаги доступа. После rebirth клиент шлёт только изменившиеся метрики в `DDATA` / `DCMD`.

## Функции ноды

Автоматизация живёт на ноде и задаётся через её метрики (`NCMD`).


| Функция       | Документ                             | Кратко                                                                              |
| ------------- | ------------------------------------ | ----------------------------------------------------------------------------------- |
| Сценарии      | [scenario.md](scenario.md)           | Python-скрипт или список действий: запись метрик, задержки, запуск других сценариев |
| События       | [events.md](events.md)               | Триггеры и условия по метрикам → запуск сценария                                    |
| Расписание    | [schedule.md](schedule.md)           | Запуск сценариев по времени, timestamp или CRON                                     |
| CRON          | [cron.md](cron.md)                   | Формат строк расписания                                                             |
| Смена брокера | [change-server.md](change-server.md) | Смена MQTT-сервера с откатом, если новый недоступен                                 |


## Как читать профили

1. Взять тип устройства из `info/type` в `DBIRTH`.
2. Открыть соответствующий файл выше.
3. Команды писать в `NCMD` / `DCMD` по `name` или `alias`.
4. Для автоматизации: событие → сценарий → при необходимости расписание.

JSON-примеры в файлах содержат комментарии (`/* … */`) — это пояснения к документации, в protobuf их нет.