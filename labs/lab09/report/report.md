---
## Front matter
title: "Отчёт по лабораторной работе №9"
subtitle: "Дисциплина:архитектура компьютера"
author: "Лобанов Владислав Олегович"

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

Приобретение навыков написания программ с использованием подпрограмм. Знакомство
с методами отладки при помощи GDB и его основными возможностями.

# Задание

1. Реализация подпрограмм в NASM
2. Отладка программам с помощью GDB


# Теоретическое введение

Подпрограмма — поименованная или иным образом идентифицированная часть компьютерной программы, содержащая описание определённого набора действий.

# Выполнение лабораторной работы

##Реализация подпрограмм в NASM

![Создаю рабочую директорию и файл в ней](image/Снимок экрана от 2023-12-25 09-13-57.png){#fig:001 width=70%}

![Редактирю файл вводя текст листинга](image/Снимок экрана от 2023-12-25 09-29-47.png){#fig:002 width=70%}

![Создаю исполняемый файл. Проверяю корректность работы програмы](image/Снимок экрана от 2023-12-25 09-59-12.png){#fig:003 width=70%}

![Изменяю текст программы чтобы она считала f(g(x))](image/Снимок экрана от 2023-12-25 10-07-37.png){#fig:004 width=70%}

![Создаю исполняемый файл. Проверяю корректность работы програмы](image/Снимок экрана от 2023-12-25 10-08-20.png){#fig:005 width=70%}

##Отладка программам с помощью GDB

![Создаю файл. Ввожу в него текст листинга](image/Снимок экрана от 2023-12-25 10-11-02.png){#fig:006 width=70%}

![Запускаю программу в отладочной оболочке GDB](image/Снимок экрана от 2023-12-25 10-17-06.png){#fig:007 width=70%}

![Для более подробного анализа программы устанавливаю брейкпоинт на метку _start, с которой начинается выполнение любой ассемблерной программы, и запускаю её](image/Снимок экрана от 2023-12-25 10-17-52.png){#fig:008 width=70%}

![Смотрю дисассимилированный код программы с помощью команды disassemble начиная с метки _start](image/Снимок экрана от 2023-12-25 10-18-19.png){#fig:009 width=70%}

![Переключаюсь на отображение команд с Intel’овским синтаксисом, введя команду setdisassembly-flavor intel. В представлении ATT в виде 16-ричного числа записаны первые аргументы всех комманд, а в представлении intel так записываются адреса вторых аргументов](image/Снимок экрана от 2023-12-25 10-20-19.png){#fig:010 width=70%}

![Включаю режим псевдографики, с помощью которго отбражается код программы и содержимое регистров](image/Снимок экрана от 2023-12-25 10-22-59.png){#fig:011 width=70%}

![Проверяю наличие точки останова](image/Снимок экрана от 2023-12-25 10-23-09.png){#fig:012 width=70%}

![Добавляю ещё одну точку останова и проверяю сколько точек останова есть](image/Снимок экрана от 2023-12-25 10-24-57.png){#fig:013 width=70%}

![Выполняю 5 инструкций с помощью команды si. Изменились значения регистров eax ecx edx ebx](image/Снимок экрана от 2023-12-25 10-25-46.png){#fig:014 width=70%}

![Просматриваю значение переменной msg1 по имени](image/Снимок экрана от 2023-12-25 10-26-36.png){#fig:015 width=70%}

![Просматриваю значение переменной msg2 по адресу](image/Снимок экрана от 2023-12-25 10-27-50.png){#fig:016 width=70%}

![Изменяю первый символ переменной msg1](image/Снимок экрана от 2023-12-25 10-29-27.png){#fig:017 width=70%}

![Изменяю первый символ переменной msg2](image/Снимок экрана от 2023-12-25 10-30-58.png){#fig:018 width=70%}

![Вывожу значение edx в разных форматах: строчном, 16-ричном, двоичном](image/Снимок экрана от 2023-12-25 10-32-37.png){#fig:019 width=70%}

![С помощью команды set изменяю значение регистра ebx. Разница вывода из-за того что в первом случае 2 это символ а во втором число.](image/Снимок экрана от 2023-12-25 10-33-55.png){#fig:020 width=70%}

Скопировал файл lab8-2.asm, созданный при выполнении лабораторной работы No8, с программой выводящей на экран аргументы командной строки. в файл с
именем lab09-3.asm, создал исполняемый файл

![Действие](image/Снимок экрана от 2023-12-25 10-38-14.png){#fig:021 width=70%}

![Запускаю программу в оболочке GDB](image/Снимок экрана от 2023-12-25 10-39-38.png){#fig:022 width=70%}

![Узнаю количество аргументов](image/Снимок экрана от 2023-12-25 10-42-57.png){#fig:023 width=70%}

![Смотрю все позиции стека. Их адреса распологаются в 4 байтах друг от друга (именно столько заниемает элемент стека)](image/Снимок экрана от 2023-12-25 10-43-05.png){#fig:024 width=70%}

# Выводы

В результате выполнения работы, я научился организовывать код в подпрограммы и познакомился с базовыми функциями отладчика gdb.

# Список литературы{.unnumbered}

1. [Лабораторная работа 9](https://esystem.rudn.ru/pluginfile.php/2089551/mod_resource/content/0/%D0%9B%D0%B0%D0%B1%D0%BE%D1%80%D0%B0%D1%82%D0%BE%D1%80%D0%BD%D0%B0%D1%8F%20%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%B0%20%E2%84%969.%20%D0%9F%D0%BE%D0%BD%D1%8F%D1%82%D0%B8%D0%B5%20%D0%BF%D0%BE%D0%B4%D0%BF%D1%80%D0%BE%D0%B3%D1%80%D0%B0%D0%BC%D0%BC%D1%8B.%20%D0%9E%D1%82%D0%BB%D0%B0%D0%B4%D1%87%D0%B8%D0%BA%20..pdf)

::: {#refs}
:::
