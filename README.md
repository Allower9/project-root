# project-root
# 🚀 CI/CD FastAPI + NGINX App

## 📦 Структура проекта

```bash
project-root/
├── backend/          # Backend на FastAPI
│   ├── app.py        # API-приложение
│   ├── Dockerfile    # Сборка образа backend
│   └── requirements.txt # Зависимости backend
├── nginx/            # Frontend (Nginx + HTML)
│   ├── app.conf      # Конфиг для Nginx
│   ├── Dockerfile    # Сборка образа nginx
│   └── index.html    # Статическая страница
├── docker-compose.yml # Комбинирует backend и nginx
├── .github/
│   └── workflows/
│       └── deploy.yml # GitHub Actions CI/CD
└── README.md         # Документация
```
⚙️ Запуск локально (Docker Compose)
```bash
git clone https://github.com/Allower9/project-root.git
cd project-root
docker-compose up -d --build
```
🌐 Доступ к приложению
Frontend: http://localhost

API: http://localhost/api

🔄 CI/CD Workflow
При пуше в ветку main:

Автоматическая сборка Docker-образов

Пуш образов в Docker Hub

Деплой на продакшен-сервер через SSH
