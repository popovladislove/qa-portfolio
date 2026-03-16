# API-тестирование

**Автор:** [Твоё Имя]
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
Проверки в Postman:
