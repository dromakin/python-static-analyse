# Type checkers

## mypy
Mypy — это средство проверки статических типов для Python.

Средства проверки типов помогают убедиться, что вы правильно используете переменные и функции в коде. С помощью mypy добавьте подсказки типов (PEP 484) в свои программы Python, и mypy предупредит вас, когда вы неправильно используете эти типы.

Python — это динамический язык, поэтому обычно вы видите ошибки в своем коде только при попытке запустить его. Mypy — это статическая проверка, поэтому она находит ошибки в ваших программах, даже не запуская их!

Mypy — это дополнительная статическая проверка типов для Python, цель которой — объединить преимущества динамической (или «утиной») типизации и статической типизации. Mypy сочетает в себе выразительную мощь и удобство Python с мощной системой типов и проверкой типов во время компиляции. Тип Mypy проверяет стандартные программы Python; запускайте их, используя любую виртуальную машину Python, практически без накладных расходов во время выполнения.

```shell
mypy --check-untyped-defs --html-report . -m db_api_protection/backend/app/app
mypy --xml-report . db_api_protection/backend/app/app
```

Вывод:

```shell
db_api_protection/backend/app/app/statistics_data_migration/__init__.py:15: error: Library stubs not installed for "pandas"  [import]
db_api_protection/backend/app/app/statistics_data_migration/__init__.py:15: note: Hint: "python3 -m pip install pandas-stubs"
db_api_protection/backend/app/app/statistics_data_migration/__init__.py:16: error: Cannot find implementation or library stub for module named "numpy"  [import]
db_api_protection/backend/app/app/schemas/user.py:16: error: Cannot find implementation or library stub for module named "pydantic"  [import]
db_api_protection/backend/app/app/schemas/token.py:16: error: Cannot find implementation or library stub for module named "pydantic"  [import]
db_api_protection/backend/app/app/schemas/statistic.py:16: error: Cannot find implementation or library stub for module named "pydantic"  [import]
db_api_protection/backend/app/app/schemas/msg.py:14: error: Cannot find implementation or library stub for module named "pydantic"  [import]
db_api_protection/backend/app/app/schemas/item.py:16: error: Cannot find implementation or library stub for module named "pydantic"  [import]
db_api_protection/backend/app/app/db/base_class.py:3: error: Cannot find implementation or library stub for module named "sqlalchemy.ext.declarative"  [import]
db_api_protection/backend/app/app/core/celery_app.py:14: error: Cannot find implementation or library stub for module named "celery"  [import]
db_api_protection/backend/app/app/crud/base.py:16: error: Cannot find implementation or library stub for module named "fastapi.encoders"  [import]
db_api_protection/backend/app/app/crud/base.py:17: error: Cannot find implementation or library stub for module named "pydantic"  [import]
db_api_protection/backend/app/app/crud/base.py:18: error: Cannot find implementation or library stub for module named "sqlalchemy.orm"  [import]
db_api_protection/backend/app/app/models/user.py:16: error: Cannot find implementation or library stub for module named "sqlalchemy"  [import]
db_api_protection/backend/app/app/models/user.py:17: error: Cannot find implementation or library stub for module named "sqlalchemy.orm"  [import]
db_api_protection/backend/app/app/models/statistic.py:17: error: Cannot find implementation or library stub for module named "sqlalchemy"  [import]
db_api_protection/backend/app/app/models/statistic.py:18: error: Cannot find implementation or library stub for module named "sqlalchemy.orm"  [import]
db_api_protection/backend/app/app/models/item.py:16: error: Cannot find implementation or library stub for module named "sqlalchemy"  [import]
db_api_protection/backend/app/app/models/item.py:17: error: Cannot find implementation or library stub for module named "sqlalchemy.orm"  [import]
db_api_protection/backend/app/app/crud/crud_statistic.py:16: error: Cannot find implementation or library stub for module named "fastapi.encoders"  [import]
db_api_protection/backend/app/app/crud/crud_statistic.py:17: error: Cannot find implementation or library stub for module named "sqlalchemy.orm"  [import]
db_api_protection/backend/app/app/crud/crud_statistic.py:39: error: Unexpected keyword argument "customer_id" for "Statistic"  [call-arg]
venv/lib/python3.10/site-packages/mypy/typeshed/stdlib/builtins.pyi:89: note: "Statistic" defined here
db_api_protection/backend/app/app/crud/crud_item.py:16: error: Cannot find implementation or library stub for module named "fastapi.encoders"  [import]
db_api_protection/backend/app/app/crud/crud_item.py:17: error: Cannot find implementation or library stub for module named "sqlalchemy.orm"  [import]
db_api_protection/backend/app/app/crud/crud_item.py:29: error: Unexpected keyword argument "owner_id" for "Item"  [call-arg]
venv/lib/python3.10/site-packages/mypy/typeshed/stdlib/builtins.pyi:89: note: "Item" defined here
db_api_protection/backend/app/app/core/config.py:17: error: Cannot find implementation or library stub for module named "pydantic"  [import]
db_api_protection/backend/app/app/worker.py:14: error: Cannot find implementation or library stub for module named "raven"  [import]
db_api_protection/backend/app/app/utils.py:19: error: Cannot find implementation or library stub for module named "emails"  [import]
db_api_protection/backend/app/app/utils.py:20: error: Cannot find implementation or library stub for module named "emails.template"  [import]
db_api_protection/backend/app/app/utils.py:21: error: Library stubs not installed for "jose"  [import]
db_api_protection/backend/app/app/tests/utils/utils.py:5: error: Cannot find implementation or library stub for module named "fastapi.testclient"  [import]
db_api_protection/backend/app/app/tests/api/api_v1/test_login.py:3: error: Cannot find implementation or library stub for module named "fastapi.testclient"  [import]
db_api_protection/backend/app/app/tests/api/api_v1/test_celery.py:3: error: Cannot find implementation or library stub for module named "fastapi.testclient"  [import]
db_api_protection/backend/app/app/db/session.py:14: error: Cannot find implementation or library stub for module named "sqlalchemy"  [import]
db_api_protection/backend/app/app/db/session.py:15: error: Cannot find implementation or library stub for module named "sqlalchemy.orm"  [import]
db_api_protection/backend/app/app/core/security.py:17: error: Library stubs not installed for "jose"  [import]
db_api_protection/backend/app/app/core/security.py:18: error: Library stubs not installed for "passlib.context"  [import]
db_api_protection/backend/app/app/core/security.py:18: note: Hint: "python3 -m pip install types-passlib"
db_api_protection/backend/app/app/core/security.py:29: error: Incompatible default for argument "expires_delta" (default has type "None", argument has type "timedelta")  [assignment]
db_api_protection/backend/app/app/core/security.py:29: note: PEP 484 prohibits implicit Optional. Accordingly, mypy has changed its default to no_implicit_optional=True
db_api_protection/backend/app/app/core/security.py:29: note: Use https://github.com/hauntsaninja/no_implicit_optional to automatically upgrade your codebase
db_api_protection/backend/app/app/tests_pre_start.py:16: error: Cannot find implementation or library stub for module named "tenacity"  [import]
db_api_protection/backend/app/app/celeryworker_pre_start.py:16: error: Cannot find implementation or library stub for module named "tenacity"  [import]
db_api_protection/backend/app/app/backend_pre_start.py:16: error: Cannot find implementation or library stub for module named "tenacity"  [import]
db_api_protection/backend/app/app/crud/crud_user.py:16: error: Cannot find implementation or library stub for module named "sqlalchemy.orm"  [import]
db_api_protection/backend/app/app/crud/crud_user.py:29: error: Unexpected keyword argument "email" for "User"  [call-arg]
venv/lib/python3.10/site-packages/mypy/typeshed/stdlib/builtins.pyi:89: note: "User" defined here
db_api_protection/backend/app/app/crud/crud_user.py:29: error: Unexpected keyword argument "hashed_password" for "User"  [call-arg]
venv/lib/python3.10/site-packages/mypy/typeshed/stdlib/builtins.pyi:89: note: "User" defined here
db_api_protection/backend/app/app/crud/crud_user.py:29: error: Unexpected keyword argument "full_name" for "User"  [call-arg]
venv/lib/python3.10/site-packages/mypy/typeshed/stdlib/builtins.pyi:89: note: "User" defined here
db_api_protection/backend/app/app/crud/crud_user.py:29: error: Unexpected keyword argument "is_superuser" for "User"  [call-arg]
venv/lib/python3.10/site-packages/mypy/typeshed/stdlib/builtins.pyi:89: note: "User" defined here
db_api_protection/backend/app/app/tests/utils/user.py:3: error: Cannot find implementation or library stub for module named "fastapi.testclient"  [import]
db_api_protection/backend/app/app/tests/utils/user.py:4: error: Cannot find implementation or library stub for module named "sqlalchemy.orm"  [import]
db_api_protection/backend/app/app/tests/crud/test_user.py:1: error: Cannot find implementation or library stub for module named "fastapi.encoders"  [import]
db_api_protection/backend/app/app/tests/crud/test_user.py:2: error: Cannot find implementation or library stub for module named "sqlalchemy.orm"  [import]
db_api_protection/backend/app/app/tests/api/api_v1/test_users.py:3: error: Cannot find implementation or library stub for module named "fastapi.testclient"  [import]
db_api_protection/backend/app/app/tests/api/api_v1/test_users.py:4: error: Cannot find implementation or library stub for module named "sqlalchemy.orm"  [import]
db_api_protection/backend/app/app/db/init_db.py:14: error: Cannot find implementation or library stub for module named "sqlalchemy.orm"  [import]
db_api_protection/backend/app/app/db/init_db.py:15: error: Cannot find implementation or library stub for module named "pydantic"  [import]
db_api_protection/backend/app/app/api/deps.py:16: error: Cannot find implementation or library stub for module named "fastapi"  [import]
db_api_protection/backend/app/app/api/deps.py:17: error: Cannot find implementation or library stub for module named "fastapi.security"  [import]
db_api_protection/backend/app/app/api/deps.py:18: error: Library stubs not installed for "jose"  [import]
db_api_protection/backend/app/app/api/deps.py:18: note: Hint: "python3 -m pip install types-python-jose"
db_api_protection/backend/app/app/api/deps.py:18: note: (or run "mypy --install-types" to install all missing stub packages)
db_api_protection/backend/app/app/api/deps.py:19: error: Cannot find implementation or library stub for module named "pydantic"  [import]
db_api_protection/backend/app/app/api/deps.py:20: error: Cannot find implementation or library stub for module named "sqlalchemy.orm"  [import]
db_api_protection/backend/app/app/tests/utils/item.py:3: error: Cannot find implementation or library stub for module named "sqlalchemy.orm"  [import]
db_api_protection/backend/app/app/tests/crud/test_item.py:1: error: Cannot find implementation or library stub for module named "sqlalchemy.orm"  [import]
db_api_protection/backend/app/app/api/api_v1/endpoints/utils.py:16: error: Cannot find implementation or library stub for module named "fastapi"  [import]
db_api_protection/backend/app/app/api/api_v1/endpoints/utils.py:17: error: Cannot find implementation or library stub for module named "pydantic.networks"  [import]
db_api_protection/backend/app/app/api/api_v1/endpoints/users.py:16: error: Cannot find implementation or library stub for module named "fastapi"  [import]
db_api_protection/backend/app/app/api/api_v1/endpoints/users.py:17: error: Cannot find implementation or library stub for module named "fastapi.encoders"  [import]
db_api_protection/backend/app/app/api/api_v1/endpoints/users.py:18: error: Cannot find implementation or library stub for module named "pydantic.networks"  [import]
db_api_protection/backend/app/app/api/api_v1/endpoints/users.py:19: error: Cannot find implementation or library stub for module named "sqlalchemy.orm"  [import]
db_api_protection/backend/app/app/api/api_v1/endpoints/statistic.py:16: error: Cannot find implementation or library stub for module named "fastapi"  [import]
db_api_protection/backend/app/app/api/api_v1/endpoints/statistic.py:17: error: Cannot find implementation or library stub for module named "sqlalchemy.orm"  [import]
db_api_protection/backend/app/app/api/api_v1/endpoints/statistic.py:122: error: "list[list[Any]]" has no attribute "customer_id"  [attr-defined]
db_api_protection/backend/app/app/api/api_v1/endpoints/statistic.py:151: error: "list[list[Any]]" has no attribute "customer_id"  [attr-defined]
db_api_protection/backend/app/app/api/api_v1/endpoints/statistic.py:180: error: "list[list[Any]]" has no attribute "customer_id"  [attr-defined]
db_api_protection/backend/app/app/api/api_v1/endpoints/statistic.py:200: error: Unexpected keyword argument "customer_id" for "get_multi_by_platform" of "CRUDStatistic"  [call-arg]
db_api_protection/backend/app/app/crud/crud_statistic.py:137: note: "get_multi_by_platform" of "CRUDStatistic" defined here
db_api_protection/backend/app/app/api/api_v1/endpoints/statistic.py:209: error: "list[list[Any]]" has no attribute "customer_id"  [attr-defined]
db_api_protection/backend/app/app/api/api_v1/endpoints/statistic.py:228: error: "Statistic" has no attribute "owner_id"  [attr-defined]
db_api_protection/backend/app/app/api/api_v1/endpoints/login.py:17: error: Cannot find implementation or library stub for module named "fastapi"  [import]
db_api_protection/backend/app/app/api/api_v1/endpoints/login.py:18: error: Cannot find implementation or library stub for module named "fastapi.security"  [import]
db_api_protection/backend/app/app/api/api_v1/endpoints/login.py:19: error: Cannot find implementation or library stub for module named "sqlalchemy.orm"  [import]
db_api_protection/backend/app/app/api/api_v1/endpoints/items.py:16: error: Cannot find implementation or library stub for module named "fastapi"  [import]
db_api_protection/backend/app/app/api/api_v1/endpoints/items.py:17: error: Cannot find implementation or library stub for module named "sqlalchemy.orm"  [import]
db_api_protection/backend/app/app/api/api_v1/endpoints/items.py:17: note: See https://mypy.readthedocs.io/en/stable/running_mypy.html#missing-imports
db_api_protection/backend/app/app/api/api_v1/endpoints/items.py:38: error: "CRUDItem" has no attribute "get_multi_by_customer"; maybe "get_multi_by_owner"?  [attr-defined]
db_api_protection/backend/app/app/tests/api/api_v1/test_items.py:1: error: Cannot find implementation or library stub for module named "fastapi.testclient"  [import]
db_api_protection/backend/app/app/tests/api/api_v1/test_items.py:2: error: Cannot find implementation or library stub for module named "sqlalchemy.orm"  [import]
db_api_protection/backend/app/app/api/api_v1/api.py:15: error: Cannot find implementation or library stub for module named "fastapi"  [import]
db_api_protection/backend/app/app/main.py:14: error: Cannot find implementation or library stub for module named "fastapi"  [import]
db_api_protection/backend/app/app/main.py:15: error: Cannot find implementation or library stub for module named "starlette.middleware.cors"  [import]
db_api_protection/backend/app/app/tests/conftest.py:17: error: Cannot find implementation or library stub for module named "pytest"  [import]
db_api_protection/backend/app/app/tests/conftest.py:18: error: Cannot find implementation or library stub for module named "fastapi.testclient"  [import]
db_api_protection/backend/app/app/tests/conftest.py:19: error: Cannot find implementation or library stub for module named "sqlalchemy.orm"  [import]
Generated XML report: python-static-analyse/index.xml
Found 88 errors in 42 files (checked 58 source files)
```

