# История изменений | API Яндекс Метрики

Шаблоны

## В этой статье:

  1. [API отчетов](index.md)
  2. Примеры

# Примеры

Ниже приведены примеры, которые позволяют решать часто встречающиеся задачи.

В данных запросах не указаны параметры `date1` и `date2` (даты начала и конца отчетного периода). По умолчанию количество дней отчетного периода равно 7 (включая текущий день).

В качестве параметра `id` представлен демо-счетчик.

Для формирования запросов используется метод [/stat/v1/data](openapi/data.md).

Примечание

Язык запроса (параметр `lang`) влияет на значения фильтров. Указывайте параметр `lang=ru`, когда используете русские имена, например, `ym:s:regionCityName=='Санкт-Петербург'`.

## [](ru/stat/examples#preset)Шаблоны

### [](ru/stat/examples#ex1)Отчет «Источники, сводка»

`preset=sources_summary`
    
    
    https://api-metrika.yandex.net/stat/v1/data?preset=sources_summary&id=44147844
    

### [](ru/stat/examples#ex2)Отчет «Источники, сводка». Посетители из Санкт-Петербурга

`preset=sources_summary`

`filters=ym:s:regionCityName=='Санкт-Петербург'`

Данные отчета сегментированы с помощью параметра `filters=ym:s:regionCityName=='Санкт-Петербург'`.
    
    
    https://api-metrika.yandex.net/stat/v1/data?preset=sources_summary&filters=ym:s:regionCityName=='Санкт-Петербург'&id=44147844&lang=ru
    

### [](ru/stat/examples#ex3)Отчет «Поисковые фразы»

`preset=sources_search_phrases`
    
    
    https://api-metrika.yandex.net/stat/v1/data?preset=sources_search_phrases&id=44147844
    

### [](ru/stat/examples#ex4)Отчет «Браузеры»

`preset=tech_platforms`

`dimensions=ym:s:browser`

Данный шаблон помогает формировать отчет по браузеру, который используют посетители сайта, без учета версии браузера.
    
    
    https://api-metrika.yandex.net/stat/v1/data?preset=tech_platforms&dimensions=ym:s:browser&id=44147844
    

где параметр `dimensions=ym:s:browser` задает группировку в шаблоне, по которой группируются полученные данные.

### [](ru/stat/examples#ex5)Контентная аналитика

**Источники переходов**
    

Шаблон помогает построить отчет по источникам, из которых посетители переходили на материалы сайта.

`preset=publishers_sources`
    
    
    https://api-metrika.yandex.net/stat/v1/data?preset=publishers_sources&id=44147844&date1=today&date2=today
    

**Рубрики**
    

Используйте этот шаблон, чтобы получить отчет с общей статистикой по рубрикам.

`preset=publishers_rubrics`
    
    
    https://api-metrika.yandex.net/stat/v1/data?preset=publishers_rubrics&id=44147844&date1=today&date2=today
    

**Авторы**
    

Используйте этот шаблон, чтобы получить стандартный отчет со статистикой по авторам статей вашего сайта.

`preset=publishers_authors`
    
    
    https://api-metrika.yandex.net/stat/v1/data?preset=publishers_authors&id=44147844&date1=today&date2=today
    

**Тематики**
    

Используйте этот шаблон, чтобы получить стандартный отчет по тематикам статей сайта.

`publishers_thematics`
    
    
    https://api-metrika.yandex.net/stat/v1/data?publishers_thematics&id=44147844&date1=today&date2=today
    

## [](ru/stat/examples#segment)Сегментация

### [](ru/stat/examples#ex0)Типы источников трафика

`dimensions=ym:s:lastTrafficSource`

`metrics=ym:s:visits,ym:s:users`

`filters=ym:s:lastTrafficSource=.('organic','direct','referral')`
    
    
    https://api-metrika.yandex.net/stat/v1/data?dimensions=ym:s:lastTrafficSource&metrics=ym:s:visits,ym:s:users&filters=ym:s:lastTrafficSource=.('organic','direct','referral')&id=44147844&lang=ru
    

