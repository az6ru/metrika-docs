# История изменений | API Яндекс Метрики

Request

## В этой статье:

  1. [API управления](../../index.md)
  2. Справочник API управления
  3. Управление экспортом в Yandex Cloud
  4. Отключение экспорта на счетчике

# Отключение экспорта на счетчике

Отключает экспорт в Yandex Cloud на указанном счетчике. Метод доступен для владельца и редактора счетчика.

## [](ru/management/openapi/cloud/removeCounter#request)Request

DELETE
    
    
    https://api-metrika.yandex.net/export/v1/cloud/{ceId}/counter/{counterId}
    

### [](ru/management/openapi/cloud/removeCounter#path-parameters)Path parameters

**Name** |  **Description**  
---|---  
ceId* |  **Type:** integer<int32> Идентификатор экспорта в Yandex Cloud. Идентификатор можно получить с помощью операции [Получение информации об объектах, которые экспортируются в Yandex Cloud](../../../management-src/upravlenie-eksportom-v-yandex-cloud/getexportsbycounter.md).  
Example: `221`  
counterId* |  **Type:** integer<int32> Идентификатор счетчика Метрики.  
Example: `2215573`  
  
## [](ru/management/openapi/cloud/removeCounter#responses)Responses

## [](ru/management/openapi/cloud/removeCounter#200-ok)200 OK

OK

### [](ru/management/openapi/cloud/removeCounter#body)Body

application/json
    
    
    {
        "success": true
    }
    

**Name** |  **Description**  
---|---  
success |  **Type:** boolean Результат выполнения операции. _Default:_ `true`  
  
No longer supported, please use an alternative and newer version.

### Была ли статья полезна?

ДаНет

Предыдущая

[Получение информации об объектах, которые экспортируются в Yandex Cloud](getexportsbycounter.md)

Следующая

[Введение](../../../data-import/index.md)