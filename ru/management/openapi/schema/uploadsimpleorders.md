# Как передавать данные о клиентах и заказах из CRM | API Яндекс Метрики

## В этой статье:

  1. API импорта данных
  2. Импорт данных о клиентах и заказах из CRM
  3. Упрощенная отправка данных
  4. Загрузка упрощенных данных о клиентах и заказах (CSV)

# Загрузка упрощенных данных о клиентах и заказах (CSV)

Упрощенный метод помогает отправлять в Метрику информацию о заказах и клиентах в CSV-файле без дополнительных настроек ([сопоставления статусов заказов](../../../data-import/maporderstatuses-about.md), загрузки отдельных списков [клиентов](../../../data-import/contacts-data.md) и [заказов](../../../data-import/orders-data.md), загрузки [списка товаров](../../../management-src/upravlenie-dannymi-o-klientah-i-zakazah-iz-crm/createproducts.md) и [дополнительных атрибутов](../../../management-src/upravlenie-dannymi-o-klientah-i-zakazah-iz-crm/createattributes.md)). Для сбора статистики достаточно передавать дату и время создания заказа в часовом поясе счетчика (`create_date_time`) и один из параметров клиентов ([ClientID](https://yandex.../../../support/metrica/objects/get-client-id.md), номер телефона или адрес электронной почты, хеши телефона или почты). Вы можете передавать заказы в разных статусах с данными о выручке и себестоимости.

Отправленная информация учитывается в отчетах [Сквозной аналитики](../../../stat/presets/preset_cdp_orders.md). Кроме этого, вы можете использовать данные для ретаргетинга и оптимизации конверсий в Директе.

[Подробно о формате передаваемых данных](../../../data-import/simple-orders-data.md)

Примечание

Ограничение на размер файла — 1 Гб.

Примеры загружаемого файла

  * [Загрузка данных по ClientID](https://download.cdn.yandex.net/from/yandex.../../../support/../../../metrica/files/simple_orders_client_ids.md). Рекомендуем использовать этот тип идентификатора, так как он обеспечивает более точную привязку загруженных данных с информацией о посетителях сайта в Метрике.
  * [Загрузка данных по адресам электронной почты](https://download.cdn.yandex.net/from/yandex.../../../support/../../../metrica/files/simple_orders_emails.md).
  * [Загрузка данных по номерам телефонов](https://download.cdn.yandex.net/from/yandex.../../../support/../../../metrica/files/simple_orders_phones.md).
  * [Загрузка в одном файле разных идентификаторов](https://download.cdn.yandex.net/from/yandex.../../../support/../../../metrica/files/simple_orders_full.md).

При отправке данных о заказах в параметре `merge_mode` передавайте значение, соответствующее состоянию загружаемых заказов. Если при повторной отправке данных вы не уверены, какой именно статус нужно передавать, укажите значение `SAVE`.

**Пример запроса**
    
    
    POST https://api-metrika.yandex.net/cdp/api/v1/counter/2215573/data/simple_orders?merge_mode=SAVE&delimiter_type=COMMA
    Content-Disposition: form-data; name="file"; filename="data.csv"
    Content-Type: multipart/form-data; boundary=------------------------7zDUQOAIAE9hEWoV
    Context-Length: TBD
    
    --------------------------7zDUQOAIAE9hEWoV
    Content-Disposition: form-data; name="file"; filename="data.csv"
    Content-Type: text/csv
    
    id,create_date_time,client_uniq_id,client_ids,emails,phones,order_status,revenue,cost,goals,currency
    s_ord1,10.01.2024 11:56,s_user1,,"mail@example.com,mail2@example.com",,PAID,200,150,"oplata_cash:200,filial_1",
    s_ord2,20.01.2024 11:59,,12345,mail3@example.com,,,200,150,,EUR
    ,12.02.2024,,34456,,79876543210,SPAM,,,plohoy_lead,
    --------------------------7zDUQOAIAE9hEWoV--
    

Разберем пример отправки

В примере мы отправили три заказа:

#### [](ru/management/openapi/schema/uploadSimpleOrders#zakaz-s-id-s_ord1)Заказ с id s_ord1

  * **Дата заказа** : 10.01.2024 11:56
  * **Идентификатор клиента в CRM** : `s_user1`
  * **Почты клиента** : mail@example.com, mail2@example.com
  * **ClientID и телефоны** : отсутствуют
  * **Статус заказа** : `PAID` (будет достигнуты цели **CRM – Заказ Создан** \+ **CRM – Заказ Оплачен**)
  * **Доход** : 200
  * **Себестоимость** : 150 (в целях будет указан доход в 50)
  * **Дополнительно отправлены javascript-цели** : 
    * `oplata_cash` с доходом в 200
    * `filial_1` без дохода (доход по цели будет использован из основных колонок заказа, а именно 200-150=50)
  * **Валюта** : не указана (все доходы будут в рублях)

#### [](ru/management/openapi/schema/uploadSimpleOrders#zakaz-s-id-s_ord2)Заказ с id s_ord2

  * **Дата заказа** : 20.01.2024 11:59
  * **Идентификатор клиента в CRM** : не передан
  * **Почта клиента** : mail3@example.com
  * **ClientID** : 12345
  * **Телефоны** : отсутствуют
  * **Статус заказа** : не передан (по умолчанию будет отправлен `PAID`, достигнуты цели: **CRM – Заказ Создан** \+ **CRM – Заказ Оплачен**)
  * **Доход** : 200
  * **Себестоимость** : 150 (в целях будет указан доход в 50)
  * **Дополнительные цели** : отсутствуют
  * **Валюта** : EUR (все доходы будут в евро)

#### [](ru/management/openapi/schema/uploadSimpleOrders#zakaz-bez-id)Заказ без id

  * **Дата заказа** : 12.02.2024 (без указания часов/минут — Метрика будет искать для привязки заказа визиты в прошлом, начиная с 12.02.2024 23:59)
  * **Идентификатор клиента в CRM** : не передан
  * **Почта клиента** : mail3@example.com
  * **ClientID** : 34456
  * **Телефон** : 79876543210
  * **Статус заказа** : `SPAM` (цели не будут достигнуты)
  * **Доход и себестоимость** : не указаны
  * **Дополнительно отправлена javascript-цель** : 
    * `plohoy_lead` — будет достигнута без дохода
  * **Валюта** : не указана

## [](ru/management/openapi/schema/uploadSimpleOrders#request)Request

POST
    
    
    https://api-metrika.yandex.net/cdp/api/v1/counter/{counterId}/data/simple_orders
    

### [](ru/management/openapi/schema/uploadSimpleOrders#path-parameters)Path parameters

**Name** |  **Description**  
---|---  
counterId* |  **Type:** integer<int32> Идентификатор счетчика, для которого вы хотите загрузить заказы.  
Example: `2215573`  
  
### [](ru/management/openapi/schema/uploadSimpleOrders#query-parameters)Query parameters

**Name** |  **Description**  
---|---  
merge_mode* |  **Type:** string Режим сохранения данных. При любом из значений передавайте все [обязательные поля](../../../data-import/orders-data.md) — даже те, которые не меняются.  

Example: `SAVE`

  
delimiter_type |  **Type:** string Вид разделителя столбцов в файле.  

  * `COMMA` — разделитель "запятая".
  * `SEMICOLON` — разделитель "точка с запятой".

_Default:_ `COMMA`  
  
### [](ru/management/openapi/schema/uploadSimpleOrders#body)Body

multipart/form-data
    
    
    {
        "file": null
    }
    

**Name** |  **Description**  
---|---  
file* |  **Type:** string<binary> Ограничение на размер файла — 1 Гб.  
  
## [](ru/management/openapi/schema/uploadSimpleOrders#responses)Responses

## [](ru/management/openapi/schema/uploadSimpleOrders#200-ok)200 OK

OK

### [](ru/management/openapi/schema/uploadSimpleOrders#body1)Body

application/json
    
    
    {
        "uploading": {
            "uploading_id": "string",
            "datetime": "2022-12-29T18:02:01Z",
            "api_validation_status": "string",
            "elements_count": 0,
            "entity_type": "string",
            "uploading_format": "string",
            "uploading_source": "string"
        }
    }
    

**Name** |  **Description**  
---|---  
uploading |  **Type:** [UploadingMetaExternal](uploadsimpleorders.md) Описание объекта `UploadingMetaExternal`.  
  
### [](ru/management/openapi/schema/uploadSimpleOrders#uploadingmetaexternal)UploadingMetaExternal

Описание объекта `UploadingMetaExternal`.

**Name** |  **Description**  
---|---  
api_validation_status |  **Type:** string Статус валидации загрузки:

  * `PASSED` — валидация прошла успешно.
  * `FAILED` — валидация прошла не успешно.

  
datetime |  **Type:** string<date-time> Время загрузки.  
elements_count |  **Type:** integer<int32> Количество элементов в загрузке.  
entity_type |  **Type:** string Тип сущности:

  * `SYSTEM` — системная сущность, например, контакты или заказы.
  * `CUSTOM_LIST` — пользовательский список.
  * `SYSTEM_LIST` — системный список, например товары.

  
uploading_format |  **Type:** string Формат загрузки. Возможные значения:

  * `JSON`.
  * `CSV`.

  
uploading_id |  **Type:** string Идентификатор загрузки.  
uploading_source |  **Type:** string Источник загрузки. Возможные значения: `API`.  
  
No longer supported, please use an alternative and newer version.

### Была ли статья полезна?

ДаНет

Предыдущая

[Настройка упрощенной отправки данных](../../../data-import/simple-orders-prep.md)

Следующая

[Формат упрощенных данных о заказах и клиентах](../../../data-import/simple-orders-data.md)