# История изменений | API Яндекс Метрики

Request

## В этой статье:

  1. API импорта данных
  2. Импорт расходов
  3. Удаление данных о расходах в запросе

# Удаление данных о расходах в запросе

Удаляет загруженные в Метрику данные о расходах. Метод позволяет прямо в запросе передать данные, которые нужно удалить.

Примечание

Данные Директа удалить невозможно.

Примечание

Значения UTM-меток регистрозависимые. Регистр должен совпадать с тем, в котором значение было указано при загрузке данных.

## [](ru/management/openapi/expense/uploadRemoveSingleLine#request)Request

POST
    
    
    https://api-metrika.yandex.net/management/v1/counter/{counterId}/expense/delete_single
    

### [](ru/management/openapi/expense/uploadRemoveSingleLine#path-parameters)Path parameters

**Name** |  **Description**  
---|---  
counterId* |  **Type:** integer<int32> Идентификатор счетчика, для которого вы хотите удалить данные.  
Example: `2215573`  
  
### [](ru/management/openapi/expense/uploadRemoveSingleLine#query-parameters)Query parameters

**Name** |  **Description**  
---|---  
date* |  **Type:** string Дата в формате YYYY-MM-DD или диапазон дат в формате YYYY-MM-DD/YYYY-MM-DD.  
UTMCampaign |  **Type:** string Строка, значение метки `utm_campaign`.  
UTMContent |  **Type:** string Строка, значение метки `utm_content`.  
UTMMedium |  **Type:** string Строка, значение метки `utm_medium`.  
UTMSource |  **Type:** string Строка, значение метки `utm_source`.  
UTMTerm |  **Type:** string Строка, значение метки `utm_term`.  
comment |  **Type:** string Комментарий.  
provider |  **Type:** string Название провайдера данных, которое могло быть передано при загрузке расходов по API. Если значение параметра не указано, будут удалены данные для всех провайдеров по заданным в загруженном файле условиям.  
trafficSource |  **Type:** string Источник трафика первого уровня. Доступные значения описаны в [таблице](../../table-source.md).  
trafficSourceDetail |  **Type:** string Источник трафика второго уровня. Доступные значения описаны в [таблице](../../table-source.md).  
  
## [](ru/management/openapi/expense/uploadRemoveSingleLine#responses)Responses

## [](ru/management/openapi/expense/uploadRemoveSingleLine#200-ok)200 OK

OK

### [](ru/management/openapi/expense/uploadRemoveSingleLine#body)Body

application/json
    
    
    {
        "uploading": {
            "id": 0,
            "create_time": "2022-12-29T18:02:01Z",
            "source_quantity": 0,
            "provider": "string",
            "comment": "string",
            "type": "string",
            "status": "string"
        }
    }
    

**Name** |  **Description**  
---|---  
uploading* |  **Type:** [ExpenseUploading](uploadremovesingleline.md) Информация о загрузке расходов.  
  
### [](ru/management/openapi/expense/uploadRemoveSingleLine#expenseuploading)ExpenseUploading

Информация о загрузке расходов.

**Name** |  **Description**  
---|---  
comment |  **Type:** string Комментарий.  
create_time |  **Type:** string<date-time> Время загрузки.  
id |  **Type:** integer<int64> Идентификатор загрузки.  
provider |  **Type:** string Имя провайдера данных.  
source_quantity |  **Type:** integer<int32> Количество строк в исходном файле.  
status |  **Type:** string Статус загрузки:

  * `UPLOADED` — загрузка завершена.
  * `IN_PROGRESS` — загрузка находится в процессе обработки.
  * `PROCESSED` — загрузка успешно обработана.

  
type |  **Type:** string Тип загрузки:

  * `EXPENSES` — расходы.
  * `REMOVES` — удаление расходов.

  
  
No longer supported, please use an alternative and newer version.

### Была ли статья полезна?

ДаНет

Предыдущая

[Загрузка расходов как multipart/form-data](uploadmultipart.md)

Следующая

[Удаление данных о расходах как multipart/form-data](uploadremovebody_1.md)