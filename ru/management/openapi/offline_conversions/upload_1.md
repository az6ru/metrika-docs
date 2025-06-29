# Список загрузок офлайн-конверсий - Импорт офлайн-конверсий | API Яндекс Метрики

Request

## В этой статье:

  1. API импорта данных
  2. Импорт офлайн-конверсий
  3. Загрузка офлайн-конверсий

# Загрузка офлайн-конверсий

Выполняет загрузку [офлайн-конверсий](../../conversion.md).

Совет

Сформируйте CSV-файл с информацией и передайте его с помощью данного метода. Также рекомендуем генерировать запросы к API в автоматическом режиме с помощью модулей языка программирования.

О том, какие данные передавать, и пример запроса см. в разделе [Передача офлайн-конверсий](../../offline-conv.md).

Примечание

  1. Обработка данных может занимать до двух часов.
  2. Ограничение на размер файла — 1 Гб.
  3. Кодировка файла — UTF-8.

## [](ru/management/openapi/offline_conversions/upload_1#request)Request

POST
    
    
    https://api-metrika.yandex.net/management/v1/counter/{counterId}/offline_conversions/upload
    

### [](ru/management/openapi/offline_conversions/upload_1#path-parameters)Path parameters

**Name** |  **Description**  
---|---  
counterId* |  **Type:** integer<int32> Идентификатор счетчика, для которого вы хотите загрузить офлайн-конверсии.  
Example: `2215573`  
  
### [](ru/management/openapi/offline_conversions/upload_1#query-parameters)Query parameters

**Name** |  **Description**  
---|---  
comment |  **Type:** string Комментарий. Максимальная длина — 255 символов. Допустимы цифры, латинские и кириллические буквы.  
  
### [](ru/management/openapi/offline_conversions/upload_1#body)Body

multipart/form-data
    
    
    {
        "file": null
    }
    

**Name** |  **Description**  
---|---  
file* |  **Type:** string<binary> Офлайн-конверсии, которые вы хотите загрузить, передаваемые как multipart/form-data. Ограничение на размер файла — 1 Гб. Кодировка файла — UTF-8.  
  
## [](ru/management/openapi/offline_conversions/upload_1#responses)Responses

## [](ru/management/openapi/offline_conversions/upload_1#200-ok)200 OK

OK

### [](ru/management/openapi/offline_conversions/upload_1#body1)Body

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
uploading* |  **Type:** [OfflineConversionUploading](upload_1.md) Информация о загрузке офлайн-конверсий.  
  
### [](ru/management/openapi/offline_conversions/upload_1#offlineconversionuploading)OfflineConversionUploading

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

[Передача офлайн-конверсий](../../offline-conv.md)

Следующая

[Список загрузок офлайн-конверсий](findall_1.md)