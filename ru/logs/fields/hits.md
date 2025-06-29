# Загрузка части подготовленных логов обработанного запроса - Справочник API Logs | API Яндекс Метрики

События

  1. [API Logs](../index.md)
  2. События

# События

**Поле** |  **Тип данных** |  **Описание**  
---|---|---  
ym:pv:watchID |  UInt64 |  Идентификатор события  
ym:pv:pageViewID |  UInt32 |  Идентификатор просмотра, в рамках которого произошло событие  
ym:pv:counterID |  UInt32 |  Номер счетчика  
ym:pv:clientID |  UInt64 |  Анонимный идентификатор пользователя в браузере (first-party cookies)  
ym:pv:counterUserIDHash |  UInt64 |  Идентификатор посетителя (в рамках одного браузера), с помощью которого производится подсчет уникальных посетителей сайта в интерфейсе Метрики  
ym:pv:date |  Date |  Дата события  
ym:pv:dateTime |  DateTime |  Дата и время события (в часовом поясе счетчика)  
ym:pv:title |  String |  Заголовок страницы  
ym:pv:pageCharset |  String |  Кодировка страницы сайта  
ym:pv:goalsID |  Array(UInt32) |  Номера целей, достигнутых в данном событии  
ym:pv:URL |  String |  Адрес страницы  
ym:pv:referer |  String |  Реферер  
ym:pv:UTMCampaign |  String |  UTM Campaign  
ym:pv:UTMContent |  String |  UTM Content  
ym:pv:UTMMedium |  String |  UTM Medium  
ym:pv:UTMSource |  String |  UTM Source  
ym:pv:UTMTerm |  String |  UTM Term  
ym:pv:openstatAd |  String |  Openstat Ad  
ym:pv:openstatCampaign |  String |  Openstat Campaign  
ym:pv:openstatService |  String |  Openstat Service  
ym:pv:openstatSource |  String |  Openstat Source  
ym:pv:operatingSystem |  String |  Операционная система (детально)  
ym:pv:from |  String |  Метка from  
ym:pv:hasGCLID |  UInt8 |  Наличие GCLID  
ym:pv:GCLID |  String |  GCLID  
ym:pv:lastTrafficSource |  String |  Источник трафика  
ym:pv:lastSearchEngineRoot |  String |  Поисковая система  
ym:pv:lastSearchEngine |  String |  Поисковая система (детально)  
ym:pv:lastAdvEngine |  String |  Рекламная система  
ym:pv:lastSocialNetwork |  String |  Социальная сеть  
ym:pv:lastSocialNetworkProfile |  String |  Страница социальной сети, с которой был переход  
ym:pv:recommendationSystem |  String |  Рекомендательная система  
ym:pv:messenger |  String |  Мессенджер  
ym:pv:browser |  String |  Браузер  
ym:pv:browserMajorVersion |  UInt16 |  Major-версия браузера  
ym:pv:browserMinorVersion |  UInt16 |  Minor-версия браузера  
ym:pv:browserCountry |  String |  Страна браузера  
ym:pv:browserEngine |  String |  Движок браузера  
ym:pv:browserEngineVersion1 |  UInt16 |  Major-версия движка браузера  
ym:pv:browserEngineVersion2 |  UInt16 |  Minor-версия движка браузера  
ym:pv:browserEngineVersion3 |  UInt16 |  Build-версия движка браузера  
ym:pv:browserEngineVersion4 |  UInt16 |  Revision-версия движка браузера  
ym:pv:browserLanguage |  String |  Язык браузера  
ym:pv:clientTimeZone |  Int16 |  Разница между часовым поясом пользователя и UTC (в минутах)  
ym:pv:cookieEnabled |  UInt8 |  Наличие Cookie  
ym:pv:deviceCategory |  String |  Тип устройства. Возможные значения:

  * 1 — десктоп;
  * 2 — мобильные телефоны;
  * 3 — планшеты;
  * 4 — TV

  
