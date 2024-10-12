---
## Front matter
lang: ru-RU
title: "Основы информационной безопасности. Индивидуальный проект"
subtitle: Этап № 5. Использование Burp Suite
author:
  - Нзита Диатезилуа Катенди
institute:
  - Российский университет дружбы народов, Москва, Россия
date: 12 октября 2024 г.

## i18n babel
babel-lang: russian
babel-otherlangs: english

## Formatting pdf
toc: false
toc-title: Содержание
slide_level: 2
aspectratio: 169
section-titles: true
theme: metropolis
header-includes:
 - \metroset{progressbar=frametitle,sectionpage=progressbar,numbering=fraction}
---

# Информация

## Докладчик

:::::::::::::: {.columns align=center}
::: {.column width="70%"}

  * Нзита Диатезилуа Катенди
  * студент
  * Российский университет дружбы народов
  * [1032215220@pfur.ru](mailto:1032215220@pfur.ru)
  * <https://github.com/NzitaKatendi>

:::
::::::::::::::

# Вводная часть

## Цели и задачи

**Задачи:**

- Перехватить HTTP запрос и ответ
- Проанализировать HTTP запрос и ответ

**Инструмент:**  DVWA, Burp Suite

# Выполнение лабораторной работы

## Установка ПО

![Установка ПО](image/1.png){#fig:001 width=80%}

## Создание проекта

![Создание проекта](image/2.png){#fig:002 width=65%}

## Создание проекта

![Установка параметров](image/3.png){#fig:003 width=65%}

## Настройка перехвата трафика

![Включение Burp Proxy](image/4.png){#fig:004 width=80%}

## Настройка перехвата трафика

![Настройка HTTP Proxy браузера](image/5.png){#fig:005 width=60%}

## Настройка перехвата трафика

![Установка флага allow_hijacking_localhost](image/6.png){#fig:006 width=70%}

## Перехват запросов

![Перехват запроса на вход на сайт](image/7.png){#fig:007 width=70%}

## Перехват запросов

![Запрос на аутентификацию](image/8.png){#fig:008 width=70%}

## Перехват запросов

![Функция повторения запроса](image/9.png){#fig:009 width=70%}

## Перехват запросов

![Изучение ответа на запрос с функцией повторения запроса](image/10.png){#fig:010 width=70%}

# Заключение

## Выводы

В результате выполнения работы научились на практике использовать ПО Burp Suite для перехвата, изменения и изучения HTTP запросов и ответов. 

## Список литературы

