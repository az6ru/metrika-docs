# Загрузка части подготовленных логов обработанного запроса - Справочник API Logs | API Яндекс Метрики

Визиты

  1. [API Logs](../index.md)
  2. Визиты

# Визиты

**Поле** |  **Тип данных** |  **Описание**  
---|---|---  
ym:s:visitID |  UInt64 |  Идентификатор визита, уникален в рамках одного года  
ym:s:counterID |  UInt32 |  Номер счетчика  
ym:s:watchIDs |  Array(UInt64) |  Просмотры, которые были в данном визите. Ограничение массива — 500 просмотров  
ym:s:date |  Date |  Дата визита  
ym:s:dateTime |  DateTime |  Дата и время визита (в часовом поясе счетчика)  
ym:s:dateTimeUTC |  DateTime |  Дата и время события (в часовом поясе UTC+3)  
ym:s:isNewUser |  UInt8 |  Первый визит посетителя  
ym:s:startURL |  String |  Страница входа  
ym:s:endURL |  String |  Страница выхода  
ym:s:pageViews |  Int32 |  Глубина просмотра (детально)  
ym:s:visitDuration |  UInt32 |  Время на сайте (детально)  
ym:s:bounce |  UInt8 |  Отказность  
ym:s:ipAddress |  String |  IP адрес  
ym:s:regionCountry |  String |  Страна (ISO)  
ym:s:regionCity |  String |  Город (английское название)  
ym:s:regionCountryID |  UInt32 |  ID страны  
ym:s:regionCityID |  UInt32 |  ID города  
ym:s:clientID |  UInt64 |  Анонимный идентификатор пользователя в браузере (first-party cookies)  
ym:s:counterUserIDHash |  UInt64 |  Идентификатор посетителя (в рамках одного браузера), с помощью которого производится подсчет уникальных посетителей сайта в интерфейсе Метрики  
ym:s:networkType |  String |  Тип соединения. Группировка устарела и скоро будет удалена из API.  
ym:s:goalsID |  Array(UInt32) |  Номера целей, достигнутых за данный визит  
ym:s:goalsSerialNumber |  Array(UInt32) |  Порядковые номера достижений цели с конкретным идентификатором  
ym:s:goalsDateTime |  Array(DateTime) |  Время достижения каждой цели (в часовом поясе UTC+3)  
ym:s:goalsPrice |  Array(Int64) |  Ценность цели  
ym:s:goalsOrder |  Array(String) |  Идентификатор заказов  
ym:s:goalsCurrency |  Array(String) |  Идентификатор валюты  
ym:s:<[attribution](../param.md)>TrafficSource |  String |  Источник трафика  
ym:s:<[attribution](../param.md)>AdvEngine |  String |  Рекламная система  
ym:s:<[attribution](../param.md)>ReferalSource |  String |  Переход с сайтов  
ym:s:<[attribution](../param.md)>SearchEngineRoot |  String |  Поисковая система  
ym:s:<[attribution](../param.md)>SearchEngine |  String |  Поисковая система (детально)  
ym:s:<[attribution](../param.md)>SocialNetwork |  String |  Cоциальная сеть  
ym:s:<[attribution](../param.md)>SocialNetworkProfile |  String |  Группа социальной сети  
ym:s:referer |  String |  Реферер  
ym:s:<[attribution](../param.md)>DirectClickOrder |  UInt32 |  Кампания Яндекс Директа  
ym:s:<[attribution](../param.md)>DirectBannerGroup |  UInt32 |  Группа объявлений  
ym:s:<[attribution](../param.md)>DirectClickBanner |  String |  Объявление Яндекс Директа  
ym:s:<[attribution](../param.md)>DirectClickOrderName |  String |  Название кампании Яндекс Директа  
ym:s:<[attribution](../param.md)>ClickBannerGroupName |  String |  Название группы объявлений  
ym:s:<[attribution](../param.md)>DirectClickBannerName |  String |  Название объявления Яндекс Директа  
ym:s:<[attribution](../param.md)>DirectPhraseOrCond |  String |  Условие показа объявления  
ym:s:<[attribution](../param.md)>DirectPlatformType |  string |  Тип площадки  
ym:s:<[attribution](../param.md)>DirectPlatform |  String |  Площадка  
ym:s:<[attribution](../param.md)>DirectConditionType |  String |  Тип условия показа объявления  
ym:s:<[attribution](../param.md)>CurrencyID |  String |  Валюта  
ym:s:from |  String |  Метка from  
ym:s:<[attribution](../param.md)>UTMCampaign |  String |  UTM Campaign  
ym:s:<[attribution](../param.md)>UTMContent |  String |  UTM Content  
ym:s:<[attribution](../param.md)>UTMMedium |  String |  UTM Medium  
ym:s:<[attribution](../param.md)>UTMSource |  String |  UTM Source  
ym:s:<[attribution](../param.md)>UTMTerm |  String |  UTM Term  
ym:s:<[attribution](../param.md)>openstatAd |  String |  Openstat Ad  
ym:s:<[attribution](../param.md)>openstatCampaign |  String |  Openstat Campaign  
ym:s:<[attribution](../param.md)>openstatService |  String |  Openstat Service  
ym:s:<[attribution](../param.md)>openstatSource |  String |  Openstat Source  
ym:s:<[attribution](../param.md)>hasGCLID |  UInt8 |  Наличие метки GCLID  
ym:s:<[attribution](../param.md)>GCLID |  String |  Метка GCLID  
ym:s:browserLanguage |  String |  Язык браузера  
ym:s:browserCountry |  String |  Страна браузера  
ym:s:clientTimeZone |  Int16 |  Разница между часовым поясом пользователя и UTC (в минутах)  
ym:s:deviceCategory |  String |  Тип устройства. Возможные значения: 1 — десктоп, 2 — мобильные телефоны, 3 — планшеты, 4 — TV  
ym:s:mobilePhone |  String |  Производитель устройства  
ym:s:mobilePhoneModel |  String |  Модель устройства  
ym:s:operatingSystemRoot |  String |  Группа операционных систем  
ym:s:operatingSystem |  String |  Операционная система (детально)  
ym:s:browser |  String |  Браузер  
ym:s:browserMajorVersion |  UInt16 |  Major-версия браузера  
ym:s:browserMinorVersion |  UInt16 |  Minor-версия браузера  
ym:s:browserEngine |  String |  Движок браузера  
ym:s:browserEngineVersion1 |  UInt16 |  Major-версия движка браузера  
ym:s:browserEngineVersion2 |  UInt16 |  Minor-версия движка браузера  
ym:s:browserEngineVersion3 |  UInt16 |  Build-версия движка браузера  
ym:s:browserEngineVersion4 |  UInt16 |  Revision-версия движка браузера  
ym:s:cookieEnabled |  UInt8 |  Наличие Cookie  
ym:s:javascriptEnabled |  UInt8 |  Наличие JavaScript  
ym:s:screenFormat |  String |  Соотношение сторон. Возможные значения:

  * `undefined`;
  * `9:21`;
  * `9:16`;
  * `3:5`;
  * `10:16`;
  * `2:3`;
  * `3:4`;
  * `4:5`;
  * `5:4`;
  * `4:3`;
  * `3:2`;
  * `16:10`;
  * `5:3`;
  * `16:9`;
  * `21:9`.

  
