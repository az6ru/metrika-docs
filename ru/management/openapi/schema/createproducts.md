# Как передавать данные о клиентах и заказах из CRM | API Яндекс Метрики

Request

## В этой статье:

  1. API импорта данных
  2. Импорт данных о клиентах и заказах из CRM
  3. Отправка подробных данных
  4. Загрузка пользовательских данных
  5. Создание списка товаров

# Создание списка товаров

Создает список товаров.

Пример тела запроса
    
    
    --data '{
            "attributes": [],
            "items": [
                {
                    "name": "pear",
                    "humanized": "Груша"
                },
                {
                    "name": "cherry",
                    "humanized": "Вишня"
                },
                {
                    "name": "apple",
                    "humanized": "Яблоко"
                },
                {
                    "name": "tomato",
                    "humanized": "Томат"
                }
            ]
        }'
    

## [](ru/management/openapi/schema/createProducts#request)Request

POST
    
    
    https://api-metrika.yandex.net/cdp/api/v1/counter/{counterId}/schema/products
    

### [](ru/management/openapi/schema/createProducts#path-parameters)Path parameters

**Name** |  **Description**  
---|---  
counterId* |  **Type:** integer<int32> Идентификатор счетчика.  
Example: `2215573`  
  
### [](ru/management/openapi/schema/createProducts#body)Body

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
        ],
        "items": [
            {
                "name": "string",
                "humanized": "string"
            }
        ]
    }
    

**Name** |  **Description**  
---|---  
attributes* |  **Type:** [Attribute](createproducts.md)[] Атрибуты списка.  
Описание объекта `Attribute`. _Min items:_ `0` _Max items:_ `160000`  
items |  **Type:** [ListItem](createproducts.md)[] Элементы списка.  
Описание объекта `ListItem`. _Min items:_ `0` _Max items:_ `160000`  
  
### [](ru/management/openapi/schema/createProducts#attribute)Attribute

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
  
### [](ru/management/openapi/schema/createProducts#listitem)ListItem

Описание объекта `ListItem`.

**Name** |  **Description**  
---|---  
name* |  **Type:** string Идентификатор элемента списка. _Min length:_ `1` _Max length:_ `255` _Pattern:_ `^[\w-:]+$`  
humanized |  **Type:** string Название элемента списка. _Min length:_ `0` _Max length:_ `4096`  
  
## [](ru/management/openapi/schema/createProducts#responses)Responses

## [](ru/management/openapi/schema/createProducts#200-ok)200 OK

OK

### [](ru/management/openapi/schema/createProducts#body1)Body

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

[Создание атрибутов](createattributes.md)

Следующая

[Информация о всех атрибутах](getattributes.md)