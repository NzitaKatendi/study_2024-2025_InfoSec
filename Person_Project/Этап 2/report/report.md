---
# Front matter
lang: ru-RU
title: "Основы информационной безопасности"
subtitle: "Индивидуальный проект. Этап №2. Установка DVWA"

author: Нзита Диатезилуа Катенди

# Formatting
toc-title: "Содержание"
toc: true # Table of contents
toc_depth: 2
lof: true # List of figures
fontsize: 12pt
linestretch: 1.5
papersize: a4paper
documentclass: scrreprt
polyglossia-lang: russian
polyglossia-otherlangs: english
mainfont: PT Serif
romanfont: PT Serif
sansfont: PT Sans
monofont: PT Mono
mainfontoptions: Ligatures=TeX
romanfontoptions: Ligatures=TeX
sansfontoptions: Ligatures=TeX,Scale=MatchLowercase
monofontoptions: Scale=MatchLowercase
indent: true
pdf-engine: lualatex
header-includes:
  - \linepenalty=10 # the penalty added to the badness of each line within a paragraph (no associated penalty node) Increasing the υalue makes tex try to haυe fewer lines in the paragraph.
  - \interlinepenalty=0 # υalue of the penalty (node) added after each line of a paragraph.
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

# Постановка задачи

Целью данной работы является установка DVWA на Kali Linux в виртуальную машину.

# Теоретические сведения

Damn Vulnerable Web Application (DVWA) -- это веб-приложение PHP/MySQL, которое чертовски уязвимо[~@dvwa]. Его основная цель -- помочь специалистам по безопасности проверить свои навыки и инструменты в правовой среде, помочь веб-разработчикам лучше понять процессы обеспечения безопасности веб-приложений, а также помочь студентам и преподавателям узнать о безопасности веб-приложений в контролируемом классе. обстановка помещения.

DVWA (Damn Vulnerable Web Application) — это приложение, предназначенное для практики работы с распространёнными веб-уязвимостями, предлагая пользователю интуитивно понятный интерфейс. Оно содержит как документированные, так и недокументированные уязвимости, позволяя исследовать безопасность веб-приложений на разных уровнях сложности.

Некоторые из уязвимостей, представленных в DVWA, включают:

- **Брутфорс**: Атака на формы входа, используемая для тестирования инструментов, позволяющих подбирать пароли, и демонстрации уязвимости слабых паролей.
- **Выполнение команд**: Позволяет злоумышленнику исполнять команды на уровне операционной системы.
- **Межсайтовая подделка запроса (CSRF)**: Позволяет злоумышленнику изменять пароль администратора.
- **Внедрение файлов**: Злоумышленник может подключать удалённые или локальные файлы к веб-приложению.
- **SQL-внедрение**: Позволяет вставлять SQL-код в запросы через поля ввода, включая слепое и основанное на ошибках внедрение.
- **Небезопасная выгрузка файлов**: Позволяет загружать вредоносные файлы на сервер.
- **Межсайтовый скриптинг (XSS)**: Злоумышленник может внедрять свои скрипты в веб-приложение или базу данных, включая отражённые и сохранённые XSS.
- **Пасхальные яйца**: Раскрытие путей к файлам, обход аутентификации и другие уязвимости.

DVWA предлагает четыре уровня безопасности, которые меняют уязвимость веб-приложений:

- **Невозможный**: Уровень безопасности, при котором приложение защищено от всех уязвимостей. Используется для сравнения уязвимого кода с безопасным.
- **Высокий**: Уровень сложности с элементами более сложных и альтернативных плохих практик, который снижает возможности эксплуатации.
- **Средний**: Уровень, показывающий примеры плохих практик безопасности, где разработчик пытался обеспечить безопасность, но не смог.
- **Низкий**: Полностью уязвимый уровень, предназначенный для демонстрации плохих практик программирования и обучения базовым методам эксплуатации.

# Выполнение лабораторной работы

Скопируем в каталог /etc/www/html файла веб приложения DVWA с Гита (рис. @fig:001)

![Клонирование репозитория с DVWA](image/1.png){#fig:001 width=70%}

Затем запускаем веб сервер(рис. @fig:002, @fig:003).

![Запуск apache2](image/2.png){#fig:002 width=70%}

![Проверка работы веб-сервера](image/3.png){#fig:003 width=70%}

Затем скопируем файл конфигураций DVWA, чтобы затем можно было его безопасно изменять. Мы воспользуемся именем пользователя и паролем по умолчанию(рис. @fig:004, @fig:005).

![Просмтр файла конфигураций](image/4.png){#fig:004 width=70%}

![Просмотр стартового окна DVWA](image/5.png){#fig:005 width=70%}

 Запустим сервер mariadb и создадтм на нем пользоватедя и пароль совпадают с данными в файле конфигураций dvwa)(рис. @fig:006, @fig:007).

![Создание пользователя mariadb и базы данных](image/6.png){#fig:006 width=70%}

![Проверка пользователя mariadb](image/7.png){#fig:007 width=70%}

Затем на стартовом окне DVWA нажмем кнопку `Create/Reset Database`, и нас перекинет на страницу ввода данных учетной записи. После ввода увидим рабочую область DVWA(рис. @fig:008, @fig:009).

![Аутентификация](image/8.png){#fig:008 width=70%}

![Запуск DVWA](image/9.png){#fig:009 width=70%}

# Выводы

В резултате выпольнения работы был установлен DVWA на Kali Linux.

# Список литературы{.unnumbered}
::::::
:::


