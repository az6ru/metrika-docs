# Использование Measurement Protocol | API Яндекс Метрики

Поддерживаемые параметры

## В этой статье:

  1. [API импорта данных](index.md)
  2. Measurement Protocol
  3. Загрузка данных

# Загрузка данных

Передача данных осуществляется на url `https://mc.yandex.../collect`.md POST|GET-запросами. Каждый параметр в запросе представляет собой пару `ключ=значение`. Есть обязательные параметры, которые зависят от типа взаимодействия, и дополнительные параметры, расширяющие возможности аналитики переданных данных. Все значения параметров должны быть URL-кодированы и закодированы в формате UTF-8 (см. [пример передачи просмотра](measurement-upload.md)).

## [](ru/data-import/measurement-upload#parameters)Поддерживаемые параметры

**Параметр** |  **Описание** |  **Комментарий**  
---|---|---  
`tid` |  Номер счетчика |  Обязательный  
`cid` |  Идентификатор клиента `ClientID` |  Обязательный  
`t` |  Тип взаимодействия. Возможные значения:

  * `pageview` — просмотр страницы
  * `event` — Javascript-событие, ecommerce-события

|  Обязательный  
`dr` |  Реферер |  Обязательный для события `pageview`  
`dl` |  Url страницы |  Обязательный для события `pageview`, а также для любого события `event`, если включена опция «Принимать данные только с указанных адресов»  
`dt` |  Заголовок страницы |  Обязательный для события `pageview`  
`ea` |  Цели |  Обязательный для события `event`  
`params` |  Параметры визита |  Отправляются вместе с событиями `pageview` или `event`. На передачу действуют [ограничения](https://yandex.../support/metrica/general/limits.md)  
`ti` |  Ecom транзакция |  Обязательный для события `event` и `pa=purchase`  
`tr` |  Ecom доход транзакции |  Обязательный для события `event` и `pa=purchase`  
`tcc` |  Ecom купон транзации |  Обязательный для события `event` и `pa=purchase`  
`et` |  Время события в Timestamp |  Если не передан — будет использовано время отправки данных. Допускается не более 12 часов назад от текущего времени.  
`pa` |  Ecom действие с товаром (расширенный ecom). Возможные значения:

  * `detail` — просмотр информации
  * `add` — добавление в корзину
  * `remove` — удаление из корзины
  * `purchase` — покупка

|  Обязательный для события `event`  
`pr<productIndex>id` |  Ecom код товара |  Обязательный для события `event` и `pa!=null`. В `productIndex` указывать порядковый номер товара в списке  
`pr<productIndex>nm` |  Ecom название товара |  Обязательный для события `event` и `pa!=null`. В `productIndex` указывать порядковый номер товара в списке  
`pr<productIndex>br` |  Ecom бренд товара |  Обязательный для события `event` и `pa!=null`. В `productIndex` указывать порядковый номер товара в списке  
`pr<productIndex>ca` |  Ecom категория товара |  Обязательный для события `event` и `pa!=null`. В `productIndex` указывать порядковый номер товара в списке  
`pr<productIndex>pr` |  Ecom цена товара |  Обязательный для события `event` и `pa!=null`. В `productIndex` указывать порядковый номер товара в списке  
`pr<productIndex>qt` |  Ecom количество единиц товара |  Обязательный для события `event` и `pa!=null`. В `productIndex` указывать порядковый номер товара в списке  
`pr<productIndex>va` |  Ecom разновидность товара |  Обязательный для события `event` и `pa!=null`. В `productIndex` указывать порядковый номер товара в списке  
`pr<productIndex>cc` |  Ecom код купона товара |  Обязательный для события `event` и `pa!=null`. В `productIndex` указывать порядковый номер товара в списке  
`pr<productIndex>ps` |  Ecom позиция товара |  Обязательный для события `event` и `pa!=null`. В `productIndex` указывать порядковый номер товара в списке  
`sr` |  Размер окна |  Формат для значения параметра: `1440x900x30`  
`cu` |  Валюта |  Поддерживается для целей с ценностью и для ecom-событий  
`ev` |  Ценность цели |  Поддерживается при передаче целей  
`ms` |  Секретный токен |  Генерируется при включении опции Measurement Protocol  
  
## [](ru/data-import/measurement-upload#examples)Примеры передачи данных

#### [](ru/data-import/measurement-upload#otpravka-prosmotra)Отправка просмотра
    
    
    https://mc.yandex.../collect/index.md
    

#### [](ru/data-import/measurement-upload#dostizhenie-js-celi-order-success)Достижение js-цели order-success
    
    
    https://mc.yandex.../collect/index.md
    

#### [](ru/data-import/measurement-upload#dostizhenie-js-celi-s-parametrami-vizita)Достижение js-цели с параметрами визита
    
    
    https://mc.yandex.../collect/index.md
    

#### [](ru/data-import/measurement-upload#prosmotr-kartochki-tovara-apple-iphone-stoimostyu-50000-s-sku-456)Просмотр карточки товара Apple iPhone стоимостью 50000 с SKU 456
    
    
    https://mc.yandex.../collect/index.md
    

#### [](ru/data-import/measurement-upload#dobavlenie-tovara-v-korzinu)Добавление товара в корзину
    
    
    https://mc.yandex.../collect/index.md
    

#### [](ru/data-import/measurement-upload#pokupka-tovara)Покупка товара
    
    
    https://mc.yandex.../collect/index.md
    

#### [](ru/data-import/measurement-upload#pokupka-neskolkih-tovarov)Покупка нескольких товаров
    
    
    https://mc.yandex.../collect/index.md
    

## [](ru/data-import/measurement-upload#nuance)Особенности

  * Через Measurement Protocol можно создать визит, либо дополнить существующий визит.
  * Для создания визита нужно обязательно указать `ClientID` пользователя.
  * Для формирования визита нужно передать как минимум один просмотр страницы (`t=pageview`) в начале визита.
  * Визиты формируются по тем же правилам и ограничениям, что и обычные визиты.
  * Данные можно отправить максимум на 12 часов назад от текущего времени. Если не отправлять параметр `et` — будет указано время отправки данных.
  * Обновить визит можно только в рамках тайм-аута визита, указанного в настройках счетчика, используя параметр `et` или отправляя данные без этого параметра в пределах тайм-аута визита. Если выйти за тайм-аут — начнется новый визит (после отправки `pageview`).

### Была ли статья полезна?

ДаНет

Предыдущая

[Управление опцией и токенами](manage-protocol.md)

Следующая

[Генерация дополнительных токенов](../management/openapi/measurement/generatetoken.md)