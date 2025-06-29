# Использование Measurement Protocol | API Яндекс Метрики

Request

## В этой статье:

  1. API импорта данных
  2. Импорт параметров посетителей
  3. Список загрузок параметров

# Список загрузок параметров

Возвращает список загрузок параметров.

## [](ru/management/openapi/user_params/findAll#request)Request

GET
    
    
    https://api-metrika.yandex.net/management/v1/counter/{counterId}/user_params/uploadings
    

### [](ru/management/openapi/user_params/findAll#path-parameters)Path parameters

**Name** |  **Description**  
---|---  
counterId* |  **Type:** integer<int32> Идентификатор счетчика, список загрузок параметров которого вы хотите получить.  
Example: `2215573`  
  
### [](ru/management/openapi/user_params/findAll#query-parameters)Query parameters

**Name** |  **Description**  
---|---  
limit |  **Type:** integer<int32> Количество объектов на одной странице.  
_Default:_ `10000`  
offset |  **Type:** integer<int32> Количество объектов в списке, которые необходимо пропустить.  
_Default:_ `0`  
  
## [](ru/management/openapi/user_params/findAll#responses)Responses

## [](ru/management/openapi/user_params/findAll#200-ok)200 OK

OK

### [](ru/management/openapi/user_params/findAll#body)Body

application/json
    
    
    {
        "uploadings": [
            {
                "id": 0,
                "create_time": "2022-12-29T18:02:01Z",
                "line_quantity": 0,
                "comment": "string",
                "content_id_type": "string",
                "action": "string",
                "status": "string"
            }
        ]
    }
    

**Name** |  **Description**  
---|---  
uploadings |  **Type:** [UserParamsUploading](findall.md)[] Информация о загруженных параметрах посетителей.  
  
### [](ru/management/openapi/user_params/findAll#userparamsuploading)UserParamsUploading

Информация о загруженных параметрах посетителей.

**Name** |  **Description**  
---|---  
action |  **Type:** string Действие, которое необходимо выполнить:

  * `update` — добавление параметров.
  * `delete_keys` — удаление параметров.

  
comment |  **Type:** string Произвольный комментарий. Количество символов не должно превышать 255. _Min length:_ `0` _Max length:_ `255`  
content_id_type |  **Type:** string Тип идентификаторов посетителей:

  * `user_id` — идентификатор посетителя сайта, назначенный владельцем сайта.
  * `client_id` — идентификатор посетителя сайта, назначенный Яндекс Метрикой.

  
create_time |  **Type:** string<date-time> Время загрузки.  
id |  **Type:** integer<int64> Идентификатор загрузки.  
line_quantity |  **Type:** integer<int32> Количество строк, прошедших валидацию при загрузке.  
status |  **Type:** string Статус загрузки:

  
  
No longer supported, please use an alternative and newer version.

### Была ли статья полезна?

ДаНет

Предыдущая

[Подтверждение загрузки параметров](confirm.md)

Следующая

[Использование Measurement Protocol](../../../data-import/measurement-about.md)