ym:s:screenColors |  UInt8 |  Глубина цвета  
ym:s:screenOrientation |  UInt8 |  Ориентация экрана. 1 - portrait, 2 - landscape  
ym:s:screenOrientationName |  String |  Ориентация экрана  
ym:s:screenWidth |  UInt16 |  Логическая ширина  
ym:s:screenHeight |  UInt16 |  Логическая высота  
ym:s:physicalScreenWidth |  UInt16 |  Физическая ширина  
ym:s:physicalScreenHeight |  UInt16 |  Физическая высота  
ym:s:windowClientWidth |  UInt16 |  Ширина окна  
ym:s:windowClientHeight |  UInt16 |  Высота окна  
ym:s:purchaseID |  Array(String) |  Идентификатор покупки. Список всех идентификаторов транзакций для визита. Идентификаторы уникальные.  
ym:s:purchaseDateTime |  Array(DateTime) |  Дата и время покупки  
ym:s:purchaseAffiliation |  Array(String) |  Магазин или филиал, в котором произошла транзакция  
ym:s:purchaseRevenue |  Array(Float64) |  Общий доход или суммарная ценность транзакции  
ym:s:purchaseTax |  Array(Float64) |  Сумма всех налогов, связанных с транзакцией  
ym:s:purchaseShipping |  Array(Float64) |  Стоимость доставки, связанная с транзакцией  
ym:s:purchaseCoupon |  Array(String) |  Промокод, ассоциированный со всей покупкой целиком  
ym:s:purchaseCurrency |  Array(String) |  Валюта транзакции  
ym:s:purchaseProductQuantity |  Array(Int64) |  Количество товаров в покупке  
ym:s:eventsProductID |  Array(String) |  Идентификатор или код товара  
ym:s:eventsProductList |  Array(String) |  Список, в который входят товары, связанные с транзакцией  
ym:s:eventsProductBrand |  Array(String) |  Бренд, к которому относится товар  
ym:s:eventsProductCategory |  Array(String) |  Категория, к которой относится товар  
ym:s:eventsProductCategory1 |  Array(String) |  Категория, к которой относится товар, уровень 1  
ym:s:eventsProductCategory2 |  Array(String) |  Категория, к которой относится товар, уровень 2  
ym:s:eventsProductCategory3 |  Array(String) |  Категория, к которой относится товар, уровень 3  
ym:s:eventsProductCategory4 |  Array(String) |  Категория, к которой относится товар, уровень 4  
ym:s:eventsProductCategory5 |  Array(String) |  Категория, к которой относится товар, уровень 5  
ym:s:eventsProductVariant |  Array(String) |  Вариант товара  
ym:s:eventsProductPosition |  Array(Int32) |  Позиция товара в списке или коллекции  
ym:s:eventsProductPrice |  Array(Int64) |  Цена товара  
ym:s:eventsProductCurrency |  Array(String) |  Валюта товара  
ym:s:eventsProductCoupon |  Array(String) |  Промокод, ассоциированный с товаром  
ym:s:eventsProductQuantity |  Array(UInt64) |  Количество товаров  
ym:s:eventsProductEventTime |  Array(DateTime) |  Дата и время события  
ym:s:eventsProductType |  Array(UInt8) |  Тип события. Возможные значения:

  * `view_item_list` — просмотр списка товара;
  * `click` — клик по товару;
  * `detail` — просмотр карточки товара;
  * `add` — добавление товара в корзину;
  * `purchase` — покупка;
  * `remove` — удаление товара из корзины.

  
