---
## Front matter
title: "Лабораторная работа №3"
subtitle: "Отчёт"
author: "Сергеев Даниил Олегович"

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
mainfont: IBM Plex Serif
romanfont: IBM Plex Serif
sansfont: IBM Plex Sans
monofont: IBM Plex Mono
mathfont: STIX Two Math
mainfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
romanfontoptions: Ligatures=Common,Ligatures=TeX,Scale=0.94
sansfontoptions: Ligatures=Common,Ligatures=TeX,Scale=MatchLowercase,Scale=0.94
monofontoptions: Scale=MatchLowercase,Scale=0.94,FakeStretch=0.9
mathfontoptions:
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

Научиться оформлять отчёты с помощью легковесного языка разметки Markdown. [@tuis]

# Задание

- Сделайте отчёт по предыдущей лабораторной работе в формате Markdown.
- В качестве отчёта просьба предоставить отчёты в 3 форматах: pdf, docx и md (в архиве, поскольку он должен содержать скриншоты, Makefile и т.д.)

# Ход выполнения лабораторной работы

## Создание отчёта

Перейдем каталог с файлами отчёта и откроем report.md. (рис. [-@fig:002])

![Каталог рабочего пространства лабораторной работы.](image/1.PNG){#fig:001 width=70%}

![Файл отчёта report.md.](image/2.PNG){#fig:002 width=70%}

Заменим титульный лист. 

![Замена Front matter.](image/3.PNG){#fig:003 width=70%}

Добавим цель, задание, ход выполнения лабораторной работы.

![Цель лабораторной работы.](image/3__.PNG){#fig:004 width=70%}

![Задание лабораторной работы.](image/4.PNG){#fig:005 width=70%}

![Ход выполнения лабораторной работы.](image/5.PNG){#fig:006 width=70%}

Начнем оформлять рисунки, используемые в лабораторной работе.

![Определение пути для рисунка и его добавление.](image/6.PNG){#fig:007 width=70%}

Для каждого нового изображения поменяем номер, чтобы небыло ошибок при генерации pdf. (рис. [-@fig:008])

![Изменение номера следующего изображения.](image/7.PNG){#fig:008 width=70%}

Добавим ответы на контрольные вопросы.

![Ответы на контрольные вопросы.](image/8.PNG){#fig:009 width=70%}

Добавим вывод лабораторной работы.

![Вывод.](image/9.PNG){#fig:010 width=70%}

К некоторым рисункам добавим ссылки (рис. [-@fig:011])

![Добавление ссылок к рисункам.](image/10.PNG){#fig:011 width=70%}

Отредактируем относительный путь к рисункам, расставим строки через одну для корректного отображения отчёта в сгенерированных файлах.

![Редактирование пути к рисункам.](image/11.PNG){#fig:012 width=70%}

## Создание файлов отчёта в формате pdf и docx

Пропишем команду make для создания файлов отчёта в pdf и docx. (рис. [-@fig:013])

![Работа команды make.](image/12.PNG){#fig:013 width=70%}

![Вид готового отчёта.](image/13.PNG){#fig:014 width=70%}

## Отправка файлов на github

Проиндексируем все изменения и проведем коммит.

![Сохранение файлов в git.](image/14.PNG){#fig:015 width=70%}

Отправим файлы на сервер github. (рис. [-@fig:016])

![Выполнение git push.](image/15.PNG){#fig:016 width=70%}

![Файлы отчёта на github.](image/16.PNG){#fig:017 width=70%}

# Вывод

В результате выполнения лабораторной работы я научиться оформлять отчёты с помощью легковесного языка разметки Markdown и создавать файлы отчёта в разных форматах.

# Список литературы{.unnumbered}

::: {#refs}
:::
