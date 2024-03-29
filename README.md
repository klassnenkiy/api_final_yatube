### Описание. Проект «API для Yatube»

Yatube - это проект 9 спринта курса "python-разработчик" Яндекс-Практикума

#### С помощью этого проекта можно:
* Подписываться на авторов и смотреть подписки.
* Просматривать, создавать новые, удалять и изменять посты.
* Просматривать группы.
* Комментировать, смотреть, удалять и обновлять комментарии.
* Фильтровать по полям.

#### Документация по адресу:
```
http://localhost:8000/redoc/
```
#### Технологии
```
Django==3.2.16
pytest==6.2.4
pytest-pythonpath==0.7.3
pytest-django==4.4.0
djangorestframework==3.12.4
djangorestframework-simplejwt==4.7.2
Pillow==9.3.0
PyJWT==2.1.0
requests==2.26.0
```
### Как запустить проект:

Клонировать репозиторий и перейти в него в командной строке:

```
git clone git@github.com:klassnenkiy/api_final_yatube.git
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
### Примеры запросов

Получение токена

Отправить POST-запрос на адрес `api/v1/jwt/create/` и передать 2 поля в `data`:

1. `username` - имя пользователя.
2. `password` - пароль пользователя.

Создание поста

Отправить POST-запрос на адрес `api/v1/posts/` и передать обязательное поле `text`, в заголовке указать `Authorization`:`Bearer <токен>`.

1. Пример запроса:

   ```json
   {
     "text": "Мой первый пост."
   }
   ```
   
2. Пример ответа:

   ```json
   {
     "id": 2,
     "author": "Stas",
     "text": "Мой первый пост",
     "pub_date": "2023-03-09T11:41:22.024183Z",
     "image": null,
     "group": null
   }
   ```
