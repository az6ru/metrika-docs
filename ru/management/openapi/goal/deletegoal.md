# Создание цели - Управление целями | API Яндекс Метрики

Request

## В этой статье:

  1. [API управления](../../index.md)
  2. Справочник API управления
  3. Управление целями
  4. Удаление цели

# Удаление цели

Удаляет цель счетчика.

## [](ru/management/openapi/goal/deleteGoal#request)Request

DELETE
    
    
    https://api-metrika.yandex.net/management/v1/counter/{counterId}/goal/{goalId}
    

### [](ru/management/openapi/goal/deleteGoal#path-parameters)Path parameters

**Name** |  **Description**  
---|---  
counterId* |  **Type:** integer<int32> Идентификатор счетчика, цель которого вы хотите удалить.  
goalId* |  **Type:** integer<int64> Идентификатор цели, которую вы хотите удалить.  
  
## [](ru/management/openapi/goal/deleteGoal#responses)Responses

## [](ru/management/openapi/goal/deleteGoal#200-ok)200 OK

OK

### [](ru/management/openapi/goal/deleteGoal#body)Body

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

[Изменение цели](editgoal.md)

Следующая

[Список целей](goals.md)