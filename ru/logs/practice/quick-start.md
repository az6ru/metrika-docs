# Список запросов логов - Справочник API Logs | API Яндекс Метрики

Сценарий работы с Logs API

  1. [API Logs](../index.md)
  2. Сценарии работы
  3. Получение готовых логов

# Сценарий работы с Logs API

  1. Чтобы создать логи, выполните запрос [POST https://api-metrika.yandex.net/management/v1/counter/{counterId}/logrequests](../openapi/createlogrequest.md).

Вы можете оценить возможность выгрузки данных с помощью запроса [GET https://api-metrika.yandex.net/management/v1/counter/{counterId}/logrequests/evaluate](../openapi/evaluate.md), если не уверены, что его удастся выгрузить.

Ограничение

В одном запросе можно запрашивать данные за период не более 1 года. Подробнее см. раздел [Ограничения](../index.md).

  2. После успешного выполнения запроса на создание логов сохраните `request_id` и дождитесь подготовки лога. Узнать статус обработки лога можно с помощью запроса [GET https://api-metrika.yandex.net/management/v1/counter/{counterId}/logrequest/{requestId}](../openapi/getlogrequest.md).

  3. Лог со статусом `processed` готов к выгрузке. Для выгрузки используйте запрос [GET https://api-metrika.yandex.net/management/v1/counter/{counterId}/logrequest/{requestId}/part/{partNumber}/download](../openapi/download.md).

  4. После выгрузки очистите подготовленные для загрузки логи, чтобы освободить место для следующих запросов. Для этого выполните запрос [POST https://api-metrika.yandex.net/management/v1/counter/{counterId}/logrequest/{requestId}/clean](../openapi/clean.md).

Нагрузка на сервис в разное время может различаться, если вам не удалось выгрузить данные, попробуйте позже или в другое время суток. Все запросы выполняются по очереди — каждый новый запрос попадает в конец очереди. Если ваш запрос находится в статусе `created`, дождитесь его выполнения.

### Была ли статья полезна?

ДаНет

Предыдущая

[Подключение Logs API к ClickHouse](../clickhouse-integration.md)

Следующая

[Список запросов логов](../openapi/getlogrequests.md)