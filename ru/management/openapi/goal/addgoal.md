# История изменений | API Яндекс Метрики

Request

## В этой статье:

  1. [API управления](../../index.md)
  2. Справочник API управления
  3. Управление целями
  4. Создание цели

# Создание цели

Создает цель счетчика.

## [](ru/management/openapi/goal/addGoal#request)Request

POST
    
    
    https://api-metrika.yandex.net/management/v1/counter/{counterId}/goals
    

### [](ru/management/openapi/goal/addGoal#path-parameters)Path parameters

**Name** |  **Description**  
---|---  
counterId* |  **Type:** integer<int32> Идентификатор счетчика, для которого вы хотите создать цель.  
  
### [](ru/management/openapi/goal/addGoal#body)Body

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
goal* |  **Type:** [ActionGoal](addgoal.md) or [CompositeGoal](addgoal.md) or [DepthGoal](addgoal.md) or [EmailGoal](addgoal.md) or [FileGoal](addgoal.md) or [MessengerGoal](addgoal.md) or [PaymentSystemGoal](addgoal.md) or [PhoneGoal](addgoal.md) or [SiteSearchGoal](addgoal.md) or [SocialNetworkGoal](addgoal.md) or [UrlGoal](addgoal.md) or [VisitDurationGoal](addgoal.md)  
  
### [](ru/management/openapi/goal/addGoal#actiongoal)ActionGoal

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

  
conditions |  **Type:** [GoalCondition](addgoal.md)[] Список структур с условиями цели.  
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
  
### [](ru/management/openapi/goal/addGoal#compositegoal)CompositeGoal

Составная цель. Нужна для группировки и задания порядка обычных целей. В качестве шагов может содержать цели типа "Посещение страниц" и "JavaScript-событие". Шаг считается достигнутым, если были достигнуты все предыдущие шаги, и после этого были выполнены все условия текущего шага.

**Name** |  **Description**  
---|---  
name* |  **Type:** string Наименование цели. _Min length:_ `0` _Max length:_ `255`  
steps* |  **Type:** [ConditionalGoal](addgoal.md)[] Список шагов составной цели. _Min items:_ `0` _Max items:_ `5`  
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
  
### [](ru/management/openapi/goal/addGoal#depthgoal)DepthGoal

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
  
### [](ru/management/openapi/goal/addGoal#emailgoal)EmailGoal

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

  
conditions |  **Type:** [GoalCondition](addgoal.md)[] Список структур с условиями цели.  
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
  
### [](ru/management/openapi/goal/addGoal#filegoal)FileGoal

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

  
conditions |  **Type:** [GoalCondition](addgoal.md)[] Список структур с условиями цели.  
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
  
### [](ru/management/openapi/goal/addGoal#messengergoal)MessengerGoal

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

  
conditions |  **Type:** [GoalCondition](addgoal.md)[] Список структур с условиями цели.  
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
  
### [](ru/management/openapi/goal/addGoal#paymentsystemgoal)PaymentSystemGoal

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
  
### [](ru/management/openapi/goal/addGoal#phonegoal)PhoneGoal

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

  
conditions |  **Type:** [GoalCondition](addgoal.md)[] Список структур с условиями цели.  
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
  
### [](ru/management/openapi/goal/addGoal#sitesearchgoal)SiteSearchGoal

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

  
conditions |  **Type:** [GoalCondition](addgoal.md)[] Список структур с условиями цели.  
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
  
### [](ru/management/openapi/goal/addGoal#socialnetworkgoal)SocialNetworkGoal

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

  
conditions |  **Type:** [GoalCondition](addgoal.md)[] Список структур с условиями цели.  
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
  
### [](ru/management/openapi/goal/addGoal#urlgoal)UrlGoal

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

  
conditions |  **Type:** [GoalCondition](addgoal.md)[] Список структур с условиями цели.  
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
  
### [](ru/management/openapi/goal/addGoal#visitdurationgoal)VisitDurationGoal

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
  
### [](ru/management/openapi/goal/addGoal#goale)GoalE

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
  
### [](ru/management/openapi/goal/addGoal#goalcondition)GoalCondition

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
  
  
### [](ru/management/openapi/goal/addGoal#conditionalgoal)ConditionalGoal

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

  
conditions |  **Type:** [GoalCondition](addgoal.md)[] Список структур с условиями цели.  
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
  
## [](ru/management/openapi/goal/addGoal#responses)Responses

## [](ru/management/openapi/goal/addGoal#200-ok)200 OK

OK

### [](ru/management/openapi/goal/addGoal#body1)Body

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
goal* |  **Type:** [ActionGoal](addgoal.md) or [CompositeGoal](addgoal.md) or [DepthGoal](addgoal.md) or [EmailGoal](addgoal.md) or [FileGoal](addgoal.md) or [MessengerGoal](addgoal.md) or [PaymentSystemGoal](addgoal.md) or [PhoneGoal](addgoal.md) or [SiteSearchGoal](addgoal.md) or [SocialNetworkGoal](addgoal.md) or [UrlGoal](addgoal.md) or [VisitDurationGoal](addgoal.md)  
  
No longer supported, please use an alternative and newer version.

### Была ли статья полезна?

ДаНет

Предыдущая

[Список целей](goals.md)

Следующая

[Список социальных сетей](getsocialnetworks.md)