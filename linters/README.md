# Linters

## pylint
Pylint анализирует ваш код, фактически не запуская его. Он проверяет наличие ошибок, обеспечивает соблюдение стандарта кодирования, ищет code smells и может вносить предложения о том, как код можно реорганизовать.

```shell
pylint db_api_protection/backend/app/app --output-format json --output example.json --max-line-length 150
```

### Report
Вывода в консоль нет, но можно поставить флаг чтобы был.

Json: https://pylint.pycqa.org/en/v2.17.4/user_guide/usage/output.html#output-options

## ruff
Ruff можно использовать для замены Flake8 (плюс десятки плагинов), isort, pydocstyle, yesqa, искоренить, pyupgrade и autoflake, при этом работая в десятки или сотни раз быстрее, чем любой отдельный инструмент.

```shell
ruff check db_api_protection/backend/                             
db_api_protection/backend/app/app/api/api_v1/endpoints/statistic.py:74:89: E501 Line too long (95 > 88 characters)
db_api_protection/backend/app/app/api/api_v1/endpoints/statistic.py:93:89: E501 Line too long (95 > 88 characters)
db_api_protection/backend/app/app/api/api_v1/endpoints/statistic.py:122:89: E501 Line too long (95 > 88 characters)
db_api_protection/backend/app/app/api/api_v1/endpoints/statistic.py:151:89: E501 Line too long (95 > 88 characters)
db_api_protection/backend/app/app/api/api_v1/endpoints/statistic.py:180:89: E501 Line too long (95 > 88 characters)
db_api_protection/backend/app/app/api/api_v1/endpoints/statistic.py:201:89: E501 Line too long (90 > 88 characters)
db_api_protection/backend/app/app/api/api_v1/endpoints/statistic.py:205:89: E501 Line too long (90 > 88 characters)
db_api_protection/backend/app/app/api/api_v1/endpoints/statistic.py:209:89: E501 Line too long (95 > 88 characters)
db_api_protection/backend/app/app/api/api_v1/endpoints/statistic.py:228:89: E501 Line too long (92 > 88 characters)
db_api_protection/backend/app/app/crud/__init__.py:1:24: F401 [*] `.crud_item.item` imported but unused
db_api_protection/backend/app/app/crud/__init__.py:2:24: F401 [*] `.crud_user.user` imported but unused
db_api_protection/backend/app/app/crud/__init__.py:3:29: F401 [*] `.crud_statistic.statistic` imported but unused
db_api_protection/backend/app/app/crud/crud_statistic.py:14:20: F401 [*] `typing.Any` imported but unused
db_api_protection/backend/app/app/crud/crud_statistic.py:14:25: F401 [*] `typing.Dict` imported but unused
db_api_protection/backend/app/app/crud/crud_statistic.py:14:31: F401 [*] `typing.Optional` imported but unused
db_api_protection/backend/app/app/crud/crud_statistic.py:14:41: F401 [*] `typing.Union` imported but unused
db_api_protection/backend/app/app/crud/crud_statistic.py:57:89: E501 Line too long (93 > 88 characters)
db_api_protection/backend/app/app/crud/crud_statistic.py:80:89: E501 Line too long (96 > 88 characters)
db_api_protection/backend/app/app/crud/crud_statistic.py:103:89: E501 Line too long (96 > 88 characters)
db_api_protection/backend/app/app/crud/crud_statistic.py:126:89: E501 Line too long (98 > 88 characters)
db_api_protection/backend/app/app/db/init_db.py:21:89: E501 Line too long (91 > 88 characters)
db_api_protection/backend/app/app/models/__init__.py:1:19: F401 [*] `.item.Item` imported but unused
db_api_protection/backend/app/app/models/__init__.py:2:19: F401 [*] `.user.User` imported but unused
db_api_protection/backend/app/app/models/__init__.py:3:24: F401 [*] `.statistic.Statistic` imported but unused
db_api_protection/backend/app/app/models/statistic.py:14:8: F401 [*] `datetime` imported but unused
db_api_protection/backend/app/app/models/statistic.py:17:24: F401 [*] `sqlalchemy.Boolean` imported but unused
db_api_protection/backend/app/app/models/statistic.py:17:58: F401 [*] `sqlalchemy.DateTime` imported but unused
db_api_protection/backend/app/app/schemas/__init__.py:1:19: F401 [*] `.item.Item` imported but unused
db_api_protection/backend/app/app/schemas/__init__.py:1:25: F401 [*] `.item.ItemCreate` imported but unused
db_api_protection/backend/app/app/schemas/__init__.py:1:37: F401 [*] `.item.ItemInDB` imported but unused
db_api_protection/backend/app/app/schemas/__init__.py:1:47: F401 [*] `.item.ItemUpdate` imported but unused
db_api_protection/backend/app/app/schemas/__init__.py:2:18: F401 [*] `.msg.Msg` imported but unused
db_api_protection/backend/app/app/schemas/__init__.py:3:20: F401 [*] `.token.Token` imported but unused
db_api_protection/backend/app/app/schemas/__init__.py:3:27: F401 [*] `.token.TokenPayload` imported but unused
db_api_protection/backend/app/app/schemas/__init__.py:4:19: F401 [*] `.user.User` imported but unused
db_api_protection/backend/app/app/schemas/__init__.py:4:25: F401 [*] `.user.UserCreate` imported but unused
db_api_protection/backend/app/app/schemas/__init__.py:4:37: F401 [*] `.user.UserInDB` imported but unused
db_api_protection/backend/app/app/schemas/__init__.py:4:47: F401 [*] `.user.UserUpdate` imported but unused
db_api_protection/backend/app/app/schemas/__init__.py:5:24: F401 [*] `.statistic.Statistic` imported but unused
db_api_protection/backend/app/app/schemas/__init__.py:5:35: F401 [*] `.statistic.StatisticCreate` imported but unused
db_api_protection/backend/app/app/schemas/__init__.py:5:52: F401 [*] `.statistic.StatisticInDB` imported but unused
db_api_protection/backend/app/app/schemas/__init__.py:5:67: F401 [*] `.statistic.StatisticUpdate` imported but unused
Found 42 errors.
[*] 28 potentially fixable with the --fix option.
```



