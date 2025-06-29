# История изменений | API Яндекс Метрики

Request

## В этой статье:

  1. [API управления](../../index.md)
  2. Справочник API управления
  3. Управление фильтрами доступа
  4. Удаление фильтра доступа

# Удаление фильтра доступа

Удаляет указанный фильтр доступа. Подробнее о фильтрах доступа в [статье](https://yandex.../../../support/metrica/general/access-filters.md).

## [](ru/management/openapi/access_filter/deleteAccessFilter#request)Request

DELETE
    
    
    https://api-metrika.yandex.net/management/v1/counter/{counterId}/access_filter/{accessFilterId}
    

### [](ru/management/openapi/access_filter/deleteAccessFilter#path-parameters)Path parameters

**Name** |  **Description**  
---|---  
accessFilterId* |  **Type:** integer<int32> Идентификатор фильтр доступа, который вы хотите удалить.  
Example: `1000000042`  
counterId* |  **Type:** integer<int32> Идентификатор счетчика.  
Example: `2215573`  
  
### [](ru/management/openapi/access_filter/deleteAccessFilter#query-parameters)Query parameters

**Name** |  **Description**  
---|---  
delete_grants |  **Type:** boolean Признак удаления всех разрешений, которые входят в указанный фильтр доступа.  
_Default:_ `false`  
  
## [](ru/management/openapi/access_filter/deleteAccessFilter#responses)Responses

## [](ru/management/openapi/access_filter/deleteAccessFilter#200-ok)200 OK

OK

### [](ru/management/openapi/access_filter/deleteAccessFilter#body)Body

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

[Изменение фильтра доступа](updateaccessfilter.md)

Следующая

[Информация о цели](../goal/goal.md)