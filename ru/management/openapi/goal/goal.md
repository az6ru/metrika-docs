# Удаление фильтра доступа - Управление фильтрами доступа | API Яндекс Метрики

Request

## В этой статье:

  1. [API управления](../../index.md)
  2. Справочник API управления
  3. Управление целями
  4. Информация о цели

# Информация о цели

Возвращает информацию об указанной цели счетчика.

## [](ru/management/openapi/goal/goal#request)Request

GET
    
    
    https://api-metrika.yandex.net/management/v1/counter/{counterId}/goal/{goalId}
    

### [](ru/management/openapi/goal/goal#path-parameters)Path parameters

**Name** |  **Description**  
---|---  
counterId* |  **Type:** integer<int32> Идентификатор счетчика, информацию о цели которого вы хотите получить.  
Example: `2215573`  
goalId* |  **Type:** integer<int64> Идентификатор цели, информацию о которой вы хотите получить.  
Example: `334423`  
  
### [](ru/management/openapi/goal/goal#query-parameters)Query parameters

**Name** |  **Description**  
---|---  
callback |  **Type:** string Функция обратного вызова, которая обрабатывает ответ API.  
  
## [](ru/management/openapi/goal/goal#responses)Responses

## [](ru/management/openapi/goal/goal#200-ok)200 OK

OK

### [](ru/management/openapi/goal/goal#body)Body

application/json
    
    
    {
        "goal": {
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
        }
    }
    

**Name** |  **Description**  
---|---  
goal* |  **Type:** [ActionGoal](goal.md) or [CompositeGoal](goal.md) or [DepthGoal](goal.md) or [EmailGoal](goal.md) or [FileGoal](goal.md) or [MessengerGoal](goal.md) or [PaymentSystemGoal](goal.md) or [PhoneGoal](goal.md) or [SiteSearchGoal](goal.md) or [SocialNetworkGoal](goal.md) or [UrlGoal](goal.md) or [VisitDurationGoal](goal.md)  
  
### [](ru/management/openapi/goal/goal#actiongoal)ActionGoal

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

  
conditions |  **Type:** [GoalCondition](goal.md)[] Список структур с условиями цели.  
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
  
### [](ru/management/openapi/goal/goal#compositegoal)CompositeGoal

Составная цель. Нужна для группировки и задания порядка обычных целей. В качестве шагов может содержать цели типа "Посещение страниц" и "JavaScript-событие". Шаг считается достигнутым, если были достигнуты все предыдущие шаги, и после этого были выполнены все условия текущего шага.

**Name** |  **Description**  
---|---  
name* |  **Type:** string Наименование цели. _Min length:_ `0` _Max length:_ `255`  
steps* |  **Type:** [ConditionalGoal](goal.md)[] Список шагов составной цели. _Min items:_ `0` _Max items:_ `5`  
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
  
### [](ru/management/openapi/goal/goal#depthgoal)DepthGoal

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
  
### [](ru/management/openapi/goal/goal#emailgoal)EmailGoal

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

  
conditions |  **Type:** [GoalCondition](goal.md)[] Список структур с условиями цели.  
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
  
### [](ru/management/openapi/goal/goal#filegoal)FileGoal

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

  
conditions |  **Type:** [GoalCondition](goal.md)[] Список структур с условиями цели.  
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
  
### [](ru/management/openapi/goal/goal#messengergoal)MessengerGoal

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

  
conditions |  **Type:** [GoalCondition](goal.md)[] Список структур с условиями цели.  
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
  
### [](ru/management/openapi/goal/goal#paymentsystemgoal)PaymentSystemGoal

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
  
### [](ru/management/openapi/goal/goal#phonegoal)PhoneGoal

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

  
conditions |  **Type:** [GoalCondition](goal.md)[] Список структур с условиями цели.  
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
  
### [](ru/management/openapi/goal/goal#sitesearchgoal)SiteSearchGoal

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

  
conditions |  **Type:** [GoalCondition](goal.md)[] Список структур с условиями цели.  
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
  
### [](ru/management/openapi/goal/goal#socialnetworkgoal)SocialNetworkGoal

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

  
conditions |  **Type:** [GoalCondition](goal.md)[] Список структур с условиями цели.  
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
  
### [](ru/management/openapi/goal/goal#urlgoal)UrlGoal

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

  
conditions |  **Type:** [GoalCondition](goal.md)[] Список структур с условиями цели.  
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
  
### [](ru/management/openapi/goal/goal#visitdurationgoal)VisitDurationGoal

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
  
### [](ru/management/openapi/goal/goal#goale)GoalE

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
  
### [](ru/management/openapi/goal/goal#goalcondition)GoalCondition

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
  
  
### [](ru/management/openapi/goal/goal#conditionalgoal)ConditionalGoal

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

  
conditions |  **Type:** [GoalCondition](goal.md)[] Список структур с условиями цели.  
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
  
No longer supported, please use an alternative and newer version.

### Была ли статья полезна?

ДаНет

Предыдущая

[Удаление фильтра доступа](../access_filter/deleteaccessfilter.md)

Следующая

[Изменение цели](editgoal.md)