---
## Front matter
title: "Отчёт по индивидуальному проекту"
subtitle: "Этап №3"
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

# Задание

В качестве задания лабораторной работы необходимо [@tuis]:

Добавить к сайту достижения.
- Добавить информацию о навыках (Skills).
- Добавить информацию об опыте (Experience).
- Добавить информацию о достижениях (Accomplishments).
Сделать пост по прошедшей неделе.
Добавить пост на тему по выбору:
- Легковесные языки разметки.
- Языки разметки. LaTeX.
- Язык разметки Markdown.

# Ход выполнения лабораторной работы

## Размещение на сайт данных о достижениях

Перейдем в рабочую директорию (рис. [-@fig:001])

![Рабочая директория.](image/1.PNG){#fig:001 width=70%}

Для начала добавим в _index.md по пути content/_index.md блок о навыках (skills).

![Добавление блока skills.](image/2.PNG){#fig:002 width=70%}

Изменим файл content/authors/admin/_index.md. Добавим в него личную информацию.

![Изменение индекса с владельцем.](image/3.PNG){#fig:003 width=70%}

Теперь добавим иконки для навыков и хобби. Для этого в assets/media/icons создадим каталог custom и загрузим туда иконки в формате svg.

![Директория с иконками для навыков и хобби.](image/4.PNG){#fig:004 width=70%}

![Итоговый вид skills на сайте.](image/5.PNG){#fig:005 width=70%}

Так же добавим блок с опытом (experience).

![Добавление блока experience.](image/6.PNG){#fig:006 width=70%}

![Изменение индекса: меняем блок work.](image/7.PNG){#fig:007 width=70%}

![Итоговый вид experience на сайте.](image/8.PNG){#fig:008 width=70%}

Добавим информацию о своих наградах (accomplishments).

![Добавление блока awards.](image/9.PNG){#fig:009 width=70%}

![Изменение индекса: меняем блок awards.](image/10.PNG){#fig:010 width=70%}

![Итоговый вид accomplishments на сайте.](image/10.2.PNG){#fig:011 width=70%}

## Размещение новых постов

Загрузим заранее подготовленные файлы постов в каталог content/post. Обновим сайт. (рис. [-@fig:011] - [-@fig:012])

![Пост о языке разметки Markdown.](image/11.PNG){#fig:012 width=70%}

![Пост по прошлой неделе.](image/12.PNG){#fig:013 width=70%}

# Вывод

В результате выполнения лабораторной работы я отредактировал информацию о сових достижениях и добавил новые посты для моего сайта.

# Список литературы{.unnumbered}

::: {#refs}
:::
