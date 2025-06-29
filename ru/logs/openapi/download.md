# Частые вопросы | API Яндекс Метрики

Request

## В этой статье:

  1. [API Logs](../index.md)
  2. Справочник API Logs
  3. Загрузка части подготовленных логов обработанного запроса

# Загрузка части подготовленных логов обработанного запроса

Загружает часть подготовленных логов обработанного запроса.

## [](ru/logs/openapi/download#request)Request

GET
    
    
    https://api-metrika.yandex.net/management/v1/counter/{counterId}/logrequest/{requestId}/part/{partNumber}/download
    

### [](ru/logs/openapi/download#path-parameters)Path parameters

**Name** |  **Description**  
---|---  
counterId* |  **Type:** integer<int32> Идентификатор счетчика.  
Example: `2215573`  
partNumber* |  **Type:** integer<int32> Номер части подготовленных логов обработанного запроса.  
Example: `0`  
requestId* |  **Type:** integer<int32> Идентификатор запроса логов.  
Example: `777`  
  
## [](ru/logs/openapi/download#responses)Responses

## [](ru/logs/openapi/download#200-ok)200 OK

OK

### [](ru/logs/openapi/download#body)Body

application/json

**Type:** string

**Format:** binary

No longer supported, please use an alternative and newer version.

### Была ли статья полезна?

ДаНет

Предыдущая

[Информация о запросе логов](getlogrequest.md)

Следующая

[Частые вопросы](../../faq.md)