# Получение информации об объектах, которые экспортируются в Yandex Cloud - Управление экспортом в Yandex Cloud | API Яндекс Метрики

Request

## В этой статье:

  1. [API управления](../../index.md)
  2. Справочник API управления
  3. Управление клиентами Директа
  4. Список доступных клиентов

# Список доступных клиентов

Возвращает данные о клиентах Яндекс Директа, к кампаниям которых есть доступ у владельца счетчика Метрики.

## [](ru/management/openapi/clients/getClients#request)Request

GET
    
    
    https://api-metrika.yandex.net/management/v1/clients
    

### [](ru/management/openapi/clients/getClients#query-parameters)Query parameters

**Name** |  **Description**  
---|---  
counters* |  **Type:** integer<int32>[] Идентификатор счетчика Яндекс Метрики. Вы можете указать несколько счетчиков через запятую.  
Example: `2215573`  
  
## [](ru/management/openapi/clients/getClients#responses)Responses

## [](ru/management/openapi/clients/getClients#200-ok)200 OK

OK

### [](ru/management/openapi/clients/getClients#body)Body

application/json
    
    
    {
        "clients": [
            {
                "id": 0,
                "name": "string",
                "chief_login": "string"
            }
        ]
    }
    

**Name** |  **Description**  
---|---  
clients |  **Type:** [Client](getclients.md)[] Список клиентов Яндекс Директа, к кампаниям которых есть доступ у владельца счетчика Метрики.  
  
### [](ru/management/openapi/clients/getClients#client)Client

Список клиентов Яндекс Директа, к кампаниям которых есть доступ у владельца счетчика Метрики.

**Name** |  **Description**  
---|---  
chief_login |  **Type:** string Логин главного представителя клиента в Директе. Может использоваться для формирования отчета [Директ-расходы](../../../stat/direct-clicks.md).  
id |  **Type:** integer<int32> Идентификатор клиента Директа.  
name |  **Type:** string Имя клиента, указанное в настройках Директа.  
  
No longer supported, please use an alternative and newer version.

### Была ли статья полезна?

ДаНет

Предыдущая

[Отменить привязку счетчика к метке](../counter-label/unsetcounterlabel.md)

Следующая

[Получение информации об объектах, которые экспортируются в Yandex Cloud](../cloud/getexportsbycounter.md)