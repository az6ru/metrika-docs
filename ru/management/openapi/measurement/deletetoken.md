# Введение | API Яндекс Метрики

Request

## В этой статье:

  1. API импорта данных
  2. Measurement Protocol
  3. Удаление токена

# Удаление токена

Удаляет токен для указанного счетчика.

## [](ru/management/openapi/measurement/deleteToken#request)Request

POST
    
    
    https://api-metrika.yandex.net/management/v1/counter/{counterId}/measurement/delete
    

### [](ru/management/openapi/measurement/deleteToken#path-parameters)Path parameters

**Name** |  **Description**  
---|---  
counterId* |  **Type:** integer<int32> Идентификатор счетчика, для которого необходимо удалить токен.  
Example: `2215573`  
  
### [](ru/management/openapi/measurement/deleteToken#query-parameters)Query parameters

**Name** |  **Description**  
---|---  
token* |  **Type:** string Токен, который необходимо удалить.  
Example: `01x0x000-x11x-4385-0x00-47xx000xx000`  
  
## [](ru/management/openapi/measurement/deleteToken#responses)Responses

## [](ru/management/openapi/measurement/deleteToken#200-ok)200 OK

OK

### [](ru/management/openapi/measurement/deleteToken#body)Body

application/json
    
    
    {
        "success": true
    }
    

**Name** |  **Description**  
---|---  
success |  **Type:** boolean Результат выполнения операции. _Default:_ `true`  
  
No longer supported, please use an alternative and newer version.

### Была ли статья полезна?

ДаНет

Предыдущая

[Генерация дополнительных токенов](generatetoken.md)

Следующая

[Введение](../../../stat/index.md)