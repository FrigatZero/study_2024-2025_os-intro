---
## Front matter
title: "Отчёт по индивидуальному проекту"
subtitle: "Этап №2"
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

- Разместить фотографию владельца сайта.
- Разместить краткое описание владельца сайта (Biography).
- Добавить информацию об интересах (Interests).
- Добавить информацию от образовании (Education).
- Сделать пост по прошедшей неделе.
- Добавить пост на тему по выбору:
  1. Управление версиями. Git.
  2. Непрерывная интеграция и непрерывное развертывание (CI/CD).

# Ход выполнения лабораторной работы

## Размещение на сайт данных о себе

Для начала добавим фотографию владельца сайта. Для этого перейдем в репозиторий сайта и в ./content/authors/admin. В данную директорию добавим фото и назовём его avatar.jpg (рис. [-@fig:001]).

![Директория с фотографией владельца.](image/1.PNG){#fig:001 width=70%}

Теперь приступим к размещению информации. Для этого откроем ./content/authors/admin/_index.md и запишем туда своё имя и фамилию (рис. [-@fig:002]) с транскрипцией на английский язык.

![Настройка отображаемого имени.](image/2.PNG){#fig:002 width=70%}

Добавим информацию об интересах и об образовании.

![Настройка информации об интересах и образовании](image/3.PNG){#fig:003 width=70%}

И завершим редактирование, добавив краткое описание владельца сайта.

![Краткое описание.](image/4.PNG){#fig:004 width=70%}

## Создание требуемых постов

Перейдем в директорию ./content/post и создадим в ней каталог first-weak (рис. [-@fig:005]) для поста по прошедшей неделе. В нем создаем файл с названием index.md и записываем туда тело поста.

![Директория first-weak.](image/5.PNG){#fig:005 width=70%}

![Редактирование поста по прошедшей неделе.](image/6.PNG){#fig:006 width=70%}

В качестве поста выберем CI/CD. В этой же директории создадим каталог ci-cd для поста по непрерывной интеграции и непрерывному развертыванию.

![Редактирование поста по CI/CD.](image/7.PNG){#fig:007 width=70%}

В результате получим два поста на сайте

![Итоговый вид постов.](image/8.PNG){#fig:008 width=70%}

# Вывод

В результате выполнения лабораторной работы я отредактировал личную информацию и научился создавать посты на академическом сайте-визитке, созданном с помощью генератора статических сайтов Hugo.

# Список литературы{.unnumbered}

::: {#refs}
:::
