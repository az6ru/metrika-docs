# Использование Measurement Protocol | API Яндекс Метрики

Включение опции через API

## В этой статье:

  1. [API импорта данных](index.md)
  2. Measurement Protocol
  3. Управление опцией и токенами

# Управление опцией и токенами

## [](ru/data-import/manage-protocol#enable-option)Включение опции через API
    
    
    curl -X PUT 'https://api-metrika.yandex.net/management/v1/counter/<counter_id>?field=counter_flags'
    -H 'accept: application/json'
    -H 'Authorization: OAuth <access_token>'
    -H 'Content-Type: application/json'
    -d '{
          "counter": {
            "counter_flags": {
              "measurement_enabled": true
            }
          }
        }'
    

## [](ru/data-import/manage-protocol#check-flag)Проверка включения флага

Чтобы проверить, включена ли фича, отправьте запрос:
    
    
    curl -X GET 'https://api-metrika.yandex.net/management/v1/counter/<counter_id>?field=counter_flags'
    -H 'Authorization: OAuth <access_token>'
    

Ответ будет содержать флаг включения (параметр `measurement_enabled`):
    
    
    {
      "counter": {
        // ...
        "counter_flags": {
          "counter_id": <counter_id>,
          "use_in_benchmarks": true,
          "direct_allow_use_goals_without_access": true,
          "incognito": "disabled",
          "collect_first_party_data": true,
          "news_enabled_by_user": true,
          "news_enabled_by_classifier": true,
          "measurement_enabled": true
        },
      //...
      }
    }
    

## [](ru/data-import/manage-protocol#get-tokens)Получение активных токенов

Примечание

В ответе на запрос вы увидите активные токены вне зависимости от статуса флага `measurement_enabled`.

**Запрос**
    
    
    curl -X GET 'https://api-metrika.yandex.net/management/v1/counter/{counter_id}?field=measurement_tokens'
    -H 'Authorization: OAuth <access_token>'
    

**Ответ**
    
    
    {
      "counter": {
        // ...
        "measurement_tokens": [
          "196aXXXX-ebe0-XddX-XxDD-bXXXX7XXXX50",
          "XXX25XX4-XxDD-XXXX-a000-XXXXe3a4XXXX",
          "52cDDd3c-XXXX-4cef-XxDD-1709bXXXXa5a",
          "XXXXb007-XxDD-4700-9002-XXXX0eae000b"
        ]
      // ...
      }
    }
    

## [](ru/data-import/manage-protocol#gen-tokens)Генерация дополнительных токенов

Дополнительные токены можно сгенерировать с помощью запроса:
    
    
    curl -X GET 'https://api-metrika.yandex.net/management/v1/counter/{counterId}/measurement/generate'
    -H 'Authorization: OAuth <access_token>'
    

В ответ вы получите новый токен:
    
    
    {
      "response": "XXXXb007-XxDD-4700-9002-XXXX0eae000b"
    }
    

Важно

Максимальное количество активных токенов на счетчик — 5. Если попробовать сгенерировать больше, вы получите ответ `400`:
    
    
    {
      "errors": [
        {
          "error_type": "invalid_parameter",
          "message": "the limit of active tokens for the following counters has been reached: [counter_id]"
        }
      ],
      "code": 400,
      "message": "the limit of active tokens for the following counters has been reached: [counter_id]"
    }
    

## [](ru/data-import/manage-protocol#delete-token)Удаление токена

Удалить токен можно с помощью запроса:
    
    
    curl -X POST 'https://api-metrika.yandex.net/management/v1/counter/{counterId}/measurement/delete?token={token}'
    -H 'Authorization: OAuth <access_token>'
    

Примечание

Все полученные токены необходимо указывать в параметре `ms` (Measurement Secret) во время [отправки данных](measurement-upload.md).

### Была ли статья полезна?

ДаНет

Предыдущая

[Использование Measurement Protocol](measurement-about.md)

Следующая

[Загрузка данных](measurement-upload.md)