# Передача данных о звонках | API Яндекс Метрики

Request

## В этой статье:

  1. API импорта данных
  2. Импорт звонков
  3. Загрузка информации о звонках

# Загрузка информации о звонках

Выполняет загрузку информации о звонках.

Совет

Сформируйте CSV-файл с информацией и передайте его с помощью данного метода. Также рекомендуем генерировать запросы к API в автоматическом режиме с помощью модулей языка программирования.

О том, какие данные передавать, и пример запроса см. в разделе [Передача данных о звонках](../../calls.md).

Примечание

Обработка данных может занимать до двух часов после загрузки.

## [](ru/management/openapi/call/uploadCalls#request)Request

POST
    
    
    https://api-metrika.yandex.net/management/v1/counter/{counterId}/offline_conversions/upload_calls
    

### [](ru/management/openapi/call/uploadCalls#path-parameters)Path parameters

**Name** |  **Description**  
---|---  
counterId* |  **Type:** integer<int32> Идентификатор счетчика, для которого вы хотите загрузить информацию о звонках.  
Example: `2215573`  
  
### [](ru/management/openapi/call/uploadCalls#query-parameters)Query parameters

**Name** |  **Description**  
---|---  
comment |  **Type:** string Комментарий.  
new_goal_name |  **Type:** string Название новой цели для звонков в случае, если такой цели не существует. Если цель существует, этот параметр игнорируется.  
Example: `Звонок`  
  
### [](ru/management/openapi/call/uploadCalls#body)Body

multipart/form-data
    
    
    {
        "file": null
    }
    

**Name** |  **Description**  
---|---  
file* |  **Type:** string<binary> Информация о звонках, которую вы хотите загрузить, передаваемая как multipart/form-data.  
  
## [](ru/management/openapi/call/uploadCalls#responses)Responses

## [](ru/management/openapi/call/uploadCalls#200-ok)200 OK

OK

### [](ru/management/openapi/call/uploadCalls#body1)Body

application/json
    
    
    {
        "uploading": {
            "id": 0,
            "create_time": "2022-12-29T18:02:01Z",
            "source_quantity": 0,
            "line_quantity": 0,
            "comment": "string",
            "client_id_type": "USER_ID",
            "status": "string",
            "static_calls_quantity": 0,
            "dynamic_calls_quantity": 0
        }
    }
    

**Name** |  **Description**  
---|---  
uploading* |  **Type:** [OfflineCallsUploading](uploadcalls.md) Информация о загрузке звонков.  
  
### [](ru/management/openapi/call/uploadCalls#offlinecallsuploading)OfflineCallsUploading

Информация о загрузке звонков.

**Name** |  **Description**  
---|---  
client_id_type |  **Type:** string Тип идентификаторов посетителей. Возможные значения:

  * `USER_ID` — идентификатор посетителя сайта, назначенный владельцем сайта.
  * `CLIENT_ID` — идентификатор посетителя сайта, назначенный Яндекс Метрикой.
  * `YCLID` — идентификатор клика по рекламному объявлению Яндекс Директа, назначенный Яндекс Директом.

_Example:_ `USER_ID`  
comment |  **Type:** string Произвольный комментарий. Количество символов не должно превышать 255. _Min length:_ `0` _Max length:_ `255`  
create_time |  **Type:** string<date-time> Время загрузки.  
dynamic_calls_quantity |  **Type:** integer<int32> Количество динамических звонков.  
id |  **Type:** integer<int64> Идентификатор загрузки.  
line_quantity |  **Type:** integer<int32> Количество строк, прошедших валидацию при загрузке.  
source_quantity |  **Type:** integer<int32> Количество строк в исходном файле.  
static_calls_quantity |  **Type:** integer<int32> Количество статических звонков.  
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

[Передача данных о звонках](../../calls.md)

Следующая

[Список загрузок информации о звонках](findallcalluploadings.md)