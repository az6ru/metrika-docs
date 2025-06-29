# Введение | API Яндекс Метрики

Request

## В этой статье:

  1. [API отчетов](../index.md)
  2. Справочник API отчетов
  3. Сравнение сегментов

# Сравнение сегментов

Позволяет сравнить два сегмента данных, указанные в запросе. Сегменты идентифицируются как сегмент А и сегмент B. Для каждого сегмента можно задать разные диапазоны дат и фильтры сегментации. Данные будут представлены в виде таблицы. Для каждой строки отчета возвращается два набора метрик: метрики сегмента А и метрики сегмента B. Посмотрите как используется данный запрос в [примере](../examples.md).

## [](ru/stat/openapi/comparison#request)Request

GET
    
    
    https://api-metrika.yandex.net/stat/v1/data/comparison
    

### [](ru/stat/openapi/comparison#query-parameters)Query parameters

**Name** |  **Description**  
---|---  
ids* |  **Type:** integer<int32>[] Идентификаторы счетчиков, через запятую.  
Example: `44147844,2215573`  
metrics* |  **Type:** string Список метрик, разделенных запятой. Лимит: 20 метрик в запросе.  
Example: `ym:s:pageviews`  
accuracy |  **Type:** string Размер выборки, используемой для отчета. Позволяет управлять [семплированием](../sampling.md) (количеством визитов, использованных при расчете итогового значения).  
callback |  **Type:** string Функция обратного вызова, которая обрабатывает ответ API.  
date1_a |  **Type:** string Дата начала периода выборки для сегмента A в формате YYYY-MM-DD. Также поддерживаются значения: `today`, `yesterday`, `ndaysAgo`.  
_Default:_ `6daysAgo`  
date1_b |  **Type:** string Дата начала периода выборки для сегмента B в формате YYYY-MM-DD. Также поддерживаются значения: `today`, `yesterday`, `ndaysAgo`.  
_Default:_ `6daysAgo`  
date2_a |  **Type:** string Дата окончания периода выборки для сегмента A в формате YYYY-MM-DD. Также поддерживаются значения: `today`, `yesterday`, `ndaysAgo`.  
_Default:_ `today`  
date2_b |  **Type:** string Дата окончания периода выборки для сегмента B в формате YYYY-MM-DD. Также поддерживаются значения: `today`, `yesterday`, `ndaysAgo`.  
_Default:_ `today`  
dimensions |  **Type:** string Список группировок, разделенных запятой. Лимит: 10 группировок в запросе.  
Example: `ym:s:trafficSource`  
direct_client_logins |  **Type:** string[] Логины клиентов Яндекс Директа, через запятую. Могут использоваться для формирования отчета [Директ-расходы](../direct-clicks.md).  
Example: `login1,login2`  
filters |  **Type:** string Фильтр [сегментации](../segmentation.md). Лимит: количество уникальных группировок и метрик — до 10, количество отдельных фильтров — до 20, длина строки в фильтре — до 10 000 символов; количество значений в одном условии фильтрации — 100.  
filters_a |  **Type:** string Фильтр сегментации для сегмента A.  
filters_b |  **Type:** string Фильтр сегментации для сегмента A.  
include_undefined |  **Type:** boolean Включает в ответ строки, для которых значения группировок не определены. Влияет только на первую группировку. По умолчанию выключено.  
lang |  **Type:** string Язык.  
limit |  **Type:** string Количество элементов на странице выдачи. Лимит: 100 000.  
_Default:_ `100` _Min value:_ `0`  
offset |  **Type:** string Индекс первой строки выборки, начиная с 1.  
_Default:_ `1` _Min value:_ `1`  
preset |  **Type:** string [Шаблон отчета](../presets.md).  
Example: `sources_summary`  
pretty |  **Type:** string Задает форматирование результата. Чтобы использовать форматирование, укажите значение `true`.  
_Default:_ `false`  
proposed_accuracy |  **Type:** boolean Если параметр выставлен в `true`, API имеет право автоматически увеличивать accuracy до рекомендованного значения.Когда идет запрос в маленькую таблицу с очень маленьким семплингом, параметр поможет получить осмысленные результаты.  
sort |  **Type:** string Список группировок и метрик, разделенных запятой, по которым осуществляется сортировка. По умолчанию сортировка производится по убыванию (указан знак `-` перед группировкой или метрикой). Чтобы отсортировать данные по возрастанию, удалите знак `-`.  
timezone |  **Type:** string Часовой пояс в формате ±hh:mm в диапазоне [-23:59; +23:59] (знак плюса нужно нужно передавать как `%2B`), в котором будут рассчитан период выборки запроса, а также связанные с датой и временем группировки. По умолчанию используется часовой пояс счетчика.  
Example: `-01:30, -01:00, -00:00, +00:00, +01:00, +01:30`  
  
## [](ru/stat/openapi/comparison#responses)Responses

## [](ru/stat/openapi/comparison#200-ok)200 OK

OK

### [](ru/stat/openapi/comparison#body)Body

