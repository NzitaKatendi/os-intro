---
## Front matter
title: "Шаблон отчёта по лабораторной работе 5"
subtitle: "Aнализ файловой систеьы LINUX. Команды для работы с файломи и Каталогамт"
author: " Нзита Диатезилуа Катенди"

## Generic otions
lang: ru-RU
toc-title: "Содержание"

## Bibliography
bibliography: bib/cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

## Pdf output format
toc: true # Table of contents
toc-depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4
documentclass: scrreprt
## I18n polyglossia
polyglossia-lang:
  name: russian
  options:
	- spelling=modern
	- babelshorthands=true
polyglossia-otherlangs:
  name: english
## I18n babel
babel-lang: russian
babel-otherlangs: english
## Fonts
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase,Scale=0.9
## Biblatex
biblatex: true
biblio-style: "gost-numeric"
biblatexoptions:
  - parentracker=true
  - backend=biber
  - hyperref=auto
  - language=auto
  - autolang=other*
  - citestyle=gost-numeric
## Pandoc-crossref LaTeX customization
figureTitle: "Рис."
tableTitle: "Таблица"
listingTitle: "Листинг"
lofTitle: "Список иллюстраций"
lotTitle: "Список таблиц"
lolTitle: "Листинги"
## Misc options
indent: true
header-includes:
  - \usepackage{indentfirst}
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Ознакомление с файловой системой Linux, её структурой, именами и
содержанием каталогов. Приобретение практических навыков по
применению команд для работы с файлами и каталогами, по
управлению процессами (и работами), по проверке использования
диска и обслуживанию файловой системы.

# Задание

1. Выполните все примеры, приведённые в первой части описания
лабораторной работы.

2. Выполните следующие действия, зафиксировав в отчёте по
лабораторной работе используемые при этом команды и
результаты их выполнения:

• Скопируйте файл /usr/include/sys/io.h в домашний каталог и
назовите его equipment. Если файла io.h нет, то используйте
любой другой файл в каталоге /usr/include/sys/ вместо него.
• В домашнем каталоге создайте директорию ~/ski.plases.
• Переместите файл equipment в каталог /ski.plases.

		_Задачи_
	
• Переименуйте файл /ski.plases/equipment в /ski.plases/equiplist.
• Создайте в домашнем каталоге файл abc1 и скопируйте его в
каталог /ski.plases, назовите его equiplist2.

• Создайте каталог с именем equipment в каталоге ~/ ski.plases.
• Переместите файлы /ski.plases/equiplist и equiplist2 в каталог
/ski.plases/equipment.

• Создайте и переместите каталог /newdir в каталог /ski.plases и
назовите его plans.

		_задачи_
3. Определите опции команды chmod, необходимые для того, чтобы
присвоить перечисленным ниже файлам выделенные права
доступа, считая, что в начале таких прав нет:
• drwxr–r– … australia
• drwx–x–x … play
• -r-xr–r– … my_os
• -rw-rw-r– … feathers При необходимости создайте нужные файлы.	

		_Задачи_

4. Проделайте приведённые ниже упражнения, записывая в отчёт по
лабораторной работе используемые при этом команды:
• Просмотрите содержимое файла /etc/password.
• Скопируйте файл /feathers в файл /file.old.
• Переместите файл /file.old в каталог /play.
• Скопируйте каталог /play в каталог /fun.
• Переместите каталог /fun в каталог /play и назовите его games.
• Лишите владельца файла /feathers права на чтение.
• Что произойдёт, если вы попытаетесь просмотреть файл /feathers
командой cat?
• Что произойдёт, если вы попытаетесь скопировать файл /feathers?

		_Задачи_
		
• Дайте владельцу файла /feathers право на чтение.
• Лишите владельца каталога /play права на выполнение.
• Перейдите в каталог /play. Что произошло?
• Дайте владельцу каталога /play право на выполнение.
5. Прочитайте man по командам mount, fsck, mkfs, kill и кратко их
охарактеризуйте, приведя примеры.

Здесь описываются теоретические аспекты, связанные с выполнением работы.

Например, в табл. [-@tbl:std-dir] приведено краткое описание стандартных каталогов Unix.

: Описание некоторых каталогов файловой системы GNU Linux {#tbl:std-dir}

| Имя каталога | Описание каталога                                                                                                          |
|--------------|----------------------------------------------------------------------------------------------------------------------------|
| `/`          | Корневая директория, содержащая всю файловую                                                                               |
| `/bin `      | Основные системные утилиты, необходимые как в однопользовательском режиме, так и при обычной работе всем пользователям     |
| `/etc`       | Общесистемные конфигурационные файлы и файлы конфигурации установленных программ                                           |
| `/home`      | Содержит домашние директории пользователей, которые, в свою очередь, содержат персональные настройки и данные пользователя |
| `/media`     | Точки монтирования для сменных носителей                                                                                   |
| `/root`      | Домашняя директория пользователя  `root`                                                                                   |
| `/tmp`       | Временные файлы                                                                                                            |
| `/usr`       | Вторичная иерархия для данных пользователя                                                                                 |

Более подробно об Unix см. в [@gnu-doc:bash;@newham:2005:bash;@zarrelli:2017:bash;@robbins:2013:bash;@tannenbaum:arch-pc:ru;@tannenbaum:modern-os:ru].

# Выполнение лабораторной работы

Выполнил все примеры, приведенные в первой части описания
лабораторной работы.(рис. 1, 2, 3)


Описываются проведённые действия, в качестве иллюстрации даётся ссылка на иллюстрацию (рис. [-@fig:001])

![Название рисунка](image/placeimg_800_600_tech.jpg){ #fig:001 width=70% }

# Выводы

Мы приобрели практические навыки по применению команд для
работы с файлами и каталогами, по управлению процессами (и
работами), по проверке использования диска и обслуживанию
файловой системы.

# Список литературы{.unnumbered}

::: {#refs}
:::
