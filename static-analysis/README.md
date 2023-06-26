# Static analysis

## jedi
Jedi — это инструмент статического анализа для Python, который обычно используется в плагинах IDE/редакторов. Jedi уделяет особое внимание функциям автозаполнения и перехода. Другие функции включают рефакторинг, поиск по коду и поиск ссылок.
Jedi — потрясающая библиотека автодополнения, статического анализа и рефакторинга для Python.

Чтобы его использовать как pylint, нужно писать плагин.
В качестве ошибок он может находить только синтаксические ошибки.

## pylint
Pylint анализирует ваш код, фактически не запуская его. Он проверяет наличие ошибок, обеспечивает соблюдение стандарта кодирования, ищет code smells и может вносить предложения о том, как код можно реорганизовать.

```shell
pylint Vulnerable-Flask-App --output-format json --output example.json --max-line-length 150
```

### Report
Вывода в консоль нет, но можно поставить флаг чтобы был.

Json: https://pylint.pycqa.org/en/v2.17.4/user_guide/usage/output.html#output-options

## semgrep
Semgrep — это быстрый механизм статического анализа с открытым исходным кодом для поиска ошибок, выявления уязвимостей в сторонних зависимостях и обеспечения соблюдения стандартов кода. Semgrep анализирует код локально на вашем компьютере или в вашей среде сборки: код никогда не загружается

```shell
semgrep --config=auto Vulnerable-Flask-App --output scan_results_1.json --json
```

### Report
Json: [scan_results.json](semgrep%2Fscan_results.json)

https://semgrep.dev/docs/cli-reference/

# Results
pylint находит ошибки лучше, чем semgrep, но у semgrep отчет в json просто лучший (в нем есть абсолютно все и даже больше).

Отчет pylint: [example.json](pylint%2Fexample.json)

Отчет semgrep: [scan_results.json](semgrep%2Fscan_results.json)

Самое главное отличие:
- pylint - нужно указывать путь до проекта с __init__.py, если их нет, то в отчете будет пусто!
- semgrep имеет большое преимущество - анализирует все файлы проекта (python, js, etc) и создает единый отчет в формате json (язык анализируемый можно выбрать в cli, если нужно)
