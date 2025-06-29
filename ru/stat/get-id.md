# Введение | API Яндекс Метрики

Идентификатор региона

## В этой статье:

  1. [API отчетов](index.md)
  2. Идентификаторы объектов

# Идентификаторы объектов

Чтобы использовать в API группировки и фильтры, нужно знать идентификаторы конкретных значений. Например, чтобы сделать отбор по пользователям определенного региона, нужно знать идентификатор этого региона.

В общем случае чтобы получить идентификатор конкретного объекта, нужно сначала сделать общий запрос на получение списка всех объектов.

Ниже приведены примеры использования идентификаторов.

## [](ru/stat/get-id#region)Идентификатор региона

Вы хотите проанализировать, из каких поисковых систем приходят пользователи из России. Для этого нужно знать идентификатор региона.

Сначала выполните запрос на получение идентификаторов всех регионов.
    
    
    https://api-metrika.yandex.net/stat/v1/data/drilldown?ids=<counter_id>&dimensions=ym:s:regionCountry&metrics=ym:s:visits
    

В ответе найдите страну `RU`, ее `id` = `225`.

Ответ со списком стран и их идентификаторов
    
    
    "data": [
      {
        "dimension": {
          "icon_id": "225",
          "icon_type": "country",
          "iso_name": "RU",
          "id": "225",
          "name": "Russia"
        },
        "metrics": [
          13193
        ],
        "expand": false
      },
      {
        "dimension": {
          "icon_id": "149",
          "icon_type": "country",
          "iso_name": "BY",
          "id": "149",
          "name": "Belarus"
        },
        "metrics": [
          515
        ],
        "expand": false
      },
      {
        "dimension": {
          "icon_id": "118",
          "icon_type": "country",
          "iso_name": "NL",
          "id": "118",
          "name": "Netherlands"
        },
        "metrics": [
          435
        ],
        "expand": false
      },
      {
        "dimension": {
          "icon_id": "159",
          "icon_type": "country",
          "iso_name": "KZ",
          "id": "159",
          "name": "Kazakhstan"
        },
        "metrics": [
          374
        ],
        "expand": false
      },
      {
        "dimension": {
          "icon_id": "96",
          "icon_type": "country",
          "iso_name": "DE",
          "id": "96",
          "name": "Germany"
        },
        "metrics": [
          332
        ],
        "expand": false
      }
    ]  
    

Теперь вы можете выполнить целевой запрос на анализ источников поискового трафика пользователей из России, используя фильтр `filters=(ym:s:regionCountry IN('225'))`.
    
    
    https://api-metrika.yandex.net/stat/v1/data?ids=<counter_id>&metrics=ym:s:visits&dimensions=ym:s:<attribution>SourceEngine&filters=(ym:s:regionCountry IN('225'))
    

## [](ru/stat/get-id#source)Идентификатор источника

Вы хотите изучить трафик из поисковых систем. Для этого нужно знать идентификатор соответствующего источника.

Сначала выполните запрос на получение идентификаторов всех источников за интересующий вас период.
    
    
    https://api-metrika.yandex.net/stat/v1/data/drilldown?ids=<counter_id>&dimensions=ym:s:<attribution>TrafficSource,ym:s:<attribution>SourceEngine&metrics=ym:s:visits&date1=2025-01-01&date2=2025-01-31&attribution=lastsign
    

В ответе найдите источник `Search engine traffic`, его `id` = `organic`.

Ответ со списком источников трафика и их идентификаторов
    
    
    "data": [
      {
        "dimension": {
          "icon_id": "1",
          "icon_type": "traffic-source",
          "name": "Link traffic",
          "id": "referral"
        },
        "metrics": [
          7725
        ],
        "expand": true
      },
      {
        "dimension": {
          "icon_id": "2",
          "icon_type": "traffic-source",
          "name": "Search engine traffic",
          "id": "organic"
        },
        "metrics": [
          6192
        ],
        "expand": true
      },
      {
        "dimension": {
          "icon_id": "0",
          "icon_type": "traffic-source",
          "name": "Direct traffic",
          "id": "direct"
        },
        "metrics": [
          3685
        ],
        "expand": false
      },
      {
        "dimension": {
          "icon_id": "-1",
          "icon_type": "traffic-source",
          "name": "Internal traffic",
          "id": "internal"
        },
        "metrics": [
          705
        ],
        "expand": false
      },
      {
        "dimension": {
          "icon_id": "7",
          "icon_type": "traffic-source",
          "name": "Mailing traffic",
          "id": "email"
        },
        "metrics": [
          316
        ],
        "expand": false
      },
      {
        "dimension": {
          "icon_id": "10",
          "icon_type": "traffic-source",
          "name": "Messenger traffic",
          "id": "messenger"
        },
        "metrics": [
          67
        ],
        "expand": true
      },
      {
        "dimension": {
          "icon_id": "8",
          "icon_type": "traffic-source",
          "name": "Social network traffic",
          "id": "social"
        },
        "metrics": [
          43
        ],
        "expand": true
      },
      {
        "dimension": {
          "icon_id": "9",
          "icon_type": "traffic-source",
          "name": "Recommendation system traffic",
          "id": "recommend"
        },
        "metrics": [
          18
        ],
        "expand": true
      }
    ]
    

Теперь вы можете выполнить целевой запрос на получение данных по трафику из поисковых систем, используя нужный идентификатор `parent_id=["organic"]`:
    
    
    https://api-metrika.yandex.net/stat/v1/data/drilldown?ids=<counter_id>&dimensions=ym:s:<attribution>TrafficSource,ym:s:<attribution>SourceEngine&metrics=ym:s:visits&date1=2025-01-01&date2=2025-01-310&attribution=lastsign&parent_id=["organic"]
    

### Была ли статья полезна?

ДаНет

Предыдущая

[Локализация и расшифровка значений группировок](localize.md)

Следующая

[Семплирование](sampling.md)