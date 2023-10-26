---
## Front matter
title: "Лабораторная работа No4. Создание и процесс
обработки программ на языке ассемблера NASM"
subtitle: "Дисциплина:Архитектура компьютера"
author: "Сущенко Алина Николаевна"

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

Освоение процедуры компиляции и сборки программ, написанных на ассемблере NASM

# Задание

1. Создать каталог для работы с заданиями на языке NASM.
2. Создать текстоый файл 'hello.asm' и открыть этот файл с помощью текстового редактора.
3. Ввести текст в созданный файл.
4. Транслировать текст в объектный файл.
5. Выполнить компановку объектного файла и запустить файл.
6. Создать копию созданного файла, переименовать его в 'lab4.asm' и проделать те же действия с файлом 'hello.asm'
7. Скопировать файлы в репозиторий.
8. Загрузить файлы на Github.

# Выполнение лабораторной работы

1. Программа Hello world!

	Создаём каталог для работы на NASM командой 'mkdir -p' (рис [#fig:001])


![Создание каталога с помощью 'mkdir'](image|1.png){#fig:001 width=70%}


	Переход в каталог

Переходим в каталог и создаём текстовй файл 'hello.asm' (рис [#fig:002])


![Переход в каталог и создание текстового файла](image|2.png){#fig:002 width=70%}


	Проверяем наличие файла.(рис [#fig:003])


![Наличие файла](image|3.png){#fig:003 width=70%}


	Открываем файл с помощью gedit (рис [#fig:004])


![Команда gedit](image|4.png){#fig:004 width=70%}


	Вводим открытый файл текст 'Hello world!' (рис [#fig:005])


![Команда gedit](image|5.png){#fig:005 width=70%}


2. Транслятор NASM

	С помощью команды 'nasm -f elf' транслируем текст программы в объектный файл и проверем наличие ([#fig:006])


![Транслируем текст и видим, что всё на месте](image|6.png){#fig:006 width=70%}


3. Синтаксис командной сторки NASM

	С помощью команд комплириуем исходный файл 'hello.asm' в 'obj.o' при помози команд 'nasm -o', '-f elf -g -l' и проверяем их наличие (рис [#fig:007])
	

![Компилировка файла и их наличие](image|7.png){#fig:007 width=70%}


4. Компановщик LD 

	Передаём файл 'hello.asm' на обработку с помощью команды 'ld -m elf_i386 .. -o' и проверяем  (рис [#fig:008])
	

![Выполняем компоновку и проверяем](image|8.png){#fig:008 width=70%}




![Выполняем компоновку и проверяем](image|9.png){#fig:009 width=70%}


	1)Имя файла 'main' 2)Имя объектного файла : 'obj.o'
	
5. Запуск файла.

	С помощью команды './hello' запускаем файл (рис [#fig:010])	


![Работа команды './hello'](image|10.png){#fig:010 width=70%}	

	
# Выполнение заданий для самостоятельной работы

1. С помощью команды 'ср' создаём компию файла и называем его 'lab4.asm' и проверяем его наличие (рис [#fig:011])


![Создание нового файла](image|11.png){#fig:011 width=70%}	
	
	
	С помощью gedit открываем файл 'lab4.asm' и вносим своё имя и фамилию (рис [#fig:012])	


![Открытие нового файла](image|12.png){#fig:012 width=70%}


	C помощью 'nasm -f elf' транслируем текст программы в файл  и проверяем  (рис [#fig:013])
	

![Транслируем текст программы](image|13.png){#fig:013 width=70%}


	Компилируем исходный файл  с помощью 'nasm -o' и '-f elf -g -l' и проверяем (рис [#fig:014])
	
	
![Компиляция и проверка](image|14.png){#fig:014 width=70%}


	Передаём объектный файл на обработку и проверяем (рис [#fig:015])
	
	
![Выполнение компановки и проверка](image|15.png){#fig:015 width=70%}


	По тому же принципу передаём файл 'obj4.o' (рис [#fig:016])
	
	
![Выполнение компановки и проверка](image|16.png){#fig:016 width=70%}


	С помощью './lab4' запускаем файл.(рис [#fig:017])
	

![Выполнение компановки и проверка](image|17.png){#fig:017 width=70%}


	Копируем файлы в лок.репозиторий в нужный нам каталог.(рис [#fig:018])
	

![Выполнение компановки и проверка](image|18.png){#fig:018 width=70%}


	Проверяем (рис [#fig:019])
	
	
![Переход и проверка](image|19.png){#fig:019 width=70%}
	
	
	Загрузка файлов на github (рис [#fig:020])
	

![Загрузка файлов](image|20.png){#fig:020 width=70%}


	Проверка (рис [#fig:021])
	
	
![Загрузка файлов](image|21.png){#fig:020 width=70%}


# Выводы

В ходе выполнения работы мы освоили компиляцию и сборку программ на ассемблере NASM.


