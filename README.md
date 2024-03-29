[![Python](https://img.shields.io/badge/-Python-464646?style=flat-square&logo=Python)](https://www.python.org/)
[![Django](https://img.shields.io/badge/-Django-464646?style=flat-square&logo=Django)](https://www.djangoproject.com/)
[![Django REST Framework](https://img.shields.io/badge/-Django%20REST%20Framework-464646?style=flat-square&logo=Django%20REST%20Framework)](https://www.django-rest-framework.org/)
# API YaTube

## Самая актуальная версия API YaTube.

YaTube API это RESTful API, позволяющий создавать и редактировать посты, оставлять комментарии к отзывам.
Подписываться на любимых авторов. 
В основе проекта лежат Django и Django REST Framework.

## Особенности

- Пишите свои посты.
- Авторизация происходит по токену. 
- Для авторизованных пользователей присутствует возможность подписки на автора поста.

## Технологии

- [Django](https://github.com/django/django) - фреймворк, который включает в себя все необходимое для быстрой разработки
  различных веб-сервисов.
- [Django REST Framework](https://www.django-rest-framework.org/) - фреймворк, расширяющий возможности Django и
  позволяющий быстро писать RESTful API для Django-проектов.

Конечно же YaTube API это ПО с открытым исходным кодом и [публичным репозиторием](https://github.com/sintecs/api_final_yatube)
на GitHub.
### Как запустить проект:

Клонировать репозиторий и перейти в него в командной строке:

```
git clone https://github.com/s1ntecs/api_final_yatube.git
```

```
cd api_final_yatube
```

Cоздать и активировать виртуальное окружение:

```
python3 -m venv env
```

```
source env/bin/activate
```

Установить зависимости из файла requirements.txt:

```
python3 -m pip install --upgrade pip
```

```
pip install -r requirements.txt
```

Выполнить миграции:

```
python3 manage.py migrate
```

Запустить проект:

```
python3 manage.py runserver
```
Примеры API запросов:
.../api/v1/posts/ .../api/v1/posts/{id}/ ==> PATCH, DELETE
GET
Ответ:
        {
        "id": 0,
        "author": "string",
        "text": "string",
        "pub_date": "2019-08-24T14:15:22Z",
        "image": "string",
        "group": 0
        }
POST: 
        {
        "text": "string",
        "image": "string",
        "group": 0
        }
Ответ:
        {
        "id": 0,
        "author": "string",
        "text": "string",
        "pub_date": "2019-08-24T14:15:22Z",
        "image": "string",
        "group": 0
        }

.../api/v1/posts/{post_id}/comments/ .../api/v1/posts/{post_id}/comments/{id}/ => PUT, PATCH. DELETE
GET
Ответ:
        [
        {
            "id": 0,
            "author": "string",
            "text": "string",
            "created": "2019-08-24T14:15:22Z",
            "post": 0
        }
        ]
POST
    {
    "text": "string"
    }
Ответ:
        [
        {
            "id": 0,
            "author": "string",
            "text": "string",
            "created": "2019-08-24T14:15:22Z",
            "post": 0
        }
        ]

.../api/v1/groups/ .../api/v1/groups/{id}/
GET
Ответ:
        [
        {
            "id": 0,
            "title": "string",
            "slug": "string",
            "description": "string"
        }
        ]

.../api/v1/follow/
GET
Ответ:
        [
        {
        "user": "string",
        "following": "string"
        }
        ]
POST
        {
        "following": "string"
        }
Ответ:
        {
        "user": "string",
        "following": "string"
        }

Аутентификация производится по JWT-токену:

.../api/v1/jwt/refresh/ Обновление JWT-токена.
.../api/v1/jwt/create/ Для Получения  JWT-токена
пример POST запроса:
        {
        "username": "string",
        "password": "string"
        }

Список всех энпоинтов можете посмотреть в докумментации: 
https://djoser.readthedocs.io/en/latest/getting_started.html#available-endpoints