application/json
    
    
    {
        "query": {
            "timezone": "string",
            "preset": "string",
            "dimensions": [
                "string"
            ],
            "metrics": [
                "string"
            ],
            "sort": [
                "string"
            ],
            "date1_a": "string",
            "date2_a": "string",
            "filters_a": "string",
            "date1_b": "string",
            "date2_b": "string",
            "filters_b": "string",
            "limit": 0,
            "offset": 0
        },
        "data": [
            {
                "dimensions": [
                    "string"
                ],
                "metrics": {
                    "a": [
                        0
                    ],
                    "b": [
                        0
                    ]
                }
            }
        ],
        "total_rows": 0,
        "total_rows_rounded": false,
        "sampled": false,
        "contains_sensitive_data": false,
        "sample_share": 0,
        "sample_size": 0,
        "sample_space": 0,
        "data_lag": 0,
        "totals": {
            "a": [
                0
            ],
            "b": [
                0
            ]
        }
    }
    

**Name** |  **Description**  
---|---  
contains_sensitive_data |  **Type:** boolean Признак возможного отсутствия [конфиденциальных данных](https://yandex.../../support/metrica/reports/report-general.md) в ответе. К ним относятся данные, которые рассчитываются алгоритмами Яндекса, например, социально-демографические (пол, возраст и др.), адреса страниц входа, поисковые фразы, информация о роботах. При значении `true` в ответе не отобразятся такие данные, если выборка составляет меньше 10 посетителей. Возможные значения: `true`, `false`.  
data |  **Type:** [ComparisonRowStaticAB](comparison.md)[] Строки ответа. Представляет собой массив, каждый элемент которого — одна строка результата.  
data_lag |  **Type:** integer<int32> Задержка в обновлении данных, в секундах.  
query |  **Type:** [ComparisonQueryAB](comparison.md) Исходный запрос. Содержит параметры запроса, включая развернутые параметры из шаблона и параметры для схемы параметризации атрибутов.  
sample_share |  **Type:** number<double> Доля данных, по которым осуществлялся расчет. Доступно значение в пределах от 0 до 1.  
sample_size |  **Type:** integer<int64> Количество строк в выборке данных.  
sample_space |  **Type:** integer<int64> Количество строк данных.  
sampled |  **Type:** boolean Признак семплирования. Показывает, был ли применен семплинг. Возможные значения: `true`, `false`.  
total_rows |  **Type:** integer<int64> Общее количество строк в ответе по всему множеству данных (с учетом фильтра).  
total_rows_rounded |  **Type:** boolean Признак того, что общее количество строк было округлено.  
totals |  **Type:** [ComparisonDataAB](comparison.md) Общие результаты для метрик по всему множеству данных (с учетом фильтра).  
  
### [](ru/stat/openapi/comparison#comparisonrowstaticab)ComparisonRowStaticAB

Строки ответа. Представляет собой массив, каждый элемент которого — одна строка результата.

**Name** |  **Description**  
---|---  
dimensions |  **Type:** string[] Массив значений группировок для данной строки. Каждое из значений группировки представляет собой объект. В нем обязательно присутствует поле `name` — текстовое значение, но могут присутствовать дополнительные поля, например идентификатор — `id`.  
  
metrics |  **Type:** [ComparisonDataAB](comparison.md) Общие результаты для метрик по всему множеству данных (с учетом фильтра).  
  
### [](ru/stat/openapi/comparison#comparisonqueryab)ComparisonQueryAB

Исходный запрос. Содержит параметры запроса, включая развернутые параметры из шаблона и параметры для схемы параметризации атрибутов.

**Name** |  **Description**  
---|---  
date1_a |  **Type:** string Дата начала периода выборки для сегмента A в формате YYYY-MM-DD.  
date1_b |  **Type:** string Дата начала периода выборки для сегмента B в формате YYYY-MM-DD.  
date2_a |  **Type:** string Дата окончания периода выборки для сегмента A в формате YYYY-MM-DD.  
date2_b |  **Type:** string Дата окончания периода выборки для сегмента B в формате YYYY-MM-DD.  
dimensions |  **Type:** string[] Массив группировок.  
filters_a |  **Type:** string Фильтр сегментации для сегмента A.  
filters_b |  **Type:** string Фильтр сегментации для сегмента B.  
limit |  **Type:** integer<int32> Количество элементов на странице выдачи.  
metrics |  **Type:** string[] Массив метрик.  
offset |  **Type:** integer<int32> Индекс первой строки выборки, начиная с 1.  
preset |  **Type:** string Пресет отчета.  
sort |  **Type:** string[] Массив сортировок.  
timezone |  **Type:** string Часовой пояс периода выборки в формате ±hh:mm.  
  
### [](ru/stat/openapi/comparison#comparisondataab)ComparisonDataAB

Общие результаты для метрик по всему множеству данных (с учетом фильтра).

**Name** |  **Description**  
---|---  
a |  **Type:** number<double>[] Массив значений метрик для сегмента A.  
b |  **Type:** number<double>[] Массив значений метрик для сегмента B.  
  
No longer supported, please use an alternative and newer version.

### Была ли статья полезна?

ДаНет

Предыдущая

[Drill down](drilldown.md)

Следующая

[Сравнение - drill down](comparison_drilldown.md)