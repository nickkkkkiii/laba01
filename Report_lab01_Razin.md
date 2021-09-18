---
# Front matter
title: "Отчёт по лабораторной работе №1"
subtitle: "Установка и конфигурация операционной системы на виртуальную машину"
author: "Разин Никита Андреевич, НБИбд-02-18"
tutor: "Кулябов Д.С."

# Generic otions
lang: ru-RU
toc-title: "Содержание"

# Bibliography
bibliography: bib/cite.bib
csl: pandoc/csl/gost-r-7-0-5-2008-numeric.csl

# Pdf output format
toc: true # Table of contents
toc_depth: 2
lof: true # List of figures
lot: true # List of tables
fontsize: 12pt
linestretch: 1.5
papersize: a4
documentclass: scrreprt
## I18n
polyglossia-lang:
  name: russian
  options:
	- spelling=modern
	- babelshorthands=true
polyglossia-otherlangs:
  name: english
### Fonts
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
## Misc options
indent: true
header-includes:
  - \linepenalty=10 # the penalty added to the badness of each line within a paragraph (no associated penalty node) Increasing the value makes tex try to have fewer lines in the paragraph.
  - \interlinepenalty=0 # value of the penalty (node) added after each line of a paragraph.
  - \hyphenpenalty=50 # the penalty for line breaking at an automatically inserted hyphen
  - \exhyphenpenalty=50 # the penalty for line breaking at an explicit hyphen
  - \binoppenalty=700 # the penalty for breaking a line at a binary operator
  - \relpenalty=500 # the penalty for breaking a line at a relation
  - \clubpenalty=150 # extra penalty for breaking after first line of a paragraph
  - \widowpenalty=150 # extra penalty for breaking before last line of a paragraph
  - \displaywidowpenalty=50 # extra penalty for breaking before last line before a display math
  - \brokenpenalty=100 # extra penalty for page breaking after a hyphenated line
  - \predisplaypenalty=10000 # penalty for breaking before a display
  - \postdisplaypenalty=0 # penalty for breaking after a display
  - \floatingpenalty = 20000 # penalty for splitting an insertion (can only be split footnote in standard LaTeX)
  - \raggedbottom # or \flushbottom
  - \usepackage{float} # keep figures where there are in the text
  - \floatplacement{figure}{H} # keep figures where there are in the text
---

# *1.1. Цель работы:*

```
- Приобретение практических навыков установки операционной системы на виртуальную машину, настройки минимально необходимых для
дальнейшей работы сервисов.
```

# Задание

```
Лабораторная работа подразумевает установку на виртуальную машину VirtualBox операционной системы Linux, дистрибутив Centos, а также минимально необходимых программ для работы в дальнейшем.
```

# Теоретическая часть


Виртуализация позволяет создать на одном компьютере (хосте) несколько виртуальных компьютеров (ВМ), причем у каждого будет своя операционная система, ядра процессора, память, хранилище и сеть. Поскольку с помощью виртуализации можно собрать множество небольших нагрузок на одном физическом компьютере, она обеспечивает высокую степень использования ресурсов, за счет чего снижаются расходы на ИТ.

Виртуализация реализуется с помощью гипервизора—, который объединяет виртуальную машину и компьютер-хост. Гипервизор — это уровень программного обеспечения, который позволяет виртуальным машинам работать на базовом компьютере и распределяет процессоры, память и хранилище между виртуальными машинами.

