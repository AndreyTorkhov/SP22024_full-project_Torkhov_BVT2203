# SP22024_docker-app_Torkhov_BVT2203
summer Practice MTUCI 2024 full task 

## Описание

Приложение со списком вакансий, который можно фильтровать.

## Задачи

1. Изучить существующие платформы для парсинга.
2. Сформулировать функциональные требования к системе.
3. Спроектировать базу данных.
4. Написать инструкцию пользователя.
5. Провести тестирование системы.

## Требования

- Docker
- Docker Compose

## Технологии

- **Backend:** FastAPI, SQLAlchemy, Beautiful Soup
- **Frontend:** React, Axios, Bootstrap
- **Database:** PostgreSQL

### Запуск проекта

1. Клонируйте репозиторий с подмодулями:

    ```bash
    git clone --recurse-submodules https://github.com/AndreyTorkhov/SP22024_full-project_Torkhov_BVT2203.git
    cd SP22024_full-project_Torkhov_BVT2203
    ```

2. Если репозиторий уже был клонирован без подмодулей, инициализируйте и обновите подмодули:

    ```bash
    git submodule update --init --recursive
    ```

3. Запустите Docker Compose:

    ```bash
    docker-compose up --build
    ```

4. Backend будет доступен по адресу  `http://localhost:8000`, а frontend по адресу  `http://localhost:3000`.

## Структура директории

- `my-backend/`: Содержит код backend (как подмодуль).
- `my-frontend/`: Содержит код frontend (как подмодуль).
- `.gitmodules` : Конфигурационный файл для подмодулей.
- `docker-compose.yaml`: Конфигурационный файл Docker Compose.
- `README.md`: Этот файл.

## Использование
Приложение будет доступно по следующим адресам:
- Backend - http://localhost:8000
- Frontend - http://localhost:3000

1.Карточки с вакансиями
На главной странице отображаются карточки с информацией о вакансиях. Каждая карточка включает в себя:

-Название вакансии
-Работодатель
-Город
-Зарплата (если указана)
-График работы
-Аккредитованность компании
-Ссылка на вакансию

2.Фильтры:

-Указана зарплата или нет: Выберите этот фильтр, чтобы показать только те вакансии, у которых указана зарплата.
-Работодатель: Выберите одного или нескольких работодателей из выпадающего списка, чтобы отфильтровать вакансии по выбранным работодателям.
-График работы: Выберите один или несколько графиков работы из выпадающего списка для фильтрации вакансий по выбранным графикам.
-Аккредитованные компании: Нажмите на кнопку, чтобы отфильтровать вакансии только от аккредитованных компаний.
-Актуальность вакансии (по дате добавления): Нажмите на кнопку "Сортировать по дате" для изменения порядка отображения вакансий от самых новых к самым старым и обратно.

## Структура базы данных

- **Таблица вакансий (jobs)**
  - ID: первичный ключ
  - Title: название вакансии
  - Employer: работодатель
  - Area: область
  - Salary: зарплата (если указана)
  - Schedule_name: график работы
  - Accredited_it_employer: аккредитованный работодатель (булево значение)
  - URL: ссылка на вакансию

## Парсинг

Парсинг данных осуществляется с помощью скрипта `main.py` в директории `parser_summerTask/parser/`. Скрипт использует библиотеку Beautiful Soup для извлечения данных с целевого веб-сайта и сохраняет эти данные в базу данных PostgreSQL.

## Тестирование

Проведено тестирование системы для проверки корректности работы парсинга, базы данных, фильтрации и сортировки вакансий на фронтенде. В тестировании были использованы следующие подходы:

-Тестирование парсинга данных для проверки корректности извлечения информации.
-Тестирование базы данных для проверки правильности сохранения и извлечения данных.
-Тестирование фильтров на фронтенде для проверки их корректной работы и отображения.
