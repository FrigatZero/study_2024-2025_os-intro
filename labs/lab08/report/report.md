---
## Front matter
title: "Лабораторная работа № 8. Поиск файлов. Перенаправление ввода-вывода. Просмотр запущенных процессов"
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

Ознакомление с инструментами поиска файлов и фильтрации текстовых данных. Приобретение практических навыков: по управлению процессами (и заданиями), по проверке использования диска и обслуживанию файловых систем [@tuis].

# Задание

1. Управление потоком вывода и его запись в файлы
2. Выполнить задания, использующие фильтр grep и команду поиска find
3. Выполнить задания, связанные с фоновыми процессами.
4. Использовать команды df и du.
5. Поработать с командой find для поиска директорий

# Ход выполнения лабораторной работы

## Выполнение примеров из описания лабораторной работы

Запишем в файл file.txt названия файлов из каталога /etc. Для этого используем команду ls и операцию перенаправления вывода (>).

![Запись файлов в file.txt](image/1.PNG){#fig:001 width=70%}

Теперь дополнительно запишем в этот файл названия файлов, содержащихся в домашнем каталоге. Для этого используем перенаправление вывода с функцией добавления в конец файла (>>) (рис. [-@fig:002]).

![Добавление файлов в конец file.txt](image/2.PNG){#fig:002 width=70%}


![Конец вывода file.txt](image/3.PNG){#fig:003 width=70%}

Выведем имена всех файлов из file.txt, имеющих расширение .conf и запишем их в новый файл conf.txt. Для этого пропишем команду cat file.txt | grep "\.conf$" > conf.txt. Символ $ нам нужен для поиска в конце имен, а символ \ для указания того, что . - не системный символ. (рис. [-@fig:005])

![Файлы формата .conf](image/4.PNG){#fig:004 width=70%}

![Запись результата в conf.txt](image/5.PNG){#fig:005 width=70%}

Определим, какие файлы в домашнем каталоге имеют имена, начинающиеся с символа c. Для этого используем два варианта:

1. ls -R ~ | grep "^c" (рис. [-@fig:006])
2. find ~ -name "c*" -print (рис. [-@fig:007])

![Первый вариант вывода](image/6.PNG){#fig:006 width=70%}

![Второй вариант вывода](image/7.PNG){#fig:007 width=70%}

Выведем на экран по странично имена файлов из /etc, начинающиеся с символа h. Для вывода по странично используем конвейер и команду more.

![Файлы, начинающиеся с h](image/8.PNG){#fig:008 width=70%}

Запустим в фоновом режиме процесс, который будет записывать в файл ~/logfile файлы, имена которых начинаются с log. Удалим созданный файл.

![Фоновый процесс для записи log*.](image/9.PNG){#fig:009 width=70%}

Запустим из консоли в фоновом режиме редактор gedit с помощью команды gedit &. Определим его идентификатор, используя ps, конвейер и фильтр grep.

1. ps | grep "gedit"
2. ps aux | grep "gedit" | grep -v grep

![Поиск процесса gedit](image/10.PNG){#fig:010 width=70%}

Завершим процесс командой kill (рис. [-@fig:011]), предварительно прочитав её описание

![Завершение gedit.](image/11.PNG){#fig:011 width=70%}

![Проверка процесса.](image/12.PNG){#fig:012 width=70%}

Выполним команды df и du, предварительно получив более подробную информацию из man. Используем df и du с ключем -h для вывода размера файлов и файловых систем в понятном для человека формате. К du добавим ключ -a для вывода размера файлов включительно.

![Команда df.](image/13.PNG){#fig:013 width=70%}

![Вывод команды du.](image/14.PNG){#fig:014 width=70%}

Воспользовавшись справкой команды find, выведем имена всех директорий, имеющихся в домашнем каталоге. Для этого используем find ~ -type d -print, где -type - ключ для выбора типа искомого объекта.

![Вывод команды find.](image/15.PNG){#fig:015 width=70%}

## Ответы на контрольные вопросы.

1. 
- stdin — поток ввода, по умолчанию: клавиатура, имеет сигнал 0.
- stdout — поток вывода, по умолчанию: консоль, имеет сигнал 1.
- stderr — поток вывода сообщений об ошибках, по умолчанию: консоль, имеет сигнал 2.
2.
- '>' – перенаправление вывода с перезаписью файла.
- '>>' – перенаправление вывода с дописыванием в конец файла.
3. Конвейер (|) – это символ для передачи вывода одной команды на вход другой.
4. Программа – исполняемый файл на диске. Процесс – экземпляр запущенной программы в памяти, имеющий собственный номер, свои ресурсы и состояние.
5. PID (Process ID) – уникальный идентификатор процесса. GID (Group ID) – идентификатор группы процессов.
6. Задачи - процессы, запущенные в текущей сессии терминала. kill %номер задачи - позволяет завершить процесс по номеру.
7. top – утилита мониторинга процессов в реальном времени. htop – улучшенная версия top с цветным интерфейсом и удобной навигацией.
8. find - рекурсивный поиск файлов по имени, размеру, дате и другим критериям. Примеры:
- find %каталог -type d -print - выведет все директории и под-директории в указанном каталоге.
- find %каталог -name %имя -print - выведет все файлы с указанным именем в текущем и под-каталогах.
9. Можно, с помощью команды grep. Синтаксис: grep "текст" /путь/.
10. С помощью команды df.
11. С помощью команды du.
12. Найти его номер PID с помощью команды ps, grep и удалить командой kill -KILL PID. 

# Вывод

В результате выполнения лабораторной работы я ознакомление с инструментами поиска файлов и фильтрации текстовых данных, приобрел практические навыков по управлению процессами и по проверке использования диска.

# Список литературы{.unnumbered}

::: {#refs}
:::
