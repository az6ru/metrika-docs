# Описание ошибок в API | API Яндекс Метрики

Использование логина при работе с API

  1. Дополнительные сценарии
  2. Использование логина при работе с API

# Использование логина при работе с API

Примечание

Работа с аккаунтами, к которым у вас есть представительский доступ.

При работе с [API управления](../management/index.md) и [API отчетов](../stat/index.md) можно добавлять в запросы GET-параметр `ulogin`. Он помогает передавать логин пользователя, в том числе представителя владельца счетчика, от имени которого совершаются действия со счетчиком или другими данными.

Примеры:

**Посмотреть счетчики с представительским доступом**
    
    
    curl -X GET https://api-metrika.yandex.net/management/v1/counters?ulogin=<user_login> \
    -H 'Authorization: OAuth <your token>' 
    

**Создать счетчик от имени определенного пользователя**
    
    
    curl -X POST https://api-metrika.yandex.net/management/v1/counters?field=goals&ulogin=<user_login> \
    -H 'Authorization: OAuth <your token>' 
    -H 'accept: application/json'
    -H 'Content-Type: application/json'
    -d '
    {
        "counter" : {
        "name" : <string>,
        "site2" : {
            "site" : <string>
        },
        "gdpr_agreement_accepted" : <boolean>,
        "mirrors2" : [ {
            "site" : <string>
        }, ... ],
        "goals" : [ <goal>, ... ],
        "filters" : [ {
            "attr" : <filter_attribute>,
            "type" : <filter_type>,
            "value" : <string>,
            "action" : <filter_action>,
            "status" : <filter_status>,
            "with_subdomains" : <boolean>
        }, ... ],
        "operations" : [ {
            "action" : <operation_type>,
            "attr" : <operation_attribute>,
            "value" : <string>,
            "status" : <operation_status> 
        }, ... ],
        "grants" : [ {
            "user_login" : <string>,
            "user_uid" : <long>,
            "perm" : <rant_type>,
            "comment" : <string>,
            "partner_data_access" : <boolean>
        }, ... ],
        "labels" : [ {
            "id" :  <int> ,
            "name" :  <string>
        }, ... ],
        "webvisor" : {
            "urls" :  <string>,
            "arch_enabled" : <boolean>,
            "arch_type" : <webvisor_arch_type>,
            "load_player_type" : <webvisor_load_player_type>,
            "wv_version" : <integer>,
            "wv_forms" : <boolean>
        },
        "code_options" : {
            "async" : <boolean>,
            "informer" : {
                "enabled" : <boolean>,
                "type" :  <informer_type>,
                "size" : <integer>,
                "indicator" :  <informer_metric>,
                "color_start" :  <string>,
                "color_end" :  <string>,
                "color_text" : <integer>,
                "color_arrow" : <integer>
            },
            "visor" : <boolean>,
            "track_hash" : <boolean>,
            "xml_site" : <boolean>,
            "clickmap" : <boolean>,
            "in_one_line" : <boolean>,
            "ecommerce" : <boolean>,
            "alternative_cdn" : <boolean>
        },
        "create_time" : <date>,
        "time_zone_name" : <string>,
        "time_zone_offset" : <int>,
        "source" :  <counter_source>,
        "filter_robots" : <integer>,
        "visit_threshold" : <integer>,
        "offline_options" : {
            "offline_conversion_extended_threshold" : <boolean>,
            "offline_calls_extended_threshold" : <boolean>,
            "offline_visits_extended_threshold" : <boolean>
        },
        "publisher_options" : {
            "enabled" : <boolean>,
            "schema" : <publisher_schema> ,
            "schema_options" : [  <publisher_schema> , ... ]
        },
        "autogoals_enabled" : <boolean>,
        "counter_flags" : {
            "use_in_benchmarks" : <boolean>,
            "direct_allow_use_goals_without_access" : <boolean>,
            "collect_first_party_data" : <boolean>
        }
        }
    }'         
    

### Была ли статья полезна?

ДаНет

Предыдущая

[Быстрый старт](../intro/quick-start.md)

Следующая

[Описание ошибок в API](../intro/errors.md)