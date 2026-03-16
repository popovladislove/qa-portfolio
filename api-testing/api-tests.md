# API-тестирование

**Автор:** Попов Владислав
**Инструмент:** Postman
**Дата:** 03.02.2025

> **Примечание:** Swag Labs (saucedemo.com) не предоставляет публичный API.
> Поэтому ниже показаны навыки API-тестирования на основе открытого
> тренировочного API **Reqres** (https://reqres.in) — бесплатный
> фейковый REST API для практики.

---

## 1. Получение списка пользователей — GET

**Запрос:**

GET https://reqres.in/api/users?page=2
**Ответ (200 OK):**
```json
{
  "page": 2,
  "per_page": 6,
  "total": 12,
  "total_pages": 2,
  "data": [
    {
      "id": 7,
      "email": "michael.lawson@reqres.in",
      "first_name": "Michael",
      "last_name": "Lawson",
      "avatar": "https://reqres.in/img/faces/7-image.jpg"
    }
  ]
}
```
**Проверки в Postman:**
```JavaScript
pm.test("Статус 200", function () {
    pm.response.to.have.status(200);
});

pm.test("Страница = 2", function () {
    pm.expect(pm.response.json().page).to.eql(2);
});

pm.test("Массив data не пустой", function () {
    pm.expect(pm.response.json().data.length).to.be.above(0);
});

pm.test("У пользователя есть email", function () {
    var user = pm.response.json().data[0];
    pm.expect(user).to.have.property("email");
    pm.expect(user.email).to.include("@");
});
```
**Результат: ✅ Pass**

## 2. Получение одного пользователя — GET

**Запрос:**

GET https://reqres.in/api/users/2

**Ответ (200 OK):**
```json
{
  "data": {
    "id": 2,
    "email": "janet.weaver@reqres.in",
    "first_name": "Janet",
    "last_name": "Weaver"
  }
}
```
Проверки:
```JavaScript
pm.test("Статус 200", function () {
    pm.response.to.have.status(200);
});

pm.test("ID совпадает с запрошенным", function () {
    pm.expect(pm.response.json().data.id).to.eql(2);
});

pm.test("Имя — Janet", function () {
    pm.expect(pm.response.json().data.first_name).to.eql("Janet");
});
```
**Результат: ✅ Pass**

## 3. Несуществующий пользователь — GET

**Запрос:**

GET https://reqres.in/api/users/999

**Ответ (404 Not Found):**
```json
{}
```
Проверки:
```JavaScript
pm.test("Статус 404", function () {
    pm.response.to.have.status(404);
});

pm.test("Тело ответа пустое", function () {
    var data = pm.response.json();
    pm.expect(Object.keys(data).length).to.eql(0);
});
```
**Результат: ✅ Pass**

## 4. Создание пользователя — POST

**Запрос:**

POST https://reqres.in/api/users

Content-Type: application/json

{
  "name": "Ivan Testov",
  "job": "QA Engineer"
}

**Ответ (201 Created):**
```json
{
  "name": "Ivan Testov",
  "job": "QA Engineer",
  "id": "312",
  "createdAt": "2025-01-28T14:22:31.789Z"
}
```
**Проверки:**
```JavaScript
pm.test("Статус 201", function () {
    pm.response.to.have.status(201);
});

pm.test("Имя совпадает с отправленным", function () {
    pm.expect(pm.response.json().name).to.eql("Ivan Testov");
});

pm.test("Есть id и createdAt", function () {
    var data = pm.response.json();
    pm.expect(data).to.have.property("id");
    pm.expect(data).to.have.property("createdAt");
});
```
**Результат: ✅ Pass**

## 5. Авторизация — POST (успешная)

**Запрос:**

POST https://reqres.in/api/login

Content-Type: application/json

{
  "email": "eve.holt@reqres.in",
  "password": "cityslicka"
}
Ответ (200):
```json
{
  "token": "QpwL5tke4Pnpja7X4"
}
```
Проверки:
```JavaScript
pm.test("Статус 200", function () {
    pm.response.to.have.status(200);
});

pm.test("Токен получен", function () {
    pm.expect(pm.response.json()).to.have.property("token");
    pm.expect(pm.response.json().token.length).to.be.above(0);
});
```
Результат: ✅ Pass

## 6. Авторизация — POST (без пароля)

**Запрос:**

POST https://reqres.in/api/login

Content-Type: application/json

{
  "email": "eve.holt@reqres.in"
}
Ответ (400):
```json
{
  "error": "Missing password"
}
```
**Проверки:**
```JavaScript
pm.test("Статус 400", function () {
    pm.response.to.have.status(400);
});

pm.test("Ошибка — Missing password", function () {
    pm.expect(pm.response.json().error).to.eql("Missing password");
});
```
**Результат: ✅ Pass**

## 7. Удаление пользователя — DELETE

**Запрос:**

DELETE https://reqres.in/api/users/2

**Ответ:**
204 No Content (пустое тело)

**Проверки:**
```JavaScript
pm.test("Статус 204", function () {
    pm.response.to.have.status(204);
});

pm.test("Тело ответа пустое", function () {
    pm.expect(pm.response.text()).to.eql("");
});
```
**Результат: ✅ Pass**

Сводка
|№|	|Метод|	|URL|	|Описание|	|Код|	|Результат|
|1|	|GET|	|/api/users?page=2|	|Список пользователей|	|200|	|✅ Pass|
|2|	|GET|	|/api/users/2|	|Один пользователь|	|200|	|✅ Pass|
|3|	|GET|	|/api/users/999|	|Несуществующий|	|404|	|✅ Pass|
|4|	|POST|	|/api/users|	|Создание|	|201|	|✅ Pass|
|5|	|POST|	|/api/login|	|Успешный логин|	|200|	|✅ Pass|
|6|	|POST|	|/api/login|	|Без пароля|	|400|	|✅ Pass|
|7|	|DELETE|	|/api/users/2|	|Удаление|	|204|	|✅ Pass|
