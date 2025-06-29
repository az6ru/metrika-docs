# Удаление данных о расходах в запросе - Импорт расходов | API Яндекс Метрики

Request

## В этой статье:

  1. API импорта данных
  2. Импорт расходов
  3. Список загрузок расходов

# Список загрузок расходов

Возвращает список загрузок расходов на рекламу.

## [](ru/management/openapi/expense/findAll_2#request)Request

GET
    
    
    https://api-metrika.yandex.net/management/v1/counter/{counterId}/expense/uploadings
    

### [](ru/management/openapi/expense/findAll_2#path-parameters)Path parameters

**Name** |  **Description**  
---|---  
counterId* |  **Type:** integer<int32> Идентификатор счетчика, для которого вы хотите получить список загрузок расходов.  
Example: `2215573`  
  
### [](ru/management/openapi/expense/findAll_2#query-parameters)Query parameters

**Name** |  **Description**  
---|---  
limit |  **Type:** integer<int32> Количество загрузок, которые вы хотите получить.  
_Default:_ `10000`  
offset |  **Type:** integer<int32> Порядковый номер загрузки, с которой начнется выдача списка загрузок. Первая загрузка имеет номер 0.  
_Default:_ `0`  
  
## [](ru/management/openapi/expense/findAll_2#responses)Responses

## [](ru/management/openapi/expense/findAll_2#200-ok)200 OK

OK

### [](ru/management/openapi/expense/findAll_2#body)Body

application/json
    
    
    {
        "uploadings": [
            {
                "id": 0,
                "create_time": "2022-12-29T18:02:01Z",
                "source_quantity": 0,
                "provider": "string",
                "comment": "string",
                "type": "string",
                "status": "string"
            }
        ]
    }
    

**Name** |  **Description**  
---|---  
uploadings |  **Type:** [ExpenseUploading](findall_2.md)[] Список загрузок расходов.  
Информация о загрузке расходов.  
  
### [](ru/management/openapi/expense/findAll_2#expenseuploading)ExpenseUploading

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

[Удаление данных о расходах как multipart/form-data](uploadremovebody_1.md)

Следующая

[Информация о загрузке расходов](findbyid_2.md)