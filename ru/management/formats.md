# Введение | API Яндекс Метрики

Формат входных данных

## В этой статье:

  1. [API управления](index.md)
  2. Форматы входных данных и результата

# Форматы входных данных и результата

## [](ru/management/formats#input)Формат входных данных

Входные структуры данных POST- и PUT-методов передаются в теле запроса. Входные структуры совпадают с выходными структурами GET-методов соответствующих ресурсов.

Примечание

Чтобы корректно сформировать входную структуру для POST- или PUT-метода, вызовите GET-метод для уже существующего ресурса. Скопируйте полученную структуру и задайте нужные значения полей.

POST- и PUT-методы API принимают входные данные в формате JSON.

Формат входных данных указывается в HTTP-заголовке `Content-Type`.

Возможные значения заголовка: `application/x-yametrika+json` или `application/json`.

## [](ru/management/formats#result)Формат результата

API управления возвращает ответы в кодировке UTF-8. Ответы имеют формат JSON.

Например, в результате выполнения следующего запроса будут получены данные о счетчике:
    
    
    GET https://api-metrika.yandex.net/management/v1/counter/<counter_id>
    

Пример:
    
    
    POST /management/v1/counters HTTP/1.1
    Host: api-metrika.yandex.net
    Authorization: OAuth <access_token>
    Content-Type: application/x-yametrika+json
    Content-Length: 127
    
    {
         "counter" : {
             "site" : "www.example.com",
             "name" : "Наименование счетчика",
        }
    }
    

Для удобства отладки результат может отображаться в отформатированном виде. Для этого в запросе любого типа передайте параметр `pretty` со значением равным `1`:
    
    
    GET https://api-metrika.yandex.net/management/v1/counter/<counter_id>?pretty=1
    PUT https://api-metrika.yandex.net/management/v1/counter/<counter_id>?pretty=1
    

При успешном выполнении DELETE-методов API возвращает HTTP-статус с кодом `200`. Если HTTP-статус содержит другой код, удаление не выполнено.

### Была ли статья полезна?

ДаНет

Предыдущая

[Введение](index.md)

Следующая

[Информация о метке](openapi/label/getlabel.md)