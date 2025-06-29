# Создание цели - Управление целями | API Яндекс Метрики

JS-событие

## В этой статье:

  1. [API управления](index.md)
  2. Справочник API управления
  3. Управление целями
  4. Примеры создания целей

# Примеры создания целей

## [](ru/management/addgoal-example#action)JS-событие
    
    
    import requests
    import json
    
    your_token = '<your_token>'
    counter_id = <Counter ID>
    
    f={"goal": 
        {
            "name" :  "API JS goal",
            "type" :  "action" ,
            "conditions" : [ {
                "type" :  "exact" ,
                "url" :  "order" 
            }]
        }
    }
    
    headers={f'Authorization': 'OAuth' + your_token}
    r = requests.post(url=f'https://api-metrika.yandex.net/management/v1/counter/{counter_id}/goals',
                      headers=headers,
                      json=f)
    
    print(json.dumps(r.json(), indent=4))
    
    

## [](ru/management/addgoal-example#step)Составная цель
    
    
    import requests
    import json
    
    your_token = '<your_token>'
    counter_id = <Counter ID>
    
    f={"goal": 
        {
            "name" :  "API Multi-step goal",
            "type" :  "step" ,
            "is_retargeting" :  0,
            "steps" : [ {
                "name" : "First step of the multi-step goal",
                "type" : "url",
                    "conditions" : [ {
                        "type" : "contain_action", #Step ID contains
                        "url" : "stepgoalID"
                    }
                    ]
            },
            {
                "name" : "Second step of the multistep goal",
                "type" : "url",
                    "conditions" : [ {
                        "type" : "regexp_action", #Step ID matches a regular expression
                        "url" : "stepgoalID2"
                    }
                    ]
            },
            {
                "name" : "Third step of the multi-step goal",
                "type" : "url",
                    "conditions" : [ {
                        "type" : "action", #Step ID matches
                        "url" : "stepgoalID3"
                    }
                    ]
            }
            ]
        }
    }
    
    headers={f'Authorization': 'OAuth' + your_token}
    r = requests.post(url=f'https://api-metrika.yandex.net/management/v1/counter/{counter_id}/goals',
                      headers=headers,
                      json=f)
    
    print(json.dumps(r.json(), indent=4))
    

## [](ru/management/addgoal-example#url)Посещение страниц
    
    
    import requests
    import json
    
    your_token = '<your_token>'
    counter_id = <Counter ID>
    
    f={"goal": 
        {
            "name" :  "API Page view",
            "type" :  "url" ,
            "conditions" : [ {
                "type" :  "contain" , #url contains
                "url" :  "mysite.../cart.md 
            }]
        }
    }
    
    headers={f'Authorization': 'OAuth' + your_token}
    r = requests.post(url=f'https://api-metrika.yandex.net/management/v1/counter/{counter_id}/goals',
                      headers=headers,
                      json=f)
    
    print(json.dumps(r.json(), indent=4))
    

## [](ru/management/addgoal-example#number)Количество просмотров
    
    
    import requests
    import json
    
    your_token = '<your_token>'
    counter_id = <Counter ID>
    
    f={"goal": 
        {
            "name" :  "API Page depth",
            "type" :  "number" ,
            "depth" : 3 #Page depth
        }
    }
    
    headers={f'Authorization': 'OAuth' + your_token}
    r = requests.post(url=f'https://api-metrika.yandex.net/management/v1/counter/{counter_id}/goals',
                      headers=headers,
                      json=f)
    
    print(json.dumps(r.json(), indent=4))
    

## [](ru/management/addgoal-example#phone)Клик по номеру телефона
    
    
    import requests
    import json
    
    your_token = '<your_token>'
    counter_id = <Counter ID>
    
    f={"goal": 
        {
            "name" :  "API Click on phone number",
            "type" :  "phone" ,
            "hide_phone_number": 1, #Hide the phone number (1 - yes, 0 - no)
            "conditions" : [ {
                "type" :  "exact" , 
                "url" :  "+79990123456" 
            }]
        }
    }
    
    headers={f'Authorization': 'OAuth' + your_token}
    r = requests.post(url=f'https://api-metrika.yandex.net/management/v1/counter/{counter_id}/goals',
                      headers=headers,
                      json=f)
    
    print(json.dumps(r.json(), indent=4))
    

