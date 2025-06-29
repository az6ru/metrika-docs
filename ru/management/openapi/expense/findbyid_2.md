# Удаление данных о расходах в запросе - Импорт расходов | API Яндекс Метрики

Request

## В этой статье:

  1. API импорта данных
  2. Импорт расходов
  3. Информация о загрузке расходов

# Информация о загрузке расходов

Возвращает информацию об указанной загрузке расходов на рекламу.

## [](ru/management/openapi/expense/findById_2#request)Request

GET
    
    
    https://api-metrika.yandex.net/management/v1/counter/{counterId}/expense/uploading/{uploadingId}
    

### [](ru/management/openapi/expense/findById_2#path-parameters)Path parameters

**Name** |  **Description**  
---|---  
counterId* |  **Type:** integer<int32> Идентификатор счетчика, для которого вы хотите получить информацию о загрузке расходов.  
Example: `2215573`  
uploadingId* |  **Type:** integer<int64> Идентификатор загрузки, информацию о которой вы хотите получить. Идентификатор доступен при загрузке файла с расходами.  
Example: `12`  
  
## [](ru/management/openapi/expense/findById_2#responses)Responses

## [](ru/management/openapi/expense/findById_2#200-ok)200 OK

OK

### [](ru/management/openapi/expense/findById_2#body)Body

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
uploading* |  **Type:** [ExpenseUploading](findbyid_2.md) Информация о загрузке расходов.  
  
### [](ru/management/openapi/expense/findById_2#expenseuploading)ExpenseUploading

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

[Список загрузок расходов](findall_2.md)

Следующая

[Доступные значения TrafficSource и TrafficSourceDetail](../../table-source.md)