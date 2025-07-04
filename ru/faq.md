# FAQ

Офлайн-конверсии и звонки

## В этой статье:

# Частые вопросы

Скрытие чувствительных данных в API отчетов

Сочетание некоторых условий или группировок может относиться к чувствительной информации, например, пол и возраст. В таком случае в отчете остаются значения строк с 10 и более посетителями (ссылка).

На наличие чувствительных данных в ответе указывает параметр `contains_sensetiva_data` со значением `true`.

Вы можете увеличить отчетный период, чтобы было больше данных, или удалить из отчета условия, вызывающие чувствительную информацию.

Подробнее про [обезличенность статистики](https://yandex.support/metrica/reports/report-general.md).

Почему данные в Logs API и в веб-интерфейсе Метрики могут различаться?

Это происходит, поскольку в интерфейсе используются дополнительные алгоритмы обработки данных. Чтобы корректно работать с этими данным, система сохраняет числа по стандарту [IEEE 754](https://ru.wikipedia.org/wiki/IEEE_754-2008).

Стандарт IEEE 754 допускает неточности при арифметических операциях. Чтобы повысить точность расчетов, числа умножаются на определенный коэффициент.

При работе с целыми числами точность не теряется. В числах с плавающей точкой исходное значение будет отличаться от полученного. При попытке вернуть полученное значение в исходный вид, результат будет отличаться на точность, заданную коэффициентом.

#### [](ru/faq#fields-with-bids)Поля, для которых используются коэффициенты

**Поле** |  **Коэффициент**  
---|---  
ym:s:purchaseRevenue |  1 (используется также в [API отчетов](stat/index.md))  
ym:s:goalsPrice |  1000  
ym:s:productsPrice |  1 000 000  
ym:s:impressionsProductPrice  
ym:s:purchaseTax  
ym:s:eventsProductPrice  
  
Что делать, если не хватает квоты в 5000 запросов на счетчик?

  1. Убедитесь, что не запрашиваете повторно одни и те же данные.
  2. Пересмотрите запросы, чтобы не делать однотипные или похожие запросы.
  3. При выгрузке большого количества данных запланируйте выгрузку в несколько частей. Каждую следующую часть выгрузки начинайте на следующие сутки.

Если вы хотите увеличить квоту, подключите [Метрику Про](https://yandex.support/metrica/pro/intro.md).

## [](ru/faq#conversion)Офлайн-конверсии и звонки

Какое максимальное количество строк может быть в файле?

Лимита на количество строк нет, но есть ограничение по объему файла — не более 1 ГБ.

Как отображаются статистические звонки?

Статитические звонки не привязываются к визитам. Если в файле звонков все звонки статические, то статус загрузки будет `LINKAGE_FAILURE`. Несмотря на это, данные в отчетах будут.

Перезапишется ли доход у цели, если повторно передать ту же строку с другим показателем дохода?

Да, перезапишется.

Какие есть ограничения для комментариев в загрузках?

В комментариях можно использовать латинские и кириллические буквы, а также цифры. Максимальная длина комментария — 255 символов.

## [](ru/faq#logs-api)Logs API

Какой доступ приложения к Метрике нужен для работы с Logs API?

Для работы с Logs API и счетчиком достаточно доступа `read`.

Как исключить роботов из данных Logs API?

В настройках счетчика включите фильтрацию роботов по поведению. Фильтр применяется только к новым данным, поступившим после установки условий фильтрации. Старые данные при этом не изменятся.

Как работает операция «Вырезать параметр URL»?

Если для счетчика включена операция «Вырезать параметр URL», то все вырезанные URL'ы недоступны и в Logs API. Если вы отключите эту операцию, новые данные будут отображаться в Logs API вместе с URL'ами. Но для данных, собранных ранее, URL'ы по-прежнему останутся недоступны.

## [](ru/faq#reports-api)API Отчетов

Нужно ли экранировать символы в регулярных выражениях?

При использовании регулярных выражений в API отчетов, например, в сегментации, нужно всегда делать двойное экранирование. Например, если вы хотите передать значение `\.string`, нужно ставить два слеша экранирования: `\\.string`.

Как есть ограничения для массива счетчиков `ids`?

Можно передавать не более 500 счетчиков.

## [](ru/faq#authorization-api)API Авторизация

Какой срок жизни токена?

Токен продлевается автоматически каждый год. Токен становится невалидным, если в течение года он не используется (с него не делаются запросы).

Как отозвать токен?

Для отзыва или удаления токена откройте настройки [учетной записи Яндекса](https://id.yandex.ru/) и перейдите на вкладку **Безопасность**. Нажмите **Выйти на всех устройствах**. Подробнее см. [Отзыв токена](https://yandex.dev/id/doc/concepts/ya-oauth-intro.md).

Почему может возникать ошибка 403 Access is denied?

Причины возникновения ошибки «Access is denied» (код 403) могут быть такими:

  * На стороне приложения:

    * Приложение не имеет доступа к Метрике. Для чтения данных счетчиков (построения отчетов, просмотра информации по счетчику и т.п.) нужен доступ `metrika:read`. Для управления счетчиками (загрузки офлайн-данных, изменения счетчиков, сегментов и т.п.) нужен ljcneg `metrika:write`.
  * На стороне токена:

    * Токен невалидный. Истек его срок действия или на аккаунте, для которого он был заведен, был изменен пароль авторизации. Если причина в этом, для устранения ошибки достаточно перевыпустить токен.

    * Токен создан для другого аккаунта. Он мог быть заведен на логине, который не имеет доступ к счетчику Яндекс Метрики.

Примечание

Владельцем токена является не владелец приложения, а аккаунт, под которым вы были авторизованы, когда выполняли GET-запрос на получение токена.

    * Токен создан для другого приложения. При выполнении GET-запроса на получение токена в параметре `client_id` было указано не то значение или была допущена опечатка, из-за которой токен был заведен на приложение, не имеющее доступа к Метрике (`metrika:read` или `metrika:write`).

  * На стороне Метрики:

    * На счетчике, к которому вы обращаетесь, у владельца токена нет доступа по API. Подробнее о типах доступов к счетчику см. [Доступ к счетчику](https://yandex.support/metrica/general/access.md). Для использования API управления владельцу нужен гостевой доступ на просмотр или гостевой доступ на редактирование.
  * На стороне API запроса:

    * В коде для вызова API-запроса некорректно заданы параметры авторизации. Из-за этого чтение токена происходит некорректно или не происходит совсем.

Почему может возникать ошибка с кодом 401?

Ошибка с кодом 401 означает, что пользователь не авторизован. Это может быть связано с двумя причинами:

  * Параметры авторизации в заголовке запроса не заданы.

  * Параметры авторизации в заголовке запроса заданы некорректно.

## [](ru/faq#archive-docs)Архивная документация

Архивная документация для API, совместимого с Google Analytics Core Reporting API

Архивную версию документации можно скачать по [ссылке](https://yastatic.net/s3/doc-binary/srcfiles/api-ru.md).

### Была ли статья полезна?

ДаНет

Предыдущая

[Загрузка части подготовленных логов обработанного запроса](logs/openapi/download.md)

Следующая

[Обратная связь](troubleshooting.md)