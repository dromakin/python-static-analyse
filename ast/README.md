# Построение синтаксического дерева, графа вызовов

## pyreverse
[Является частью pylint!](https://pylint.readthedocs.io/en/latest/pyreverse.html#pyreverse)
pyreverse анализирует исходный код и создает диаграммы пакетов и классов.

Он поддерживает вывод в форматы файлов .dot/.gv, .puml/.plantuml (PlantUML) и .mmd/.html (MermaidJS). Если установлен Graphviz (или команда dot), можно также использовать все выходные форматы, поддерживаемые Graphviz. В этом случае pyreverse сначала создает временный файл .gv, который затем передается в Graphviz для создания окончательного изображения.

```shell
pyreverse --colorized --max-color-depth 10 db_api_protection/backend/app/app
```

### Report
pyreverse создает dot файлы, которые можно переделать в png формат для удобства.

```shell
dot -Tpng classes.dot > classes.png
```
![classes.png](pyreverse-pylint%2Fclasses.png)


```shell
dot -Tpng packages.dot > packages.png
```
![packages.png](pyreverse-pylint%2Fpackages.png)


## code2flow
code2flow /Users/dromakin/GitHubDesktop/db_api_protection/backend/ -o png --language py 

### Report
![example.png](code2flow%2Fexample.png)

## libCST
LibCST анализирует исходный код Python 3.0 -> 3.11 как дерево CST, в котором хранятся все детали форматирования (комментарии, пробелы, круглые скобки и т. д.). Это полезно для создания приложений и линтеров с автоматическим рефакторингом (codemod).

По выше указанной причине report никакого не имеет.

Инструмент создан для создания линтеров.