# 📦 Parcel Tracker

Простое CLI-приложение на Go для отслеживания посылок. Хранит данные в SQLite и поддерживает автоматическое тестирование и деплой через GitHub Actions и DockerHub.

## 🚀 Функциональность

- Добавление и отслеживание посылок
- Хранение данных в SQLite
- Покрытие unit-тестами
- Сборка и публикация Docker-образа
- CI/CD через GitHub Actions

## 📁 Структура проекта

- `main.go` — точка входа
- `parcel.go` — логика работы с посылками
- `parcel_test.go` — тесты
- `dockerfile` — инструкция сборки Docker-образа
- `.github/workflows/push.yaml` — CI/CD workflow
- `tracker.db` — SQLite база данных (локальная)

## 🐳 Docker

Собрать образ:
```bash
docker build -t yourdockerhubusername/parcel-tracker .
```

Запустить контейнер:
```bash
docker run --rm yourdockerhubusername/parcel-tracker
```

## 🧪 Тесты

Для запуска всех тестов:
```bash
go test ./...
```

## ⚙️ CI/CD (GitHub Actions)

В проекте настроен workflow `.github/workflows/push.yaml`, включающий два job'а:

1. **Тестирование при push'е в репозиторий**:
   - Проверка кода (`go vet`)
   - Запуск юнит-тестов (`go test`)

2. **Автопубликация при создании Git-тега**:
   - Сборка Docker-образа
   - Push на DockerHub

✅ Перед отправкой убедись, что все job'ы завершились успешно.

## 🐙 DockerHub

Docker-образ публикуется сюда:
```
https://hub.docker.com/r/<yourdockerhubusername>/parcel-tracker
```

## 👤 Автор

**Константин Сундуков**  
[GitHub](https://github.com/Spok95)
