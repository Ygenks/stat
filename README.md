Математическая статистика
=========================

Описание
--------
В этом репозитории находятся утилиты для расчета параметров одномерных
и двумерных выборок в соответствии с заданиями №10, 11 типового расчета
по ТВиМС в БГУИР.
С их помощью можно выполнить следующие операции:

Для одномерной выборки:
+ построение равноинтервальной и равновероятностной гистограмм
+ расчет параметров гипотетической функции распределения вероятности
+ построение графика эмпирической и гипотетической функции распеределения вероятности
+ расчет точечных и интервальных оценок параметров распределения
+ проверка гипотез о характере распределения значений в выборках

Для двумерной выборки:
+ расчет и построение линии регрессии
+ расчет точечных и интервальных оценок параметров распределения
+ проверка гипотез о характере распределения значений в выборках

Все необходимые промежуточные вычисления выводятся в консоль, а также в текстовые файлы.

По результатам вычислений генерируется __отчет__, который после минимальных модификаций
готов к сдаче преподавателю.

В папке
/one-dimension находятся утилиты для одномерной выборки;
/two-dimension содержит утилиты для двумерной выборки.

В корне каждой из этих папок, а также в папках /doc есть __примеры сгенерированных отчетов__.


Использование
-------------

Для использования всех возможностей у вас должны быть установлены следующие программы:

+ [python 2.7](http://www.python.org/download/releases/2.7.6/) + [matplotlib](http://matplotlib.org/) -> для расчета значений
+ [latex](http://www.latex-project.org/) (а лучше [texlive](http://www.tug.org/texlive/)) -> для генерации отчета
+ [make](http://www.gnu.org/software/make/) --> для автоматизации

Все эти пакеты есть в стандартных репозиториях большинства linux-дистрибутивов, установить их
обычно не составляет труда.

Рассмотрим процесс работы на примере одномерной выборки; работа с двумерной выборкой производится аналогично.

1. Заходим в папку /one-dimension;
2. Заменяем файл data/data.txt файлом с требуемой выборкой в соответствии с форматом исходного файла;
3. Пишем в консоли:

```bash
$ make && make report
```

4. Если все прошло гладко, проверяем результат: report.pdf

Для изменения состава графиков, подставляемых значений, выдвигаемых гипотез необходимо
редактировать файл report.tex; после чего повторять опичанный выше процесс генерации отчета.

Все доступные для подстановки значения находятся в папках /pic (графики), /val (значения), /tbl (таблицы).

В каждом файле --- одно значение в соответствии с названием. Все просто!


Дополнительно
-------------

+ Все доступные make-команды находятся в соответствующем Makefile.

+ Для генерации справочного отчета, содержащего все возможные графики, воспользуйтесь командой

```bash
$ make && make doc
```

Сгенерированный отчет будет находиться в папке usage/usage.pdf.

+ Для того, чтобы __отключить прогонку графиков через LaTeX__ (чтобы получить расчетные данные без него),
закомментируйте следующие строки в начале файла script/statistics.py:

```python
...
rc('font',**{'family':'serif','serif':['Palatino']})
rc('text', usetex=True)
...
```

+ Для того, чтобы при генерации отчета использовался красивый кириллический Times New Roman,
  установите latex-пакет [pscyr](http://donik.org/wiki/index.php/%D0%A3%D1%81%D1%82%D0%B0%D0%BD%D0%BE%D0%B2%D0%BA%D0%B0_%D0%BF%D0%B0%D0%BA%D0%B5%D1%82%D0%B0_PSCyr_%D0%B2_LaTeX) и
  раскомментируйте следующую строчку в файле tex/packages.tex

```latex
\usepackage{pscyr}
```

Bugs & Reports
--------------

Замечания и предложения приветствуются!

Присылайте их сюда: [budnyjj@gmail.com](mailto:budnyjj@gmail.com); [anashkevichp@gmail.com](mailto:anashkevichp@gmail.com).


