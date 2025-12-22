---
## Front matter
title: "Отчёт по лабораторной работе №6


Компьютерный практикум по статистическому анализу данных"
subtitle: "Решение моделей в непрерывном и дискретном времени"
author: "Выполнил: Исаев Булат Абубакарович, 


НПИбд-01-22, 1132227131"

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
lolTitle: "Листинги"
## Misc options
indent: true
header-includes:
  - \usepackage{indentfirst}
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# Цель работы

Основной целью работы является освоение специализированных пакетов для решения задач в 
непрерывном и дискретном времени.
 
# Выполнение лабораторной работы

## Решение обыкновенных дифференциальных уравнений

Вспомним, что обыкновенное дифференциальное уравнение (ОДУ) описывает изменение некоторой 
переменной u.

Для решения обыкновенных дифференциальных уравнений (ОДУ) в Julia можно использовать пакет 
diffrentialEquations.jl.

## Модель экспоненциального роста

Рассмотрим пример использования этого пакета для решение уравнения модели экспоненциального роста, 
описываемую уравнением, где a — коэффициент роста. 

Численное решение в Julia будет иметь следующий вид, а также график, 
соответствующий полученному решению (рис. [-@fig:001]):

![График модели экспоненциального роста](images/1.PNG){ #fig:001 width=100% height=100% }

При построении одного из графиков использовался вызов sol.t, чтобы захватить массив моментов 
времени. Массив решений можно получить, воспользовавшись sol.u.

Если требуется задать точность решения, то можно воспользоваться параметрами abstol 
(задаёт близость к нулю) и reltol (задаёт относительную точность). По умолчанию эти параметры 
имеют значение abstol = 1e-6 и reltol = 1e-3.

Для модели экспоненциального роста (рис. [-@fig:002]):

![График модели экспоненциального роста (задана точность решения)](images/2.PNG){ #fig:002 width=100% height=100% }

## Система Лоренца

Динамической системой Лоренца является нелинейная автономная система обыкновенных дифференциальных 
уравнений третьего порядка.

Система получена из системы уравнений Навье–Стокса и описывает движение воздушных потоков в 
плоском слое жидкости постоянной толщины при разложении скорости течения и температуры в 
двойные ряды Фурье с последующем усечением до первых-вторых гармоник.

Решение системы неустойчиво на аттракторе, что не позволяет применять классические численные методы на 
больших отрезках времени, требуется использовать высокоточные вычисления.

Численное решение в Julia будет иметь следующий вид (рис. [-@fig:003]):

![Аттрактор Лоренца](images/3.PNG){ #fig:003 width=100% height=100% }

Можно отключить интерполяцию (рис. [-@fig:004]):

![Аттрактор Лоренца (интерполяция отключена)](images/4.PNG){ #fig:004 width=100% height=100% }

## Модель Лотки–Вольтерры

Модель Лотки–Вольтерры описывает взаимодействие двух видов типа «хищник – жертва».

Численное решение в Julia будет иметь следующий вид (рис. [-@fig:005]):

![Модель Лотки–Вольтерры: динамика изменения численности популяций](images/5.PNG){ #fig:005 width=100% height=100% }

Фазовый портрет (рис. [-@fig:006]):

![Модель Лотки–Вольтерры: фазовый портрет](images/6.PNG){ #fig:006 width=100% height=100% }

## Самостоятельное выполнение

Выполнение задания №1 (рис. [-@fig:007]):

![Решение задания №1](images/7.PNG){ #fig:007 width=100% height=100% }

Выполнение задания №2 (рис. [-@fig:008]):

![Решение задания №2](images/8.PNG){ #fig:008 width=100% height=100% }

Выполнение задания №3 (рис. [-@fig:009]):

![Решение задания №3](images/9.PNG){ #fig:009 width=100% height=100% }

Выполнение задания №4 (рис. [-@fig:010]):

![Решение задания №4](images/10.PNG){ #fig:010 width=100% height=100% }

Выполнение задания №5 (рис. [-@fig:011]):

![Решение задания №5](images/11.PNG){ #fig:011 width=100% height=100% }

Выполнение задания №6 (рис. [-@fig:012]):

![Решение задания №6](images/12.PNG){ #fig:012 width=100% height=100% }

Выполнение задания №7 (рис. [-@fig:013]):

![Решение задания №7](images/13.PNG){ #fig:013 width=100% height=100% }

Выполнение задания №8 (рис. [-@fig:014]):

![Решение задания №8](images/14.PNG){ #fig:014 width=100% height=100% }

# Вывод

В ходе выполнения лабораторной работы были освоены специализированные пакеты для 
решения задач в непрерывном и дискретном времени.

# Список литературы. Библиография


[1] Julia Documentation: https://docs.julialang.org/en/v1/
