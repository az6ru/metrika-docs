# История изменений | API Яндекс Метрики

## В этой статье:

  1. API импорта данных
  2. Импорт расходов
  3. Загрузка расходов как multipart/form-data

# Загрузка расходов как multipart/form-data

Выполняет загрузку расходов.

Важно

Данные Директа загружать не нужно — они передаются в Метрику автоматически. Если вы загрузите данные в файле, они будут дублироваться с переданными автоматически — отчет станет некорректным.

Данные передаются как `multipart/form-data` в параметре `file`, в формате CSV. В первой строке запроса необходимо передать названия колонок.

Обязательные колонки:

  * `Date` — строка, дата в формате YYYY-MM-DD или диапазон дат в формате YYYY-MM-DD/YYYY-MM-DD.
  * `UTMSource` — строка, значение метки utm_source. Необязательна, если передается `TrafficSource`.
Необязательные колонки:

Примечание

Значения UTM-меток регистрозависимые. Это важно учесть при загрузке и удалении данных.

## [](ru/management/openapi/expense/uploadMultipart#request)Request

POST
    
    
    https://api-metrika.yandex.net/management/v1/counter/{counterId}/expense/upload
    

### [](ru/management/openapi/expense/uploadMultipart#path-parameters)Path parameters

**Name** |  **Description**  
---|---  
counterId* |  **Type:** integer<int32> Идентификатор счетчика, для которого вы хотите загрузить расходы.  
Example: `2215573`  
  
### [](ru/management/openapi/expense/uploadMultipart#query-parameters)Query parameters

**Name** |  **Description**  
---|---  
comment |  **Type:** string Комментарий.  
provider |  **Type:** string Сервис, который передает данные в Метрику (провайдер). Если не указано, используется значение `default`.  
  
### [](ru/management/openapi/expense/uploadMultipart#body)Body

multipart/form-data
    
    
    {
        "file": null
    }
    

**Name** |  **Description**  
---|---  
file* |  **Type:** string<binary>  
  
## [](ru/management/openapi/expense/uploadMultipart#responses)Responses

## [](ru/management/openapi/expense/uploadMultipart#200-ok)200 OK

OK

### [](ru/management/openapi/expense/uploadMultipart#body1)Body

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
uploading* |  **Type:** [ExpenseUploading](uploadmultipart.md) Информация о загрузке расходов.  
  
### [](ru/management/openapi/expense/uploadMultipart#expenseuploading)ExpenseUploading

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

[Введение](../../../data-import/index.md)

Следующая

[Удаление данных о расходах в запросе](uploadremovesingleline.md)