ym:s:eventsProductDiscount |  Array(String) |  Процент скидки на товар  
ym:s:eventsProductName |  Array(String) |  Название товара  
ym:s:productsPurchaseID |  Array(String) |  Идентификатор покупки. Для каждого купленного товара `ym:s:productsID` указывается транзакция, в рамках которой он был куплен. Идентификаторы могут дублироваться.  
ym:s:productsID |  Array(String) |  Идентификатор или код купленного товара  
ym:s:productsName |  Array(String) |  Название купленного товара  
ym:s:productsBrand |  Array(String) |  Бренд, к которому относится купленный товар  
ym:s:productsCategory |  Array(String) |  Категория, к которой относится купленный товар  
ym:s:productsCategory1 |  Array(String) |  Категория, к которой относится купленный товар, уровень 1  
ym:s:productsCategory2 |  Array(String) |  Категория, к которой относится купленный товар, уровень 2  
ym:s:productsCategory3 |  Array(String) |  Категория, к которой относится купленный товар, уровень 3  
ym:s:productsCategory4 |  Array(String) |  Категория, к которой относится купленный товар, уровень 4  
ym:s:productsCategory5 |  Array(String) |  Категория, к которой относится купленный товар, уровень 5  
ym:s:productsVariant |  Array(String) |  Вариант купленного товара  
ym:s:productsPosition |  Array(Int32) |  Позиция купленного товара в списке или коллекции  
ym:s:productsPrice |  Array(Float64) |  Цена купленного товара  
ym:s:productsCurrency |  Array(String) |  Валюта купленного товара  
ym:s:productsCoupon |  Array(String) |  Промокод, ассоциированный с купленным товаром  
ym:s:productsQuantity |  Array(Int64) |  Количество купленных товаров  
ym:s:productsList |  Array(String) |  Список, в который входят купленные товары, связанные с транзакцией  
ym:s:productsEventTime |  Array(DateTime) |  Дата и время покупки товара  
ym:s:productsDiscount |  Array(String) |  Процент скидки на купленный товар  
ym:s:impressionsURL |  Array(String) |  URL страницы с товаром  
ym:s:impressionsDateTime |  Array(DateTime) |  Дата и время просмотра  
ym:s:impressionsProductID |  Array(String) |  Идентификатор просмотренного товара  
ym:s:impressionsProductName |  Array(String) |  Название просмотренного товара  
ym:s:impressionsProductBrand |  Array(String) |  Бренд, к которому относится просмотренный товар  
ym:s:impressionsProductCategory |  Array(String) |  Категория, к которой относится просмотренный товар  
ym:s:impressionsProductCategory1 |  Array(String) |  Категория, к которой относится просмотренный товар, уровень 1  
ym:s:impressionsProductCategory2 |  Array(String) |  Категория, к которой относится просмотренный товар, уровень 2  
ym:s:impressionsProductCategory3 |  Array(String) |  Категория, к которой относится просмотренный товар, уровень 3  
ym:s:impressionsProductCategory4 |  Array(String) |  Категория, к которой относится просмотренный товар, уровень 4  
ym:s:impressionsProductCategory5 |  Array(String) |  Категория, к которой относится просмотренный товар, уровень 5  
ym:s:impressionsProductVariant |  Array(String) |  Вариант просмотренного товара  
ym:s:impressionsProductPrice |  Array(Int64) |  Цена просмотренного товара  
ym:s:impressionsProductCurrency |  Array(String) |  Валюта просмотренного товара  
ym:s:impressionsProductCoupon |  Array(String) |  Промокод, ассоциированный с просмотренным товаром  
ym:s:impressionsProductList |  Array(String) |  Список, в который входят просмотренные товары, связанные с транзакцией  
ym:s:impressionsProductQuantity |  Array(UInt64) |  Количество просмотренных товаров  
ym:s:impressionsProductEventTime |  Array(DateTime) |  Дата и время просмотра товара. То же, что и `ym:s:impressionsDateTime`  
ym:s:impressionsProductDiscount |  Array(String) |  Процент скидки на просмотренный товар  
ym:s:promotionID |  Array(String) |  Идентификатор или код промокампании  
ym:s:promotionName |  Array(String) |  Название промокампании  
ym:s:promotionCreative |  Array(String) |  Название рекламного баннера  
ym:s:promotionPosition |  Array(String) |  Позиция рекламного баннера  
ym:s:promotionCreativeSlot |  Array(String) |  Слот рекламного баннера  
ym:s:promotionEventTime |  Array(DateTime) |  Дата и время события рекламной кампании  
ym:s:promotionType |  Array(UInt8) |  Тип события рекламной кампании: `promoView` — просмотр рекламного материала, `promoClick` — клик по рекламному материалу  
ym:s:offlineCallTalkDuration |  Array(UInt32) |  Длительность звонка в секундах  
ym:s:offlineCallHoldDuration |  Array(UInt32) |  Длительность ожидания звонка в секундах  
ym:s:offlineCallMissed |  Array(UInt32) |  Пропущен ли звонок  
ym:s:offlineCallTag |  Array(String) |  Произвольная метка  
ym:s:offlineCallFirstTimeCaller |  Array(Int32) |  Первичный ли звонок  
ym:s:offlineCallURL |  Array(String) |  URL, с которого был звонок (ассоциированная с событием страница)  
ym:s:parsedParamsKey1 |  Array(String) |  Параметры визита, ур. 1  
ym:s:parsedParamsKey2 |  Array(String) |  Параметры визита, ур. 2  
ym:s:parsedParamsKey3 |  Array(String) |  Параметры визита, ур. 3  
ym:s:parsedParamsKey4 |  Array(String) |  Параметры визита, ур. 4  
ym:s:parsedParamsKey5 |  Array(String) |  Параметры визита, ур. 5  
ym:s:parsedParamsKey6 |  Array(String) |  Параметры визита, ур. 6  
ym:s:parsedParamsKey7 |  Array(String) |  Параметры визита, ур. 7  
ym:s:parsedParamsKey8 |  Array(String) |  Параметры визита, ур. 8  
ym:s:parsedParamsKey9 |  Array(String) |  Параметры визита, ур. 9  
ym:s:parsedParamsKey10 |  Array(String) |  Параметры визита, ур. 10  
ym:s:<[attribution](../param.md)>RecommendationSystem |  String |  Переход из рекомендательных систем. [Подробнее о параметре](../openapi/getlogrequests.md)  
ym:s:<[attribution](../param.md)>Messenger |  String |  Переход из мессенджера. [Подробнее о параметре](../openapi/getlogrequests.md)  
  
### Была ли статья полезна?

ДаНет

Предыдущая

[События](hits.md)

Следующая

[Параметризация](../param.md)