# Использование Measurement Protocol | API Яндекс Метрики

Request

## В этой статье:

  1. API импорта данных
  2. Measurement Protocol
  3. Генерация дополнительных токенов

# Генерация дополнительных токенов

Генерирует дополнительный токен для указанного счетчика. Максимальное количество активных токенов на счетчик — 5.

## [](ru/management/openapi/measurement/generateToken#request)Request

GET
    
    
    https://api-metrika.yandex.net/management/v1/counter/{counterId}/measurement/generate
    

### [](ru/management/openapi/measurement/generateToken#path-parameters)Path parameters

**Name** |  **Description**  
---|---  
counterId* |  **Type:** integer<int32> Идентификатор счетчика, для которого необходимо сгенерировать дополнительный токен.  
Example: `2215573`  
  
## [](ru/management/openapi/measurement/generateToken#responses)Responses

## [](ru/management/openapi/measurement/generateToken#200-ok)200 OK

Сгенерированный токен

### [](ru/management/openapi/measurement/generateToken#body)Body

application/json

**Type:** string

No longer supported, please use an alternative and newer version.

### Была ли статья полезна?

ДаНет

Предыдущая

[Загрузка данных](../../../data-import/measurement-upload.md)

Следующая

[Удаление токена](deletetoken.md)