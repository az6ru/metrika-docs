# Список доступных счетчиков - Управление счетчиками | API Яндекс Метрики

Request

## В этой статье:

  1. [API управления](../../index.md)
  2. Справочник API управления
  3. Управление счетчиками
  4. Создание счетчика

# Создание счетчика

Создает счетчик с заданными параметрами. Один пользователь может создать не больше 100 000 счетчиков.

## [](ru/management/openapi/counter/addCounter#request)Request

POST
    
    
    https://api-metrika.yandex.net/management/v1/counters
    

### [](ru/management/openapi/counter/addCounter#query-parameters)Query parameters

**Name** |  **Description**  
---|---  
field |  **Type:** string Один или несколько дополнительных параметров возвращаемого объекта. Названия дополнительных параметров указываются в любом порядке через запятую, без пробелов. Например: `field=goals,mirrors,grants,filters,operations,counter_flags,measurement_tokens`.  
  
### [](ru/management/openapi/counter/addCounter#body)Body

application/json
    
    
    {
        "counter": {
            "id": 0,
            "status": "string",
            "owner_login": "string",
            "activity_status": "string",
            "name": "string",
            "type": "string",
            "favorite": false,
            "permission": "string",
            "goals": [
                {
                    "id": 0,
                    "name": "string",
                    "type": "string",
                    "default_price": 0,
                    "goal_source": "string",
                    "is_favorite": false,
                    "status": "string",
                    "conditions": [
                        {
                            "type": "string",
                            "url": "string"
                        }
                    ],
                    "flag": "basket"
                },
                {
                    "id": 0,
                    "name": "string",
                    "type": "string",
                    "default_price": 0,
                    "goal_source": "string",
                    "is_favorite": false,
                    "status": "string",
                    "steps": [
                        {
                            "id": 0,
                            "name": "string",
                            "type": "string",
                            "default_price": 0,
                            "goal_source": "string",
                            "is_favorite": false,
                            "status": "string",
                            "conditions": [
                                {
                                    "type": "string",
                                    "url": "string"
                                }
                            ],
                            "flag": "string"
                        }
                    ]
                },
                {
                    "id": 0,
                    "name": "string",
                    "type": "string",
                    "default_price": 0,
                    "goal_source": "string",
                    "is_favorite": false,
                    "status": "string",
                    "depth": 0
                },
                {
                    "id": 0,
                    "name": "string",
                    "type": "string",
                    "default_price": 0,
                    "goal_source": "string",
                    "is_favorite": false,
                    "status": "string",
                    "conditions": [
                        {
                            "type": "string",
                            "url": "string"
                        }
                    ],
                    "flag": "basket"
                },
                {
                    "id": 0,
                    "name": "string",
                    "type": "string",
                    "default_price": 0,
                    "goal_source": "string",
                    "is_favorite": false,
                    "status": "string",
                    "conditions": [
                        {
                            "type": "string",
                            "url": "string"
                        }
                    ],
                    "flag": "basket"
                },
                {
                    "id": 0,
                    "name": "string",
                    "type": "string",
                    "default_price": 0,
                    "goal_source": "string",
                    "is_favorite": false,
                    "status": "string",
                    "conditions": [
                        {
                            "type": "string",
                            "url": "string"
                        }
                    ],
                    "flag": "basket"
                },
                {
                    "id": 0,
                    "name": "string",
                    "type": "string",
                    "default_price": 0,
                    "goal_source": "string",
                    "is_favorite": false,
                    "status": "string"
                },
                {
                    "id": 0,
                    "name": "string",
                    "type": "string",
                    "default_price": 0,
                    "goal_source": "string",
                    "is_favorite": false,
                    "status": "string",
                    "conditions": [
                        {
                            "type": "string",
                            "url": "string"
                        }
                    ],
                    "flag": "basket",
                    "hide_phone_number": false
                },
                {
                    "id": 0,
                    "name": "string",
                    "type": "string",
                    "default_price": 0,
                    "goal_source": "string",
                    "is_favorite": false,
                    "status": "string",
                    "conditions": [
                        {
                            "type": "string",
                            "url": "string"
                        }
                    ],
                    "flag": "basket"
                },
                {
                    "id": 0,
                    "name": "string",
                    "type": "string",
                    "default_price": 0,
                    "goal_source": "string",
                    "is_favorite": false,
                    "status": "string",
                    "conditions": [
                        {
                            "type": "string",
                            "url": "string"
                        }
                    ],
                    "flag": "basket"
                },
                {
                    "id": 0,
                    "name": "string",
                    "type": "string",
                    "default_price": 0,
                    "goal_source": "string",
                    "is_favorite": false,
                    "status": "string",
                    "conditions": [
                        {
                            "type": "string",
                            "url": "string"
                        }
                    ],
                    "flag": "basket"
                },
                {
                    "id": 0,
                    "name": "string",
                    "type": "string",
                    "default_price": 0,
                    "goal_source": "string",
                    "is_favorite": false,
                    "status": "string",
                    "duration": 0
                }
            ],
            "filters": [
                {
                    "id": 0,
                    "attr": "string",
                    "type": "string",
                    "value": "string",
                    "action": "string",
                    "status": "string",
                    "start_ip": "string",
                    "end_ip": "string",
                    "with_subdomains": false
                }
            ],
            "operations": [
                {
                    "id": 0,
                    "action": "string",
                    "attr": "string",
                    "value": "string",
                    "status": "string"
                }
            ],
            "grants": [
                {
                    "user_login": "string",
                    "perm": "string",
                    "created_at": "2022-12-29T18:02:01Z",
                    "comment": "string",
                    "partner_data_access": false
                },
                {
                    "user_login": "string",
                    "perm": "string",
                    "created_at": "2022-12-29T18:02:01Z",
                    "comment": "string",
                    "partner_data_access": false,
                    "access_filters": [
                        {
                            "id": 0,
                            "name": "string"
                        }
                    ]
                }
            ],
            "labels": [
                {
                    "id": 0,
                    "name": "string"
                }
            ],
            "webvisor": {
                "urls": "string",
                "arch_enabled": false,
                "arch_type": "string",
                "load_player_type": "string",
                "wv_version": 0,
                "wv_forms": false
            },
            "code_options": {
                "async": false,
                "informer": {
                    "enabled": false,
                    "type": "string",
                    "size": 0,
                    "indicator": "string",
                    "color_start": "FFFFFFFF.",
                    "color_end": "EFEFEFFF",
                    "color_text": 0,
                    "color_arrow": 0
                },
                "visor": false,
                "track_hash": false,
                "xml_site": false,
                "clickmap": false,
                "in_one_line": false,
                "ecommerce": false,
                "alternative_cdn": false,
                "ytm": false
            },
            "create_time": "2022-12-29T18:02:01Z",
            "time_zone_name": "string",
            "time_zone_offset": 0,
            "source": "string",
            "update_time": "string",
            "delete_time": "string",
            "code": "string",
            "filter_robots": 0,
            "visit_threshold": 1800,
            "publisher_options": {
                "enabled": false,
                "schema": "string",
                "schema_options": [
                    "string"
                ]
            },
            "site2": {
                "site": "string"
            },
            "gdpr_agreement_accepted": false,
            "mirrors2": [
                {
                    "site": "string"
                }
            ],
            "autogoals_enabled": false,
            "counter_flags": {
                "use_in_benchmarks": false,
                "direct_allow_use_goals_without_access": false,
                "collect_first_party_data": false,
                "measurement_enabled": false
            },
            "measurement_tokens": [
                "string"
            ]
        }
    }
    

