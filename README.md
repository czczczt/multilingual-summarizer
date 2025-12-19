# Multilingual Learning Material Summarizer

Инструмент для автоматического резюмирования учебных материалов с поддержкой нескольких языков (English, Russian, German).

## Описание

Система разработана для автоматизации процесса создания кратких резюме из учебных материалов на различных языках. Особенно полезна для:

- Быстрого усвоения больших объемов информации
- Создания справочников и шпаргалок
- Преподавателей, готовящих материалы для студентов
- Исследователей, работающих с многоязычными данными

**Область применения:** AI в образовании, обработка текста (NLP)

## Особенности

- ✓ Поддержка 3 языков: English, Russian, German
- ✓ Выбор уровня сжатия: 20%, 30%, 50%
- ✓ Выделение ключевых моментов
- ✓ Сохранение результатов в файлы
- ✓ Автоматическое определение языка текста

## Установка

### Требования
- Python 3.8+
- pip

### Быстрый старт

```bash
python -m venv venv
venv\Scripts\activate
pip install -r requirements.txt
```

## Использование

### Базовый пример

```python
from src.summarizer import TextSummarizer

summarizer = TextSummarizer()

text = """Machine learning is a subset of artificial intelligence that focuses on 
the development of computer programs that can learn and adapt from experience."""

summary = summarizer.summarize(text, compression_ratio=0.3)
print(summary)
```

## Структура проекта

```
multilingual-summarizer/
├── src/
│   ├── __init__.py
│   ├── main.py
│   ├── summarizer.py
│   ├── language_detector.py
│   └── utils.py
├── tests/
│   ├── __init__.py
│   ├── test_summarizer.py
│   ├── test_main.py
│   └── test_language.py
├── data/
│   ├── sample.txt
│   └── sample.csv
├── .github/workflows/
│   ├── tests.yml
│   └── scheduled-analysis.yml
├── .gitignore
├── requirements.txt
└── README.md
```

## Тестирование

```bash
pytest                           # Все тесты
pytest --cov=src tests/          # С покрытием
flake8 src tests                 # Проверка PEP8
black src tests                  # Форматирование
```

## CI/CD

- Автоматическое тестирование на каждый push
- Проверка PEP 8 (flake8)
- Scheduled workflow для анализа данных (раз в неделю)
- Artifact upload с результатами
