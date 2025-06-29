# Загрузка части подготовленных логов обработанного запроса - Справочник API Logs | API Яндекс Метрики

Request

## В этой статье:

  1. [API Logs](../index.md)
  2. Справочник API Logs
  3. Отмена не обработанного запроса логов

# Отмена не обработанного запроса логов

Отменяет еще не обработанный запрос логов.

## [](ru/logs/openapi/cancel#request)Request

POST
    
    
    https://api-metrika.yandex.net/management/v1/counter/{counterId}/logrequest/{requestId}/cancel
    

### [](ru/logs/openapi/cancel#path-parameters)Path parameters

**Name** |  **Description**  
---|---  
counterId* |  **Type:** integer<int32> Идентификатор счетчика.  
Example: `2215573`  
requestId* |  **Type:** integer<int32> Идентификатор запроса логов.  
Example: `777`  
  
## [](ru/logs/openapi/cancel#responses)Responses

## [](ru/logs/openapi/cancel#200-ok)200 OK

OK

### [](ru/logs/openapi/cancel#body)Body

application/json
    
    
    {
        "log_request": {
            "request_id": 0,
            "counter_id": 0,
            "source": [
                "string"
            ],
            "date1": "string",
            "date2": "string",
            "fields": [
                "string"
            ],
            "status": "string",
            "size": 0,
            "parts": [
                {
                    "part_number": 0,
                    "size": 0
                }
            ],
            "attribution": "string"
        }
    }
    

**Name** |  **Description**  
---|---  
log_request |  **Type:** [LogRequest](cancel.md) Запрос логов.  
  
### [](ru/logs/openapi/cancel#logrequest)LogRequest

Запрос логов.

**Name** |  **Description**  
---|---  
attribution |  **Type:** string Модель атрибуции. Возможные значения:

  * `FIRST` — первый переход.
  * `LAST` — последний переход.
  * LASTSIGN — последний значимый переход.
  * `LAST_YANDEX_DIRECT_CLICK` — последний переход из Директа.
  * `CROSS_DEVICE_LAST_SIGNIFICANT` — последний значимый переход (кросс-девайс) с учетом визитов со всех устройств посетителя.
  * `CROSS_DEVICE_FIRST` — первый переход (кросс-девайс) с учетом визитов со всех устройств посетителя.
  * `CROSS_DEVICE_LAST_YANDEX_DIRECT_CLICK` — последний переход из Директа (кросс-девайс) с учетом визитов со всех устройств посетителя.
  * `CROSS_DEVICE_LAST` — последний переход (кросс-девайс) с учетом визитов со всех устройств посетителя.
  * `AUTOMATIC` — автоматическая атрибуция.

  
counter_id |  **Type:** integer<int32> Идентификатор счётчика.  
date1 |  **Type:** string Первый день.  
date2 |  **Type:** string Последний день.  
fields |  **Type:** string[] Список полей.  
parts |  **Type:** [LogRequestPart](cancel.md)[] Часть ответа  
request_id |  **Type:** integer<int32> Идентификатор запроса логов.  
size |  **Type:** integer Размер логов запроса в байтах.  
source |  **Type:** string[] Источник логов. Возможные значения:

  * `hits` — события.
  * `visits` — визиты.

Примечание В параметрах визитов `ym:s:&lt;attribution&gt;RecommendationSystem` и `ym:s:&lt;attribution&gt;Messenger` могут возвращаться массивы с пропусками:

  * Если все источники просмотра неизвестны, в ответе будет `[]`.
  * Если в массиве несколько источников, часть из которых известна, а часть — нет, в ответе они будут разделены запятыми.
  * Неизвестный источник придет в виде пустой строки. Например, `[,,,telegram]`.

  
status |  **Type:** string Статус запроса:

  * `created` — создан.
  * `canceled` — отменён.
  * `processed` — обработан.
  * `cleaned_by_user` — очищен пользователем.
  * `cleaned_automatically_as_too_old` — очищен автоматически.
  * `processing_failed` — ошибка при обработке.
  * `awaiting_retry` — ожидает перезапуска.

  
  
### [](ru/logs/openapi/cancel#logrequestpart)LogRequestPart

Часть ответа

**Name** |  **Description**  
---|---  
part_number |  **Type:** integer<int32> Номер части.  
size |  **Type:** integer<int64> Размер в байтах.  
  
No longer supported, please use an alternative and newer version.

### Была ли статья полезна?

ДаНет

Предыдущая

[Очистка подготовленных для загрузки логов обработанного запроса](clean.md)

Следующая

[Оценка возможности создания запроса](evaluate.md)