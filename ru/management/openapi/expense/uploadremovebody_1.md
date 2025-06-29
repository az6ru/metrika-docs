# Удаление данных о расходах в запросе - Импорт расходов | API Яндекс Метрики

## В этой статье:

  1. API импорта данных
  2. Импорт расходов
  3. Удаление данных о расходах как multipart/form-data

# Удаление данных о расходах как multipart/form-data

Удаляет загруженные в Метрику данные о расходах.

Примечание

Данные Директа удалить невозможно.

Данные передаются как multipart/form-data в параметре `file`, в формате CSV — укажите, какую именно информацию нужно удалить.

Обязательные колонки:

  * `Date` — строка, дата в формате YYYY-MM-DD или диапазон дат в формате YYYY-MM-DD/YYYY-MM-DD.

Необязательные колонки:

  * `UTMSource` — строка, значение метки `utm_source`.
  * `UTMMedium` — строка, значение метки `utm_medium`.
  * `UTMCampaign` — строка, значение метки `utm_campaign`.
  * `UTMTerm` — строка, значение метки `utm_term`.
  * `UTMContent` — строка, значение метки `utm_content`.
Примечание

Значения UTM-меток регистрозависимые. Регистр должен совпадать с тем, в котором значение было указано при загрузке данных.

## [](ru/management/openapi/expense/uploadRemoveBody_1#request)Request

POST
    
    
    https://api-metrika.yandex.net/management/v1/counter/{counterId}/expense/delete
    

### [](ru/management/openapi/expense/uploadRemoveBody_1#path-parameters)Path parameters

**Name** |  **Description**  
---|---  
counterId* |  **Type:** integer<int32> Идентификатор счетчика, для которого вы хотите удалить данные.  
Example: `2215573`  
  
### [](ru/management/openapi/expense/uploadRemoveBody_1#query-parameters)Query parameters

**Name** |  **Description**  
---|---  
comment |  **Type:** string Комментарий.  
provider |  **Type:** string Название провайдера данных, которое могло быть передано при загрузке расходов по API. Если значение параметра не указано, будут удалены данные для всех провайдеров по заданным в загруженном файле условиям.  
  
### [](ru/management/openapi/expense/uploadRemoveBody_1#body)Body

multipart/form-data
    
    
    {
        "file": null
    }
    

**Name** |  **Description**  
---|---  
file* |  **Type:** string<binary>  
  
## [](ru/management/openapi/expense/uploadRemoveBody_1#responses)Responses

## [](ru/management/openapi/expense/uploadRemoveBody_1#200-ok)200 OK

OK

### [](ru/management/openapi/expense/uploadRemoveBody_1#body1)Body

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
uploading* |  **Type:** [ExpenseUploading](uploadremovebody_1.md) Информация о загрузке расходов.  
  
### [](ru/management/openapi/expense/uploadRemoveBody_1#expenseuploading)ExpenseUploading

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

[Удаление данных о расходах в запросе](uploadremovesingleline.md)

Следующая

[Список загрузок расходов](findall_2.md)