# API для социальной сети Yatube

## Описание

Yatube API — это REST API для социальной сети, в которой пользователи могут публиковать посты, оставлять комментарии, подписываться на других авторов и объединять публикации в сообщества.

API позволяет:

- создавать, редактировать и удалять публикации;
- просматривать список публикаций;
- комментировать публикации;
- получать список сообществ;
- подписываться на других пользователей;
- работать с JWT-аутентификацией.

## Установка проекта

### 1. Клонировать репозиторий

```bash
git clone https://github.com/your_username/api_yatube.git
cd api_yatube
```

### 2. Создать виртуальное окружение
```bash
python3 -m venv venv
```

### Активировать виртуальное окружение.
```bash
source venv/bin/activate
```
### 3. Установить зависимости

```bash
pip install -r requirements.txt
```

### 4. Выполнить миграции
```bash
python manage.py migrate
```

### 5. Запустить сервер
```bash
python manage.py runserver
```

## Примеры запросов

### Создать публикацию
POST /api/v1/posts/
```JSON
{
  "id": 0,
  "author": "string",
  "text": "string",
  "pub_date": "2019-08-24T14:15:22Z",
  "image": "string",
  "group": 0
}
```

### Добавление комментария
POST /api/v1/posts/{post_id}/comments/
```JSON
{
  "id": 0,
  "author": "string",
  "text": "string",
  "created": "2019-08-24T14:15:22Z",
  "post": 0
}
```

### Получение списка доступных сообществ.
GET /api/v1/groups/
```JSON
[
  {
    "id": 0,
    "title": "string",
    "slug": "string",
    "description": "string"
  }
]
```
