# История изменений | API Яндекс Метрики

Request

## В этой статье:

  1. [API управления](../../index.md)
  2. Справочник API управления
  3. Управление фильтрами доступа
  4. Информация о фильтре доступа

# Информация о фильтре доступа

Возвращает информацию об указанном фильтре доступа. Подробнее о фильтрах доступа в [статье](https://yandex.../../../support/metrica/general/access-filters.md).

## [](ru/management/openapi/access_filter/getAccessFilter#request)Request

GET
    
    
    https://api-metrika.yandex.net/management/v1/counter/{counterId}/access_filter/{accessFilterId}
    

### [](ru/management/openapi/access_filter/getAccessFilter#path-parameters)Path parameters

**Name** |  **Description**  
---|---  
accessFilterId* |  **Type:** integer<int32> Идентификатор фильтра, информацию о котором вы хотите получить.  
counterId* |  **Type:** integer<int32> Идентификатор счетчика.  
  
## [](ru/management/openapi/access_filter/getAccessFilter#responses)Responses

## [](ru/management/openapi/access_filter/getAccessFilter#200-ok)200 OK

OK

### [](ru/management/openapi/access_filter/getAccessFilter#body)Body

application/json
    
    
    {
        "access_filter": {
            "id": 0,
            "counter_id": 0,
            "name": "string",
            "expression": "string",
            "interface_value": "string",
            "create_time": "2022-12-29T18:02:01Z"
        }
    }
    

**Name** |  **Description**  
---|---  
access_filter* |  **Type:** [AccessFilterDto](getaccessfilter.md) Фильтр доступа.  
  
### [](ru/management/openapi/access_filter/getAccessFilter#accessfilterdto)AccessFilterDto

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

[Удаление разрешения](../grant/deletegrant.md)

Следующая

[Список фильтров доступа для счетчика](getaccessfiltersforcounter.md)