# История изменений | API Яндекс Метрики

Request

## В этой статье:

  1. [API управления](../../index.md)
  2. Справочник API управления
  3. [Управление фильтрами доступа](getaccessfilter.md)
  4. Список фильтров доступа для счетчика

# Список фильтров доступа для счетчика

Возвращает список фильтров доступа. Подробнее о фильтрах доступа в [статье](https://yandex.../../../support/metrica/general/access-filters.md).

## [](ru/management/openapi/access_filter/getAccessFiltersForCounter#request)Request

GET
    
    
    https://api-metrika.yandex.net/management/v1/counter/{counterId}/access_filters
    

### [](ru/management/openapi/access_filter/getAccessFiltersForCounter#path-parameters)Path parameters

**Name** |  **Description**  
---|---  
counterId* |  **Type:** integer<int32> Идентификатор счетчика.  
Example: `2215573`  
  
## [](ru/management/openapi/access_filter/getAccessFiltersForCounter#responses)Responses

## [](ru/management/openapi/access_filter/getAccessFiltersForCounter#200-ok)200 OK

OK

### [](ru/management/openapi/access_filter/getAccessFiltersForCounter#body)Body

application/json
    
    
    {
        "access_filters": [
            {
                "id": 0,
                "counter_id": 0,
                "name": "string",
                "expression": "string",
                "interface_value": "string",
                "create_time": "2022-12-29T18:02:01Z"
            }
        ]
    }
    

**Name** |  **Description**  
---|---  
access_filters* |  **Type:** [AccessFilterDto](getaccessfiltersforcounter.md)[] Фильтры доступа.  
Фильтр доступа.  
  
### [](ru/management/openapi/access_filter/getAccessFiltersForCounter#accessfilterdto)AccessFilterDto

Фильтр доступа.

**Name** |  **Description**  
---|---  
counter_id |  **Type:** integer<int32> Идентификатор счетчика.  
create_time |  **Type:** string<date-time> Время создания фильтра доступа в формате yyyy-MM-dd'T'HH:mm:ssXXX.  
expression |  **Type:** string Выражение, которое соответствует [значению параметра filters](../../../stat/segmentation.md). _Min length:_ `1` _Max length:_ `65535`  
id |  **Type:** integer<int32> Идентификатор фильтра доступа.  
interface_value |  **Type:** string _Min length:_ `1` _Max length:_ `65535`  
name |  **Type:** string Название фильтра доступа. _Min length:_ `1` _Max length:_ `255`  
  
No longer supported, please use an alternative and newer version.

### Была ли статья полезна?

ДаНет

Предыдущая

[Информация о фильтре доступа](getaccessfilter.md)

Следующая

[Создание фильтра доступа](createaccessfilter.md)