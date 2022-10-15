### Краткое описание проекта YaMDb

Проект YaMDb собирает отзывы (Review) пользователей на произведения (Title). Произведения делятся на категории: «Книги», «Фильмы», «Музыка». Список категорий (Category) может быть расширен. Есть возможность оставлять комментарии. Подробнее [здесь](https://github.com/AnthonyHol/api_yamdb "здесь").


### Стек технологий
- DRF
- Gunicorn
- Nginx
- Docker
- Docker-compose
- PostgreSQL


### Шаблон наполнения env-файла

```
DB_ENGINE=django.db.backends.postgresql
DB_NAME=postgres
POSTGRES_USER=postgres
POSTGRES_PASSWORD=postgres
DB_HOST=db
DB_PORT=5432
```


### Запуск контейнера и приложения в нем

Перейти в репозиторий для запуска докера

```
cd infra/
```

Запуск docker-compose

```
docker-compose up -d --build
```

После создайте суперпользователя
```
docker-compose exec web python manage.py createsuperuser
```
Войдите в админку и создайте одну-две записи объектов


### При необходимости можно создать дамп (резервную копию) базы:

```
docker-compose exec web python manage.py dumpdata > fixtures.json
```
