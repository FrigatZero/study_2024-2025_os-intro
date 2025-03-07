---
## Front matter
title: "ШЛабораторная работа №1"
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

Приобретение практических навыков установки операционной системы на виртуальную машину, настройки минимально необходимых для дальнейшей работы сервисов. [@tuis]

# Задание

- Установить операционную систему.
- Обновить или установить необходимое программное обеспечение.
- Повысить комфорт работы с операционной системой.
- Настроить раскладку клавиатуры
- Установить программное обеспечение для создания документации.
- Создать локальный каталог для выполнения заданий по предмету.

# Ход выполнения лабораторной работы

## Создание виртуальной машины

Для начала откроем менеджер виртуальных машин Oracle VirtualBox и нажмем на кнопку создать в графическом интерфейсе. Выберем тип машины Linux, подтип Fedora. Зададим имя, удовлетворяющее соглашению о наименовании.

![Окно создания ВМ.](image/1.PNG){#fig:001 width=70%}

Выделим размер основной памяти виртуальной машины до 4096 МБ и 4 процессора. Включим поддержку UEFI(EFI).

![Окно оборудования ВМ.](image/2.PNG){#fig:002 width=70%}

Зададим жёсткий диск VDI с размером 80 ГБ.

![Окно настройки жёсткого диска.](image/3.PNG){#fig:003 width=70%}

В качестве графического контроллера поставим VMSVGA, включим 3D ускорение, выделим 256 МБ видеопамяти.

![Настройка дисплея ВМ.](image/4.PNG){#fig:004 width=70%}

Включим общий буфер обмена и перетаскивание объектов между хостом и гостевой ОС.

![Окно дополнительных настроек.](image/5.PNG){#fig:005 width=70%}

Запустим виртуальную машину. После вставим оптический диск с образом Fedora-Sway-Live-x86_64-41-1.4.iso и перезагрузим её.

![Установка live CD.](image/6.PNG){#fig:006 width=70%}

##Установка операционной системы

Запустим Fedora, перейдем в режим базовой графики в меню boot, чтобы не было проблем при отображении.

![Меню GRUB.](image/7.PNG){#fig:007 width=70%}

![Запуск ОС в режиме базовой графики.](image/8.PNG){#fig:008 width=70%}

После запуска системы, нажмем Win+d и запустим установщик Anaconda командой liveinst.

![Интерфейс ОС Fedora sway.](image/9.PNG){#fig:009 width=70%}

![Запуск liveinst.](image/10.PNG){#fig:010 width=70%}

Выберем язык интерфейса Русский

![Приветствие загрузчика Anaconda, выбор языка.](image/11.PNG){#fig:011 width=70%}

Выберем стандартное место установки ОС.

![Выбор устройства для установки ОС.](image/12.PNG){#fig:012 width=70%}

Установим имя и пароль для пользователя.

![Создание пользователя.](image/13.PNG){#fig:013 width=70%}

Начнем установку ОС Fedora sway на жёсткий диск.

![Процесс установки ОС.](image/14.PNG){#fig:014 width=70%}

Перезапустим виртуальную машину и войдем в качестве созданного пользователя.

![Окно входа в сеанс.](image/15.PNG){#fig:015 width=70%}

## Установка драйверов для VirtualBox

Запустим терминальный мультиплексор tmux, переключимся на роль супер-пользователя, установим средства разработки.

![Установка development-tools.](image/16.PNG){#fig:016 width=70%}

Также установим пакет DKMS.

![Установка пакета DKMS.](image/17.PNG){#fig:017 width=70%}

Подмонтируем диск и запустим установку драйверов. В конце установки перезагрузим виртуальную машину.

![Установка дополнений гостевой ОС.](image/18.PNG){#fig:018 width=70%}

## Подключение общей папки

Внутри виртуальной машины добавим своего пользователя в группу vboxsf.

![Добавление пользователя в vboxsf.](image/19.PNG){#fig:019 width=70%}

В хостовой системе подключим общую папку с помощью графического интерфейса.

![Добавление общей папке через настройки VirtualBox.](image/20.PNG){#fig:020 width=70%}

## Установка и обновление программного обеспечения

Средства установки уже были установлены в предыдущих пунктах, поэтому начнем с обновления всех пакетов.

![Обновление пакетов.](image/21.PNG){#fig:021 width=70%}

Установим программу для удобства работы в консоли: Midnight commander.

![Установка mc.](image/22.PNG){#fig:022 width=70%}

Теперь установим другой вариант консоли.

![Установка kitty.](image/23.PNG){#fig:023 width=70%}

Подключим автоматическое обновление. Для этого установим dnf-automatic и запустим таймер.

![Подключение dnf-automatic.](image/24.PNG){#fig:024 width=70%}

Отключим SELinux. В файле /etc/selinux/config заменим значение selinux с enforcing на permissive. Перезагрузим виртуальную машину.

![Настройка SELinux.](image/25.PNG){#fig:025 width=70%}

## Настройка раскладки клавиатуры

Запустим терминальный мультиплексор tmux, создадим конфигурационный файл.

![Создание 95-system-keyboard-config.conf.](image/26.PNG){#fig:026 width=70%}

Отредактируем созданный файл.

![Редактирование 95-system-keyboard-config.conf.](image/27.PNG){#fig:027 width=70%}

Переключимся на роль супер-пользователя и отредактируем 00-keyboard.conf. Перезапустим виртуальную машину.

![Редактирование 00-keyboard.conf.](image/28.PNG){#fig:028 width=70%}

## Установка ПО для создания документации

Запустим терминальный мультиплексор tmux, переключимя на роль супер-пользователя. Установим pandoc с помощью менеджера пакетов dnf.

![Установка pandoc.](image/29.PNG){#fig:029 width=70%}

Установим pandoc-crossref. Для начала проверим версию pandoc:

![Проверка версии pandoc.](image/30.PNG){#fig:030 width=70%}

Получается, что версия pandoc - 3.1.11.1. Зайдем на github и найдем соответствующий релиз. Скачаем его и распакуем в /tmp.

![Скачивание нужной версии pandoc-crossref.](image/31.PNG){#fig:031 width=70%}

![Распаковка архива в /tmp.](image/32.PNG){#fig:032 width=70%}

Скопируем все файлы из архива в каталог /usr/local/bin.

![Копирование pandoc-crossref в нужный каталог.](image/33.PNG){#fig:033 width=70%}

И скачаем дистрибутив TeXlive:

![Установка TeXlive.](image/34.PNG){#fig:034 width=70%}

# Ход выполнения домашнего задания

1. Дождемся загрузки графического окружения и откроем терминал. Пропишем команду dmesg и узнаем последовательность загрузки системы.

![Вывод команды dmesg](image/35.PNG){#fig:035 width=70%}

2. Получим имформацию о:
- Версии ядра Linux -> 6.13.5-200.fc41.x86_64
- Частоте процессора -> 3400 MHz
- Модели процессора -> AMD Ryzen 5 2600
- Объёме доступной ОЗУ -> ~4 GB
- Типе гипервизора -> KVM
- Типе файловой системы корневого раздела -> EXT4-fs
- Последовательности монтирования файловых систем -> BTRFS, EXT4-fs

![Нахождение информации о системе](image/36.PNG){#fig:036 width=70%}

# Вывод

В результате выполнения лабораторной работы я приобрел навыки установки операционной системы на виртуальную машину и научился минимально настраивать систему для дальнейшей работы сервисов.

# Список литературы{.unnumbered}

::: {#refs}
:::
