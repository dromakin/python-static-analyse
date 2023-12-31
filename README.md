# python-static-analyse
Instruments for static analyse in Python with examples

Лучшие инструменты, которые показали себя на практике по частям статического анализа в Python.

## Анализ кода
- bandit
- pylint

У Bandit приятнее api, в cli достаточно просто указать путь до проекта с github и дальше он сам все сделает. Найдет нужные файлы и сделает отчет в том формате, в котором требуется.
С pylint немного сложнее, приходиться указывать путь прям до конкретного модуля с __init__.py, чтобы заставить его работать так как bandit.
У обоих есть возможность написания плагинов для работы.

## Построение синтаксического дерева, диаграмму классов
- pyreverse (входит в pylint)
- code2flow

code2flow значительно лучше генерирует диаграмму классов с описанием вызовов кто кого вызывает.

## Linters
- ruff (улучшенный вариант flake8)
- pylint

Если нам не важна скорость и важно, чтобы было все на 1 ЯП, то смело берем pylint.
Если нем важна скорость, то используем ruff.

## Type checkers
- mypy

Лучше инструмента нет, но для работы нужно знать заранее все зависимости проекта, чтобы установить нужные зависимости для проведения анализа.
Самый большой минус - выводит все в консоль.

## Статический анализатор
- pylint - это линтер и статический анализатор с разными плагинами.
- semgrep - это быстрый механизм статического анализа с открытым исходным кодом.

Если нам важна возможность поддержки проекта на Python (с возможностью написания плагинов и гибкой настройкой), то pylint, иначе - semgrep.

## Проекты, которые использовались для тестирования инструментов
- https://github.com/we45/Vulnerable-Flask-App
- https://github.com/dromakin/db_api_protection
