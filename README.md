# QA Portfolio — Попов Владислав

## Обо мне
Начинающий QA-инженер с глубоким знанием теории тестирования и жизненного цикла ПО. 
Изучаю тестирование на практике. 
Умею составлять тестовую документацию, работать с DevTools,тестировать API, писать SQL-запросы.

[Сертификат](Certificate.pdf)

## Навыки и инструменты
- Инструменты: Jira, TestRail, Test it, Charles Proxy, Fiddler, Docker.
- Веб-тестирование: Chrome DevTools, работа с логами.
- API: Postman, REST JSON, SOAP XML, Kafka.
- Базы данных: SQL запросы в СУБД: MySQL, PostgreSQL.
- Прочее: HTML/CSS, Git, GitHub.
- Изучаю Java на базовом уровне для лучшего понимания разработки и дальнейшего роста в автоматизации тестирования.

## Контакты

- Email: windbow78@gmail.com
- Telegram: @popovladislove
  
## Учебный проект "Тестирование Swag Labs"

## О проекте

Тестирование открытого демо-сайта
[Swag Labs](https://www.saucedemo.com) (Sauce Demo) — интернет-магазин
от компании Sauce Labs.

Сайт предоставляет готовые учётные записи и специально содержит ряд дефектов

**URL:** https://www.saucedemo.com
**Тестовые учётные записи:**
- `standard_user` / `secret_sauce` — обычный пользователь
- `locked_out_user` / `secret_sauce` — заблокированный
- `problem_user` / `secret_sauce` — пользователь с багами
- `performance_glitch_user` / `secret_sauce` — медленная загрузка
- `error_user` / `secret_sauce` — пользователь с ошибками
- `visual_user` / `secret_sauce` — визуальные баги

## Результат

| № | Артефакт | Описание |
|---|----------|----------|
| 1 | [Тест-план](test-plan/test-plan.md) | Общий план тестирования сайта |
| 2 | [Чек-лист](checklist/checklist-cart.md) | Чек-лист модуля корзины |
| 3 | [Тест-кейсы](test-cases/test-cases-login.md) | Тест-кейсы авторизации |
| 4 | [Баг-репорты](bug-reports/bug-reports.md) | Найденные дефекты |
| 5 | [API-тесты](api-testing/api-tests.md) | Примеры тестирования API через Postman |
| 6 | [SQL-запросы](sql/sql-queries.md) | Примеры запросов для проверки данных |

---

## Учебный проект "Тестирование Wikipedia Mobile"

## О проекте

Учебный проект по тестированию реального мобильного приложения **Wikipedia Mobile**.

Проект выполнен с фокусом на:
- mobile testing;
- составление тестовой документации;
- bug reporting;
- валидацию данных через публичный **MediaWiki API**.

В рамках проекта были проверены основные пользовательские сценарии:
- первый запуск приложения;
- onboarding;
- поиск статьи;
- открытие статьи;
- переходы по внутренним ссылкам;
- переключение языка статьи;
- сохранение статьи;
- история просмотров;
- share статьи;
- работа без интернета;
- сохранение состояния после сворачивания;
- отображение интерфейса при смене ориентации устройства.

**Репозиторий проекта:**  
[Wikipedia Mobile QA Project](https://github.com/popovladislove/Wikipedia-Mobile-QA-Project)

## Результат

| № | Артефакт | Описание |
|---|----------|----------|
| 1 | [README проекта](https://github.com/popovladislove/Wikipedia-Mobile-QA-Project/blob/main/README.md) | Общая информация о mobile QA проекте |
| 2 | [Тест-план](https://github.com/popovladislove/Wikipedia-Mobile-QA-Project/blob/main/02_%D0%A2%D0%B5%D1%81%D1%82%D0%BE%D0%B2%D0%B0%D1%8F_%D0%B4%D0%BE%D0%BA%D1%83%D0%BC%D0%B5%D0%BD%D1%82%D0%B0%D1%86%D0%B8%D1%8F/%D0%A2%D0%B5%D1%81%D1%82_%D0%BF%D0%BB%D0%B0%D0%BD.md) | План тестирования мобильного приложения |
| 3 | [Чек-лист](https://github.com/popovladislove/Wikipedia-Mobile-QA-Project/blob/main/02_%D0%A2%D0%B5%D1%81%D1%82%D0%BE%D0%B2%D0%B0%D1%8F_%D0%B4%D0%BE%D0%BA%D1%83%D0%BC%D0%B5%D0%BD%D1%82%D0%B0%D1%86%D0%B8%D1%8F/%D0%A7%D0%B5%D0%BA_%D0%BB%D0%B8%D1%81%D1%82_Wikipedia_Mobile.csv) | Чек-лист основных mobile-сценариев |
| 4 | [Тест-кейсы](https://github.com/popovladislove/Wikipedia-Mobile-QA-Project/blob/main/02_%D0%A2%D0%B5%D1%81%D1%82%D0%BE%D0%B2%D0%B0%D1%8F_%D0%B4%D0%BE%D0%BA%D1%83%D0%BC%D0%B5%D0%BD%D1%82%D0%B0%D1%86%D0%B8%D1%8F/%D0%A2%D0%B5%D1%81%D1%82_%D0%BA%D0%B5%D0%B9%D1%81%D1%8B_Wikipedia_Mobile.csv) | Набор тест-кейсов по функциональности приложения |
| 5 | [Баг-репорты](https://github.com/popovladislove/Wikipedia-Mobile-QA-Project/blob/main/03_%D0%91%D0%B0%D0%B3_%D1%80%D0%B5%D0%BF%D0%BE%D1%80%D1%82%D1%8B/%D0%91%D0%B0%D0%B3_%D1%80%D0%B5%D0%BF%D0%BE%D1%80%D1%82%D1%8B.md) | Примеры оформленных дефектов |
| 6 | [API-тесты](https://github.com/popovladislove/Wikipedia-Mobile-QA-Project/blob/main/04_API_%D1%82%D0%B5%D1%81%D1%82%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B5/API_%D1%82%D0%B5%D1%81%D1%82_%D0%BA%D0%B5%D0%B9%D1%81%D1%8B.md) | Проверка данных через публичный MediaWiki API |
| 7 | [Итоговый отчет](https://github.com/popovladislove/Wikipedia-Mobile-QA-Project/blob/main/06_%D0%9E%D1%82%D1%87%D0%B5%D1%82_%D0%BE_%D1%82%D0%B5%D1%81%D1%82%D0%B8%D1%80%D0%BE%D0%B2%D0%B0%D0%BD%D0%B8%D0%B8/%D0%98%D1%82%D0%BE%D0%B3%D0%BE%D0%B2%D1%8B%D0%B9_%D0%BE%D1%82%D1%87%D0%B5%D1%82.md) | Summary по результатам тестирования |

- 📌 Учебный проект на Java: [To-Do List](https://github.com/popovladislove/java-todo-list) — консольное приложение для управления задачами, созданное для практики Java Core, ООП и базовой логики CRUD-операций.