### [](ru/stat/examples#visits)Количество визитов и посетителей из поисковых систем

`dimensions=ym:s:searchEngine`

`metrics=ym:s:visits,ym:s:users`

`filters=ym:s:trafficSource=='organic'`
    
    
    https://api-metrika.yandex.net/stat/v1/data?dimensions=ym:s:searchEngine&metrics=ym:s:visits,ym:s:users&filters=ym:s:trafficSource=='organic'&id=44147844
    

### [](ru/stat/examples#robots)Количество визитов и посетителей из поисковых систем без визитов роботов

Яндекс Метрика определяет роботов по поведенческим факторам и другим техническим сигналам. Фильтрация роботов в отчетах Метрики помогает получать точные значения метрик. Например, показателя отказов, времени на сайте и глубины просмотра. Подробно об этом см. в [Справке](https://yandex.../support/metrica/general/robots.md).

`dimensions=ym:s:searchEngine`

`metrics=ym:s:visits,ym:s:users`

`filters=ym:s:trafficSource=='organic' AND ym:s:isRobot=='No'`
    
    
    https://api-metrika.yandex.net/stat/v1/data?dimensions=ym:s:searchEngine&metrics=ym:s:visits,ym:s:users&filters=ym:s:trafficSource=='organic' AND ym:s:isRobot=='No'&id=44147844
    

### [](ru/stat/examples#search)Количество визитов и новых посетителей из поисковых систем

`dimensions=ym:s:searchEngine`

`metrics=ym:s:visits,ym:s:users`

`filters=ym:s:trafficSource=='organic' AND ym:s:isNewUser=='Yes'`
    
    
    https://api-metrika.yandex.net/stat/v1/data?dimensions=ym:s:searchEngine&metrics=ym:s:visits,ym:s:users&filters=ym:s:trafficSource=='organic' AND ym:s:isNewUser=='Yes'&id=44147844
    

### [](ru/stat/examples#segment)Количество визитов и посетителей с учетом заданного региона

`metrics=ym:s:visits,ym:s:users`

`filters=ym:s:regionCityName=.('Москва','Санкт-Петербург')`
    
    
    https://api-metrika.yandex.net/stat/v1/data?metrics=ym:s:visits,ym:s:users&filters=ym:s:regionCityName=.('Москва','Санкт-Петербург')&id=44147844&lang=ru
    
    
    
    https://api-metrika.yandex.net/stat/v1/data?metrics=ym:s:visits,ym:s:users&filters=ym:s:regionCityName=.('Moscow','Saint Petersburg')&id=44147844
    

### [](ru/stat/examples#page-view)Количество визитов с глубиной просмотра больше 5 страниц

`metrics=ym:s:visits`

`filters=ym:s:pageViews>5`
    
    
    https://api-metrika.yandex.net/stat/v1/data?metrics=ym:s:visits&filters=ym:s:pageViews>5&id=44147844
    

## [](ru/stat/examples#dim-metrics)Группировки и метрики

### [](ru/stat/examples#dim-metrics)Количество визитов

`metrics=ym:s:visits`
    
    
    https://api-metrika.yandex.net/stat/v1/data?metrics=ym:s:visits&id=44147844
    

### [](ru/stat/examples#conv)Количество пользователей и конверсия по указанной цели

В данном примере используется параметризация метрики `ym:s:goal<goal_id>conversionRate` идентификатором цели:

`metrics=ym:s:users,ym:s:goal<goal_id>conversionRate`

`dimensions=ym:s:trafficSource`

`goal_id=<идентификатор цели>`

В отчете будет получено количество пользователей, достигших указанную цель. Данные будут сгруппированы по источнику трафика.
    
    
    https://api-metrika.yandex.net/stat/v1/data?dimensions=ym:s:trafficSource&metrics=ym:s:users,ym:s:goal%3Cgoal_id%3EconversionRate&goal_id=30606879&id=44147844
    

### [](ru/stat/examples#conv-mult)Конверсия по нескольким целям

В данном примере используется параметризация метрики `ym:s:goal<goal_id>conversionRate` идентификатором цели в теле выражения.
    
    
    metrics=ym:s:users,ym:s:goal<идентификатор первой цели>conversionRate,ym:s:goal<идентификатор второй цели>conversionRate
    
    
    
    https://api-metrika.yandex.net/stat/v1/data?metrics=ym:s:users,ym:s:goal30606879conversionRate,ym:s:goal30606884conversionRate&id=44147844
    

### [](ru/stat/examples#dim-metrics)Отчет по сегментам эксперимента в Яндекс Директе

В данном примере используется параметризация группировки `ym:s:experimentAB<experiment_ab>`.

`metrics=ym:s:bounceRate`

`dimensions=ym:s:experimentAB123`, где 123 — это идентификатор эксперимента.
    
    
    https://api-metrika.yandex.net/stat/v1/data?id=44147844;&metrics=ym:s:bounceRate&dimensions=ym:s:experimentAB123
    

### [](ru/stat/examples#content)Контентная аналитика. Отчет по материалам

Отчет по количеству просмотров материалов сайта. Данные сгруппированы по материалу.

`dimensions=ym:s:publisherArticle`

`metrics=ym:s:publisherviews`

`filters=(ym:s:publisherArticle!n)`

`sort=-ym:s:publisherviews`
    
    
    https://api-metrika.yandex.net/stat/v1/data?ids=44147844&date1=2019-10-01&date2=2019-10-01&dimensions=ym:s:publisherArticle&metrics=ym:s:publisherviews&filters=(ym:s:publisherArticle!n)&sort=-ym:s:publisherviews
    

## [](ru/stat/examples#query)Отображение данных по времени

Для получения данных используется метод [/stat/v1/data/bytime](openapi/bytime.md).

Ниже приведены примеры получения данных за определенный период времени. Эти данные могут быть сгруппированы. Чтобы указать тип или количество группировок (`dimensions`), используйте параметры `row_ids` или `top_keys`. Если параметр `row_ids` не указан, автоматически используется параметр `top_keys`. По умолчанию он принимает значение 7 (максимальное — 30).

Подробно о параметрах

Например, данные сгруппированы по одному измерению — длина этого подмассива равна 1.
        
        ...?row_ids=[["Россия"]]&...&dimensions=ym:s:regionCountryName,ym:s:regionAreaName,ym:s:regionCityName&...
        

Примечание

Если подмассив содержит значения измерений одной группы (например, [География](attributes/visitsaudience_/geo.md)), то данные будут сгруппированы по последнему указанному измерению.
        
        ...?row_ids=[["Россия","Саратовская область","Саратов"]]&...&dimensions=ym:s:regionCountryName,ym:s:regionAreaName,ym:s:regionCityName&...
        

Чтобы использовать несколько подмассивов, перечислите их через запятую:
        
        ...?row_ids=[["Россия"],["Россия","Саратовская область"],["Россия","Саратовская область","Саратов"]]&...&dimensions=ym:s:regionCountryName,ym:s:regionAreaName,ym:s:regionCityName&...
        

  * Параметр `top_keys` выбирает первые значения из набора данных первого измерения, указанного в запросе. Вы можете задать количество этих значений (максимум 30). Сортировка данных в ответе API производится по убыванию первого значения параметра`metrics`.
        
        ...?top_keys=3&...&dimensions=ym:s:regionCountry,ym:s:regionArea,ym:s:regionCity&group=day&ids=44147844&metrics=ym:s:visits
        

### [](ru/stat/examples#query)Отчет «Источники, сводка»

В примере будут получены данные, сгруппированные по типу источника трафика.

Пример без указания параметра `row_ids`, используется параметр `top_keys` по умолчанию:
    
    
    https://api-metrika.yandex.net/stat/v1/data/bytime?date1=2018-01-01&date2=2018-01-14&group=day&dimensions=ym:s:<attribution>TrafficSource&attribution=last&ids=44147844&metrics=ym:s:visits
    

Пример с указанием значения параметра `top_keys`:
    
    
    https://api-metrika.yandex.net/stat/v1/data/bytime?top_keys=3&date1=2018-01-01&date2=2018-01-14&group=day&dimensions=ym:s:<attribution>TrafficSource&attribution=last&ids=44147844&metrics=ym:s:visits
    

Ниже представлены примеры отчетов с указанием значений измерений группы [Источники](attributes/visits/source.md).

Источники трафика за день:
    
    
    https://api-metrika.yandex.net/stat/v1/data/bytime?row_ids=[["direct"],["organic","organic.yandex"],["social","social.ya"],["ad"]]&date1=2018-01-13&date2=2018-01-13&group=day&dimensions=ym:s:<attribution>TrafficSource,ym:s:<attribution>SourceEngine&attribution=last&ids=44147844&metrics=ym:s:visits
    

Источники трафика за две недели с группировкой по дням:
    
    
    https://api-metrika.yandex.net/stat/v1/data/bytime?row_ids=[["direct"],["organic","organic.yandex"],["social","social.ya"],["ad"]]&date1=2018-01-01&date2=2018-01-14&group=day&dimensions=ym:s:<attribution>TrafficSource,ym:s:<attribution>SourceEngine&attribution=last&ids=44147844&metrics=ym:s:visits
    

Источники трафика за две недели с группировкой по неделям. При этом данные группируются по календарным неделям:
    
    
    https://api-metrika.yandex.net/stat/v1/data/bytime?row_ids=[["direct"],["organic","organic.yandex"],["social","social.ya"],["ad"]]&date1=2018-01-01&date2=2018-01-14&group=week&dimensions=ym:s:<attribution>TrafficSource,ym:s:<attribution>SourceEngine&attribution=last&ids=44147844&metrics=ym:s:visits
    

### [](ru/stat/examples#query)Отчет **Посетители - География**

В этом примере будут получены данные о количестве посетителей, сгруппированные по географической принадлежности.

Пример без указания параметра `row_ids`, используется параметр `top_keys` по умолчанию:
    
    
    https://api-metrika.yandex.net/stat/v1/data/bytime?date1=2018-01-01&date2=2018-01-14&group=day&dimensions=ym:s:regionCountry,ym:s:regionArea,ym:s:regionCity&ids=44147844&metrics=ym%3As%3Avisits
    

Пример с указанием значения параметра `top_keys`:
    
    
    https://api-metrika.yandex.net/stat/v1/data/bytime?top_keys=3&date1=2018-01-01&date2=2018-01-14&group=day&dimensions=ym:s:regionCountry,ym:s:regionArea,ym:s:regionCity&ids=44147844&metrics=ym%3As%3Avisits
    

Ниже представлены примеры отчетов с указанием значений измерений группы [География](attributes/visitsaudience_/geo.md).

Количество визитов из России, Саратовской области и Саратова за две недели. Группировка производится по календарным неделям:
    
    
    https://api-metrika.yandex.net/stat/v1/data/bytime?row_ids=[["Россия"],["Россия","Саратовская%20область"],["Россия","Саратовская%20область","Саратов"]]&date1=2018-01-01&date2=2018-01-14&group=week&dimensions=ym:s:regionCountryName,ym:s:regionAreaName,ym:s:regionCityName&ids=44147844&metrics=ym%3As%3Avisits&lang=ru
    
    
    
    https://api-metrica.yandex.net/stat/v1/data/bytime?row_ids=[["Russia"],["Russia","Saratovskaya%region"],["Russia","Saratovskaya%20region","Saratov"]]&date1=2018-01-01&date2=2018-01-14&group=week&dimensions=ym:s:regionCountryName,ym:s:regionAreaName,ym:s:regionCityName&ids=44147844&metrics=ym%3As%3Avisits
    

Количество визитов из России, Москвы и Московской области, Санкт-Петербурга и Ленинградской области за две недели:
    
    
    https://api-metrika.yandex.net/stat/v1/data/bytime?row_ids=[["Россия"],["Россия","Москва%20и%20Московская область"],["Россия","Санкт-Петербург%20и%20Ленинградская%20область"]]&date1=2018-01-01&date2=2018-01-14&group=week&dimensions=ym:s:regionCountryName,ym:s:regionAreaName,ym:s:regionCityName&ids=44147844&metrics=ym%3As%3Avisits&lang=ru
    
    
    
    https://api-metrica.yandex.net/stat/v1/data/bytime?row_ids=[["Russia"],["Russia","Moscow%20и%Moscow region"],["Russia","Saint Peteresburg%20и%20Leningradskaya region"]]&date1=2018-01-01&date2=2018-01-14&group=week&dimensions=ym:s:regionCountryName,ym:s:regionAreaName,ym:s:regionCityName&ids=44147844&metrics=ym%3As%3Avisits
    

### [](ru/stat/examples#query)Отчет по операционным системам и браузерам

В этом примере будут получены данные о количестве посетителей, сгруппированные по типу операционной системы, которую они используют.

Пример без указания параметра `row_ids`, используется параметр `top_keys` по умолчанию:
    
    
    https://api-metrika.yandex.net/stat/v1/data/bytime?date1=2018-01-01&date2=2018-01-14&group=day&dimensions=ym:s:operatingSystemRootName,ym:s:browserName&ids=44147844&accuracy=medium&metrics=ym:s:visits
    

Пример с указанием значения параметра `top_keys`:
    
    
    https://api-metrika.yandex.net/stat/v1/data/bytime?top_keys=10&date1=2018-01-01&date2=2018-01-14&group=day&dimensions=ym:s:operatingSystemRootName,ym:s:browserName&ids=44147844&accuracy=medium&metrics=ym:s:visits
    

Ниже представлены примеры отчетов с указанием значений измерений групп [Операционные системы](attributes/visitstechnology_/os.md) и [Браузеры](attributes/visitstechnology_/browser.md).

Количество визитов пользователей ОС Windows, Яндекс Браузера и Internet Explorer. Данные сгруппированы по дням:
    
    
    https://api-metrika.yandex.net/stat/v1/data/bytime?row_ids=[["Windows"],["Windows","Яндекс.Браузер"],["Windows","MSIE"]]&date1=2018-01-01&date2=2018-01-14&group=day&dimensions=ym:s:operatingSystemRootName,ym:s:browserName&ids=44147844&accuracy=medium&metrics=ym:s:visits&lang=ru
    
    
    
    https://api-metrica.yandex.net/stat/v1/data/bytime?row_ids=[["Windows"],["Windows","Yandex.Browser"],["Windows","MSIE"]]&date1=2018-01-01&date2=2018-01-14&group=day&dimensions=ym:s:operatingSystemRootName,ym:s:browserName&ids=44147844&accuracy=medium&metrics=ym:s:visits
    

Данные сгруппированы по календарным неделям:
    
    
    https://api-metrika.yandex.net/stat/v1/data/bytime?row_ids=[["Windows"],["Windows","Яндекс.Браузер"],["Windows","MSIE"]]&date1=2018-01-01&date2=2018-01-14&group=week&dimensions=ym:s:operatingSystemRootName,ym:s:browserName&ids=44147844&accuracy=medium&metrics=ym:s:visits&lang=ru
    
    
    
    https://api-metrica.yandex.net/stat/v1/data/bytime?row_ids=[["Windows"],["Windows","Yandex.Browser"],["Windows","MSIE"]]&date1=2018-01-01&date2=2018-01-14&group=week&dimensions=ym:s:operatingSystemRootName,ym:s:browserName&ids=44147844&accuracy=medium&metrics=ym:s:visits
    

### [](ru/stat/examples#query)Количество просмотров по дням за последние 30 дней (график)

В примере будут получены данные для построения графика. Для получения данных используется метод `/stat/v1/data/bytime`.

`metrics=ym:s:hits`

`date1=30daysAgo`

`date2=today`

`group=day`
    
    
    https://api-metrika.yandex.net/stat/v1/data/bytime?metrics=ym:s:hits&date1=30daysAgo&date2=today&group=day&id=44147844
    

## [](ru/stat/examples#comparison)Сравнение сегментов

Для сравнения данных используется метод [/stat/v1/data/comparison](openapi/comparison.md).

### [](ru/stat/examples#comparison)Сравнение двух дней

В данном примере сравнивается количество пользователей. Данные сгруппированы по источнику трафика.

`metrics=ym:s:users`

`dimensions=ym:s:trafficSource`

`date1_a=today`

`date1_b=yesterday`
    
    
    https://api-metrika.yandex.net/stat/v1/data/comparison?metrics=ym:s:users&dimensions=ym:s:trafficSource&date1_a=today&date1_b=yesterday&id=44147844
    

### [](ru/stat/examples#comparison)Сравнение визитов с мобильных и не мобильных устройств

В данном примере сравниваются количество посетителей и доля отказов. Данные сгруппированы по источнику трафика.

`metrics=ym:s:users,ym:s:bounceRate`

`dimensions=ym:s:trafficSource`

`filters_a=ym:s:isMobile=='Yes'`

`filters_b=ym:s:isMobile=='No'`
    
    
    https://api-metrika.yandex.net/stat/v1/data/comparison?metrics=ym:s:users,ym:s:bounceRate&dimensions=ym:s:trafficSource&filters_a=ym:s:isMobile=='Yes'&filters_b=ym:s:isMobile=='No'
    

## [](ru/stat/examples#drilldown)Drilldown

Для получения данных используется метод [/stat/v1/data/drilldown](openapi/drilldown.md).

### [](ru/stat/examples#drilldown)Отчет «Операционные системы» в виде дерева

Чтобы сформировать отчет «Операционные системы» в виде дерева, необходимо:

  1. Отправить запрос для получения данных первого уровня, с помощью шаблона [tech_platforms](presets/preset_tech.md) (отчет **Операционные системы**).
         
         https://api-metrika.yandex.net/stat/v1/data/drilldown?preset=tech_platforms&id=44147844
         

  2. В полученном ответе параметр `expand` имеет значение `true`. Это означает, что данный узел можно развернуть на следующий уровень. В нашем случаем можно получить данные о версии операционной системы.
         
         ...
         {
             "dimension": {
                 "id": "100",
                 "name": "Windows"
             },
             "metrics": [
                 21779,
                 52056,
                 17.7786,
                 2.39019,
                 182.664
             ],
             "expand": true
         }
         ...
         

Чтобы это сделать, укажем в параметре `parent_id` путь уровня от корня. Так как элемент `id` параметра `dimension` имеет значение `"100"`, запрос будет выглядеть следующим образом:
         
         https://api-metrika.yandex.net/stat/v1/data/drilldown?preset=tech_platforms&id=44147844&parent_id=["100"]
         

В полученном ответе параметр `expand` имеет значение `false`. То есть развернуть данный узел дальше нельзя.
         
         ...
         {
             "dimension": {
                 "id": "33",
                 "name": "Windows 7 or 2008 Server"
             },
             "metrics": [
                 14948,
                 36300,
                 7214,
                 42842,
                 048
             ],
             "expand": false
         }
         ...
         

## [](ru/stat/examples#filtry-dostupa)Фильтры доступа

Позволяют ограничить передаваемую информацию с конкретного счетчика для пользователей. Подробнее в [статье](https://yandex.../support/metrica/general/access-filters.md).

Чтобы использовать фильтры доступа в запросе, сначала получите их идентификаторы для нужного счетчика:
    
    
    https://api-metrika.yandex.net/management/v1/counter/44147844/access_filters
    

Затем добавьте нужный идентификатор в запрос через параметр `access_filter_id`, например:
    
    
    https://api-metrika.yandex.net/stat/v1/data?ids=44147844&metrics=ym:s:visits&dimensions=ym:s:date&access_filter_id=12345
    

### Была ли статья полезна?

ДаНет

Предыдущая

[Семплирование](sampling.md)

Следующая

[Директ-расходы](direct-clicks.md)