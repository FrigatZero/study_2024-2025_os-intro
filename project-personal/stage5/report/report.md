---
## Front matter
title: "Отчёт по индивидуальному проекту"
subtitle: "Этап №5"
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

- Сделать записи для персональных проектов.
- Сделать пост по прошедшей неделе.
- Добавить пост на тему по выбору:
  - Языки научного программирования.

# Ход выполнения лабораторной работы

## Создание блока для записей проектов

Откроем файл content/_index.md в каталоге проекта. Добавим блок записей для персональных проектов (рис. [-@fig:007]). Укажем id: proj, который пригодится нам далее.

![Редактирование _index.md.](image/1.PNG){#fig:001 width=70%}

В файле конфига config/_default/params.yaml поменяем текст в верхней панели с Your Name на имя и фамилию автора сайта.

![Редактирование params.yaml.](image/2.PNG){#fig:002 width=70%}

В том же каталоге отредактируем menus.yaml. Укажем в строке url пункта Projects указание на блок, созданный в индексе, с помощью id: proj. Это нужно для того, чтобы при нажатии на кнопку Projects в меню навигации нас перекидывало на необходимый блок с проектами на главном экране.

![Редактирование menus.yaml.](image/3.PNG){#fig:003 width=70%}

Очистим проекты-загатовки в каталоге content/project и добавим свой проект, ведущий на github, и проект прохождения внешнего курса.

![Редактирование проекта github.](image/4.PNG){#fig:004 width=70%}

## Размещение новых постов

Загрузим заранее подготовленные файлы постов (рис. [-@fig:005]-[-@fig:006]) в каталог content/post. Обновим сайт.

![Пост по прошлой неделе.](image/5.PNG){#fig:005 width=70%}

![Пост о научных языках программирования.](image/6.PNG){#fig:006 width=70%}

![Посты и блок проектов на сайте.](image/7.PNG){#fig:007 width=70%}

# Вывод

В результате выполнения лабораторной работы я добавил к сайту блок с персональными проектами и новые посты.

# Список литературы{.unnumbered}

::: {#refs}
:::