ym:pv:javascriptEnabled |  UInt8 |  Наличие JavaScript  
ym:pv:mobilePhone |  String |  Производитель устройства  
ym:pv:mobilePhoneModel |  String |  Модель устройства  
ym:pv:operatingSystemRoot |  String |  Группа операционных систем  
ym:pv:physicalScreenHeight |  UInt16 |  Физическая высота  
ym:pv:physicalScreenWidth |  UInt16 |  Физическая ширина  
ym:pv:screenColors |  UInt8 |  Глубина цвета  
ym:pv:screenFormat |  String |  Соотношение сторон. Возможные значения:

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

  
ym:pv:screenHeight |  UInt16 |  Логическая высота  
ym:pv:screenOrientation |  UInt8 |  Ориентация экрана. 1 - portrait, 2 - landscape  
ym:pv:screenOrientationName |  String |  Ориентация экрана  
ym:pv:screenWidth |  UInt16 |  Логическая ширина  
ym:pv:windowClientHeight |  UInt16 |  Высота окна  
ym:pv:windowClientWidth |  UInt16 |  Ширина окна  
ym:pv:ipAddress |  String |  IP адрес  
ym:pv:regionCity |  String |  Город (английское название)  
ym:pv:regionCountry |  String |  Страна (ISO)  
ym:pv:regionCityID |  UInt32 |  ID города  
ym:pv:regionCountryID |  UInt32 |  ID страны  
ym:pv:isPageView |  UInt8 |  Было ли событие просмотром страницы  
ym:pv:isTurboPage |  UInt8 |  Было ли событие совершено на Турбо-странице  
ym:pv:isTurboApp |  UInt8 |  Было ли событие совершено на Турбо-сервисе  
ym:pv:iFrame |  UInt8 |  Было ли событие совершено в iframe  
ym:pv:link |  UInt8 |  Было ли событие переходом по ссылке или загрузкой файла  
ym:pv:download |  UInt8 |  Было ли событие загрузкой файла  
ym:pv:notBounce |  UInt8 |  Было ли событие специальным событием «неотказ» (для точного показателя отказов)  
ym:pv:artificial |  UInt8 |  Было ли событие искусственным, переданным с помощью функций hit(), event() и пр.  
ym:pv:ecommerce |  String |  События электронной коммерции  
ym:pv:params |  String |  Параметры  
ym:pv:parsedParamsKey1 |  Array(String) |  Параметры просмотра, ур. 1  
ym:pv:parsedParamsKey2 |  Array(String) |  Параметры просмотра, ур. 2  
ym:pv:parsedParamsKey3 |  Array(String) |  Параметры просмотра, ур. 3  
ym:pv:parsedParamsKey4 |  Array(String) |  Параметры просмотра, ур. 4  
ym:pv:parsedParamsKey5 |  Array(String) |  Параметры просмотра, ур. 5  
ym:pv:parsedParamsKey6 |  Array(String) |  Параметры просмотра, ур. 6  
ym:pv:parsedParamsKey7 |  Array(String) |  Параметры просмотра, ур. 7  
ym:pv:parsedParamsKey8 |  Array(String) |  Параметры просмотра, ур. 8  
ym:pv:parsedParamsKey9 |  Array(String) |  Параметры просмотра, ур. 9  
ym:pv:parsedParamsKey10 |  Array(String) |  Параметры просмотра, ур. 10  
ym:pv:httpError |  String |  Код ошибки  
ym:pv:networkType |  String |  Тип соединения. Группировка устарела и скоро будет удалена из API  
ym:pv:shareService |  String |  Кнопка «Поделиться», имя сервиса  
ym:pv:shareURL |  String |  Кнопка «Поделиться», URL  
ym:pv:shareTitle |  String |  Кнопка «Поделиться», заголовок страницы  
  
### Была ли статья полезна?

ДаНет

Предыдущая

[Введение](../index.md)

Следующая

[Визиты](visits.md)