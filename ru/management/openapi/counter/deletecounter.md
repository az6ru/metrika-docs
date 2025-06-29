# Список доступных счетчиков - Управление счетчиками | API Яндекс Метрики

Request

## В этой статье:

  1. [API управления](../../index.md)
  2. Справочник API управления
  3. Управление счетчиками
  4. Удаление счетчика

# Удаление счетчика

Удаляет указанный счетчик.

## [](ru/management/openapi/counter/deleteCounter#request)Request

DELETE
    
    
    https://api-metrika.yandex.net/management/v1/counter/{counterId}
    

### [](ru/management/openapi/counter/deleteCounter#path-parameters)Path parameters

**Name** |  **Description**  
---|---  
counterId* |  **Type:** integer<int32> Идентификатор счетчика, информацию о котором вы хотите получить.  
  
## [](ru/management/openapi/counter/deleteCounter#responses)Responses

## [](ru/management/openapi/counter/deleteCounter#200-ok)200 OK

OK

### [](ru/management/openapi/counter/deleteCounter#body)Body

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

[Изменение счетчика](editcounter.md)

Следующая

[Список доступных счетчиков](counters.md)