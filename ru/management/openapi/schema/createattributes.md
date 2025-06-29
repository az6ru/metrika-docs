# Как передавать данные о клиентах и заказах из CRM | API Яндекс Метрики

Request

## В этой статье:

  1. API импорта данных
  2. Импорт данных о клиентах и заказах из CRM
  3. Отправка подробных данных
  4. Загрузка пользовательских данных
  5. Создание атрибутов

# Создание атрибутов

Создает атрибуты клиентов и заказов. При создании пользовательских атрибутов не используйте идентификаторы системных атрибутов. Чтобы получить список идентификаторов системных атрибутов, используйте метод [GET /cdp/api/v1/counter/{counterId}/schema/attributes](../../../management-src/upravlenie-dannymi-o-klientah-i-zakazah-iz-crm/getattributes.md).

Пример тела запроса
    
    
    --data '{
            "attributes": [
                {
                    "name": "dates_of_meetings",
                    "type_name": "date",
                    "multivalued": true,
                    "humanized": "Даты обращений в магазин"
                },
                {
                    "name": "age",
                    "type_name": "numeric",
                    "multivalued": false,
                    "humanized": "Возраст"
                },
                {
                    "name": "first_seen",
                    "type_name": "date",
                    "multivalued": false,
                    "humanized": "Первый заказ"
                }
            ]
        }'
    

## [](ru/management/openapi/schema/createAttributes#request)Request

POST
    
    
    https://api-metrika.yandex.net/cdp/api/v1/counter/{counterId}/schema/attributes
    

### [](ru/management/openapi/schema/createAttributes#path-parameters)Path parameters

**Name** |  **Description**  
---|---  
counterId* |  **Type:** integer<int32> Идентификатор счетчика.  
Example: `2215573`  
  
### [](ru/management/openapi/schema/createAttributes#query-parameters)Query parameters

**Name** |  **Description**  
---|---  
entity_type* |  **Type:** string Принадлежность атрибутов.  
Возможные значения:

  * `CONTACT` — принадлежность контактам.
  * `COMPANY` — принадлежность компаниям.
  * `ORDER` — принадлежность заказам.
  * `SIMPLE_ORDER` — принадлежность простым заказам.   
Example: `CONTACT`

  
  
### [](ru/management/openapi/schema/createAttributes#body)Body

application/json
    
    
    {
        "attributes": [
            {
                "name": "string",
                "type_name": "string",
                "type_group": "string",
                "type_humanized": "string",
                "multivalued": false,
                "humanized": "string"
            }
        ]
    }
    

**Name** |  **Description**  
---|---  
attributes* |  **Type:** [Attribute](createattributes.md)[] Атрибуты списка.  
Описание объекта `Attribute`.  
  
### [](ru/management/openapi/schema/createAttributes#attribute)Attribute

Описание объекта `Attribute`.

**Name** |  **Description**  
---|---  
multivalued* |  **Type:** boolean Определяет, может ли атрибут иметь несколько значений.  
name* |  **Type:** string Идентификатор атрибута. _Min length:_ `1` _Max length:_ `255` _Pattern:_ `^[\w-:]+$`  
humanized |  **Type:** string Название атрибута. _Min length:_ `0` _Max length:_ `4096`  
type_group |  **Type:** string Группа типа атрибута. Возможные значения:

  * `PREDEFINED` — скалярный тип атрибута. Примеры значений `type_name`: `numeric`, `date`, `datetime`, `email`, `text`.
  * `CUSTOM_LIST` — произвольный тип атрибута.
  * `SYSTEM_LIST` — список продуктов, `type_name`: `product`.

  
type_humanized |  **Type:** string Название типа атрибута.  
type_name |  **Type:** string Идентификатор типа атрибута.  
  
## [](ru/management/openapi/schema/createAttributes#responses)Responses

## [](ru/management/openapi/schema/createAttributes#200-ok)200 OK

OK

### [](ru/management/openapi/schema/createAttributes#body1)Body

application/json
    
    
    {
        "success": true
    }
    

**Name** |  **Description**  
---|---  
success |  **Type:** boolean Результат выполнения операции. _Default:_ `true`  
  
No longer supported, please use an alternative and newer version.

### Была ли статья полезна?

ДаНет

Предыдущая

[Загрузка заказов (JSON)](uploadordersjson_1.md)

Следующая

[Создание списка товаров](createproducts.md)