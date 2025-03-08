---
## Front matter
title: "Отчёт по индивидуальному проекту"
subtitle: "Этап №1"
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

- Установить необходимое программное обеспечение.
- Скачать шаблон темы сайта.
- Разместить его на хостинге git.
- Установить параметр для URLs сайта.
- Разместить заготовку сайта на Github pages.

# Ход выполнения лабораторной работы

## Установка необходимого программного обеспечения

Для начала установим GO, необхоимый для работы генератора статических сайтов hugo. (рис. [-@fig:001])

![Установка GO.](image/1.PNG){#fig:001 width=70%}

Теперь перейдем на github репозиторий с генератором [@hugo] и скачаем оттуда необходимый релиз расширенной версии hugo_extended_0.134.1 для linux систем.

![Находим необходимый архив.](image/2.PNG){#fig:002 width=70%}

Распакуем архив в каталог /tmp. (рис. [-@fig:003])

![Распаковка архива hugo_extended.](image/3.PNG){#fig:003 width=70%}

Создадим локальный репозиторий в рабочем каталоге с шаблона сайта-визитки научного сотрудника [@academic].

![Копирование репозитория шаблона.](image/4.PNG){#fig:004 width=70%}

Перенесем исполнительный файл hugo в созданный локальный репозиторий.

![Копирование исполнительного файла в каталог репозитория.](image/5.PNG){#fig:005 width=70%}

## Работа с сайтом научного сотрудника

Запускаем локальный сервер для проверки работы сайта с помощью команды ./hugo server -D. (рис. [-@fig:006])

![Запуск сервера с помощью hugo](image/6.PNG){#fig:006 width=70%}

![Вид локального сайта](image/7.PNG){#fig:007 width=70%}

После чего завершаем процесс комбинацией Ctrl+C.

## Размещение заготовки сайта на Github pages.

Приступим к размещению сайта на Github pages. Для начала изменим параметр URL в конфиге сайта. (рис. [-@fig:008])

![Замена URL сайта](image/8.PNG){#fig:008 width=70%}

Теперь создадим новый репозиторий на Github. Назовём его так же, как и будущий URL сайта.

![Создание нового репозитория](image/9.PNG){#fig:009 width=70%}

Скопируем ключ SSH и подключим локальный репозиторий к созданному.

![Копирование ключа SSH](image/10.PNG){#fig:010 width=70%}

![Подключение к Github](image/11.PNG){#fig:011 width=70%}

![Отправка файлов локального репозитория](image/12.PNG){#fig:012 width=70%}

Запустим процесс по развертыванию сайта на Github pages.

![Процесс по развертыванию сайта](image/13.PNG){#fig:013 width=70%}

После окончания процесса, перейдём по созданной ссылке и взглянем на сайт.

![Вид сайта в браузере](image/14.PNG){#fig:014 width=70%}

# Вывод

В результате выполнения лабораторной работы я научился создавать сайты на Github pages по шаблону с помощью генератора статических сайтов Hugo.

# Список литературы{.unnumbered}

::: {#refs}
:::
