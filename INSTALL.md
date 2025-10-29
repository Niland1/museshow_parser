# Инструкция по установке

## Требования

- Python 3.11 или выше
- Poetry (менеджер зависимостей Python)

## Шаг 1: Установка Python

Если у вас еще не установлен Python:

1. Скачайте Python с официального сайта: https://www.python.org/downloads/
2. При установке **обязательно** отметьте галочку "Add Python to PATH"
3. Проверьте установку:
```bash
python --version
```

## Шаг 2: Установка Poetry

Poetry - это современный менеджер зависимостей для Python.

### Windows (PowerShell):
```powershell
(Invoke-WebRequest -Uri https://install.python-poetry.org -UseBasicParsing).Content | python -
```

### Linux/macOS:
```bash
curl -sSL https://install.python-poetry.org | python3 -
```

Проверьте установку:
```bash
poetry --version
```

## Шаг 3: Установка зависимостей проекта

Откройте терминал в папке с парсером и выполните:

```bash
# Установка всех зависимостей
poetry install

# Установка браузеров для Playwright
poetry run playwright install
```

## Шаг 4: Запуск парсера

```bash
poetry run python concerts_parser.py
```

Парсер начнет работу и создаст Excel файл с результатами в текущей папке.

## Альтернативный способ (без Poetry)

Если вы не хотите использовать Poetry, можно установить зависимости через pip:

```bash
# Создание виртуального окружения
python -m venv venv

# Активация виртуального окружения
# Windows:
venv\Scripts\activate
# Linux/macOS:
source venv/bin/activate

# Установка зависимостей
pip install playwright pandas openpyxl

# Установка браузеров
playwright install

# Запуск парсера
python concerts_parser.py
```

## Возможные проблемы

### Ошибка "playwright not found"
Выполните:
```bash
poetry run playwright install
```

### Ошибка "Module not found"
Переустановите зависимости:
```bash
poetry install
```

### Парсер не находит концерты
Проверьте подключение к интернету и доступность сайта museshow.ru

## Результат работы

После успешного запуска в папке появится файл вида:
```
concerts_2025-10-22_01-30-45.xlsx
```

Файл содержит таблицу со всеми спарсенными концертами.

## Логи

Все действия парсера записываются в файл `parser.log` для отладки.