## [](ru/management/addgoal-example#email)Клик по email
    
    
    import requests
    import json
    
    your_token = '<your_token>'
    counter_id = <Counter ID>
    
    f={"goal": 
        {
            "name" :  "API Click on email",
            "type" :  "email" ,
            "conditions" : [ {
                "type" :  "exact" , 
                "url" :  "mail@mail.ru" 
            }]
        }
    }
    
    headers={f'Authorization': 'OAuth' + your_token}
    r = requests.post(url=f'https://api-metrika.yandex.net/management/v1/counter/{counter_id}/goals',
                      headers=headers,
                      json=f)
    
    print(json.dumps(r.json(), indent=4))
    

## [](ru/management/addgoal-example#messenger)Переход в мессенджер
    
    
    import requests
    import json
    
    your_token = '<your_token>'
    counter_id = <Counter ID>
    
    f={"goal": 
        {
            "name" :  "API Open messenger",
            "type" :  "messenger" ,
            "conditions" : [ {
                "type" :  "messenger", 
                "url" :  "whatsapp" #Opening WhatsApp
            }]
        }
    }
    
    headers={f'Authorization': 'OAuth' + your_token}
    r = requests.post(url=f'https://api-metrika.yandex.net/management/v1/counter/{counter_id}/goals',
                      headers=headers,
                      json=f)
    
    print(json.dumps(r.json(), indent=4))
    

## [](ru/management/addgoal-example#file)Скачивание файлов
    
    
    import requests
    import json
    
    your_token = '<your_token>'
    counter_id = <Counter ID>
    
    f={"goal": 
        {
            "name" :  "API File downloads",
            "type" :  "file" ,
            "conditions" : [ {
                "type" :  "file", 
                "url" :  "file.pdf" #Filename with or without an extension
            }]
        }
    }
    
    headers={f'Authorization': 'OAuth' + your_token}
    r = requests.post(url=f'https://api-metrika.yandex.net/management/v1/counter/{counter_id}/goals',
                      headers=headers,
                      json=f)
    
    print(json.dumps(r.json(), indent=4))
    

## [](ru/management/addgoal-example#search)Поиск по сайту
    
    
    import requests
    import json
    
    your_token = '<your_token>'
    counter_id = <Counter ID>
    
    f={"goal": 
        {
            "name" :  "API Site search",
            "type" :  "search" ,
            "conditions" : [ {
                "type" :  "search", 
                "url" :  "result" #Name of the GET parameter that accepts a search query on the site
            }]
        }
    }
    
    headers={f'Authorization': 'OAuth' + your_token}
    r = requests.post(url=f'https://api-metrika.yandex.net/management/v1/counter/{counter_id}/goals',
                      headers=headers,
                      json=f)
    
    print(json.dumps(r.json(), indent=4))
    

## [](ru/management/addgoal-example#social)Переход в соц. сети
    
    
    import requests
    import json
    
    your_token = '<your_token>'
    counter_id = <Counter ID>
    
    f={"goal": 
        {
            "name" :  "API Click-through to social network",
            "type" :  "social" ,
            "conditions" : [ {
                "type" :  "social", 
                "url" :  "vkontakte" #Name of the social network
            }]
        }
    }
    
    headers={f'Authorization': 'OAuth' + your_token}
    r = requests.post(url=f'https://api-metrika.yandex.net/management/v1/counter/{counter_id}/goals',
                      headers=headers,
                      json=f)
    
    print(json.dumps(r.json(), indent=4))
    

## [](ru/management/addgoal-example#payment_system)Возвращение из платежной системы
    
    
    import requests
    import json
    
    your_token = '<your_token>'
    counter_id = <Counter ID>
    
    f={"goal": 
        {
            "name" :  "API Transition back from payment system",
            "type" :  "payment_system" 
        }
    }
    
    headers={f'Authorization': 'OAuth' + your_token}
    r = requests.post(url=f'https://api-metrika.yandex.net/management/v1/counter/{counter_id}/goals',
                      headers=headers,
                      json=f)
    
    print(json.dumps(r.json(), indent=4))
    

## [](ru/management/addgoal-example#visit_durration)Продолжительность визита
    
    
    import requests
    import json
    
    your_token = '<your_token>'
    counter_id = <Counter ID>
    
    f={"goal": 
        {
            "name" :  "API Session duration",
            "type" :  "visit_duration",
            "duration": 90 #Time in seconds
        }
    }
    
    headers={f'Authorization': 'OAuth' + your_token}
    r = requests.post(url=f'https://api-metrika.yandex.net/management/v1/counter/{counter_id}/goals',
                      headers=headers,
                      json=f)
    
    print(json.dumps(r.json(), indent=4))
    

### Была ли статья полезна?

ДаНет

Предыдущая

[Список мессенджеров](openapi/goal/getmessengers.md)

Следующая

[Информация о фильтре](openapi/filter/filter.md)