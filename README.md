# Kittygram
![workflow](https://github.com/wildcat3333/kittygram_final/actions/workflows/main.yml/badge.svg)

URL: https://kittygramm.ddns.net
IP: 158.160.69.26

Проект Kittygram — социальная сеть для обмена фотографиями любимых питомцев. Это полностью рабочий проект, который состоит из бэкенд-приложения на Django и фронтенд-приложения на React.
Задача — задеплоить проект Kittygram на удалённый сервер.
___
![DjangoREST](https://img.shields.io/badge/DJANGO-REST-ff1709?style=for-the-badge&logo=django&logoColor=white&color=ff1709&labelColor=gray)
![Django](https://img.shields.io/badge/django-%23092E20.svg?style=for-the-badge&logo=django&logoColor=white)
![SQLite](https://img.shields.io/badge/sqlite-%2307405e.svg?style=for-the-badge&logo=sqlite&logoColor=white)
![pythonversion](https://img.shields.io/badge/python-%3E%3D3.9-blue)
![react](https://img.shields.io/badge/-ReactJs-61DAFB?logo=react&logoColor=white&style=for-the-badge)

## Оглавление
1. [Описание](#описание)
2. [Стек технологий](#стек-технологий)
3. [Как запустить проект](#как-запустить-проект)
4. [Автор проекта](#автор-проекта)


## Описание
Пользователь может получить доступ к проекту Kittygram по доменному имени https://kittygramm.ddns.net
При подключении к Kittygram доступны все возможности проекта: можно зарегистрироваться и авторизоваться, добавить нового котика на сайт или изменить существующего, а также просмотреть записи других пользователей.
Секреты подключаются из файла .env.
В проекте Kittygram подгружаются файлы со стилями для панели администратора.



## Стек технологий
- проект написан на Python с использованием Django, Django REST Framework
- базы данны - PostgreSQL
- система контроля версий - git
- frontend - React



## Как запустить проект:

- Переходим в директорию проекта
```
cd /home/yc-user/kittygram
```

- Параметры .env
```
cd /home/yc-user/kittygram/.env

POSTGRES_DB=kittygram
POSTGRES_USER=<user>
POSTGRES_PASSWORD=<password>
DB_HOST=db
DB_PORT=5432
SECRET_KEY=<sekret key>
MEDIA_DOMAIN='https://kittygramm.ddns.net'
ALLOWED_HOSTS='158.160.69.26 127.0.0.1 localhost kittygramm.ddns.net'
DEBUG=False

```

- Запускаем docker compose файл конфигурации проекта docker-compose.production.yml
```
cd /home/yc-user/kittygram
sudo docker compose -f docker-compose.production.yml up -d
```

- Выполнить миграции:
```
sudo docker compose -f docker-compose.production.yml exec backend python manage.py migrate
```

- Собираем статику приложения
```
sudo docker compose -f docker-compose.production.yml exec backend python manage.py collectstatic
sudo docker compose -f docker-compose.production.yml exec backend cp -r /app/collected_static/. /static/static/
```


## Автор проекта
_[Мария Константинова](https://github.com/wildcat3333)_, python-developer

___
<p>
    <span>© 2023, Contributors on git </span>
</p>
