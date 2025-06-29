# Информация о фильтре доступа - Управление фильтрами доступа | API Яндекс Метрики

Request

## В этой статье:

  1. [API управления](../../index.md)
  2. Справочник API управления
  3. Управление доступами
  4. Индивидуальный доступ
  5. Удаление разрешения

# Удаление разрешения

Удаляет разрешения на управление счетчиком и просмотр статистики.

## [](ru/management/openapi/grant/deleteGrant#request)Request

DELETE
    
    
    https://api-metrika.yandex.net/management/v1/counter/{counterId}/grant
    

### [](ru/management/openapi/grant/deleteGrant#path-parameters)Path parameters

**Name** |  **Description**  
---|---  
counterId* |  **Type:** integer<int32> Идентификатор счетчика.  
  
### [](ru/management/openapi/grant/deleteGrant#query-parameters)Query parameters

**Name** |  **Description**  
---|---  
user_login |  **Type:** string Логин пользователя.  
user_uid |  **Type:** integer<int64> Идентификатор пользователя.  
  
## [](ru/management/openapi/grant/deleteGrant#responses)Responses

## [](ru/management/openapi/grant/deleteGrant#200-ok)200 OK

OK

### [](ru/management/openapi/grant/deleteGrant#body)Body

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

[Изменение разрешения](editgrant.md)

Следующая

[Информация о фильтре доступа](../access_filter/getaccessfilter.md)