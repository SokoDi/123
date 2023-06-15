![YAMDB workflow](https://github.com/SokoDi/yamdb_final/actions/workflows/yamdb_workflow.yml/badge.svg)
# Проект API Yamdb - api для сайта с отзывами на кино, книги и музыку
# IP Боевого сервера : 84.201.175.221
## Запуск проекта:

Клонировать репозиторий и перейти в него в командной строке:

```
git clone git@github.com:golenkovyura/api_yamdb.git
```


```
cd api_yamdb
```

Cоздать и активировать виртуальное окружение:

```
python -m venv venv
```

```
source venv/Scripts/activate
```

```
python -m pip install --upgrade pip
```

Установить зависимости из файла requirements.txt:

```
pip install -r requirements.txt
```

Выполнить миграции:

```
python manage.py migrate
```
Выполнить загрузку информации в базу данных:

```
python manage.py csv_to_db
```

Запустить проект:

```
python manage.py runserver
```

## Примеры запросов

* Основные эндпоинты для аутентификации нового пользователя
> Для аутентификации применены JWT-токены.

  Регистрация нового пользователя:
```
http://127.0.0.1:8000/api/v1/auth/signup/
```
  Получение JWT-токена:
```
http://127.0.0.1:8000/api/v1/auth/token/
```
> Токен необходимо передавать в заголовке каждого запроса, в поле Authorization. Перед самим токеном должно стоять ключевое слово Bearer и пробел.

* Основные эндпоинты API
```
http://127.0.0.1:8000/api/v1/categories/
```
```
http://127.0.0.1:8000/api/v1/genres/
```
```
http://127.0.0.1:8000/api/v1/titles/
```
> пример POST запроса на (http://127.0.0.1:8000/api/v1/categories/):
```
{
  "name": "Василий",
  "slug": "Текст"
}
```
Полный список эндпойнтов, методы и параметры запросов описаны в докуметации:
```
http://127.0.0.1:8000/redoc/
```
## Авторы:
[Юрий Голенков(тимлид, разработка ресурсов Categories, Genres и Titles)](https://github.com/golenkovyura)

[Дмитрий Соколов(разработка ресурсов Auth и Users)](https://github.com/SokoDi)

[Александр Джуманов(разработка ресурсов Review и Comments)](https://github.com/AlexDjum)
