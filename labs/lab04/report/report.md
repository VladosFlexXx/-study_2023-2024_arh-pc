---
## Front matter
title: "Отчет по лабораторной работе №4"
subtitle: "Создание и процесс обработки программ на языке ассемблера NASM"
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

Освоение процедуры компиляции и сборки программ, написанных на ассемблере NASM.

# Задание

Здесь приводится описание задания в соответствии с рекомендациями
методического пособия и выданным вариантом.

# Теоретическое введение

Ассемблер - специальная программа для трансляции команд языка ассемблера в исполняемый машинный код. Язык ассемблера больше других приближен к архитектуре ЭВМ и её аппаратным возможностям, что позволяет получить к ним полный доступ, нежели языки высшего уровня (C#/C++, Python)

# Выполнение лабораторной работы

1. Перешел в каталог для работы на ассемблере, создал требуемый файл и открыл его через текстовый редактор (рис. @fig:001)

![Начало работы с ассемблером](image/Снимок экрана от 2023-10-28 01-16-56.png){#fig:001 width=70%}

2. Ввел в ранее созданый файл данный в задании текст, скомпилил его и проверил наличие в каталоге (рис. @fig:002)

![Компиляция](image/Снимок экрана от 2023-10-28 01-32-05.png){fig:002 width=70%}

3. Выполнил компиляцию файла из предыдущего шага со сменой его имени (рис. @fig:003)

![Комписляция со сменой имени](image/Снимок экрана от 2023-10-28 01-33-14.png){#fig:003 width=70%}

4. Передал объектный файл hello.o компоновщику и проверил (рис. @fig:004)

![Компоновка](image/Снимок экрана от 2023-10-28 01-36-11.png){#fig:004 width=70%}

5. Передал объектный файл obj.o компоновщику и проверил (рис. @fig:005)

![Компоновка](image/Снимок экрана от 2023-10-28 01-37-18.png){#fig:005 width=70%}

6. Запустил исполняемый файл (рис. @fig:006)

![Запуск файла](image/Снимок экрана от 2023-10-28 01-37-38.png){#fig:006 width=70%}

7. Задание для самостоятельной работы. В упомянутом каталоге создал копию файла hello.asm с именем lab4.asm. С помощью текстового редактора внес изменения в текст программы так, чтобы она выводила мои имя и фамилию (рис. @fig:007)

![Задание часть 1](image/Снимок экрана от 2023-10-28 01-52-39.png){#fig:007 width=70%}

8. Загрузил файлы на Github (рис. @fig:008)

![Задание часть 2](image/Снимок экрана от 2023-10-28 02-02-17.png){#fig:008 width=70%}

# Выводы

Я освоил процедуры компиляции и сборки программ, написанных на NASM.


