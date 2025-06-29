# Загрузка части подготовленных логов обработанного запроса - Справочник API Logs | API Яндекс Метрики

Request

## В этой статье:

  1. [API Logs](../index.md)
  2. Справочник API Logs
  3. Оценка возможности создания запроса

# Оценка возможности создания запроса

Оценивает возможность создания запроса логов по его примерному размеру.

## [](ru/logs/openapi/evaluate#request)Request

GET
    
    
    https://api-metrika.yandex.net/management/v1/counter/{counterId}/logrequests/evaluate
    

### [](ru/logs/openapi/evaluate#path-parameters)Path parameters

**Name** |  **Description**  
---|---  
counterId* |  **Type:** integer<int32> Идентификатор счетчика.  
Example: `2215573`  
  
### [](ru/logs/openapi/evaluate#query-parameters)Query parameters

**Name** |  **Description**  
---|---  
date1* |  **Type:** string Первый день.  
Example: `2016-01-01`  
date2* |  **Type:** string Последний день (не может быть текущим днем).  
Example: `2016-01-31`  
fields* |  **Type:** string Список полей через запятую.  
Example: `ym:pv:dateTime,ym:pv:referer`  
source* |  **Type:** string Источник логов.  
Источник логов. Возможные значения:

  * `hits` — события.
  * `visits` — визиты.   
Example: `hits`

  
  
## [](ru/logs/openapi/evaluate#responses)Responses

## [](ru/logs/openapi/evaluate#200-ok)200 OK

OK

### [](ru/logs/openapi/evaluate#body)Body

application/json
    
    
    {
        "log_request_evaluation": {
            "possible": false,
            "max_possible_day_quantity": 0
        }
    }
    

**Name** |  **Description**  
---|---  
log_request_evaluation |  **Type:** [LogRequestEvaluation](evaluate.md) Оценка возможности создания запросов логов.  
  
### [](ru/logs/openapi/evaluate#logrequestevaluation)LogRequestEvaluation

Оценка возможности создания запросов логов.

**Name** |  **Description**  
---|---  
max_possible_day_quantity |  **Type:** integer<int64> Максимальное количество дней периода, который можно указать в запросах логов, с учетом текущей квоты.  
possible |  **Type:** boolean Возможность создания запроса логов за указанный период.  
  
No longer supported, please use an alternative and newer version.

### Была ли статья полезна?

ДаНет

Предыдущая

[Отмена не обработанного запроса логов](cancel.md)

Следующая

[Информация о запросе логов](getlogrequest.md)