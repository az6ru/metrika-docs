# Создание цели - Управление целями | API Яндекс Метрики

Request

## В этой статье:

  1. [API управления](../../index.md)
  2. Справочник API управления
  3. Управление целями
  4. Список социальных сетей

# Список социальных сетей

Возвращает список всех социальных сетей.

## [](ru/management/openapi/goal/getSocialNetworks#request)Request

GET
    
    
    https://api-metrika.yandex.net/management/v1/social_networks
    

## [](ru/management/openapi/goal/getSocialNetworks#responses)Responses

## [](ru/management/openapi/goal/getSocialNetworks#200-ok)200 OK

OK

### [](ru/management/openapi/goal/getSocialNetworks#body)Body

application/json
    
    
    {
        "social_networks": [
            {}
        ]
    }
    

**Name** |  **Description**  
---|---  
social_networks |  **Type:** [SocialNetwork](getsocialnetworks.md)[] Список социальных сетей.  
  
### [](ru/management/openapi/goal/getSocialNetworks#socialnetwork)SocialNetwork

Список социальных сетей.

No longer supported, please use an alternative and newer version.

### Была ли статья полезна?

ДаНет

Предыдущая

[Создание цели](addgoal.md)

Следующая

[Список мессенджеров](getmessengers.md)