**Name** |  **Description**  
---|---  
counter* |  **Type:** [CounterFull](addcounter.md) Счетчик.  
  
### [](ru/management/openapi/counter/addCounter#counterfull)CounterFull

Счетчик.

**Name** |  **Description**  
---|---  
activity_status |  **Type:** string Посещаемость счетчика. Возможные значения:

  * `low` — низкая посещаемость.
  * `high` — высокая посещаемость.

  
autogoals_enabled |  **Type:** boolean Включение [автоматических целей](https://yandex.../../../support/metrica/general/auto-goals.md). Возможные значения:

  * `true` — опция включена.
  * `false` — опция выключена.

  
code |  **Type:** string HTML-код счетчика.  
code_options |  **Type:** [CodeOptionsE](addcounter.md) Настройки кода счетчика.  
counter_flags |  **Type:** [CounterFlags](addcounter.md) Безопасность и использование данных.  
create_time |  **Type:** string<date-time> Дата и время создания счетчика.  
delete_time |  **Type:** string Время удаления счетчика.  
favorite |  **Type:** boolean Добавлен ли счетчик в избранное:

  * 0 ― не добавлен (по умолчанию);
  * 1 ― добавлен.

  
filter_robots |  **Type:** integer<int32> Фильтрация роботов:

  * 1 — фильтровать роботов только по строгим правилам (по умолчанию);
  * 2 — фильтровать роботов по строгим правилам и по поведению.

_Min value:_ `1` _Max value:_ `2`  
filters |  **Type:** [FilterE](addcounter.md)[] Список структур с информацией о фильтрах счетчика.  
gdpr_agreement_accepted |  **Type:** boolean Согласие с [Договором об обработке данных в сервисе Яндекс Метрика](https://yandex.../../../legal/metrica_agreement/index.md).

  * 0 — договор не принят (по умолчанию).
  * 1 — договор принят.

  
goals |  **Type:** ([ActionGoal](addcounter.md) or [CompositeGoal](addcounter.md) or [DepthGoal](addcounter.md) or [EmailGoal](addcounter.md) or [FileGoal](addcounter.md) or [MessengerGoal](addcounter.md) or [PaymentSystemGoal](addcounter.md) or [PhoneGoal](addcounter.md) or [SiteSearchGoal](addcounter.md) or [SocialNetworkGoal](addcounter.md) or [UrlGoal](addcounter.md) or [VisitDurationGoal](addcounter.md))[] Список структур с информацией о целях счетчика.  
  
grants |  **Type:** ([CounterGrantE](addcounter.md) or [AccessFiltersGrantE](addcounter.md))[]  
id |  **Type:** integer<int32> Идентификатор счетчика.  
labels |  **Type:** [Label](addcounter.md)[] Список структур с информацией о метках.  
Метка.  
measurement_tokens |  **Type:** string[] Список активных токенов.  
mirrors2 |  **Type:** [CounterMirrorE](addcounter.md)[] Список зеркал (доменов) сайта.  
name |  **Type:** string Наименование счетчика. _Min length:_ `0` _Max length:_ `255`  
operations |  **Type:** [OperationE](addcounter.md)[] Список структур с информацией об операциях счетчика.  
owner_login |  **Type:** string Логин владельца счетчика.  
permission |  **Type:** string Уровень доступа к счетчику:

  * `own` — счетчик, принадлежащий пользователю.
  * `view` — гостевой счетчик с уровнем доступа **только просмотр**.
  * `edit` — гостевой счетчик с уровнем доступа **полный доступ**.
  * `analyst` — гостевой счетчик с уровнем доступа **аналитика**.
  * `view_access_filter` — гостевой счетчик с уровнем доступа **только просмотр через фильтр доступа**.
  * `analyst_access_filter` — гостевой счетчик с уровнем доступа **аналитика данных через фильтр доступа**.

  
publisher_options |  **Type:** [PublisherOptions](addcounter.md) Структура с информацией о настройках контентной аналитики.  
site2 |  **Type:** [CounterMirrorE](addcounter.md) Список зеркал (доменов) сайта.  
source |  **Type:** string Тип счетчика. Возможные значения:

  * `turbodirect` — Турбо Директ.
  * `marketplace_direct` — Маркетплейсы Директ.
  * `sprav` — Бизнес.
  * `partner` — РСЯ.
  * `system` — Системный.
  * `market` — Маркет.
  * `eda` — Еда.
  * `dzen` — Дзен.
  * `geoadv` — Кабинет рекламодателя.
  * `games` — Игры.

  
status |  **Type:** string Статус счетчика. возможные значения:

  * `Active` — счетчик активен.
  * `Deleted` — счетчик удален.

  
time_zone_name |  **Type:** string [Часовой пояс](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones) для расчета статистики.  
time_zone_offset |  **Type:** integer<int32> Текущее смещение часового пояса от Гринвича, минуты.  
type |  **Type:** string Тип счетчика. Возможные значения:

  * `simple` — счетчик создан пользователем в Яндекс Метрике.
  * `partner` — счетчик импортирован из РСЯ.

  
update_time |  **Type:** string Время последнего изменения счетчика.  
visit_threshold |  **Type:** integer<int32> Таймаут визита в секундах. _Default:_ `1800` _Min value:_ `1800` _Max value:_ `21600`  
webvisor |  **Type:** [WebvisorOptions](addcounter.md) Структура с информацией о настройках Вебвизора.  
  
### [](ru/management/openapi/counter/addCounter#codeoptionse)CodeOptionsE

Настройки кода счетчика.

**Name** |  **Description**  
---|---  
alternative_cdn |  **Type:** boolean Позволяет корректно учитывать посещения из регионов, в которых ограничен доступ к ресурсам Яндекса. Использование этой опции может снизить скорость загрузки кода счётчика:

  * 0 ― отключено (по умолчанию).
  * 1 ― включено.

  
async |  **Type:** boolean Асинхронный код счетчика:

  * 0 ― отключено.
  * 1 ― включено (по умолчанию).

  
clickmap |  **Type:** boolean Сбор статистики для работы отчета Карта кликов:

  * 0 ― отключено (по умолчанию).
  * 1 ― включено.

  
ecommerce |  **Type:** boolean Сбор данных по электронной коммерции:

  * 0 ― отключено (по умолчанию).
  * 1 ― включено.

  
in_one_line |  **Type:** boolean Выводить код счетчика в одну строку:

  * 0 ― отключено (по умолчанию).
  * 1 ― включено.

  
informer |  **Type:** [InformerOptionsE](addcounter.md) Настройки информера.  
track_hash |  **Type:** boolean Отслеживание хеша в адресной строке браузера. Опция применима для AJAX-сайтов:

  * 0 ― отключено (по умолчанию).
  * 1 ― включено.

  
visor |  **Type:** boolean Запись и анализ поведения посетителей сайта:

  * 0 ― отключено (по умолчанию).
  * 1 ― включено.

  
xml_site |  **Type:** boolean Для XML-сайтов. Элемент noscript не должен использоваться в XML документах:

  * 0 ― отключено (по умолчанию).
  * 1 ― включено.

  
ytm |  **Type:** boolean Использование системы управления тегами. Возможные значения:

  * 0 ― не используется.
  * 1 — используется.

  
  
### [](ru/management/openapi/counter/addCounter#counterflags)CounterFlags

Безопасность и использование данных.

**Name** |  **Description**  
---|---  
collect_first_party_data |  **Type:** boolean Использовать дополнительные настройки отслеживания. Опция разрешает Метрике использовать введенные посетителем контактные данные с сайта для улучшения работы рекламных алгоритмов и более точного анализа поведения посетителей сайта. Это поможет вам повышать эффективность рекламных кампаний и узнавать больше о поведении посетителей, даже если они используют браузеры с ограничением межсайтовых cookies (third-party cookies) — например, Safari или Mozilla Firefox.  
direct_allow_use_goals_without_access |  **Type:** boolean Разрешить в рекламных кампаниях оптимизацию по целям без доступа к счетчику. Если управлением ваших рекламных кампаний в Директе занимается кто-то кроме вас, например, агентство или специалист по настройке, вы можете дать разрешение на использование существующих в Метрике целей. Если счетчик создан недавно, опция включена по умолчанию. Подробно см. [в Справке](https://yandex.../../../support/metrica/general/goals.md).  
measurement_enabled |  **Type:** boolean Включить опцию [Measurement Protocol](../../../data-import/measurement-about.md). Measurement Protocol — API для отправки данных о взаимодействиях пользователей напрямую на сервера Метрики через HTTP-запросы.  
use_in_benchmarks |  **Type:** boolean Получать доступ к отчетам по рынку. Опция разрешает Метрике использовать агрегированные обезличенные данные счетчика для построения отчетов по аналитике рынка. Собираемые данные дадут вам возможность понимать состояние своего бизнеса относительно рынка. Если счетчик создан недавно, опция включена по умолчанию.  
  
### [](ru/management/openapi/counter/addCounter#filtere)FilterE

Список структур с информацией о фильтрах счетчика.

**Name** |  **Description**  
---|---  
action* |  **Type:** string Тип фильтра:

  * `exclude` — исключить трафик.
  * `include` — оставить только трафик.

  
attr* |  **Type:** string Тип данных, к которым применяется фильтр:

  * `title` — заголовок страницы.
  * `client_ip` — IP-адрес.
  * `url` — URL страницы.
  * `referer` — реферер.
  * `uniq_id` — специальный атрибут для фильтра **не учитывать мои визиты**.

  
status* |  **Type:** string Статус фильтра:

  * `active` — фильтр используется.
  * `disabled` — фильтр отключен (без удаления).

  
type* |  **Type:** string Отношение или действие для фильтра:

  * `equal` — равно.
  * `start` — начинается с.
  * `contain` — содержит.
  * `interval` — в интервале, используется только с типом данных «IP-адрес» (`attr = client_ip`).
  * `me` — мои посещения, используется только с типом данных `attr = uniq_id`.
  * `only_mirrors` — только сайт и зеркала, используется только для типа данных «URL страницы» (`attr = url`) и типа фильтра **оставить только трафик** (`action = include`), а также при условии, что для счетчика заданы зеркала.
  * `regexp` — регулярное выражение.

  
end_ip |  **Type:** string Последний IP-адрес диапазона.  
id |  **Type:** integer<int32> Идентификатор фильтра. Укажите данный параметр при изменении фильтра счетчика.  
start_ip |  **Type:** string Первый IP-адрес диапазона.  
value |  **Type:** string Значение фильтра.  
with_subdomains |  **Type:** boolean Фильтровать по поддоменам.  
  
### [](ru/management/openapi/counter/addCounter#actiongoal)ActionGoal

JavaScript-событие.

**Name** |  **Description**  
---|---  
name* |  **Type:** string Наименование цели. _Min length:_ `0` _Max length:_ `255`  
type* |  **Type:** string Тип цели:

  * `url` — посещение страниц.
  * `number` — количество просмотров.
  * `step` — составная цель.
  * `action` — JavaScript-событие.
  * `phone` — клик по номеру телефона.
  * `email` — клик по email.
  * `payment_system` — платежная система.
  * `messenger` — переход в мессенджер.
  * `file` — скачивание файлов.
  * `search` — поиск по сайту.
  * `social` — переход в соц. сети.
  * `visit_duration` — продолжительность визита.

  
conditions |  **Type:** [GoalCondition](addcounter.md)[] Список структур с условиями цели.  
default_price |  **Type:** number<double> Цена цели по умолчанию.  
flag |  **Type:** string Тип цели для клиентов Яндекс Маркета:

  * `basket` — **корзина** , страница посещения корзины.
  * `order` — **заказ** , страница подтверждения заказа.

_Enum:_ `basket`, `order`, ``  
goal_source |  **Type:** string Признак того, как создана цель:

  * `user` — цель создана пользователем Метрики.
  
id |  **Type:** integer<int64> Идентификатор цели. Укажите данный параметр при изменении и удалении цели счетчика.  
is_favorite |  **Type:** boolean Является ли цель избранной:

  * 0 ― не является (по умолчанию).
  * 1 ― является.

  
status |  **Type:** string  
  
### [](ru/management/openapi/counter/addCounter#compositegoal)CompositeGoal

Составная цель. Нужна для группировки и задания порядка обычных целей. В качестве шагов может содержать цели типа "Посещение страниц" и "JavaScript-событие". Шаг считается достигнутым, если были достигнуты все предыдущие шаги, и после этого были выполнены все условия текущего шага.

**Name** |  **Description**  
---|---  
name* |  **Type:** string Наименование цели. _Min length:_ `0` _Max length:_ `255`  
steps* |  **Type:** [ConditionalGoal](addcounter.md)[] Список шагов составной цели. _Min items:_ `0` _Max items:_ `5`  
type* |  **Type:** string Тип цели:

  * `url` — посещение страниц.
  * `number` — количество просмотров.
  * `step` — составная цель.
  * `action` — JavaScript-событие.
  * `phone` — клик по номеру телефона.
  * `email` — клик по email.
  * `payment_system` — платежная система.
  * `messenger` — переход в мессенджер.
  * `file` — скачивание файлов.
  * `search` — поиск по сайту.
  * `social` — переход в соц. сети.
  * `visit_duration` — продолжительность визита.

  
default_price |  **Type:** number<double> Цена цели по умолчанию.  
goal_source |  **Type:** string Признак того, как создана цель:

  * `user` — цель создана пользователем Метрики.
  
id |  **Type:** integer<int64> Идентификатор цели. Укажите данный параметр при изменении и удалении цели счетчика.  
is_favorite |  **Type:** boolean Является ли цель избранной:

  * 0 ― не является (по умолчанию).
  * 1 ― является.

  
status |  **Type:** string  
  
### [](ru/management/openapi/counter/addCounter#depthgoal)DepthGoal

Количество просмотров. Цель считается достигнутой, если посетитель просмотрел заданное количество страниц сайта.

**Name** |  **Description**  
---|---  
depth* |  **Type:** integer<int64> Количество просмотренных пользователем страниц. _Min value:_ `2`  
name* |  **Type:** string Наименование цели. _Min length:_ `0` _Max length:_ `255`  
type* |  **Type:** string Тип цели:

  * `url` — посещение страниц.
  * `number` — количество просмотров.
  * `step` — составная цель.
  * `action` — JavaScript-событие.
  * `phone` — клик по номеру телефона.
  * `email` — клик по email.
  * `payment_system` — платежная система.
  * `messenger` — переход в мессенджер.
  * `file` — скачивание файлов.
  * `search` — поиск по сайту.
  * `social` — переход в соц. сети.
  * `visit_duration` — продолжительность визита.

  
default_price |  **Type:** number<double> Цена цели по умолчанию.  
goal_source |  **Type:** string Признак того, как создана цель:

  * `user` — цель создана пользователем Метрики.
  
id |  **Type:** integer<int64> Идентификатор цели. Укажите данный параметр при изменении и удалении цели счетчика.  
is_favorite |  **Type:** boolean Является ли цель избранной:

  * 0 ― не является (по умолчанию).
  * 1 ― является.

  
status |  **Type:** string  
  
### [](ru/management/openapi/counter/addCounter#emailgoal)EmailGoal

Нажатие на email.

**Name** |  **Description**  
---|---  
name* |  **Type:** string Наименование цели. _Min length:_ `0` _Max length:_ `255`  
type* |  **Type:** string Тип цели:

  * `url` — посещение страниц.
  * `number` — количество просмотров.
  * `step` — составная цель.
  * `action` — JavaScript-событие.
  * `phone` — клик по номеру телефона.
  * `email` — клик по email.
  * `payment_system` — платежная система.
  * `messenger` — переход в мессенджер.
  * `file` — скачивание файлов.
  * `search` — поиск по сайту.
  * `social` — переход в соц. сети.
  * `visit_duration` — продолжительность визита.

  
conditions |  **Type:** [GoalCondition](addcounter.md)[] Список структур с условиями цели.  
default_price |  **Type:** number<double> Цена цели по умолчанию.  
flag |  **Type:** string Тип цели для клиентов Яндекс Маркета:

  * `basket` — **корзина** , страница посещения корзины.
  * `order` — **заказ** , страница подтверждения заказа.

_Enum:_ `basket`, `order`, ``  
goal_source |  **Type:** string Признак того, как создана цель:

  * `user` — цель создана пользователем Метрики.
  
id |  **Type:** integer<int64> Идентификатор цели. Укажите данный параметр при изменении и удалении цели счетчика.  
is_favorite |  **Type:** boolean Является ли цель избранной:

  * 0 ― не является (по умолчанию).
  * 1 ― является.

  
status |  **Type:** string  
  
### [](ru/management/openapi/counter/addCounter#filegoal)FileGoal

Скачивание файлов. Цель считается достигнутой, если посетитель скачал любой файл или определенный файл.

**Name** |  **Description**  
---|---  
name* |  **Type:** string Наименование цели. _Min length:_ `0` _Max length:_ `255`  
type* |  **Type:** string Тип цели:

  * `url` — посещение страниц.
  * `number` — количество просмотров.
  * `step` — составная цель.
  * `action` — JavaScript-событие.
  * `phone` — клик по номеру телефона.
  * `email` — клик по email.
  * `payment_system` — платежная система.
  * `messenger` — переход в мессенджер.
  * `file` — скачивание файлов.
  * `search` — поиск по сайту.
  * `social` — переход в соц. сети.
  * `visit_duration` — продолжительность визита.

  
conditions |  **Type:** [GoalCondition](addcounter.md)[] Список структур с условиями цели.  
default_price |  **Type:** number<double> Цена цели по умолчанию.  
flag |  **Type:** string Тип цели для клиентов Яндекс Маркета:

  * `basket` — **корзина** , страница посещения корзины.
  * `order` — **заказ** , страница подтверждения заказа.

_Enum:_ `basket`, `order`, ``  
goal_source |  **Type:** string Признак того, как создана цель:

  * `user` — цель создана пользователем Метрики.
  
id |  **Type:** integer<int64> Идентификатор цели. Укажите данный параметр при изменении и удалении цели счетчика.  
is_favorite |  **Type:** boolean Является ли цель избранной:

  * 0 ― не является (по умолчанию).
  * 1 ― является.

  
status |  **Type:** string  
  
### [](ru/management/openapi/counter/addCounter#messengergoal)MessengerGoal

Переход в мессенджер. Цель будет достигнута при клике пользователем на ссылку, которая ведет в мессенджер.

**Name** |  **Description**  
---|---  
name* |  **Type:** string Наименование цели. _Min length:_ `0` _Max length:_ `255`  
type* |  **Type:** string Тип цели:

  * `url` — посещение страниц.
  * `number` — количество просмотров.
  * `step` — составная цель.
  * `action` — JavaScript-событие.
  * `phone` — клик по номеру телефона.
  * `email` — клик по email.
  * `payment_system` — платежная система.
  * `messenger` — переход в мессенджер.
  * `file` — скачивание файлов.
  * `search` — поиск по сайту.
  * `social` — переход в соц. сети.
  * `visit_duration` — продолжительность визита.

  
conditions |  **Type:** [GoalCondition](addcounter.md)[] Список структур с условиями цели.  
default_price |  **Type:** number<double> Цена цели по умолчанию.  
flag |  **Type:** string Тип цели для клиентов Яндекс Маркета:

  * `basket` — **корзина** , страница посещения корзины.
  * `order` — **заказ** , страница подтверждения заказа.

_Enum:_ `basket`, `order`, ``  
goal_source |  **Type:** string Признак того, как создана цель:

  * `user` — цель создана пользователем Метрики.
  
id |  **Type:** integer<int64> Идентификатор цели. Укажите данный параметр при изменении и удалении цели счетчика.  
is_favorite |  **Type:** boolean Является ли цель избранной:

  * 0 ― не является (по умолчанию).
  * 1 ― является.

  
status |  **Type:** string  
  
### [](ru/management/openapi/counter/addCounter#paymentsystemgoal)PaymentSystemGoal

Платежные системы. Цель считается достигнутой, если посетитель совершил оплату через платежную систему.

**Name** |  **Description**  
---|---  
name* |  **Type:** string Наименование цели. _Min length:_ `0` _Max length:_ `255`  
type* |  **Type:** string Тип цели:

  * `url` — посещение страниц.
  * `number` — количество просмотров.
  * `step` — составная цель.
  * `action` — JavaScript-событие.
  * `phone` — клик по номеру телефона.
  * `email` — клик по email.
  * `payment_system` — платежная система.
  * `messenger` — переход в мессенджер.
  * `file` — скачивание файлов.
  * `search` — поиск по сайту.
  * `social` — переход в соц. сети.
  * `visit_duration` — продолжительность визита.

  
default_price |  **Type:** number<double> Цена цели по умолчанию.  
goal_source |  **Type:** string Признак того, как создана цель:

  * `user` — цель создана пользователем Метрики.
  
id |  **Type:** integer<int64> Идентификатор цели. Укажите данный параметр при изменении и удалении цели счетчика.  
is_favorite |  **Type:** boolean Является ли цель избранной:

  * 0 ― не является (по умолчанию).
  * 1 ― является.

  
status |  **Type:** string  
  
### [](ru/management/openapi/counter/addCounter#phonegoal)PhoneGoal

Нажатие на номер телефона.

**Name** |  **Description**  
---|---  
name* |  **Type:** string Наименование цели. _Min length:_ `0` _Max length:_ `255`  
type* |  **Type:** string Тип цели:

  * `url` — посещение страниц.
  * `number` — количество просмотров.
  * `step` — составная цель.
  * `action` — JavaScript-событие.
  * `phone` — клик по номеру телефона.
  * `email` — клик по email.
  * `payment_system` — платежная система.
  * `messenger` — переход в мессенджер.
  * `file` — скачивание файлов.
  * `search` — поиск по сайту.
  * `social` — переход в соц. сети.
  * `visit_duration` — продолжительность визита.

  
conditions |  **Type:** [GoalCondition](addcounter.md)[] Список структур с условиями цели.  
default_price |  **Type:** number<double> Цена цели по умолчанию.  
flag |  **Type:** string Тип цели для клиентов Яндекс Маркета:

  * `basket` — **корзина** , страница посещения корзины.
  * `order` — **заказ** , страница подтверждения заказа.

_Enum:_ `basket`, `order`, ``  
goal_source |  **Type:** string Признак того, как создана цель:

  * `user` — цель создана пользователем Метрики.
  
hide_phone_number |  **Type:** boolean Скрывать номер телефона на десктопах.  
id |  **Type:** integer<int64> Идентификатор цели. Укажите данный параметр при изменении и удалении цели счетчика.  
is_favorite |  **Type:** boolean Является ли цель избранной:

  * 0 ― не является (по умолчанию).
  * 1 ― является.

  
status |  **Type:** string  
  
### [](ru/management/openapi/counter/addCounter#sitesearchgoal)SiteSearchGoal

Поиск по сайту. Цель будет достигнута при поиске на сайте, если в урле в get-параметрах есть хотя бы одно совпадение.

**Name** |  **Description**  
---|---  
name* |  **Type:** string Наименование цели. _Min length:_ `0` _Max length:_ `255`  
type* |  **Type:** string Тип цели:

  * `url` — посещение страниц.
  * `number` — количество просмотров.
  * `step` — составная цель.
  * `action` — JavaScript-событие.
  * `phone` — клик по номеру телефона.
  * `email` — клик по email.
  * `payment_system` — платежная система.
  * `messenger` — переход в мессенджер.
  * `file` — скачивание файлов.
  * `search` — поиск по сайту.
  * `social` — переход в соц. сети.
  * `visit_duration` — продолжительность визита.

  
conditions |  **Type:** [GoalCondition](addcounter.md)[] Список структур с условиями цели.  
default_price |  **Type:** number<double> Цена цели по умолчанию.  
flag |  **Type:** string Тип цели для клиентов Яндекс Маркета:

  * `basket` — **корзина** , страница посещения корзины.
  * `order` — **заказ** , страница подтверждения заказа.

_Enum:_ `basket`, `order`, ``  
goal_source |  **Type:** string Признак того, как создана цель:

  * `user` — цель создана пользователем Метрики.
  
id |  **Type:** integer<int64> Идентификатор цели. Укажите данный параметр при изменении и удалении цели счетчика.  
is_favorite |  **Type:** boolean Является ли цель избранной:

  * 0 ― не является (по умолчанию).
  * 1 ― является.

  
status |  **Type:** string  
  
### [](ru/management/openapi/counter/addCounter#socialnetworkgoal)SocialNetworkGoal

Переход в социальную сеть. Цель будет достигнута при клике пользователем на ссылку, которая ведет в социальную сеть.

**Name** |  **Description**  
---|---  
name* |  **Type:** string Наименование цели. _Min length:_ `0` _Max length:_ `255`  
type* |  **Type:** string Тип цели:

  * `url` — посещение страниц.
  * `number` — количество просмотров.
  * `step` — составная цель.
  * `action` — JavaScript-событие.
  * `phone` — клик по номеру телефона.
  * `email` — клик по email.
  * `payment_system` — платежная система.
  * `messenger` — переход в мессенджер.
  * `file` — скачивание файлов.
  * `search` — поиск по сайту.
  * `social` — переход в соц. сети.
  * `visit_duration` — продолжительность визита.

  
conditions |  **Type:** [GoalCondition](addcounter.md)[] Список структур с условиями цели.  
default_price |  **Type:** number<double> Цена цели по умолчанию.  
flag |  **Type:** string Тип цели для клиентов Яндекс Маркета:

  * `basket` — **корзина** , страница посещения корзины.
  * `order` — **заказ** , страница подтверждения заказа.

_Enum:_ `basket`, `order`, ``  
goal_source |  **Type:** string Признак того, как создана цель:

  * `user` — цель создана пользователем Метрики.
  
id |  **Type:** integer<int64> Идентификатор цели. Укажите данный параметр при изменении и удалении цели счетчика.  
is_favorite |  **Type:** boolean Является ли цель избранной:

  * 0 ― не является (по умолчанию).
  * 1 ― является.

  
status |  **Type:** string  
  
### [](ru/management/openapi/counter/addCounter#urlgoal)UrlGoal

Посещение страниц. Достигается, когда выполняется хотя бы одно из условий.

**Name** |  **Description**  
---|---  
name* |  **Type:** string Наименование цели. _Min length:_ `0` _Max length:_ `255`  
type* |  **Type:** string Тип цели:

  * `url` — посещение страниц.
  * `number` — количество просмотров.
  * `step` — составная цель.
  * `action` — JavaScript-событие.
  * `phone` — клик по номеру телефона.
  * `email` — клик по email.
  * `payment_system` — платежная система.
  * `messenger` — переход в мессенджер.
  * `file` — скачивание файлов.
  * `search` — поиск по сайту.
  * `social` — переход в соц. сети.
  * `visit_duration` — продолжительность визита.

  
conditions |  **Type:** [GoalCondition](addcounter.md)[] Список структур с условиями цели.  
default_price |  **Type:** number<double> Цена цели по умолчанию.  
flag |  **Type:** string Тип цели для клиентов Яндекс Маркета:

  * `basket` — **корзина** , страница посещения корзины.
  * `order` — **заказ** , страница подтверждения заказа.

_Enum:_ `basket`, `order`, ``  
goal_source |  **Type:** string Признак того, как создана цель:

  * `user` — цель создана пользователем Метрики.
  
id |  **Type:** integer<int64> Идентификатор цели. Укажите данный параметр при изменении и удалении цели счетчика.  
is_favorite |  **Type:** boolean Является ли цель избранной:

  * 0 ― не является (по умолчанию).
  * 1 ― является.

  
status |  **Type:** string  
  
### [](ru/management/openapi/counter/addCounter#visitdurationgoal)VisitDurationGoal

Продолжительность визита. Цель будет достигнута при времени визита больше заданного.

**Name** |  **Description**  
---|---  
name* |  **Type:** string Наименование цели. _Min length:_ `0` _Max length:_ `255`  
type* |  **Type:** string Тип цели:

  * `url` — посещение страниц.
  * `number` — количество просмотров.
  * `step` — составная цель.
  * `action` — JavaScript-событие.
  * `phone` — клик по номеру телефона.
  * `email` — клик по email.
  * `payment_system` — платежная система.
  * `messenger` — переход в мессенджер.
  * `file` — скачивание файлов.
  * `search` — поиск по сайту.
  * `social` — переход в соц. сети.
  * `visit_duration` — продолжительность визита.

  
default_price |  **Type:** number<double> Цена цели по умолчанию.  
duration |  **Type:** integer<int32> Продолжительность визита в секундах. _Min value:_ `1`  
goal_source |  **Type:** string Признак того, как создана цель:

  * `user` — цель создана пользователем Метрики.
  
id |  **Type:** integer<int64> Идентификатор цели. Укажите данный параметр при изменении и удалении цели счетчика.  
is_favorite |  **Type:** boolean Является ли цель избранной:

  * 0 ― не является (по умолчанию).
  * 1 ― является.

  
status |  **Type:** string  
  
### [](ru/management/openapi/counter/addCounter#countergrante)CounterGrantE

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
  
### [](ru/management/openapi/counter/addCounter#accessfiltersgrante)AccessFiltersGrantE

**Name** |  **Description**  
---|---  
access_filters* |  **Type:** [AccessFiltersShortE](addcounter.md)[] Список фильтров доступа, к которым выдано разрешение. _Min items:_ `1` _Max items:_ `1`  
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
  
### [](ru/management/openapi/counter/addCounter#label)Label

Метка.

**Name** |  **Description**  
---|---  
id |  **Type:** integer<int32> Идентификатор метки.  
name |  **Type:** string Имя метки. _Min length:_ `0` _Max length:_ `255`  
  
### [](ru/management/openapi/counter/addCounter#countermirrore)CounterMirrorE

Список зеркал (доменов) сайта.

**Name** |  **Description**  
---|---  
site* |  **Type:** string Полный домен сайта. _Min length:_ `0` _Max length:_ `255`  
  
### [](ru/management/openapi/counter/addCounter#operatione)OperationE

Список структур с информацией об операциях счетчика.

**Name** |  **Description**  
---|---  
action* |  **Type:** string Тип операции:

  * `cut_fragment` — вырезать якорь из URL.
  * `cut_parameter` — вырезать определенный параметр из URL.
  * `cut_all_parameters` — вырезать все параметры из URL.
  * `merge_https_and_http` — заменить https:// на http://.
  * `to_lower` — привести к нижнему регистру.
  * `replace_domain` — заменить домен.

  
attr* |  **Type:** string Поле для фильтрации:

  * `referer` — реферер.
  * `url` — URL страницы.

  
status* |  **Type:** string Статус операции:

  * `active` — операция используется.
  * `disabled` — операция отключена (без удаления).

  
id |  **Type:** integer<int32> Идентификатор операции (требуется указывать при изменении операции счетчика).  
value |  **Type:** string Значение для замены.  
  
### [](ru/management/openapi/counter/addCounter#publisheroptions)PublisherOptions

Структура с информацией о настройках контентной аналитики.

**Name** |  **Description**  
---|---  
enabled |  **Type:** boolean Сбор данных [контентной аналитики](https://yandex.../../../support/metrica/publishers/about.md). Для начала сбора статистики нужно [добавить на сайт разметку](https://yandex.../../../support/metrica/publishers/about.md).

  * 0 ― отключено (по умолчанию).
  * 1 ― включено.

  
schema |  **Type:** string Доступные варианты разметки сайта. Возможные значения:

  * `microdata`.
  * `json_ld`.
  * `opengraph`.

  
schema_options |  **Type:** string[] Доступные варианты разметки сайта. Возможные значения:

  * `microdata`.
  * `json_ld`.
  * `opengraph`.

  
  
### [](ru/management/openapi/counter/addCounter#webvisoroptions)WebvisorOptions

Структура с информацией о настройках Вебвизора.

**Name** |  **Description**  
---|---  
arch_enabled |  **Type:** boolean Сохранение страниц сайта:

  * 0 ― отключено (по умолчанию).
  * 1 ― включено.

  
arch_type |  **Type:** string Запись содержимого страниц:

  * `none` — выключено.
  * `load` — загружать с сайта.
  * `html` — из браузера.

  
load_player_type |  **Type:** string Загрузка страниц в плеер:

  * `proxy` — от имени анонимного пользователя.
  * `on_your_behalf` — от вашего имени.

  
urls |  **Type:** string Список страниц для сохранения. _Min length:_ `0` _Max length:_ `2000`  
wv_forms |  **Type:** boolean Запись содержимого полей и форм:

  * 0 — не записывать содержимое полей и форм за исключением тех из них, которые помечены css-классом -metrika-recordkeys.
  * 1 — записывать содержимое полей и форм за исключением тех из них, которые помечены css-классом -metrika-nokeys (по умолчанию).

  
wv_version |  **Type:** integer<int32> Версия вебвизора.  
  
### [](ru/management/openapi/counter/addCounter#informeroptionse)InformerOptionsE

Настройки информера.

**Name** |  **Description**  
---|---  
color_arrow |  **Type:** integer<int32> Цвет стрелки на информере:

  * 0 ― черный;
  * 1 ― фиолетовый (по умолчанию).

_Min value:_ `0` _Max value:_ `1`  
color_end |  **Type:** string Конечный (нижний) цвет информера в формате RRGGBBAA. Параметр предназначен для создания градиента фона. Насыщенность и прозрачность цвета задаются аналогично параметру color_start. _Default:_ `EFEFEFFF` _Pattern:_ `[0-9A-F]{8}`  
color_start |  **Type:** string Начальный (верхний) цвет информера в формате RRGGBBAA. RR, GG, BB ― насыщенность красного, зеленого и синего цвета. Насыщенность каждого цвета задается значениями в диапазоне от 00 до FF. AA ― прозрачность от 00 (прозрачный) до FF (непрозрачный). _Default:_ `FFFFFFFF.` _Pattern:_ `[0-9A-F]{8}`  
color_text |  **Type:** integer<int32> Цвет текста на информере:

  * 0 ― черный (по умолчанию);
  * 1 ― белый.

_Min value:_ `0` _Max value:_ `1`  
enabled |  **Type:** boolean Разрешение отображения информера:

  * 0 ― информер не отображается (по умолчанию).
  * 1 ― информер отображается.

  
indicator |  **Type:** string Показатель, который будет отображаться на информере:

  * `pageviews` — просмотры (по умолчанию).
  * `visits` — визиты.
  * `uniques` — посетители.

  
size |  **Type:** integer<int32> Размер информера:

  * 1 — размер 80х15;
  * 2 — размер 80х31;
  * 3 — размер 88х31 (по умолчанию). На вид информера этого типа не влияет значение поля `indicator`.

_Min value:_ `1` _Max value:_ `3`  
type |  **Type:** string Тип информера:

  * `simple` — простой.
  * `ext` — расширенный (по умолчанию).

  
  
### [](ru/management/openapi/counter/addCounter#goalcondition)GoalCondition

Список структур с условиями цели.

**Name** |  **Description**  
---|---  
type* |  **Type:** string Тип условия:

  * `contain` — содержит;
  * `exact` — совпадает;
  * `start` — начинается с;
  * `regexp` — удовлетворяет регулярному выражению;
  * `action` — специальный тип условия для целей «JavaScript-событие»;
  * `messenger` — специальный тип условия для целей типа form, путь в dom дереве;
  * `all_files` — признак для целей «Переход в мессенджер»;
  * `file` — скачивание конкретного файла для целей «Скачивание файлов»;
  * `search` — признак для целей «Поиск по сайту»;
  * `all_social` — специальный тип условия для целей типа `social` (все социальные сети);
  * `social` — специальный тип условия для целей типа `social` (конкретная социальная сеть);
  * `regexp_action` — js-событие удовлетворяет регулярному выражению (используется только в шаге составной цели);
  * `contain_action` — js-событие содержит (используется только в шаге составной цели).

  
url |  **Type:** string Значение зависит от типа цели:

  * **Посещение страниц**. Адрес страницы или части страницы для условия.
  * **Клик по email** или **Клик по номеру телефона**. Email или номер телефона, который указан в ссылках на сайте. Подробнее о том, как отследить клик по [email](https://yandex.../../../support/metrica/simple-goal/email.md) или [номеру телефона](https://yandex.../../../support/metrica/simple-goal/tel.md).
  
  
### [](ru/management/openapi/counter/addCounter#conditionalgoal)ConditionalGoal

Список шагов составной цели.

**Name** |  **Description**  
---|---  
name* |  **Type:** string Наименование цели. _Min length:_ `0` _Max length:_ `255`  
type* |  **Type:** string Тип цели:

  * `url` — посещение страниц.
  * `number` — количество просмотров.
  * `step` — составная цель.
  * `action` — JavaScript-событие.
  * `phone` — клик по номеру телефона.
  * `email` — клик по email.
  * `payment_system` — платежная система.
  * `messenger` — переход в мессенджер.
  * `file` — скачивание файлов.
  * `search` — поиск по сайту.
  * `social` — переход в соц. сети.
  * `visit_duration` — продолжительность визита.

  
conditions |  **Type:** [GoalCondition](addcounter.md)[] Список структур с условиями цели.  
default_price |  **Type:** number<double> Цена цели по умолчанию.  
flag |  **Type:** string Тип цели для клиентов Яндекс Маркета:

  * `basket` — **корзина** , страница посещения корзины.
  * `order` — **заказ** , страница подтверждения заказа.

  
goal_source |  **Type:** string Признак того, как создана цель:

  * `user` — цель создана пользователем Метрики.
  
id |  **Type:** integer<int64> Идентификатор цели. Укажите данный параметр при изменении и удалении цели счетчика.  
is_favorite |  **Type:** boolean Является ли цель избранной:

  * 0 ― не является (по умолчанию).
  * 1 ― является.

  
status |  **Type:** string  
  
### [](ru/management/openapi/counter/addCounter#accessfiltersshorte)AccessFiltersShortE

Список фильтров доступа, к которым выдано разрешение.

**Name** |  **Description**  
---|---  
id |  **Type:** integer<int32> id фильтра доступа.  
name |  **Type:** string Название фильтра доступа.  
  
## [](ru/management/openapi/counter/addCounter#responses)Responses

## [](ru/management/openapi/counter/addCounter#200-ok)200 OK

OK

### [](ru/management/openapi/counter/addCounter#body1)Body

application/json
    
    
    {
        "counter": {
            "id": 0,
            "status": "string",
            "owner_login": "string",
            "activity_status": "string",
            "name": "string",
            "type": "string",
            "favorite": false,
            "permission": "string",
            "goals": [
                {
                    "id": 0,
                    "name": "string",
                    "type": "string",
                    "default_price": 0,
                    "goal_source": "string",
                    "is_favorite": false,
                    "status": "string",
                    "conditions": [
                        {
                            "type": "string",
                            "url": "string"
                        }
                    ],
                    "flag": "basket"
                },
                {
                    "id": 0,
                    "name": "string",
                    "type": "string",
                    "default_price": 0,
                    "goal_source": "string",
                    "is_favorite": false,
                    "status": "string",
                    "steps": [
                        {
                            "id": 0,
                            "name": "string",
                            "type": "string",
                            "default_price": 0,
                            "goal_source": "string",
                            "is_favorite": false,
                            "status": "string",
                            "conditions": [
                                {
                                    "type": "string",
                                    "url": "string"
                                }
                            ],
                            "flag": "string"
                        }
                    ]
                },
                {
                    "id": 0,
                    "name": "string",
                    "type": "string",
                    "default_price": 0,
                    "goal_source": "string",
                    "is_favorite": false,
                    "status": "string",
                    "depth": 0
                },
                {
                    "id": 0,
                    "name": "string",
                    "type": "string",
                    "default_price": 0,
                    "goal_source": "string",
                    "is_favorite": false,
                    "status": "string",
                    "conditions": [
                        {
                            "type": "string",
                            "url": "string"
                        }
                    ],
                    "flag": "basket"
                },
                {
                    "id": 0,
                    "name": "string",
                    "type": "string",
                    "default_price": 0,
                    "goal_source": "string",
                    "is_favorite": false,
                    "status": "string",
                    "conditions": [
                        {
                            "type": "string",
                            "url": "string"
                        }
                    ],
                    "flag": "basket"
                },
                {
                    "id": 0,
                    "name": "string",
                    "type": "string",
                    "default_price": 0,
                    "goal_source": "string",
                    "is_favorite": false,
                    "status": "string",
                    "conditions": [
                        {
                            "type": "string",
                            "url": "string"
                        }
                    ],
                    "flag": "basket"
                },
                {
                    "id": 0,
                    "name": "string",
                    "type": "string",
                    "default_price": 0,
                    "goal_source": "string",
                    "is_favorite": false,
                    "status": "string"
                },
                {
                    "id": 0,
                    "name": "string",
                    "type": "string",
                    "default_price": 0,
                    "goal_source": "string",
                    "is_favorite": false,
                    "status": "string",
                    "conditions": [
                        {
                            "type": "string",
                            "url": "string"
                        }
                    ],
                    "flag": "basket",
                    "hide_phone_number": false
                },
                {
                    "id": 0,
                    "name": "string",
                    "type": "string",
                    "default_price": 0,
                    "goal_source": "string",
                    "is_favorite": false,
                    "status": "string",
                    "conditions": [
                        {
                            "type": "string",
                            "url": "string"
                        }
                    ],
                    "flag": "basket"
                },
                {
                    "id": 0,
                    "name": "string",
                    "type": "string",
                    "default_price": 0,
                    "goal_source": "string",
                    "is_favorite": false,
                    "status": "string",
                    "conditions": [
                        {
                            "type": "string",
                            "url": "string"
                        }
                    ],
                    "flag": "basket"
                },
                {
                    "id": 0,
                    "name": "string",
                    "type": "string",
                    "default_price": 0,
                    "goal_source": "string",
                    "is_favorite": false,
                    "status": "string",
                    "conditions": [
                        {
                            "type": "string",
                            "url": "string"
                        }
                    ],
                    "flag": "basket"
                },
                {
                    "id": 0,
                    "name": "string",
                    "type": "string",
                    "default_price": 0,
                    "goal_source": "string",
                    "is_favorite": false,
                    "status": "string",
                    "duration": 0
                }
            ],
            "filters": [
                {
                    "id": 0,
                    "attr": "string",
                    "type": "string",
                    "value": "string",
                    "action": "string",
                    "status": "string",
                    "start_ip": "string",
                    "end_ip": "string",
                    "with_subdomains": false
                }
            ],
            "operations": [
                {
                    "id": 0,
                    "action": "string",
                    "attr": "string",
                    "value": "string",
                    "status": "string"
                }
            ],
            "grants": [
                {
                    "user_login": "string",
                    "perm": "string",
                    "created_at": "2022-12-29T18:02:01Z",
                    "comment": "string",
                    "partner_data_access": false
                },
                {
                    "user_login": "string",
                    "perm": "string",
                    "created_at": "2022-12-29T18:02:01Z",
                    "comment": "string",
                    "partner_data_access": false,
                    "access_filters": [
                        {
                            "id": 0,
                            "name": "string"
                        }
                    ]
                }
            ],
            "labels": [
                {
                    "id": 0,
                    "name": "string"
                }
            ],
            "webvisor": {
                "urls": "string",
                "arch_enabled": false,
                "arch_type": "string",
                "load_player_type": "string",
                "wv_version": 0,
                "wv_forms": false
            },
            "code_options": {
                "async": false,
                "informer": {
                    "enabled": false,
                    "type": "string",
                    "size": 0,
                    "indicator": "string",
                    "color_start": "FFFFFFFF.",
                    "color_end": "EFEFEFFF",
                    "color_text": 0,
                    "color_arrow": 0
                },
                "visor": false,
                "track_hash": false,
                "xml_site": false,
                "clickmap": false,
                "in_one_line": false,
                "ecommerce": false,
                "alternative_cdn": false,
                "ytm": false
            },
            "create_time": "2022-12-29T18:02:01Z",
            "time_zone_name": "string",
            "time_zone_offset": 0,
            "source": "string",
            "update_time": "string",
            "delete_time": "string",
            "code": "string",
            "filter_robots": 0,
            "visit_threshold": 1800,
            "publisher_options": {
                "enabled": false,
                "schema": "string",
                "schema_options": [
                    "string"
                ]
            },
            "site2": {
                "site": "string"
            },
            "gdpr_agreement_accepted": false,
            "mirrors2": [
                {
                    "site": "string"
                }
            ],
            "autogoals_enabled": false,
            "counter_flags": {
                "use_in_benchmarks": false,
                "direct_allow_use_goals_without_access": false,
                "collect_first_party_data": false,
                "measurement_enabled": false
            },
            "measurement_tokens": [
                "string"
            ]
        }
    }
    

**Name** |  **Description**  
---|---  
counter* |  **Type:** [CounterFull](addcounter.md) Счетчик.  
  
No longer supported, please use an alternative and newer version.

### Была ли статья полезна?

ДаНет

Предыдущая

[Список доступных счетчиков](counters.md)

Следующая

[Восстановление счетчика](undeletecounter.md)