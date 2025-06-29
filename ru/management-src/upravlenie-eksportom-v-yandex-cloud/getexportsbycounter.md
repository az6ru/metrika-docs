# Отключение экспорта на счетчике - Управление экспортом в Yandex Cloud | API Яндекс Метрики

Request

## В этой статье:

# Получение информации об объектах, которые экспортируются в Yandex Cloud

Возвращает информацию об объектах, которые экспортируются в Yandex Cloud, с учетом указанного счетчика.

## [](ru/management-src/Upravlenie-eksportom-v-Yandex-Cloud/getExportsByCounter#request)Request

GET
    
    
    https://api-metrika.yandex.net/export/v1/cloud/counter/{counterId}
    

### [](ru/management-src/Upravlenie-eksportom-v-Yandex-Cloud/getExportsByCounter#path-parameters)Path parameters

**Name** |  **Description**  
---|---  
counterId* |  **Type:** integer<int32> Идентификатор счетчика Метрики.  
Example: `2215573`  
  
## [](ru/management-src/Upravlenie-eksportom-v-Yandex-Cloud/getExportsByCounter#responses)Responses

## [](ru/management-src/Upravlenie-eksportom-v-Yandex-Cloud/getExportsByCounter#200-ok)200 OK

OK

### [](ru/management-src/Upravlenie-eksportom-v-Yandex-Cloud/getExportsByCounter#body)Body

application/json
    
    
    {
        "cloud_exports": [
            {
                "ce_id": 0,
                "folder_id": "string",
                "transfer_id": "string",
                "status": "string",
                "quota": 0,
                "type": "string",
                "locked": false,
                "tables": [
                    {
                        "ce_id": 0,
                        "table_name": "string",
                        "status": "string",
                        "columns": [
                            "string"
                        ],
                        "statistics": {
                            "bytes_per_second_by_hour": 0,
                            "bytes_per_second_by_day": 0,
                            "bytes_per_second_by_week": 0,
                            "bytes_per_second_by_month": 0,
                            "bytes_per_second_by_year": 0,
                            "update_time": "2022-12-29T18:02:01Z"
                        }
                    }
                ]
            }
        ]
    }
    

**Name** |  **Description**  
---|---  
cloud_exports |  **Type:** [CloudExport](getexportsbycounter.md)[] Список объектов `cloud_exports`.  
  
### [](ru/management-src/Upravlenie-eksportom-v-Yandex-Cloud/getExportsByCounter#cloudexport)CloudExport

Список объектов `cloud_exports`.

**Name** |  **Description**  
---|---  
folder_id* |  **Type:** string Идентификатор папки в Yandex Cloud. _Pattern:_ `^[0-9a-zA-Z]{10,64}$`  
transfer_id* |  **Type:** string Идентификатор трансфера в Yandex Cloud. _Pattern:_ `^[0-9a-zA-Z]{10,64}$`  
ce_id |  **Type:** integer<int32> Внутренний идентификатор Метрики. Автоматически генерируется при создании экспорта.  
locked |  **Type:** boolean  
quota |  **Type:** integer<int64> Значение квоты.  
status |  **Type:** string Статус экспорта в Yandex Cloud. Возможные значения:

  * `ACTIVE` — экспорт включен.
  * `DELETED` — экспорт отключен.

  
tables |  **Type:** [CloudExportTable](getexportsbycounter.md)[] Список объектов `cloud_export_table`.  
type |  **Type:** string  
  
### [](ru/management-src/Upravlenie-eksportom-v-Yandex-Cloud/getExportsByCounter#cloudexporttable)CloudExportTable

Список объектов `cloud_export_table`.

**Name** |  **Description**  
---|---  
ce_id |  **Type:** integer<int32> Внутренний идентификатор Метрики. Автоматически генерируется при создании экспорта.  
columns |  **Type:** string[] Список столбцов таблицы для экспорта в Yandex Cloud.  
statistics |  **Type:** [CloudExportStatistics](getexportsbycounter.md) Статистика по экспорту.  
status |  **Type:** string Статус экспорта таблицы с данными в Yandex Cloud:

  * `NEW` — Таблица новая, не экспортировалась.
  * `ACTIVATING` — Экспорт таблицы в процессе.
  * `ACTIVE` — Экспорт таблицы включен.
  * `DELETING` — Экспорт таблицы отключается.
  * `DELETED` — Экспорт таблицы отключен.

  
table_name |  **Type:** string Название таблицы. Возможные значения:

  * `HITS` — Метрика хиты.
  * `HITS_V2` — Метрика обновляемые хиты.
  * `VISITS` — Метрика визиты.

  
  
### [](ru/management-src/Upravlenie-eksportom-v-Yandex-Cloud/getExportsByCounter#cloudexportstatistics)CloudExportStatistics

Статистика по экспорту.

**Name** |  **Description**  
---|---  
bytes_per_second_by_day |  **Type:** integer<int64> Среднее количество байт в секунду, период расчета — сутки.  
bytes_per_second_by_hour |  **Type:** integer<int64> Среднее количество байт в секунду, период расчета — час.  
bytes_per_second_by_month |  **Type:** integer<int64> Среднее количество байт в секунду, период расчета — месяц.  
bytes_per_second_by_week |  **Type:** integer<int64> Среднее количество байт в секунду, период расчета — неделя.  
bytes_per_second_by_year |  **Type:** integer<int64> Среднее количество байт в секунду, период расчета — год.  
update_time |  **Type:** string<date-time> Дата обновления в формате ISO 8601, например `2024-03-04T17:10:03Z`.  
  
No longer supported, please use an alternative and newer version.

### Была ли статья полезна?

ДаНет