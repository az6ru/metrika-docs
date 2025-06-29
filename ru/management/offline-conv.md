# Список загрузок офлайн-конверсий - Импорт офлайн-конверсий | API Яндекс Метрики

Шаг 1. Подготовка данных

## В этой статье:

  1. API импорта данных
  2. Импорт офлайн-конверсий
  3. Передача офлайн-конверсий

# Передача офлайн-конверсий

О том, что такое офлайн-конверсии и какие бизнес-задачи можно решить, отслеживая их, см. в разделе [Офлайн-конверсии и звонки](conversion.md).

## [](ru/management/offline-conv#data)Шаг 1. Подготовка данных

  1. Подготовьте [специальные идентификаторы](conversion.md) — `ClientID`, `UserID`, `yclid` или `PurchaseId`.

  2. Создайте цель [JavaScript-событие](https://yandex.../support/metrica/general/goal-js-event.md) с помощью метода [POST /management/v1/counter/{counterId}/goals](openapi/goal/addgoal.md). В качестве идентификатора цели укажите событие, которое нужно отслеживать (например, подтверждение заказа — «order_confirmed»). Этот идентификатор понадобится при формировании CSV-файла.

Примечание

При создании цели «JavaScript-событие» обязательно используйте условие «совпадает».

Можно использовать ранее созданную цель, если конверсия по этой цели совершается и на сайте, и вне его и вы хотите получать общую статистику.

## [](ru/management/offline-conv#csv)Шаг 2. Подготовка данных о конверсиях

Данные о конверсиях передаются в CSV-формате. Вы можете передать их несколькими способами:

CSV-файл (рекомендуемый)

multipart/form-data

В файле укажите данные, которые хотите передать в Метрику. [Пример файла](https://download.cdn.yandex.net/from/yandex.../support/../metrica/files/offline-conversions.md).

В первой строке необходимо передать названия колонок.

**Колонки** |  **Описание**  
---|---  
**Обязательные** |   
`UserId` |  Идентификатор посетителя сайта, назначенный владельцем сайта.  
`ClientId` |  Идентификатор посетителя сайта, назначенный Яндекс Метрикой.  
`Yclid` |  Идентификатор клика по рекламному объявлению Яндекс Директа, назначается Яндекс.Директом. Передается в URL объявления.  
`PurchaseId` |  Идентификатор покупки электронной коммерции назначенный владельцем сайта.  
`Target` |  Идентификатор цели.  
`DateTime` |  Дата и время конверсии в формате [Unix Time Stamp](http://www.unixtimestamp.com/index.php). В DateTime можно указывать только прошедшее время. Если на момент загрузки файла время из DateTime еще не наступило, возникнет ошибка.  
**Необязательные** |   
`Price` |  Цена (ценность) цели, десятичным разделителем является точка (.).  
`Currency` |  Валюта в трехбуквенном формате ISO 4217.  
  
## [](ru/management/offline-conv#upload)Шаг 3. Передача данных

Примечание

Сформируйте CSV-файл с информацией и передайте его с помощью данного метода. Также рекомендуем генерировать запросы к API в автоматическом режиме с помощью модулей языка программирования.

Примечание

Данные появятся в отчетах Метрики в течение двух часов после их загрузки.

C помощью метода [POST /management/v1/counter/{counterId}/offline_conversions/upload](openapi/offline_conversions/upload_1.md). Укажите во входных данных OAuth-токен и номер счетчика.

PHP

Python
    
    
    $counter = "";            // Specify the counter ID
    $token = "";              // Specify the OAuth token
    
    $curl = curl_init("https://api-metrika.yandex.net/management/v1/counter/$counter/offline_conversions/upload");
    
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
    
    url = "https://api-metrika.yandex.net/management/v1/counter/{}/offline_conversions/upload".format(counter)
    headers = {
     "Authorization": "OAuth {}".format(token)
    }
    
    req = requests.post(url, headers=headers, files={"file":file})
    

## [](ru/management/offline-conv#other)Что делать дальше?

Отслеживайте статус загрузки конверсий с помощью метода [GET /management/v1/counter/{counterId}/offline_conversions/uploading/{id}](openapi/offline_conversions/findbyid_1.md).

## [](ru/management/offline-conv#uznajte-bolshe)Узнайте больше

### Была ли статья полезна?

ДаНет

Предыдущая

[Отслеживание конверсий](conversion.md)

Следующая

[Загрузка офлайн-конверсий](openapi/offline_conversions/upload_1.md)