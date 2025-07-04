# Как передавать данные о клиентах и заказах из CRM | API Яндекс Метрики

Шаг 1. Подготовка данных для привязки к визитам

## В этой статье:

  1. [API импорта данных](index.md)
  2. Импорт данных о клиентах и заказах из CRM
  3. Отправка подробных данных
  4. Настройка отправки подробных данных

# Настройка отправки подробных данных о клиентах и заказах из CRM

## [](ru/data-import/data#data)Шаг 1. Подготовка данных для привязки к визитам

Метрика привязывает данные из CRM к посетителям и их визитам на сайте. Для привязки Метрика использует характеристики клиентов (`phones`, `emails`, `phones_md5`, `emails_md5`), а также специальный идентификатор [ClientId](https://yandex.../support/metrica/general/clientid-userid.md). Идентификатор Метрики [ClientId](https://yandex.../support/metrica/general/clientid-userid.md) обеспечивает самый высокий уровень привязки заказов к визитам пользователей на сайте — рекомендуем передавать именно его.

**Как настроить передачу ClientID?**

Передача [ClientId](https://yandex.../support/metrica/general/clientid-userid.md) — это процесс включения уникального идентификатора пользователя Метрики в записи о сделках в вашей CRM-системе. Настройте передачу параметра в зависимости от того, как именно происходит контакт с пользователем:

  * **Формы и заказы на сайте**. Получите `ClientId` с помощью JavaScript-метода [getClientID](https://yandex.../support/metrica/objects/get-client-id.md) и запишите его в скрытое поле ваших лид-форм для последующей передачи в CRM.

  * **Звонки посетителей**. Если в вашей CRM сделки создаются после звонков, то, скорее всего, вы используете сервис коллтрекинга. Проверьте, что ваша система коллтрекинга имеет функцию передачи `ClientId` в сделки внутри CRM.

  * **Письма от посетителей**. Для сделок, инициированных через e-mail, используйте сервисы e-mail-трекинга, которые позволяют определить `ClientId` отправителя письма благодаря подмене e-mail-адресов на сайте и отправить информацию о новом письме в вашу CRM в виде сделки.

  * **Чаты в мессенджерах**. При начале общения в мессенджерах инициируйте метод [getClientID](https://yandex.../support/metrica/objects/get-client-id.md) на сайте и включите идентификатор `ClientId` в диплинк (Telegram, Viber) или в шаблон сообщения (WhatsApp). При создании сделки указывайте идентификатор в отдельном поле.

  * **Виджеты на сайте**. Удостоверьтесь, что виджеты, используемые на сайте, могут передавать `ClientId` Метрики в вашу CRM при передаче сделок.

Примечание

Если вы не можете записать идентификатор [ClientId](https://yandex.../support/metrica/general/clientid-userid.md) (например, при покупке в офлайн-точке) или настроить его передачу из своей CRM, используйте опцию Дополнительные настройки отслеживания в настройках счетчика для более точной привязки заказов по e-mail и телефонам.

## [](ru/data-import/data#csv)Шаг 2. Подготовка данных о клиентах и заказах

Для отправки нужно подготовить ваши данные из CRM:

#### [](ru/data-import/data#21-raspredelite-statusy-zakazov-iz-vashej-crm-po-tipam-statusov-zakazov-v-metrike)2.1 Распределите статусы заказов из вашей CRM по типам статусов заказов в Метрике

Распределите все статусы, которые есть в вашей CRM, на группы соответствий с типами статусов в Метрике:

  * `PAID` — оплачен (применяется по умолчанию если вы не передаете статусы заказов), при передаче будут достигнуты цели **CRM: Заказ создан** и **CRM: Заказ оплачен** ;
  * `IN_PROGRESS` — в работе, при передаче будет достигнута цель **CRM: Заказ создан** ;
  * `CANCELLED` — отменен, при передаче этого типа статуса не будут достигнуты цели;
  * `SPAM` — спам, аналогично отмененному заказу не будут достигнуты цели;
  * `OTHER` — заказы в другом статусе, этот тип статуса будет автоматически использован если вы пришлете в качестве статуса заказа идентификатор javascript-цели или укажете его вручную.

Без сопоставления вам доступны статусы по умолчанию — в виде статуса можно прислать идентификаторы `PAID`, `IN_PROGRESS`, `CANCELLED`, `SPAM` и идентификаторы javascript-целей вашего счетчика.

Сопоставить передаваемые статусы заказов с типами статусов в Метрике можно с помощью метода [POST /cdp/api/v1/counter/{counterId}/schema/order_statuses](../management/openapi/schema/maporderstatuses.md). Например, статусу **Новый** c идентификатором `new` можно назначить тип `IN_PROGRESS` (в работе), статусу **Успешно** c идентификатором `success` — тип `PAID` (оплачен).

[Подробнее про сопоставление статусов заказов](maporderstatuses-about.md)

#### [](ru/data-import/data#22-podgotovte-informaciyu-o-klientah-v-vashej-crm-pod-format-klientov-v-metrike)2.2 Подготовьте информацию о клиентах в вашей CRM под формат клиентов в Метрике

Информация о клиентах включает в себя идентификатор клиента в вашей CRM (обязательный параметр), название (имя) клиента, дата и время создания контакта в часовом поясе счетчика, дата и время последнего обновления контакта и идентификаторы для сопоставления клиента с визитами в Метрике — `client_ids`, адреса электронной почты и телефоны.

[Подробнее про формат данных о клиентах](contacts-data.md)

#### [](ru/data-import/data#23-podgotovte-informaciyu-o-sdelkah-v-vashej-crm-pod-format-sdelok-v-metrike)2.3 Подготовьте информацию о сделках в вашей CRM под формат сделок в Метрике

Обязательными параметрами являются идентификатор заказа в вашей CRM, идентификатор клиента в вашей СRM (совершившего заказ), тип клиента, дата создания заказа в часовом поясе счетчика и статус заказа.

Кроме этого, можно передать последнюю дату и время обновления заказа, дату и время завершения заказа (его выкупа/отмены), доход, себестоимость и товары (услуги) в заказе.

[Подробнее о формате данных о заказах](orders-data.md)

#### [](ru/data-import/data#24-opcionalno-—-peredacha-dopolnitelnoj-informacii-o-klientah-i-zakazah-v-vide-dopolnitelnyh-atributov-i-tovarov)2.4 (Опционально) — передача дополнительной информации о клиентах и заказах в виде дополнительных атрибутов и товаров

Определите, какие дополнительные данные о клиентах и заказах вы хотите передавать. С помощью этой информации можно строить сегменты, которые можно отслеживать в отчетах Метрики или использовать в рекламе.

**Атрибуты для клиентов и заказов**

Например, можно создать атрибут «размер обуви» и сформировать сегмент аудитории с заданным размером. Затем настроить в Директе ретаргетинг на эту аудиторию и показать специальное предложение.

Примеры дополнительных данных: тип клиента (VIP, физическое лицо, юридическое лицо), тип услуги, категория товара. Чтобы создать дополнительные атрибуты, используйте метод [POST /cdp/api/v1/counter/{counterId}/schema/attributes](../management/openapi/schema/createattributes.md) с path-параметром:

  * `entity_type=contact` для передачи пользовательских полей клиентов;
  * `entity_type=order` для передачи пользовательских полей заказов.

**Списки товаров**

Загрузите списки товаров/услуг для ваших заказов – после этого в Метрике будут доступны данные из этих списков, например, названия товаров. Используйте метод [POST /cdp/api/v1/counter/{counterId}/schema/products](../management/openapi/schema/createproducts.md).

## [](ru/data-import/data#upload)Шаг 3. Отправка данных о клиентах и заказах

Передайте данные о клиентах и заказах в CSV-формате или внутри запроса в формате JSON. Формат CSV можно передавать несколькими способами:

  * CSV-файл. В файле укажите данные, которые хотите передать в Метрику.
  * multipart/form-data. В первой строке необходимо передать названия колонок.

Загрузите данные из CRM в Метрику:

**О клиентах**

Рекомендуем сделать первую загрузку клиентов как можно раньше — данные о заказах будут привязываться к визитам, которые были совершены после первой удачной загрузки информации о клиентах.

**О заказах**

### Была ли статья полезна?

ДаНет

Предыдущая

[Формат упрощенных данных о заказах и клиентах](simple-orders-data.md)

Следующая

[Как сопоставить статусы заказов](maporderstatuses-about.md)