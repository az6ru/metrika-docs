# Создание публичного разрешения - Публичный доступ | API Яндекс Метрики

Request

## В этой статье:

  1. [API управления](../../index.md)
  2. Справочник API управления
  3. Управление доступами
  4. Публичный доступ
  5. Удаление публичного разрешения

# Удаление публичного разрешения

Удаляет разрешение на публичный просмотр статистики.

## [](ru/management/openapi/grant/deletePublicGrant#request)Request

DELETE
    
    
    https://api-metrika.yandex.net/management/v1/counter/{counterId}/public_grant
    

### [](ru/management/openapi/grant/deletePublicGrant#path-parameters)Path parameters

**Name** |  **Description**  
---|---  
counterId* |  **Type:** integer<int32> Идентификатор счетчика.  
  
## [](ru/management/openapi/grant/deletePublicGrant#responses)Responses

## [](ru/management/openapi/grant/deletePublicGrant#200-ok)200 OK

OK

### [](ru/management/openapi/grant/deletePublicGrant#body)Body

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

[Создание публичного разрешения](addpublicgrant.md)

Следующая

[Создание разрешения](addgrant.md)