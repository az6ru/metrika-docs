# Создание публичного разрешения - Публичный доступ | API Яндекс Метрики

Request

## В этой статье:

  1. [API управления](../../index.md)
  2. Справочник API управления
  3. Управление доступами
  4. Информация о разрешении текущего пользователя

# Информация о разрешении текущего пользователя

Возвращает информацию о разрешениях на управление счетчиком и просмотр статистики для авторизированного пользователя.

## [](ru/management/openapi/grant/myGrant#request)Request

GET
    
    
    https://api-metrika.yandex.net/management/v1/counter/{counterId}/my_grant
    

### [](ru/management/openapi/grant/myGrant#path-parameters)Path parameters

**Name** |  **Description**  
---|---  
counterId* |  **Type:** integer<int32> Идентификатор счетчика.  
Example: `2215573`  
  
## [](ru/management/openapi/grant/myGrant#responses)Responses

## [](ru/management/openapi/grant/myGrant#200-ok)200 OK

OK

### [](ru/management/openapi/grant/myGrant#body)Body

application/json
    
    
    {
        "grant": {
            "user_login": "string",
            "perm": "string",
            "created_at": "2022-12-29T18:02:01Z",
            "comment": "string",
            "partner_data_access": false
        }
    }
    

**Name** |  **Description**  
---|---  
grant* |  **Type:** [CounterGrantE](mygrant.md) or [AccessFiltersGrantE](mygrant.md)  
  
### [](ru/management/openapi/grant/myGrant#countergrante)CounterGrantE

Список структур с информацией о правах доступа к счетчику.

**Name** |  **Description**  
---|---  
perm* |  **Type:** string Уровень доступа:

  * `public_stat` — публичный доступ к статистике.
  * `view` — только просмотр.
  * `edit` — полный доступ.
  * `analyst` — аналитик.
  * `analyst_access_filter` — аналитик данных через фильтр.

  
comment |  **Type:** string Произвольный комментарий. Количество символов не должно превышать 255. _Min length:_ `0` _Max length:_ `255`  
created_at |  **Type:** string<date-time> Дата предоставления доступа в формате YYYY-MM-DD'T'hh:mm:ssZ.  
partner_data_access |  **Type:** boolean Доступ к группе отчетов «Монетизация». Пользователь сможет просматривать отчеты, добавлять группировки и метрики из группы «Монетизация» в другие отчеты. Если у пользователя есть доступ на редактирование, то ему уже доступны отчеты группы «Монетизация». Возможные значения:

  * `true` — доступ разрешен;
  * `false` — доступ не разрешен.

  
user_login |  **Type:** string Логин пользователя, которому выдано разрешение на управление счетчиком. Параметр содержит пустую строку, если к статистике счетчика предоставлен публичный доступ (`perm = public_stat`).  
  
### [](ru/management/openapi/grant/myGrant#accessfiltersgrante)AccessFiltersGrantE

**Name** |  **Description**  
---|---  
access_filters* |  **Type:** [AccessFiltersShortE](mygrant.md)[] Список фильтров доступа, к которым выдано разрешение. _Min items:_ `1` _Max items:_ `1`  
perm* |  **Type:** string Уровень доступа:

  * `public_stat` — публичный доступ к статистике.
  * `view` — только просмотр.
  * `edit` — полный доступ.
  * `analyst` — аналитик.
  * `analyst_access_filter` — аналитик данных через фильтр.

  
comment |  **Type:** string Произвольный комментарий. Количество символов не должно превышать 255. _Min length:_ `0` _Max length:_ `255`  
created_at |  **Type:** string<date-time> Дата предоставления доступа в формате YYYY-MM-DD'T'hh:mm:ssZ.  
partner_data_access |  **Type:** boolean Доступ к группе отчетов «Монетизация». Пользователь сможет просматривать отчеты, добавлять группировки и метрики из группы «Монетизация» в другие отчеты. Если у пользователя есть доступ на редактирование, то ему уже доступны отчеты группы «Монетизация». Возможные значения:

  * `true` — доступ разрешен;
  * `false` — доступ не разрешен.

  
user_login |  **Type:** string Логин пользователя, которому выдано разрешение на управление счетчиком. Параметр содержит пустую строку, если к статистике счетчика предоставлен публичный доступ (`perm = public_stat`).  
  
### [](ru/management/openapi/grant/myGrant#accessfiltersshorte)AccessFiltersShortE

Список фильтров доступа, к которым выдано разрешение.

**Name** |  **Description**  
---|---  
id |  **Type:** integer<int32> id фильтра доступа.  
name |  **Type:** string Название фильтра доступа.  
  
No longer supported, please use an alternative and newer version.

### Была ли статья полезна?

ДаНет

Предыдущая

[Информация о разрешении](grant.md)

Следующая

[Создание публичного разрешения](addpublicgrant.md)