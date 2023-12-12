---
## Front matter
title: "Отчёт по лабораторной работе №8"
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

Приобретение навыков написания программ с использованием циклов и обработкой
аргументов командной строки.

# Задание

1. Реализация циклов в NASM
2. Обработка аргументов командной строки
3. Задание для самостоятельной работы

# Теоретическое введение

Цикл в программировании — это управляющая конструкция, которая заставляет какой-то блок кода выполняться несколько раз.

# Выполнение лабораторной работы

## Реализация циклов в NASM

 Создаю каталог для программ для лабораторной работы №8, перехожу в него и создаю файл lab8-1.asm, в который ввожу программу вывода значений регистра ecx (рис. @fig:001).

![Создание каталога и файла в ней, редактирование файла](image/Снимок экрана от 2023-12-12 23-03-27.png){#fig:001 width=70%}


Создаю исполняемый файл и запускаю его (рис. @fig:002). Программа отработала корректно.

![Исполнение программы](image/Снимок экрана от 2023-12-12 23-05-05.png){#fig:002 width=70%}


Изменяю текст программы добавив изменение значения регистра ecx в цикле (рис. @fig:003).

![Изменение текста программы](image/Снимок экрана от 2023-12-12 23-21-17.png){#fig:003 width=70%}


Создаю исполняемый файл и запускаю его (рис. @fig:004). Число проходов цикла равно N/2.

![Исполнение программы](image/Снимок экрана от 2023-12-12 23-21-34.png){#fig:004 width=70%}


Вношу изменения в текст программы добавив команды push и pop для сохранения значения счётчика loop(рис. @fig:005).

![Изменение программы](image/Снимок экрана от 2023-12-12 23-22-38.png){#fig:005 width=70%}


Создаю исполняемый файл и проверяю его работу (рис. @fig:006). Число проходов соответствует значению N введённому с клавиатуры.

![Исполнение программы](image/Снимок экрана от 2023-12-12 23-23-22.png){#fig:006 width=70%}

## Обработка аргументов командной строки

Создаю файл lab8-2.asm и ввожу в него программу обработки аргументов командной строки (рис. @fig:007).

![Создание и редактирование файла](image/Снимок экрана от 2023-12-12 23-26-35.png){#fig:007 width=70%}


Создаю исполняемый файл. Запускаю исполняемый файл (рис. @fig:008). Программой были обработаны все аргументы.

![Запуск исполняемого файла](image/Снимок экрана от 2023-12-12 23-26-52.png){#fig:008 width=70%}


Создаю файл lab8-3.asm и ввожу в него программу вычисления суммы аргументов командной строки (рис. @fig:009).

![Создание файла и его редактирование](image/Снимок экрана от 2023-12-12 23-27-59.png){#fig:009 width=70%}


Создаю исполняемый файл и запускаю его, указав аргументы 12, 13, 7, 10, 5 (рис. @fig:010). Программа отработала корректно.

![Запуск исполняемого файла](image/Снимок экрана от 2023-12-12 23-29-26.png){#fig:010 width=70%}


Создаю файл lab8-3-1.asm и ввожу в него программу вычисления произведения аргументов командной строки (рис. @fig:011).

![Создание файла и его редактирование](image/Снимок экрана от 2023-12-12 23-34-36.png){#fig:011 width=70%}


Создаю исполняемый файл и запускаю его, указав аргументы 4 5 6 7 8 9 (рис. @fig:012). Программа отработала корректно.

![Запуск исполняемого файла](image/Снимок экрана от 2023-12-12 23-35-48.png){#fig:012 width=70%}

Текст программы из файла lab8-3-1.asm:

```NASM
%include "in_out.asm"
SECTION .data
msg db 'результат: '
SECTION .text
GLOBAL _start

_start:
pop ecx
pop edx
sub ecx,1
mov esi,1

next:
cmp ecx,0
jz _end

pop eax
call atoi
mul esi
mov esi, eax

loop next

_end:
mov eax, msg
call sprint
mov eax, esi
call iprintLF
call quit
```

## Задание для самостоятельной работы (Вариант 5)

Создаю файл lab8-4.asm и ввожу текст программы для вычисления суммы значений функции f(x)=3(10+x) (рис. @fig:013).

![Создание и редактирование файла](image/Снимок экрана от 2023-12-12 23-56-39.png){#fig:013 width=70%}

Текст программы из файла lab8-4.asm:

%include 'in_out.asm'

SECTION .data
f_x db "f(x)=4x+3",0h
msg db 10,13,'результат: ',0h

SECTION .text
global _start

_start:
pop ecx
pop edx
sub ecx, 1
mov esi, 0

next:
cmp ecx,0h
jz _end
pop eax
call atoi
mov ebx, 4                                                                                 
mul ebx
add eax, 3
add esi, eax

loop next

_end:
mov eax, f_x
call sprint
mov eax, msg
call sprint
mov eax, esi
call iprintLF

call quit

Создаю исполняемый файл и запускаю исполняемый файл с разными аргументами (рис. @fig:014). Программа отработала корректно.

![Запуск исполняемого файла](image/Снимок экрана от 2023-12-12 23-58-39.png){#fig:014 width=70%}

# Выводы

Были получены навыки по организации циклов и работе со стеком на языке NASM.

# Список литературы{.unnumbered}

1. [Лабораторная работа №8](https://esystem.rudn.ru/pluginfile.php/2089548/mod_resource/content/0/%D0%9B%D0%B0%D0%B1%D0%BE%D1%80%D0%B0%D1%82%D0%BE%D1%80%D0%BD%D0%B0%D1%8F%20%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%B0%20%E2%84%968.%20%D0%9F%D1%80%D0%BE%D0%B3%D1%80%D0%B0%D0%BC%D0%BC%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5%20%D1%86%D0%B8%D0%BA%D0%BB%D0%B0.%20%D0%9E%D0%B1%D1%80%D0%B0%D0%B1%D0%BE%D1%82%D0%BA%D0%B0%20%D0%B0%D1%80%D0%B3%D1%83%D0%BC%D0%B5%D0%BD%D1%82%D0%BE%D0%B2%20%D0%BA%D0%BE%D0%BC%D0%B0%D0%BD%D0%B4%D0%BD%D0%BE%D0%B9%20%D1%81%D1%82%D1%80%D0%BE%D0%BA%D0%B8..pdf)
