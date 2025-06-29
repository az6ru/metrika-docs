# Как передавать данные о клиентах и заказах из CRM | API Яндекс Метрики

Request

## В этой статье:

  1. API импорта данных
  2. Импорт данных о клиентах и заказах из CRM
  3. Информация о последних загрузках

# Информация о последних загрузках

Информация о последних загрузках.

## [](ru/management/openapi/schema/getLastUploadings#request)Request

GET
    
    
    https://api-metrika.yandex.net/cdp/api/v1/counter/{counterId}/last_uploadings
    

### [](ru/management/openapi/schema/getLastUploadings#path-parameters)Path parameters

**Name** |  **Description**  
---|---  
counterId* |  **Type:** integer<int32> Идентификатор счетчика.  
Example: `2215573`  
  
### [](ru/management/openapi/schema/getLastUploadings#query-parameters)Query parameters

**Name** |  **Description**  
---|---  
datetime_offset |  **Type:** string<date-time> Сдвиг по времени. Все возвращаемые загрузки будут строго раньше указанного времени.  
Example: `2020-02-10 10:00:00`  
limit |  **Type:** integer<int64> Количество возвращаемых загрузок. Допускаются значения от 1 до 1000 включительно.  
_Default:_ `10`   
Example: `10`  
source |  **Type:** string Источник загрузки. Все возвращаемые загрузки будут из указанного источника.  
Источник загрузки. Возможные значения: `API`.  
Example: `API`  
  
## [](ru/management/openapi/schema/getLastUploadings#responses)Responses

## [](ru/management/openapi/schema/getLastUploadings#200-ok)200 OK

OK

### [](ru/management/openapi/schema/getLastUploadings#body)Body

application/json
    
    
    {
        "uploadings": [
            {
                "uploading_id": "string",
                "datetime": "2022-12-29T18:02:01Z",
                "api_validation_status": "string",
                "elements_count": 0,
                "entity_type": "string",
                "uploading_format": "string",
                "uploading_source": "string"
            }
        ]
    }
    

**Name** |  **Description**  
---|---  
uploadings |  **Type:** [UploadingMetaExternal](getlastuploadings.md)[] Информация о загрузках.  
Описание объекта `UploadingMetaExternal`.  
  
### [](ru/management/openapi/schema/getLastUploadings#uploadingmetaexternal)UploadingMetaExternal

Описание объекта `UploadingMetaExternal`.

**Name** |  **Description**  
---|---  
api_validation_status |  **Type:** string Статус валидации загрузки:

  * `PASSED` — валидация прошла успешно.
  * `FAILED` — валидация прошла не успешно.

  
datetime |  **Type:** string<date-time> Время загрузки.  
elements_count |  **Type:** integer<int32> Количество элементов в загрузке.  
entity_type |  **Type:** string Тип сущности:

  * `SYSTEM` — системная сущность, например, контакты или заказы.
  * `CUSTOM_LIST` — пользовательский список.
  * `SYSTEM_LIST` — системный список, например товары.

  
uploading_format |  **Type:** string Формат загрузки. Возможные значения:

  * `JSON`.
  * `CSV`.

  
uploading_id |  **Type:** string Идентификатор загрузки.  
uploading_source |  **Type:** string Источник загрузки. Возможные значения: `API`.  
  
No longer supported, please use an alternative and newer version.

### Была ли статья полезна?

ДаНет

Предыдущая

[Информация о типах системных атрибутов](gettypes.md)

Следующая

[Формат даты и времени](../../../data-import/date.md)