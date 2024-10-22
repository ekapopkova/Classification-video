# Проект: Классификация видеороликов по описанию 

Студия мультфильмов собирает статистику для оценки популярности различных проектов. Им важно агрегировать данные по проектам, а не по отдельным роликам – агрегация статистики по проектам помогает принимать обоснованные бизнес-решения и увеличивать успех новых проектов.

## Задача

Нужно создать автоматизированное решение для определения принадлежности видеороликов к проектам на основе анализа текстового описания, субтитров и другой доступной информации. При разработке надо не только максимизировать метрику f1, но и создать наиболее гибкое и масштабируемое решение по возможности без ручной разметки.

## Данные

Для работы над задачей были предоставлены следующие данные:

- файл с обучающей выборкой 

- файл с тестовой выборкой

Описание данных

date дата, когда ролик появился на ютубе
reel_name название ролика
yt_reel_id уникальный идентификатор ролика на ютубе
cartoon название проекта, целевая переменная
url ссылка на ролик (включает идентификатор)
text текст сниппета, включает название ролика и описание
seconds длительность
is_shorts вертикальные видеоролики продолжительностью <60сек
broadcast лайвы, прямые эфиры
yt_channel_id идентификатор ютуб канала
yt_channel_name название ютуб канала
yt_ch_url ссылка на ютуб канал
yt_channel_type тип канала (Мультфильмы, Детские, Блогеры, Shorts…)
flag_closed ютуб канал закрыт, если 1
international метка международных каналов,
каналов на иностранном языке (переведенный контент)
language язык

## В процессе работы над проектом сделано следующее (смотри ноутбук **project_mult_final.ipynb**):

1. Загружены и первроначально обработанны данные (ноутбук - project_mult_preparetion.ipynb )
2. Исследованы данные, выбрана и обучена модель классификации роликов (более подробный поиск модели и набора данных можно посмотреть в ноутбуке project_mult_research.ipynb)
3. Разработа функция для классификация роликов, на вход подается список id роликов, на выходе получаем словарь типа:
  {‘yt_reel_id’: идентификатор,‘cartoon’: название_проекта_или_none}
Для роликов, которые не входят ни в один проект, функция возвращает значение none

## Используемые библиотеки
*pandas, numpy, scikit-learn, spacy, googletrans, nltk, re, BERT


## Технические требования

* googletrans 3.1.0a0
* spasy 3.8.0


