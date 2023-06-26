# Analysis tools

## bandit
Bandit — это инструмент, предназначенный для поиска распространенных проблем безопасности в коде Python. Для этого Bandit обрабатывает каждый файл, строит из него AST и запускает соответствующие плагины для узлов AST. Как только Bandit завершит сканирование всех файлов, он создаст отчет.

Достаточно указать проект и bandit сам найдет python файлы и проанализирует их.

```shell
bandit -r db_api_protection --severity-level all --format json -o ./example.json
```

### Report
Complete Formatter Listing:
- csv 
- custom 
- html 
- [json](https://bandit.readthedocs.io/en/latest/formatters/json.html#module-bandit.formatters.json) 
- screen 
- text 
- xml 
- yaml

### Test Plugins
Bandit поддерживает множество различных тестов для обнаружения различных проблем безопасности в коде Python. Эти тесты создаются в виде плагинов, и могут быть созданы новые для расширения функциональности, предлагаемой Bandit сегодня.

## pyflake
Pyflake советует использовать flake8 для работы с pyflake.

Выходной формат только txt:
- https://flake8.pycqa.org/en/latest/user/options.html#cmdoption-flake8-output-file

## vulture
Vulture находит неиспользуемый код в программах Python. Это полезно для очистки и поиска ошибок в больших базах кода. Если вы запустите Vulture и в своей библиотеке, и в наборе тестов, вы можете найти непроверенный код.

### Report
Выводит все в консоль

```shell
vulture db_api_protection
db_api_protection/backend/app/alembic/versions/a616262daf6d_new_model.py:13: unused variable 'revision' (60% confidence)
db_api_protection/backend/app/alembic/versions/a616262daf6d_new_model.py:14: unused variable 'down_revision' (60% confidence)
db_api_protection/backend/app/alembic/versions/a616262daf6d_new_model.py:15: unused variable 'branch_labels' (60% confidence)
db_api_protection/backend/app/alembic/versions/a616262daf6d_new_model.py:16: unused variable 'depends_on' (60% confidence)
db_api_protection/backend/app/alembic/versions/a616262daf6d_new_model.py:19: unused function 'upgrade' (60% confidence)
db_api_protection/backend/app/alembic/versions/a616262daf6d_new_model.py:53: unused function 'downgrade' (60% confidence)
db_api_protection/backend/app/alembic/versions/d4867f3a4c0a_first_revision.py:13: unused variable 'revision' (60% confidence)
db_api_protection/backend/app/alembic/versions/d4867f3a4c0a_first_revision.py:14: unused variable 'down_revision' (60% confidence)
db_api_protection/backend/app/alembic/versions/d4867f3a4c0a_first_revision.py:15: unused variable 'branch_labels' (60% confidence)
db_api_protection/backend/app/alembic/versions/d4867f3a4c0a_first_revision.py:16: unused variable 'depends_on' (60% confidence)
db_api_protection/backend/app/alembic/versions/d4867f3a4c0a_first_revision.py:19: unused function 'upgrade' (60% confidence)
db_api_protection/backend/app/alembic/versions/d4867f3a4c0a_first_revision.py:49: unused function 'downgrade' (60% confidence)
db_api_protection/backend/app/app/api/api_v1/endpoints/items.py:25: unused function 'read_items' (60% confidence)
db_api_protection/backend/app/app/api/api_v1/endpoints/items.py:44: unused function 'create_item' (60% confidence)
db_api_protection/backend/app/app/api/api_v1/endpoints/items.py:58: unused function 'update_item' (60% confidence)
db_api_protection/backend/app/app/api/api_v1/endpoints/items.py:78: unused function 'read_item' (60% confidence)
db_api_protection/backend/app/app/api/api_v1/endpoints/items.py:96: unused function 'delete_item' (60% confidence)
db_api_protection/backend/app/app/api/api_v1/endpoints/login.py:35: unused function 'login_access_token' (60% confidence)
db_api_protection/backend/app/app/api/api_v1/endpoints/login.py:58: unused function 'test_token' (60% confidence)
db_api_protection/backend/app/app/api/api_v1/endpoints/login.py:66: unused function 'recover_password' (60% confidence)
db_api_protection/backend/app/app/api/api_v1/endpoints/login.py:85: unused function 'reset_password' (60% confidence)
db_api_protection/backend/app/app/api/api_v1/endpoints/statistic.py:25: unused function 'read_statistics' (60% confidence)
db_api_protection/backend/app/app/api/api_v1/endpoints/statistic.py:44: unused function 'create_statistic' (60% confidence)
db_api_protection/backend/app/app/api/api_v1/endpoints/statistic.py:60: unused function 'update_statistic' (60% confidence)
db_api_protection/backend/app/app/api/api_v1/endpoints/statistic.py:80: unused function 'read_statistic_by_id' (60% confidence)
db_api_protection/backend/app/app/api/api_v1/endpoints/statistic.py:98: unused function 'read_statistic_by_tid' (60% confidence)
db_api_protection/backend/app/app/api/api_v1/endpoints/statistic.py:127: unused function 'read_statistic_by_target' (60% confidence)
db_api_protection/backend/app/app/api/api_v1/endpoints/statistic.py:156: unused function 'read_statistic_by_cookie' (60% confidence)
db_api_protection/backend/app/app/api/api_v1/endpoints/statistic.py:185: unused function 'read_statistic_by_platform' (60% confidence)
db_api_protection/backend/app/app/api/api_v1/endpoints/statistic.py:215: unused function 'delete_statistic' (60% confidence)
db_api_protection/backend/app/app/api/api_v1/endpoints/users.py:29: unused function 'read_users' (60% confidence)
db_api_protection/backend/app/app/api/api_v1/endpoints/users.py:43: unused function 'create_user' (60% confidence)
db_api_protection/backend/app/app/api/api_v1/endpoints/users.py:67: unused function 'update_user_me' (60% confidence)
db_api_protection/backend/app/app/api/api_v1/endpoints/users.py:91: unused function 'read_user_me' (60% confidence)
db_api_protection/backend/app/app/api/api_v1/endpoints/users.py:102: unused function 'create_user_open' (60% confidence)
db_api_protection/backend/app/app/api/api_v1/endpoints/users.py:129: unused function 'read_user_by_id' (60% confidence)
db_api_protection/backend/app/app/api/api_v1/endpoints/users.py:148: unused function 'update_user' (60% confidence)
db_api_protection/backend/app/app/api/api_v1/endpoints/utils.py:27: unused function 'test_celery' (60% confidence)
db_api_protection/backend/app/app/api/api_v1/endpoints/utils.py:39: unused function 'test_email' (60% confidence)
db_api_protection/backend/app/app/core/celery_app.py:18: unused attribute 'task_routes' (60% confidence)
db_api_protection/backend/app/app/core/config.py:25: unused variable 'SERVER_NAME' (60% confidence)
db_api_protection/backend/app/app/core/config.py:32: unused function 'assemble_cors_origins' (60% confidence)
db_api_protection/backend/app/app/core/config.py:43: unused function 'sentry_dsn_can_be_blank' (60% confidence)
db_api_protection/backend/app/app/core/config.py:49: unused variable 'POSTGRES_SERVER' (60% confidence)
db_api_protection/backend/app/app/core/config.py:50: unused variable 'POSTGRES_USER' (60% confidence)
db_api_protection/backend/app/app/core/config.py:51: unused variable 'POSTGRES_PASSWORD' (60% confidence)
db_api_protection/backend/app/app/core/config.py:52: unused variable 'POSTGRES_DB' (60% confidence)
db_api_protection/backend/app/app/core/config.py:55: unused function 'assemble_db_connection' (60% confidence)
db_api_protection/backend/app/app/core/config.py:77: unused function 'get_project_name' (60% confidence)
db_api_protection/backend/app/app/core/config.py:87: unused function 'get_emails_enabled' (60% confidence)
db_api_protection/backend/app/app/core/config.py:100: unused class 'Config' (60% confidence)
db_api_protection/backend/app/app/core/config.py:101: unused variable 'case_sensitive' (60% confidence)
db_api_protection/backend/app/app/crud/crud_item.py:35: unused method 'get_multi_by_owner' (60% confidence)
db_api_protection/backend/app/app/db/base_class.py:11: unused function '__tablename__' (60% confidence)
db_api_protection/backend/app/app/models/item.py:30: unused variable 'owner' (60% confidence)
db_api_protection/backend/app/app/models/statistic.py:17: unused import 'DateTime' (90% confidence)
db_api_protection/backend/app/app/models/statistic.py:29: unused variable 'value' (60% confidence)
db_api_protection/backend/app/app/models/statistic.py:31: unused variable 'date' (60% confidence)
db_api_protection/backend/app/app/models/statistic.py:33: unused variable 'time' (60% confidence)
db_api_protection/backend/app/app/models/statistic.py:35: unused variable 'hashid' (60% confidence)
db_api_protection/backend/app/app/models/statistic.py:36: unused variable 'ip' (60% confidence)
db_api_protection/backend/app/app/models/statistic.py:38: unused variable 'customer' (60% confidence)
db_api_protection/backend/app/app/models/statistic.py:40: unused variable 'webGL' (60% confidence)
db_api_protection/backend/app/app/models/statistic.py:41: unused variable 'canvas' (60% confidence)
db_api_protection/backend/app/app/models/statistic.py:42: unused variable 'deviceId' (60% confidence)
db_api_protection/backend/app/app/schemas/item.py:41: unused class 'Config' (60% confidence)
db_api_protection/backend/app/app/schemas/item.py:42: unused variable 'orm_mode' (60% confidence)
db_api_protection/backend/app/app/schemas/item.py:51: unused class 'ItemInDB' (60% confidence)
db_api_protection/backend/app/app/schemas/statistic.py:22: unused variable 'value' (60% confidence)
db_api_protection/backend/app/app/schemas/statistic.py:24: unused variable 'date' (60% confidence)
db_api_protection/backend/app/app/schemas/statistic.py:26: unused variable 'hashid' (60% confidence)
db_api_protection/backend/app/app/schemas/statistic.py:27: unused variable 'ip' (60% confidence)
db_api_protection/backend/app/app/schemas/statistic.py:29: unused variable 'webGL' (60% confidence)
db_api_protection/backend/app/app/schemas/statistic.py:30: unused variable 'canvas' (60% confidence)
db_api_protection/backend/app/app/schemas/statistic.py:31: unused variable 'deviceId' (60% confidence)
db_api_protection/backend/app/app/schemas/statistic.py:49: unused class 'Config' (60% confidence)
db_api_protection/backend/app/app/schemas/statistic.py:50: unused variable 'orm_mode' (60% confidence)
db_api_protection/backend/app/app/schemas/statistic.py:59: unused class 'StatisticInDB' (60% confidence)
db_api_protection/backend/app/app/schemas/token.py:20: unused variable 'access_token' (60% confidence)
db_api_protection/backend/app/app/schemas/token.py:21: unused variable 'token_type' (60% confidence)
db_api_protection/backend/app/app/schemas/user.py:41: unused class 'Config' (60% confidence)
db_api_protection/backend/app/app/schemas/user.py:42: unused variable 'orm_mode' (60% confidence)
db_api_protection/backend/app/app/schemas/user.py:51: unused class 'UserInDB' (60% confidence)
db_api_protection/backend/app/app/worker.py:19: unused variable 'client_sentry' (60% confidence)
db_api_protection/backend/app/app/worker.py:22: unused function 'test_celery' (60% confidence)
```

## pylint
Pylint анализирует ваш код, фактически не запуская его. Он проверяет наличие ошибок, обеспечивает соблюдение стандарта кодирования, ищет code smells и может вносить предложения о том, как код можно реорганизовать.

```shell
pylint db_api_protection/backend/app/app --output-format json --output example.json --max-line-length 150
```

### Report
Вывода в консоль нет, но можно поставить флаг чтобы был.

Json: https://pylint.pycqa.org/en/v2.17.4/user_guide/usage/output.html#output-options



 

