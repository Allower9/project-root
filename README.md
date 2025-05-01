# project-root
🚀 CI/CD FastAPI + NGINX App
📦 Структура проекта
bash
Копировать
Редактировать
project-root/
├── backend/               # Backend на FastAPI
│   ├── app.py             # API-приложение
│   ├── Dockerfile         # Сборка образа backend
│   └── requirements.txt   # Зависимости backend
├── nginx/                 # Frontend (Nginx + HTML)
│   ├── app.conf           # Конфиг для Nginx
│   ├── Dockerfile         # Сборка образа nginx
│   └── index.html         # Статическая страница
├── docker-compose.yml     # Комбинирует backend и nginx
├── .github/
│   └── workflows/
│       └── deploy.yml     # GitHub Actions CI/CD
└── README.md              # Документация
⚙️ Запуск локально (Docker Compose)
bash
Копировать
Редактировать
git clone https://github.com/<yourname>/<repo>.git
cd <repo>
docker-compose up -d --build
Доступ к приложению:

http://localhost/ — фронтенд (index.html)

http://localhost/api/ — API от FastAPI

🚀 CI/CD (GitHub Actions)
🔑 Secrets (в настройках репозитория):
Название	Что хранить
DOCKER_USERNAME	Логин Docker Hub
DOCKER_PASSWORD	Пароль Docker Hub
PROD_SSH_PRIVATE_KEY	Приватный ключ с вашей рабочей станции
PROD_SERVER_IP	IP адрес production-сервера (например: 176....)

📤 Что происходит при git push:
Собираются образы backend и nginx

Заливаются в Docker Hub

CI/CD подключается к прод-серверу по SSH

Обновляется docker-compose.yml

Производится деплой

