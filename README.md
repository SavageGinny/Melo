# 🎵 Melo — платформа для музыкантов

Melo — сайт, где музыканты могут делиться своими треками, получать обратную связь, делать ремиксы и общаться. Проект построен на микросервисной архитектуре с использованием современного стека технологий.

---

## 📦 Архитектура микросервисов

| Микросервис          | Назначение                                      | Фреймворк   | БД / Инструменты                         | Особенности                     |
|----------------------|--------------------------------------------------|-------------|------------------------------------------|----------------------------------|
| `user-service`       | Пользователи, регистрация, роли                  | Django      | PostgreSQL                               | djoser / JWT / кастомный auth   |
| `track-service`      | Треки, теги, метаинформация                      | Django      | PostgreSQL + S3 / MinIO                  | `boto3`, `django-storages`, `mutagen` |
| `remix-service`      | Связь оригинала и ремиксов                       | Django      | PostgreSQL                               | DRF                             |
| `comment-service`    | Комментарии к трекам                             | FastAPI     | PostgreSQL / Redis (кеш)                 | asyncpg, aioredis               |
| `chat-service`       | Личные и групповые чаты                          | aiohttp     | MongoDB (сообщения) + Redis Streams      | WebSocket, motor                |
| `analytics-service`  | Прослушивания, действия                          | FastAPI     | ClickHouse                               | clickhouse-driver               |
| `search-service`     | Поиск по тегам, авторам, названиям              | FastAPI     | Elasticsearch                            | elasticsearch-py                |
| `media-service`      | Аудиостриминг (HLS)                              | FastAPI     | —                                        | ffmpeg, aiofiles                |
| `frontend`           | Веб-интерфейс                                    | React       | —                                        | TailwindCSS, Zustand, Router    |
| `notification-service` (будущ.) | Уведомления                           | FastAPI     | Redis                                    | Celery (опц.)                   |
| `gateway`            | Reverse proxy                                    | Nginx       | —                                        | docker-compose + volumes        |

---

## 🧰 Технологии

- **Backend:** Django, DRF, FastAPI, aiohttp
- **Frontend:** React, TailwindCSS, Zustand
- **Базы данных:** PostgreSQL, MongoDB, Redis, ClickHouse
- **Поиск:** Elasticsearch
- **Файлы и стриминг:** MinIO/S3, ffmpeg, HLS
- **Кеш и очереди:** Redis, Redis Streams, Celery
- **Контейнеризация:** Docker, docker-compose, .env
- **CI/CD:** (в будущем) GitHub Actions / GitLab CI
- **Тесты:** pytest, Playwright, Django tests

---

## 🔨 Структура проекта

### /melo-platform
### │
### ├── user-service/
### ├── track-service/
### ├── remix-service/
### ├── comment-service/
### ├── chat-service/
### ├── analytics-service/
### ├── search-service/
### ├── media-service/
### ├── notification-service/
### ├── frontend/
### ├── gateway/ # Nginx config
### ├── docker-compose.yml
### ├── .env/
### └── docs/


---

## 🧑‍💻 Разделение задач

### Backend
- Проектирование моделей (ORM)
- API
- Хранение файлов
- Генерация HLS
- Интеграции с Redis, ClickHouse, Elasticsearch
- Валидации, безопасность, тесты

### Frontend
- Создание прототипа UI/UX
- Реализация интерфейса на React
- Взаимодействие с API
- Реализация WebSocket (чат), фильтров, плеера

### DevOps
- Docker-окружение
- docker-compose + сети
- Nginx конфиг
- Подключение внешних сервисов
- Поддержка .env

### Тестирование
- Unit / интеграционные тесты
- UI-тесты (Playwright)
- Локальная отладка и мануальное тестирование

---

## 🎯 Цель

- Создать pet-проект с микросервисной архитектурой
- Прокачаться в Django, React, FastAPI, DevOps
- Поднять уровень до уверенного Junior → Middle

---

## 📌 Примечания

- Работа ведется **в фоновом режиме**: по вечерам и выходным, в зависимости от загруженности (работа, учеба, здоровье)
- Приоритет: **получение опыта и постепенное развитие**, а не скорость

---

## 🚀 Поехали!
