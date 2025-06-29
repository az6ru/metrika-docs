# Целевые события на Яндексе | API Яндекс Метрики

Источники

  1. [API отчетов](../index.md)
  2. [Шаблоны](../presets.md)
  3. Источники

# Источники

**Шаблон** |  **Отчет** |  **Группировки** |  **Метрики**  
---|---|---|---  
`visits_by_client_user_id` |  Визиты по UserID посетителей |  `ym:s:userClientUserId` |  `ym:s:visits`, `ym:s:users`, `ym:s:bounceRate`, `ym:s:pageDepth`, `ym:s:avgVisitDurationSeconds`, `ym:s:favoriteGoalsReaches`, `ym:s:favoriteGoalsConverted<currency>Revenue`, `ym:s:favoriteGoalsUserConversionRate`  
`visits_by_user_param` |  Визиты по параметрам посетителей |  `ym:s:userParamsLevel1`, `ym:s:userParamsLevel2`, `ym:s:userParamsLevel3`, `ym:s:userParamsLevel4`, `ym:s:userParamsLevel5` |  `ym:s:visits`, `ym:s:users`, `ym:s:bounceRate`, `ym:s:pageDepth`, `ym:s:avgVisitDurationSeconds`, `ym:s:favoriteGoalsReaches`, `ym:s:favoriteGoalsConverted<currency>Revenue`, `ym:s:favoriteGoalsUserConversionRate`  
`search_engines` |  Поисковые системы |  `ym:s:<attribution>SearchEngineRoot`, `ym:s:<attribution>SearchEngine`, `ym:s:<attribution>SearchPhrase` |  `ym:s:visits`, `ym:s:users`, `ym:s:bounceRate`, `ym:s:pageDepth`, `ym:s:avgVisitDurationSeconds`, `ym:s:favoriteGoalsReaches`, `ym:s:favoriteGoalsConverted<currency>Revenue`, `ym:s:favoriteGoalsUserConversionRate`  
`sources_search_phrases` |  Поисковые запросы |  `ym:s:<attribution>SearchPhrase`, `ym:s:<attribution>SearchEngineRoot` |  `ym:s:visits`, `ym:s:users`, `ym:s:bounceRate`, `ym:s:pageDepth`, `ym:s:avgVisitDurationSeconds`, `ym:s:favoriteGoalsReaches`, `ym:s:favoriteGoalsConverted<currency>Revenue`, `ym:s:favoriteGoalsUserConversionRate`  
`sources_sites` |  Сайты |  `ym:s:externalRefererPathLevel1Hash`, `ym:s:externalRefererPathLevel2Hash`, `ym:s:externalRefererPathLevel3Hash`, `ym:s:externalRefererPathLevel4Hash`, `ym:s:externalRefererHash` |  `ym:s:visits`, `ym:s:users`, `ym:s:bounceRate`, `ym:s:pageDepth`, `ym:s:avgVisitDurationSeconds`, `ym:s:favoriteGoalsReaches`, `ym:s:favoriteGoalsConverted<currency>Revenue`, `ym:s:favoriteGoalsUserConversionRate`  
`sources_social` |  Социальные сети |  `ym:s:<attribution>SocialNetwork`, `ym:s:<attribution>SocialNetworkProfile` |  `ym:s:visits`, `ym:s:users`, `ym:s:bounceRate`, `ym:s:pageDepth`, `ym:s:avgVisitDurationSeconds`, `ym:s:favoriteGoalsReaches`, `ym:s:favoriteGoalsConverted<currency>Revenue`, `ym:s:favoriteGoalsUserConversionRate`  
`sources_messenger` |  Мессенджеры |  `ym:s:<attribution>Messenger` |  `ym:s:visits`, `ym:s:users`, `ym:s:bounceRate`, `ym:s:pageDepth`, `ym:s:avgVisitDurationSeconds`, `ym:s:favoriteGoalsReaches`, `ym:s:favoriteGoalsConverted<currency>Revenue`, `ym:s:favoriteGoalsUserConversionRate`  
`sources_recommend` |  Рекомендательные системы |  `ym:s:<attribution>RecommendationSystem` |  `ym:s:visits`, `ym:s:users`, `ym:s:bounceRate`, `ym:s:pageDepth`, `ym:s:avgVisitDurationSeconds`, `ym:s:favoriteGoalsReaches`, `ym:s:favoriteGoalsConverted<currency>Revenue`, `ym:s:favoriteGoalsUserConversionRate`  
`sources_summary` |  Источники, сводка |  `ym:s:<attribution>TrafficSource`, `ym:s:<attribution>SourceEngine`, `ym:s:<attribution>DirectPlatformType` |  `ym:s:visits`, `ym:s:users`, `ym:s:bounceRate`, `ym:s:pageDepth`, `ym:s:avgVisitDurationSeconds`, `ym:s:favoriteGoalsReaches`, `ym:s:favoriteGoalsConverted<currency>Revenue`, `ym:s:favoriteGoalsUserConversionRate`  
`tags_from` |  Метки From |  `ym:s:<attribution>From` |  `ym:s:visits`, `ym:s:users`, `ym:s:bounceRate`, `ym:s:pageDepth`, `ym:s:avgVisitDurationSeconds`, `ym:s:favoriteGoalsReaches`, `ym:s:favoriteGoalsConverted<currency>Revenue`, `ym:s:favoriteGoalsUserConversionRate`  
`tags_gclid` |  Метка gcl |  `ym:s:<attribution>HasGCLID` |  `ym:s:visits`, `ym:s:users`, `ym:s:bounceRate`, `ym:s:pageDepth`, `ym:s:avgVisitDurationSeconds`  
`tags_openstat` |  Метки Openstat |  `ym:s:<attribution>OpenstatService`, `ym:s:<attribution>OpenstatCampaign`, `ym:s:<attribution>OpenstatAd`, `ym:s:<attribution>OpenstatSource` |  `ym:s:visits`, `ym:s:users`, `ym:s:bounceRate`, `ym:s:pageDepth`, `ym:s:avgVisitDurationSeconds`, `ym:s:favoriteGoalsReaches`, `ym:s:favoriteGoalsConverted<currency>Revenue`, `ym:s:favoriteGoalsUserConversionRate`  
`tags_u_t_m` |  Метки UTM |  `ym:s:<attribution>UTMSource`, `ym:s:<attribution>UTMMedium`, `ym:s:<attribution>UTMCampaign`, `ym:s:<attribution>UTMContent`, `ym:s:<attribution>UTMTerm` |  `ym:s:visits`, `ym:s:users`, `ym:s:bounceRate`, `ym:s:pageDepth`, `ym:s:avgVisitDurationSeconds`, `ym:s:favoriteGoalsReaches`, `ym:s:favoriteGoalsConverted<currency>Revenue`, `ym:s:favoriteGoalsUserConversionRate`  
`adv_engine` |  Рекламные системы |  `ym:s:<attribution>AdvEngine` |  `ym:s:visits`, `ym:s:users`, `ym:s:bounceRate`, `ym:s:pageDepth`, `ym:s:avgVisitDurationSeconds`, `ym:s:favoriteGoalsReaches`, `ym:s:favoriteGoalsConverted<currency>Revenue`, `ym:s:favoriteGoalsUserConversionRate`  
  
### Была ли статья полезна?

ДаНет

Предыдущая

[Посещаемость](preset_traffic.md)

Следующая

[Директ](preset_direct.md)