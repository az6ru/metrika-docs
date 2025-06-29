# История изменений | API Яндекс Метрики

Шаг 1. Подготовка данных

## В этой статье:

  1. API импорта данных
  2. Импорт звонков
  3. Передача данных о звонках

# Передача данных о звонках

## [](ru/management/calls#data)Шаг 1. Подготовка данных

Подготовьте [специальные идентификаторы](conversion.md).

## [](ru/management/calls#csv)Шаг 2. Подготовка CSV-файла

Данные о звонках передаются в CSV-формате. Вы можете передать их несколькими способами:

CSV-файл (рекомендуемый)

multipart/form-data

В файле укажите данные, которые хотите передать в Метрику.

В первой строке необходимо передать названия колонок.

Обязательные колонки:

  * `UserId` — идентификатор посетителя сайта, назначенный владельцем сайта.
  * `ClientId` — идентификатор посетителя сайта, назначенный Яндекс Метрикой.
  * `Yclid` — идентификатор клика по рекламному объявлению Яндекс Директа, назначенный Яндекс Директом.
  * `DateTime` — дата и время конверсии в формате [Unix Time Stamp](http://www.unixtimestamp.com/index.php). Указывайте время в часовом поясе UTC+0..

Необязательные колонки:

  * `StaticCall` — является ли звонок статическим (1 — статический, 0 — динамический).

О статическом и динамическом звонке

Тип звонка определяет колл-трекер. При динамическом методе колл-трекер закрепляет номер телефона за каждой сессией пользователя, то есть использует подмену номеров. Когда колл-трекер передает динамический звонок, Метрика привязывает данные о звонке к ближайшему подходящему по времени визиту. Статический звонок не привязывается к визитам посетителей. [Подробно о методах отслеживания звонков](https://ya.cc/t/PlSdbuP7AmqdM)

Метрика не привязывает звонок к посетителю и его визиту, если:

    * передан идентификатор посетителя, которого нет в базе Метрики;
    * визит посетителя совершен после звонка, данные о котором переданы в сервис, или ранее 21 дня до момента отправки данных;
    * учет конверсий включен после того, как данные были переданы в Метрику, и период учета конверсий еще не достиг 21 дня.

  * `Price` — цена цели, десятичным разделителем является точка (.).

  * `Currency` — валюта в трехбуквенном формате ISO 4217.

  * `PhoneNumber` — номер телефона без пробелов (с указанием кода страны и города). Например, +70123456789.

  * `TalkDuration` — длительность разговора в секундах.

  * `HoldDuration` — длительность ожидания ответа в секундах.

  * `CallMissed` — пропущен ли звонок (1 — пропущенный, 0 — отвеченный).

  * `Tag` — произвольная метка. Может использоваться для отметки качества звонка или его итоге и т. д. Например, «клиента не устроила цена».

  * `FirstTimeCaller` — первичность (1 — первичный звонок, 0 — вторичный звонок).

  * `URL` — URL, с которого был звонок (ассоциированная с событием страница). Например, это может быть лэндинг для рекламной кампании, на котором указан номер телефона (PhoneNumber).

  * `CallTrackerURL` — URL перехода в интерфейс колл-трекера.

## [](ru/management/calls#upload)Шаг 3. Передача данных

Примечание

Сформируйте CSV-файл с информацией и передайте его с помощью данного метода. Также рекомендуем генерировать запросы к API в автоматическом режиме с помощью модулей языка программирования.

Примечание

Данные появятся в отчетах Метрики в течение двух часов после их загрузки.

Для передачи данных используйте метод [POST /management/v1/counter/{counterId}/offline_conversions/upload_calls](openapi/call/uploadcalls.md). В запросе передается название цели, которая будет создана при передаче данных. Далее эту цель можно добавлять в отчеты Метрики.

Укажите во входных данных OAuth-токен и номер счетчика.

PHP

Python
    
    
    $counter = "";            // Specify the counter ID
    $token = "";              // Specify the OAuth token
    
    $curl = curl_init("https://api-metrika.yandex.net/management/v1/counter/{counterId}/offline_conversions/upload_calls");
    
    curl_setopt($curl, CURLOPT_POST, true);
    curl_setopt($curl, CURLOPT_POSTFIELDS, array('file' => new CurlFile(realpath('file.csv'))));
    curl_setopt($curl, CURLOPT_SSL_VERIFYPEER, false);
    curl_setopt($curl, CURLOPT_RETURNTRANSFER, true);
    curl_setopt($curl, CURLOPT_HTTPHEADER, array("Content-Type: multipart/form-data", "Authorization: OAuth $token"));
    
    $result = curl_exec($curl);
    
    echo $result;
    
    curl_close($curl);
    
    
    
    import requests
    
    counter = 123456
    token = "token"
    
    file = open("offline-conversions.csv", "r").read()
    
    url = "https://api-metrika.yandex.net/management/v1/counter/{counterId}/offline_conversions/upload_calls".format(counter)
    headers = {
    	"Authorization": "OAuth {}".format(token)
    }
    
    req = requests.post(url, headers=headers, files={"file":file})
    

## [](ru/management/calls#other)Что делать дальше?

Отслеживайте статус загрузки звонков с помощью метода [GET /management/v1/counter/{counterId}/offline_conversions/calls_uploading/{id}](openapi/call/findcalluploadingbyid.md).

## [](ru/management/calls#uznajte-bolshe)Узнайте больше

### Была ли статья полезна?

ДаНет

Предыдущая

[Режимы загрузки данных](../data-import/modes.md)

Следующая

[Загрузка информации о звонках](openapi/call/uploadcalls.md)