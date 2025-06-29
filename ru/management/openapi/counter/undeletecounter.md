# Список доступных счетчиков - Управление счетчиками | API Яндекс Метрики

Request

## В этой статье:

  1. [API управления](../../index.md)
  2. Справочник API управления
  3. Управление счетчиками
  4. Восстановление счетчика

# Восстановление счетчика

Восстанавливает удаленный счетчик.

## [](ru/management/openapi/counter/undeleteCounter#request)Request

POST
    
    
    https://api-metrika.yandex.net/management/v1/counter/{counterId}/undelete
    

### [](ru/management/openapi/counter/undeleteCounter#path-parameters)Path parameters

**Name** |  **Description**  
---|---  
counterId* |  **Type:** integer<int32> идентификатор счетчика, который вы хотите восстановить.  
  
## [](ru/management/openapi/counter/undeleteCounter#responses)Responses

## [](ru/management/openapi/counter/undeleteCounter#200-ok)200 OK

OK

### [](ru/management/openapi/counter/undeleteCounter#body)Body

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

[Создание счетчика](addcounter.md)

Следующая

[Информация о операции](../operation/operation.md)