[Самый большой минус в том, что для того чтобы mypy сработал корректно, нам нужно установить необходимые зависимости, чтобы правильно обработать тип.](https://mypy.readthedocs.io/en/stable/getting_started.html#types-from-libraries)

Если этого не сделать, то отчет будет пустой!


## pyright
Pyright — это полнофункциональная стандартная программа проверки статических типов для Python. Он разработан для обеспечения высокой производительности и может использоваться с большими базами исходных текстов Python.

```shell
pyright --outputjson -p /Users/dromakin/GitHubDesktop/db_api_protection/backend/app/app
```

Вывод:
```shell
{
    "version": "1.1.316",
    "time": "1687784226310",
    "generalDiagnostics": [],
    "summary": {
        "filesAnalyzed": 0,
        "errorCount": 0,
        "warningCount": 0,
        "informationCount": 0,
        "timeInSec": 0
    }
}
```

## pytype
Pytype проверяет и выводит типы для вашего кода Python, не требуя аннотаций типов. Pytype может:
- Простой код Python Lint, помечающий распространенные ошибки, такие как неправильно написанные имена атрибутов, неправильные вызовы функций и многое другое, даже в пределах файла.
- Внедряйте предоставленные пользователем аннотации типов. Хотя аннотации необязательны для pytype, он будет проверять и применять их там, где они есть.
- Создавайте аннотации типов в автономных файлах («файлы pyi»), которые можно объединить обратно в исходный код Python с помощью предоставленного инструмента merge-pyi.

Pytype — статический анализатор; он не выполняет код, который анализирует.

```shell
pytype db_api_protection/backend/        
Computing dependencies
Analyzing 61 sources with 0 local dependencies
ninja: Entering directory `.pytype'
[1/63] check app.core.config
FAILED: /Users/dromakin/PycharmProjects/python-static-analyse/.pytype/pyi/app/core/config.pyi 
/Users/dromakin/PycharmProjects/python-static-analyse/venv/bin/python -m pytype.single --imports_info /Users/dromakin/PycharmProjects/python-static-analyse/.pytype/imports/app.core.config.imports --module-name app.core.config --platform darwin -V 3.10 -o /Users/dromakin/PycharmProjects/python-static-analyse/.pytype/pyi/app/core/config.pyi --analyze-annotated --nofail --quick /Users/dromakin/GitHubDesktop/db_api_protection/backend/app/app/core/config.py
File "/Users/dromakin/GitHubDesktop/db_api_protection/backend/app/app/core/config.py", line 17, in <module>: Can't find module 'pydantic'. [import-error]

For more details, see https://google.github.io/pytype/errors.html#import-error
ninja: build stopped: subcommand failed.
Leaving directory '.pytype'
```

Код рабочий в проекте, но pytype останавливается с ошибкой.
