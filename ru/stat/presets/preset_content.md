# История изменений | API Яндекс Метрики

      * Посетители
Содержание

  1. [API отчетов](../index.md)
  2. [Шаблоны](../presets.md)
  3. Содержание

# Содержание

**Шаблон** |  **Отчет** |  **Группировки** |  **Метрики**  
---|---|---|---  
`content_entrance` |  Страницы входа |  `ym:s:startURLPathLevel1Hash`, `ym:s:startURLPathLevel2Hash`, `ym:s:startURLPathLevel3Hash`, `ym:s:startURLPathLevel4Hash`, `ym:s:startURLHash` |  `ym:s:visits`, `ym:s:users`, `ym:s:bounceRate`, `ym:s:pageDepth`, `ym:s:avgVisitDurationSeconds`, `ym:s:favoriteGoalsReaches`, `ym:s:favoriteGoalsConverted<currency>Revenue`, `ym:s:favoriteGoalsUserConversionRate`  
`content_exit` |  Страницы выхода |  `ym:s:endURLPathLevel1Hash`, `ym:s:endURLPathLevel2Hash`, `ym:s:endURLPathLevel3Hash`, `ym:s:endURLPathLevel4Hash`, `ym:s:endURLHash` |  `ym:s:visits`, `ym:s:users`, `ym:s:bounceRate`, `ym:s:pageDepth`, `ym:s:avgVisitDurationSeconds`, `ym:s:favoriteGoalsReaches`, `ym:s:favoriteGoalsConverted<currency>Revenue`, `ym:s:favoriteGoalsUserConversionRate`  
`turbo_pages` |  Турбо-страницы |  `ym:s:isTurboPage`, `ym:s:deviceCategory`, `ym:s:<attribution>TrafficSource`, `ym:s:<attribution>SourceEngine`, `ym:s:startURLPathLevel1Hash`, `ym:s:startURLPathLevel2Hash`, `ym:s:startURLHash` |  `ym:s:visits`, `ym:s:users`, `ym:s:bounceRate`, `ym:s:pageDepth`, `ym:s:avgVisitDurationSeconds`, `ym:s:favoriteGoalsReaches`, `ym:s:favoriteGoalsConverted<currency>Revenue`, `ym:s:favoriteGoalsUserConversionRate`  
`turbo_app` |  Турбо-сервис |  `ym:s:isTurboApp`, `ym:s:<attribution>TrafficSource`, `ym:s:<attribution>SourceEngine`, `ym:s:startURLPathLevel1Hash`, `ym:s:startURLPathLevel2Hash`, `ym:s:startURLHash` |  `ym:s:visits`, `ym:s:users`, `ym:s:bounceRate`, `ym:s:pageDepth`, `ym:s:avgVisitDurationSeconds`  
`content_visit_params` |  Параметры визитов |  `ym:s:paramsLevel1`, `ym:s:paramsLevel2`, `ym:s:paramsLevel3`, `ym:s:paramsLevel4`, `ym:s:paramsLevel5` |  `ym:s:visits`, `ym:s:users`, `ym:s:sumParams`, `ym:s:avgParams`, `ym:s:paramsNumber`, `ym:s:bounceRate`, `ym:s:pageDepth`, `ym:s:avgVisitDurationSeconds`  
`event_params` |  Параметры событий |  `ym:ep:eventURLHash`, `ym:ep:eventParamsLevel1`, `ym:ep:eventParamsLevel2`, `ym:ep:eventParamsLevel3`, `ym:ep:eventParamsLevel4`, `ym:ep:eventParamsLevel5` |  `ym:ep:eventsNumber`, `ym:ep:users`  
`goal_params` |  Параметры цели |  `ym:ep:goalReached`, `ym:ep:eventParamsLevel1`, `ym:ep:eventParamsLevel2`, `ym:ep:eventParamsLevel3`, `ym:ep:eventParamsLevel4`, `ym:ep:eventParamsLevel5` |  `ym:ep:eventsNumber`, `ym:ep:users`  
`popular` |  Популярное |  `ym:pv:URLPathLevel1Hash`, `ym:pv:URLPathLevel2Hash`, `ym:pv:URLPathLevel3Hash`, `ym:pv:URLPathLevel4Hash`, `ym:pv:URLHash` |  `ym:pv:pageviews`, `ym:pv:users`  
`titles` |  Заголовки страниц |  `ym:pv:title` |  `ym:pv:pageviews`, `ym:pv:users`  
`url_params` |  По параметрам URL |  `ym:pv:URLParamName`, `ym:pv:URLParamNameAndValue` |  `ym:pv:pageviews`, `ym:pv:users`  
`downloads` |  Загрузки файлов |  `ym:dl:URLPathLevel1Hash`, `ym:dl:URLPathLevel2Hash`, `ym:dl:URLPathLevel3Hash`, `ym:dl:URLPathLevel4Hash`, `ym:dl:URLHash` |  `ym:dl:downloads`, `ym:dl:users`  
`content_user_params` |  Параметры посетителей |  `ym:up:paramsLevel1`, `ym:up:paramsLevel2`, `ym:up:paramsLevel3`, `ym:up:paramsLevel4`, `ym:up:paramsLevel5` |  `ym:up:users`  
  
### Была ли статья полезна?

ДаНет

Предыдущая

[Лояльность](visitors/preset_loyalty.md)

Следующая

[Электронная коммерция](preset_ecommerce.md)