[![.github/workflows/main.yml](https://github.com/Randy-Colt/kittygram_final/actions/workflows/main.yml/badge.svg)](https://github.com/Randy-Colt/kittygram_final/actions/workflows/main.yml)

## Описание проекта

**Kittygram** - это сайт, на котором люди могут выставлять фотографии своих котов и их достижения.

## Стек

- Python 3.9
- Django 3.2.3
- Django REST framework 3.12.4
- Node.JS 18
- Nginx
- Docker compose


## Запуск проекта

Клонируем репозиторий: 

```bash 
git clone git@github.com:Randy-Colt/kittygram_final.git
```

Запускаем docker compose:

```bash
sudo docker compose up
```

## Действия после запуска контейнеров

После запуска нужно выполнить сбор статики и миграцию для бэкенда. Статика фронтенда собирается во время запуска контейнера, после чего он останавливается. 

```bash
sudo docker compose exec backend python manage.py migrate

sudo docker compose exec backend python manage.py collectstatic

sudo docker compose exec backend cp -r /app/collected_static/. /backend_static/static/
```

Проект доуступен по адресу:

```
http://localhost:9000/
```

## Описание переменных окружения

Ниже пример файла .env c переменными окружения, необходимыми для запуска приложения

```bash
POSTGRES_DB=kittygram
POSTGRES_USER=kittygram_user
POSTGRES_PASSWORD=kittygram_password
DB_NAME=kittygram
DB_HOST=db
DEBUG=False
SECRET_KEY=django_secret_key_example
SQLITE=True
```

## Автор

Логвинов Андрей https://github.com/Randy-Colt
