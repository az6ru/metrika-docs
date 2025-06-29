# Примеры | API Яндекс Метрики

Подробно о direct_client_logins

## В этой статье:

  1. [API отчетов](index.md)
  2. [Примеры](examples.md)
  3. Директ-расходы

# Директ-расходы

API Яндекс.Метрики позволяет формировать [отчет с данными о количестве и стоимости кликов](https://yandex.../support/metrika/sources/direct-clicks.md) по объявлениям Директа. Для формирования отчета необходимо иметь доступ к кампаниям Директа, информацию о которых вы хотите получить. В запросе обязательно указывается параметр [direct_client_logins](direct-clicks.md) и используется определенный набор [группировок](attributes/advertising/direct_advertising.md) и [метрик](metrics/advertising/basic.md).

Вы можете дополнять отчет другими сведениями с помощью соответствующих группировок и метрик (например, отказы, глубина просмотра). Также можно использовать дополнительные возможности Метрики (например, сегментацию, семплирование).

## [](ru/stat/direct-clicks#direct-client)Подробно о direct_client_logins

Это логин главного представителя клиента Яндекс.Директа, к кампаниям которого есть доступ у владельца счетчика Метрики.

Получить список логинов, доступных для используемого счетчика Метрики (`ids`), можно с помощью [специального запроса](../management/openapi/clients/getclients.md).

При получении данных для отчета в запросе можно указать несколько логинов, если это необходимо — через запятую (`direct_client_logins=XXXXXX,YYYYYY,ZZZZZZ`).

## [](ru/stat/direct-clicks#primer-zaprosa)Пример запроса
    
    
    curl -H "Authorization: OAuth y0_XXX...XXX" "https://api-metrika.yandex.net/stat/v1/data?date1=2015-11-08&date2=2015-12-09&dimensions=ym%3Aad%3AdirectOrder&ids=2138128&direct_client_logins=wildberries1%2COzon1112006&metrics=ym%3Aad%3Avisits"
    

## [](ru/stat/direct-clicks#uznajte-bolshe)Узнайте больше

### Была ли статья полезна?

ДаНет

Предыдущая

[Примеры](examples.md)

Следующая

[Список группировок и метрик](attrandmetr/dim_all.md)