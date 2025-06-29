# Создание цели - Управление целями | API Яндекс Метрики

Request

## В этой статье:

  1. [API управления](../../index.md)
  2. Справочник API управления
  3. Управление целями
  4. Список мессенджеров

# Список мессенджеров

Возвращает список мессенджеров, переход в которые можно отслеживать с помощью цели типа **Переход в мессенджер**.

## [](ru/management/openapi/goal/getMessengers#request)Request

GET
    
    
    https://api-metrika.yandex.net/management/v1/messengers
    

## [](ru/management/openapi/goal/getMessengers#responses)Responses

## [](ru/management/openapi/goal/getMessengers#200-ok)200 OK

OK

### [](ru/management/openapi/goal/getMessengers#body)Body

application/json
    
    
    {
        "messengers": [
            {}
        ]
    }
    

**Name** |  **Description**  
---|---  
messengers |  **Type:** [Messenger](getmessengers.md)[] Название мессенджера. Например, telegram, whatsapp, facebook, vk, skype.  
  
### [](ru/management/openapi/goal/getMessengers#messenger)Messenger

Название мессенджера. Например, telegram, whatsapp, facebook, vk, skype.

No longer supported, please use an alternative and newer version.

### Была ли статья полезна?

ДаНет

Предыдущая

[Список социальных сетей](getsocialnetworks.md)

Следующая

[Примеры создания целей](../../addgoal-example.md)