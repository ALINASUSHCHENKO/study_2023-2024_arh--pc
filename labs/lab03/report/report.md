---
## Front matter
title: "Лабораторная работа No3. Язык разметки Markdown"
subtitle: "Архитектура Компьютера"
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

Целью работы является освоение процедуры оформления отчетов с помощью легковесного
языка разметки Markdown

# Теоретическое введение

Чтобы создать заголовок, используйте знак #, например:
# This is heading 1
## This is heading 2
### This is heading 3
#### This is heading 4
Чтобы задать для текста полужирное начертание, заключите его в двойные звездочки:
This text is **bold**.
Чтобы задать для текста курсивное начертание, заключите его в одинарные звездочки:
This text is *italic*.
Чтобы задать для текста полужирное и курсивное начертание, заключите его в тройные
звездочки:
This is text is both ***bold and italic***.
Блоки цитирования создаются с помощью символа >:
> The drought had lasted now for ten million years, and the reign of the
terrible lizards had long since ended. Here on the Equator, in the
continent which would one day be known as Africa, the battle for existence
had reached a new climax of ferocity, and the victor was not yet in sight.
In this barren and desiccated land, only the small or the swift or the
fierce could flourish, or even hope to survive.
↪
↪
↪
↪
↪
Упорядоченный список можно отформатировать с помощью соответствующих цифр:
Архитектура ЭВМ
1. First instruction
1. Sub-instruction
1. Sub-instruction
1. Second instruction
Чтобы вложить один список в другой, добавьте отступ для элементов дочернего списка:
1. First instruction
1. Second instruction
1. Third instruction
Неупорядоченный (маркированный) список можно отформатировать с помощью звездо-
чек или тире:
* List item 1
* List item 2
* List item 3
Чтобы вложить один список в другой, добавьте отступ для элементов дочернего списка:
- List item 1
- List item A
- List item B
- List item 2
Синтаксис Markdown для встроенной ссылки состоит из части [link text], представляю-
щей текст гиперссылки, и части (file-name.md) – URL-адреса или имени файла, на который
дается ссылка:
[link text](file-name.md)
или
[link text](http://example.com/ "Необязательная подсказка")
Markdown поддерживает как встраивание фрагментов кода в предложение, так и их разме-
щение между предложениями в виде отдельных огражденных блоков. Огражденные блоки
кода — это простой способ выделить синтаксис для фрагментов кода. Общий формат ограж-
денных блоков кода:
``` language
your code goes in here
```
Архитектура ЭВМ
3.2.2. Оформление формул в Markdown
Внутритекстовые формулы делаются аналогично формулам LaTeX. Например, формула
sin2(𝑥) + cos2(𝑥) = 1 запишется как
$\sin^2 (x) + \cos^2 (x) = 1$
Выключение формулы:
sin2(𝑥) + cos2(𝑥) = 1 (3.1)
со ссылкой в тексте «Смотри формулу ({-eq. 3.1}).» записывается как
$$
\sin^2 (x) + \cos^2 (x) = 1
$$ {#eq:eq1}
Смотри формулу (`[-@eq:eq1]`).
3.2.3. Оформление изображений в Markdown
В Markdown вставить изображение в документ можно с помощью непосредственного
указания адреса изображения. Синтаксис данной команды выглядит следующим образом:
! [Подпись к рисунку](/путь/к/изображению.png "Необязательная подсказка"){
#fig:fig1 width=70% }↪
Здесь:
• в квадратных скобках указывается подпись к изображению;
• в круглых скобках указывается URL-адрес или относительный путь изображения, а так-
же (необязательно) всплывающую подсказку, заключённую в двойные или одиночные
кавычки.
• в фигурных скобках указывается идентификатор изображения (#fig:fig1) для ссылки
на него по тексту и размер изображения относительно ширины страницы (width=90%)
Ссылка на изображение (рис. 3.1) может быть оформлена следующим образом (рис. [-
@fig:fig1])
3.2.4. Обработка файлов в формате Markdown
Преобразовать файл README.md можно следующим образом:
pandoc README.md -o README.pdf
или так
Демидова А. В. 25
Архитектура ЭВМ
Рис. 3.1. Подпись к рисунку
pandoc README.md -o README.docx
Для компиляции отчетов по лабораторным работам предлагается использовать следую-
щий Makefile
FILES = $(patsubst %.md, %.docx, $(wildcard *.md))
FILES += $(patsubst %.md, %.pdf, $(wildcard *.md))
LATEX_FORMAT =
FILTER = --filter pandoc-crossref
%.docx: %.md
-pandoc "$<" $(FILTER) -o "$@"
%.pdf: %.md
-pandoc "$<" $(LATEX_FORMAT) $(FILTER) -o "$@"
all: $(FILES)
@echo $(FILES)
clean:
-rm $(FILES) *~
26 Демидова А. В.
Архитектура ЭВМ
3.3. Техническое обеспечение
При выполнении лабораторной работы на своей технике необходимо установить следую-
щее ПО:
• TeX Live (https://www.tug.org/texlive/) последней версии.
• Pandoc (https://pandoc.org/).
На компьютерах в дисплейных классах факультета физико-математических и естествен-
ных наук РУДН все необходимое ПО установлено

# Выполнение лабораторной работы

1. Перейдите в каталог курса сформированный при выполнении лабораторной работы
No2

![Переход в каталог курса ](image/1.png){#fig:001 width=70%}


![Обновление локального репозиторий](image/2.png){#fig:002 width=70%}


![Переход к отчёту лаборатноной работе 2](image/3.png){#fig:003 width=70%}


![проводим компиляцию шаблона с использованием Makefile](image/4.png){#fig:004 width=70%}


![Удаление файлов](image/5.png){#fig:005 width=70%}

2. Откройте файл report.md c помощью любого текстового редактора, например gedit

![Использование команды gedit](image/6.png){#fig:006 width=70%}


![Создание отчёта](image/7.png){#fig:007 width=70%}

3. Загрузить файлы на github.

![Загрузка файлов](image/8.png){#fig:008 width=70%}


![Наличие файлов](image/9.png){#fig:009 width=70%}


4. Задание для самостоятельной работы.

![Наличие файлов](image/10.png){#fig:009 width=70%}

# Выводы

Мы приобрели практические навыки по работе с Markdown. Сохранили предыдущие лабораторные работы в github.

# Список литературы{.unnumbered}

::: {#refs}
:::