VirtualBox — это широко используемый продукт для виртуализации. Это бесплатное программное обеспечение с открытым исходным кодом, которое позволяет разработчикам и ИТ-администраторам быстро развертывать операционные системы. У VirtualBox есть версии для macOS, Linux и Windows. Среди других гипервизоров можно выделить VMware vSphere и Microsoft Hyper-V. [[1]](https://www.oracle.com/ru/cloud/compute/virtual-machines/what-is-virtual-machine/) . Возможна установка и запуск стольких виртуальных машин, сколько пользователь захочет. Единственные ограничения - это дисковое пространство и память. 

**Пару слов об ОС, которую мы собираемся установить на нашу ВМ, а именно CentOS:**
CentOS (англ. Community ENTerprise Operating System) — дистрибутив Linux, основанный на коммерческом Red Hat Enterprise Linux компании Red Hat и совместимый с ним. Срок поддержки каждой версии CentOS составляет 10 лет. Каждая версия обновляется каждые 6 месяцев для поддержки новых аппаратных средств.

CentOS использует программу yum (начиная с версии 7.0 используется пакетный менеджер dnf) для скачивания и установки обновлений из репозитория CentOS Mirror Network, тогда как Red Hat Enterprise Linux получают обновления с серверов Red Hat Network. CentOS до версии 5.0 для обновлений использовал также программу up2date.

Помимо прочего, CentOS использовалась как ОС по умолчанию в проекте Cluster Compute Instance (CCI) от Amazon, суть которого заключается в том, что сдаются в аренду мощности большого числа стандартных стоечных серверов.



# *1.2. Практическая часть - ход радоты:*
## 1.

![](https://github.com/nickkkkkiii/lab01/blob/main/Screenshot_1.png?raw=true)

На данном скриншоте я запустил Oracle Virtual Box и даю имя и указываю тип своей ОС.
## 2.

![](https://github.com/nickkkkkiii/lab01/blob/main/Screenshot_2.png?raw=true)

На данном скриншоте я указываю объем оперативной памяти в 2 ГБ своей ОС.

## 3.

![](https://github.com/nickkkkkiii/lab01/blob/main/Screenshot_3.png?raw=true)

На данном скриншоте я указываю тип файла, который определяет формат для использования при создании нового жесткого диска.

## 4.

![](https://github.com/nickkkkkiii/lab01/blob/main/Screenshot_4.png?raw=true)

На данном скриншоте я указываю формат хранения, где динамический жесткий диск более подходит для нашего проекта, потому что диск будет в зависимости от количества информации расширятся или уменьшаться.

## 5.

![](https://github.com/nickkkkkiii/lab01/blob/main/Screenshot_5.png?raw=true)

На данном скриншоте я указываю размер нового виртуального диска.

## 6.

![](https://github.com/nickkkkkiii/lab01/blob/main/Screenshot_6.png?raw=true)

На данном скриншоте я указываю место, где находится образ устанавливаемой ОС на VB.

## 7.

![](https://github.com/nickkkkkiii/lab01/blob/main/Screenshot_7.png?raw=true)

На данном скриншоте я подтверждаю установку ОС на VB.

## 8.

![](https://github.com/nickkkkkiii/lab01/blob/main/Screenshot_8.png?raw=true)

На данном скриншоте после загрузки образа я выбираю язык системы.

## 9.

![](https://github.com/nickkkkkiii/lab01/blob/main/Screenshot_9.png?raw=true)

На данном скриншоте я выбираю пакет программ для установки на ОС.

## 10.

![](https://github.com/nickkkkkiii/lab01/blob/main/Screenshot_10.png?raw=true)

На данном скриншоте я прописываю имя узла "razin.localdomain" и подключаю к сети.

## 11.

![](https://github.com/nickkkkkiii/lab01/blob/main/Screenshot_11.png?raw=true)

На данном скриншоте я создаю пользователя (прописываю пароль и имя пользователя).

## 12.

![](https://github.com/nickkkkkiii/lab01/blob/main/Screenshot_12.png?raw=true)

Наша ОС загрузилась и готова к использованию.

# *2.0. Вывод:*
После выполнения данной лабораторной работы мы научились ставить ОС на Oracle Virtual VM Box, а также настраивать параметры к ее запуску.

# Список литературы{.unnumbered}

1. [Что такое виртуальная машина?](https://www.oracle.com/ru/cloud/compute/virtual-machines/what-is-virtual-machine/)
2. [Операционная система CentOS.](https://andreyex.ru/centos-7/)