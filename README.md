# CI/CD Quiz Bot

Telegram-бот для подготовки к собеседованиям и изучения **CI/CD** в формате интерактивных тестов.

Проект создан на основе учебного Telegram-бота по Linux и развивается как отдельный проект для изучения практик CI/CD и инструментов автоматизации.

## 🎯 Цель проекта

Помочь изучать CI/CD через короткие тесты с вопросами разного уровня сложности.

Основные направления:

* основы CI/CD;
* GitHub Actions;
* GitLab CI/CD;
* Jenkins;
* Docker в CI/CD;
* Deployment;
* CI/CD Security;
* продвинутые практики CI/CD.

Каждая тема разделена на три уровня:

* **Junior** — базовые понятия и принципы;
* **Middle** — практическое понимание pipeline и его компонентов;
* **Senior** — архитектура, безопасность, оптимизация и разбор реальных ситуаций.

## 🧩 Формат обучения

Пользователь выбирает:

```text
Тема
  ↓
Уровень сложности
  ↓
Вопрос
  ↓
Варианты ответа
  ↓
Результат
```

Пример:

```text
Основы CI/CD
    ├── Junior
    ├── Middle
    └── Senior

GitHub Actions
    ├── Junior
    ├── Middle
    └── Senior

GitLab CI/CD
    ├── Junior
    ├── Middle
    └── Senior

Jenkins
    ├── Junior
    ├── Middle
    └── Senior
```

## 🛠️ Технологии

Проект использует:

* Python 3.12
* Telegram Bot API
* pytest
* Flake8
* Black
* Docker
* Docker Compose
* GitHub Actions

## 📁 Структура проекта

```text
CI-CD_quiz/
│
├── .github/
│   └── workflows/
│       └── ci.yml
│
├── bot/
│   ├── data/
│   ├── db/
│   ├── handlers/
│   ├── keyboards/
│   ├── services/
│   ├── states.py
│   ├── config.py
│   └── __main__.py
│
├── tests/
│
├── Dockerfile
├── docker-compose.dev.yml
├── docker-compose.prod.yml
├── requirements.txt
├── .flake8
├── .gitignore
└── README.md
```

## 🚀 Локальный запуск

### 1. Клонирование репозитория

```bash
git clone https://github.com/shura-dvornikova/CI-CD_quiz.git
cd CI-CD_quiz
```

### 2. Создание виртуального окружения

```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 3. Установка зависимостей

```bash
python -m pip install --upgrade pip
pip install -r requirements.txt
```

### 4. Переменные окружения

Секретные значения хранятся в `.env`.

Файл `.env` не должен добавляться в Git.

Пример необходимых переменных можно оформить в `.env.example`.

## 🧪 Проверка проекта

Перед отправкой изменений в GitHub рекомендуется локально выполнить проверки.

### Flake8

```bash
flake8 --config .flake8 .
```

### Black

Проверка форматирования:

```bash
black --check .
```

Автоматическое форматирование:

```bash
black .
```

### Pytest

```bash
python -m pytest -q
```

## 🔄 CI/CD

Проект использует GitHub Actions для Continuous Integration.

Текущий pipeline запускается при:

* `push` в `main`;
* `push` в `develop`;
* создании или изменении Pull Request в `main` или `develop`.

Текущий CI выполняет:

```text
Push / Pull Request
        ↓
Checkout
        ↓
Python 3.12
        ↓
Install dependencies
        ↓
Flake8
        ↓
Black
        ↓
Pytest
        ↓
Success / Failure
```

Workflow находится в:

```text
.github/workflows/ci.yml
```

На текущем этапе CI **только проверяет проект**. Deployment на сервер не выполняется.

В дальнейшем pipeline будет расширен:

```text
CI
 ↓
Tests
 ↓
Docker build
 ↓
Docker image
 ↓
Registry
 ↓
Deployment
 ↓
Production
```

## 🐳 Docker

Проект содержит Dockerfile и конфигурации Docker Compose:

```text
Dockerfile
docker-compose.dev.yml
docker-compose.prod.yml
```

Docker используется для последующего построения воспроизводимого процесса сборки и deployment.

## 🔐 Безопасность

Секреты не должны храниться в Git-репозитории.

В `.gitignore` исключены:

```text
.env
.env.dev
.env.prod
```

Production credentials и другие секретные значения должны передаваться через защищённые механизмы CI/CD.

## 📚 Учебная цель

Проект одновременно является рабочим Telegram-ботом и учебным стендом для изучения CI/CD.

В процессе развития проекта планируется самостоятельно реализовать:

* Continuous Integration;
* автоматические тесты;
* Docker build;
* публикацию Docker image;
* CI/CD variables и secrets;
* GitHub Actions;
* deployment на сервер;
* staging и production environments;
* rollback;
* health checks;
* безопасный deployment;
* оптимизацию pipeline.

## 📌 Статус проекта

Проект находится в разработке.

### Реализовано

* [x] Базовая структура Telegram-бота
* [x] Система тестов
* [x] Flake8
* [x] Black
* [x] GitHub Actions CI
* [x] Проверка CI на push
* [ ] Вопросы по всем темам CI/CD
* [ ] Docker build в CI
* [ ] Docker Registry
* [ ] Staging deployment
* [ ] Production deployment
* [ ] Rollback
* [ ] Deployment security

## 👤 Автор

**Shura Dvornikova**

Проект создан как практический учебный проект для изучения CI/CD и подготовки к техническим собеседованиям.
