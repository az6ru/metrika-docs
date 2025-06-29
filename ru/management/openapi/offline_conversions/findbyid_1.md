# Список загрузок офлайн-конверсий - Импорт офлайн-конверсий | API Яндекс Метрики

Request

## В этой статье:

  1. API импорта данных
  2. Импорт офлайн-конверсий
  3. Информация о загрузке офлайн-конверсий

# Информация о загрузке офлайн-конверсий

Возвращает информацию об указанной загрузке [офлайн-конверсий](../../conversion.md).

## [](ru/management/openapi/offline_conversions/findById_1#request)Request

GET
    
    
    https://api-metrika.yandex.net/management/v1/counter/{counterId}/offline_conversions/uploading/{id}
    

### [](ru/management/openapi/offline_conversions/findById_1#path-parameters)Path parameters

**Name** |  **Description**  
---|---  
counterId* |  **Type:** integer<int32> Идентификатор счетчика, для которого вы хотите получить информацию о загрузке офлайн-конверсий.  
Example: `2215573`  
id* |  **Type:** integer<int64> Идентификатор загрузки, информацию о которой вы хотите получить. Идентификатор доступен при загрузке информации об офлайн-конверсии.  
Example: `12`  
  
## [](ru/management/openapi/offline_conversions/findById_1#responses)Responses

## [](ru/management/openapi/offline_conversions/findById_1#200-ok)200 OK

OK

### [](ru/management/openapi/offline_conversions/findById_1#body)Body

application/json
    
    
    {
        "uploading": {
            "id": 0,
            "create_time": "2022-12-29T18:02:01Z",
            "source_quantity": 0,
            "line_quantity": 0,
            "comment": "string",
            "client_id_type": "USER_ID",
            "status": "string"
        }
    }
    

**Name** |  **Description**  
---|---  
uploading* |  **Type:** [OfflineConversionUploading](findbyid_1.md) Информация о загрузке офлайн-конверсий.  
  
### [](ru/management/openapi/offline_conversions/findById_1#offlineconversionuploading)OfflineConversionUploading

Информация о загрузке офлайн-конверсий.

**Name** |  **Description**  
---|---  
client_id_type |  **Type:** string Тип идентификаторов посетителей. Возможные значения:

  * `USER_ID` — идентификатор посетителя сайта, назначенный владельцем сайта.
  * `CLIENT_ID` — идентификатор посетителя сайта, назначенный Яндекс Метрикой.
  * `YCLID` — идентификатор клика по рекламному объявлению Яндекс Директа, назначенный Яндекс Директом.

_Example:_ `USER_ID`  
comment |  **Type:** string Произвольный комментарий. Количество символов не должно превышать 255. _Min length:_ `0` _Max length:_ `255`  
create_time |  **Type:** string<date-time> Время загрузки.  
id |  **Type:** integer<int64> Идентификатор загрузки.  
line_quantity |  **Type:** integer<int32> Количество строк, прошедших валидацию при загрузке.  
source_quantity |  **Type:** integer<int32> Количество строк в исходном файле.  
status |  **Type:** string Статус загрузки:

  * `PREPARED` — загрузка подготовлена.
  * `UPLOADED` — загрузка завершена.
  * `EXPORTED` — загрузка экспортирована.
  * `MATCHED` — произведено сопоставление идентификаторов событий.
  * `PROCESSED` — загрузка успешно обработана.
  * `LINKAGE_FAILURE` — не удалось сопоставить ни один идентификатор посетителя. Если передана информация о статических звонках, они не будут привязаны к визитам в Метрике, но будут доступны в отчетах по звонкам.

  
  
No longer supported, please use an alternative and newer version.

### Была ли статья полезна?

ДаНет

Предыдущая

[Список загрузок офлайн-конверсий](findall_1.md)

Следующая

[Информация о загрузке параметров](../user_params/findbyid.md)