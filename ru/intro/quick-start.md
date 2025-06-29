# Частые вопросы | API Яндекс Метрики

Шаг 1. Получите oauth-токен

## В этой статье:

# Быстрый старт

## [](ru/intro/quick-start#token)Шаг 1. Получите oauth-токен

  1. [Создайте приложение](https://oauth.yandex.../client/new.md), при этом заполните поля:

     * **название** — можно указать произвольно;

     * **иконка сервиса** — необязательно;

     * **платформы приложения** — выберите **веб-сервисы** ;

     * **redirect URI** — укажите `https://oauth.yandex.../verification_code`.md

     * **доступ к данным** — укажите набор доступов для вашего приложения. Какие бывают доступы:

       * **metrika:read** — получение статистики, чтение параметров своих и доверенных счетчиков, получение списка счетчиков;
       * **metrika:write** — создание счетчиков, изменение параметров своих и доверенных счетчиков, загрузка любых данных;
       * **metrika:expenses** — загрузка в счетчики расходов;
       * **metrika:user_params** — загрузка в счетчики параметров пользователей;
       * **metrika:offline_data** — загрузка в счетчики офлайн-данных (данные из CRM, офлайн-конверсии, звонки).

Примечание

Доступы **metrika:expenses** , **metrika:user_params** , **metrika:offline_data** не обязательны, если используется доступ **metrika:write**.

  2. Нажмите **Создать приложение** и скопируйте его ClientID (напротив идентификатора нажмите значок ![](docs-assets/dev-metrika/rev/r16873860/_images/token-copy.png)).

  3. Добавьте скопированный ClientID в ссылку вида
         
         https://oauth.yandex.../authorize.md
         

  4. Перейдите по ссылке и на открывшейся странице скопируйте ваш авторизационный токен.

### [](ru/intro/quick-start#troubles)Возможные проблемы и их решение

Ошибка 403 (Access is denied) после получения токена

Возможные причины:

**На стороне приложения**

  * Приложение не имеет доступа к Метрике. Для чтения данных счётчиков (построение отчётов, просмотр информации по счётчику и т.п.) нужен доступ `metrika:read`. Для управления счётчиками (загрузка офлайн-данных, изменения счётчиков, сегментов и т.п.) нужен `metrika:write`.

**На стороне токена**

  * Токен невалидный. Срок действия токена истек, либо на аккаунте, для которого он был заведен, изменился пароль авторизации. Перевыпустите токен.

  * Токен создан не для того аккаунта. Мог быть заведён на логине, который не имеет доступ к счётчику Яндекс Метрики.

Важно

Владельцем токена является не владелец приложения, а аккаунт, из-под которого вы были авторизованы, когда выполняли GET-запрос на получение токена.

  * Токен создан не для того приложения. При выполнении GET-запроса на получение токена в параметре `client_id` было указано не то значение или была допущена опечатка, из-за которой токен был заведён на приложение, не имеющее доступа к Метрике (`metrika:read` или `metrika:write`).

**На стороне Метрики**

  * На счётчике, к которому вы обращаетесь по API нет доступа у владельца токена. [Подробнее](https://yandex.../support/metrica/general/access.md) о типах доступов к счётчику. Для API нужен владелец, гостевой доступ на просмотр или гостевой доступ на редактирование, если речь идёт об API управления.

**На стороне API запроса**

  * В коде для вызова API-запроса некорректно заданы параметры авторизации, из-за чего чтение токена происходит некорректно/не происходит вообще.

Ошибка 401 (unauthorized) после получения токена

Возможные причины:

  1. Параметры авторизации в заголовке запроса заданы некорректно.
  2. Параметры авторизации в заголовке отсутствуют.

## [](ru/intro/quick-start#api)Шаг 2. Выберите API для работы

Метрика предоставляет три основных API:

## [](ru/intro/quick-start#edit)Шаг 3. Измените объект через API

В качестве примера возьмем API управления и создадим цель:

  1. Перед тем как создать цель, выбираем счетчик, на котором необходимо создать цель. Для этого вызываем метод [GET https://api-metrika.yandex.net/management/v1/counters](../management/openapi/counter/counters.md) и выбираем нужный счетчик из списка.

**Запрос:**
         
         curl -i -X GET 'https://api-metrika.yandex.net/management/v1/counters' \
         -H 'Authorization: OAuth 05dd3dd8...'
         

**Ответ:**
         
         {
           "rows": 2,
           "counters": [
             {
               "id": 880000,
               "status": "Active",
               "owner_login": "example-developer",
               "code_status": "CS_ERR_UNKNOWN",
               "activity_status": "low",
               "name": "counter_option test example-developer",
               "type": "simple",
               "favorite": 0,
               "hide_address": 0,
               "pro": 0,
               "permission": "view",
               "webvisor": {
                 "arch_enabled": 0,
                 "arch_type": "none",
                 "load_player_type": "proxy",
                 "wv_version": 2,
                 "allow_wv2": true,
                 "notify_wv2": false,
                 "wv_forms": 1
               },
               "code_options": {
                 "async": 1,
                 "informer": {
                   "enabled": 0,
                   "type": "ext",
                   "size": 3,
                   "indicator": "pageviews",
                   "color_start": "FFFFFFFF",
                   "color_end": "EFEFEFFF",
                   "color_text": 0,
                   "color_arrow": 1
                 },
                 "visor": 0,
                 "track_hash": 0,
                 "xml_site": 0,
                 "clickmap": 1,
                 "in_one_line": 0,
                 "ecommerce": 0,
                 "alternative_cdn": 0,
                 "ecommerce_object": "dataLayer",
                 "ytm": false
               },
               "create_time": "2022-03-25T15:59:52+03:00",
               "time_zone_name": "Europe/Moscow",
               "time_zone_offset": 180,
               "partner_id": 0,
               "site": "example-developer.ru",
               "site2": {
                 "site": "example-developer.ru",
                 "domain": "example-developer.ru"
               },
               "gdpr_agreement_accepted": 0,
               "delete_guest_allowed": 1
             },
             {
               "id": 87686941,
               "status": "Active",
               "owner_login": "example-manager",
               "code_status": "CS_ERR_UNKNOWN",
               "activity_status": "low",
               "name": "example-manager_1",
               "type": "simple",
               "favorite": 0,
               "hide_address": 0,
               "pro": 0,
               "permission": "edit",
               "webvisor": {
                 "arch_enabled": 0,
                 "arch_type": "none",
                 "load_player_type": "proxy",
                 "wv_version": 2,
                 "allow_wv2": true,
                 "notify_wv2": false,
                 "wv_forms": 1
               },
               "code_options": {
                 "async": 1,
                 "informer": {
                   "enabled": 0,
                   "type": "ext",
                   "size": 3,
                   "indicator": "pageviews",
                   "color_start": "FFFFFFFF",
                   "color_end": "EFEFEFFF",
                   "color_text": 0,
                   "color_arrow": 1
                 },
                 "visor": 0,
                 "track_hash": 0,
                 "xml_site": 0,
                 "clickmap": 1,
                 "in_one_line": 0,
                 "ecommerce": 0,
                 "alternative_cdn": 0,
                 "ecommerce_object": "dataLayer",
                 "ytm": false
               },
               "create_time": "2022-03-02T16:06:27+03:00",
               "time_zone_name": "Europe/Moscow",
               "time_zone_offset": 180,
               "partner_id": 0,
               "site": "example-manager.ru",
               "site2": {
                 "site": "example-manager.ru",
                 "domain": "example-manager.ru"
               },
               "gdpr_agreement_accepted": 0,
               "delete_guest_allowed": 1
             }
           ]
         }
         

  2. Для создания цели используем метод [POST https://api-metrika.yandex.net/management/v1/counter/{counterId}/goals](../management/openapi/goal/addgoal.md). Создадим цель [MessengerGoal](../management/openapi/goal/addgoal.md), которая будет фиксировать переходы в определенный мессенджер.

**Запрос:**
         
         curl -i -X POST 'https://api-metrika.yandex.net/management/v1/counter/XXX/goals' \
         -H 'Authorization: OAuth 05dd3dd8...' \
         -H 'Content-Type: application/json' \
         
         -d '{
                "goal": {
                  "id": 0,
                  "name": "MyMessengerGoal",
                  "type": "messenger ",
                  "conditions" : [{
                    "type" :  "messenger", 
                    "url" :  "whatsapp"
                  }]
                }
          }'
         

**Ответ:**
         
         HTTP/1.1 200 OK
         
         {
            "goal": {
              "id": 222,
              "name": "MyMessengerGoal",
              "type": "messenger",
              "conditions" : [{
                    "type" :  "messenger", 
                    "url" :  "whatsapp"
                  }]
              }
          }
         

### Была ли статья полезна?

ДаНет

Предыдущая

[Авторизация](authorization.md)

Следующая

[Использование логина при работе с API](../advanced/ulogin.md)