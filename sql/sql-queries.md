# SQL-запросы для тестирования

**Автор:** Попов Владислав
**СУБД:** PostgreSQL

> **Примечание:** У Swag Labs нет прямого доступа к БД.
> Ниже — примеры SQL-запросов, которые я бы использовал для проверки
> данных интернет-магазина, если бы имел доступ к базе данных.
> Схема таблиц смоделирована по функциональности saucedemo.com.

---

## Схема таблиц
|--------|---------------------------------------------------------------|
| users: | id, username, password_hash, user_type, is_locked, created_at |
| products: | id, name, description, price, image_url |
| cart_items: | id, user_id, product_id, quantity, added_at |
| orders: | id, user_id, first_name, last_name, postal_code, total, created_at |
| order_items: | id, order_id, product_id, quantity, price |


---

## 1. Все пользователи и их тип

** Проверяем что все тестовые аккаунты на месте **

```sql
SELECT id, username, user_type, is_locked
FROM users
ORDER BY id;
```

Ожидаемый результат:

| id |	username |	user_type |	is_locked |
|----|-----------|------------|-----------|
| 1 |	standard_user |	standard |	false |
| 2	| locked_out_user |	standard |	true |
| 3	| problem_user |	problem |	false |
| 4	| performance_glitch_user |	glitch |	false |
| 5	| error_user |	error |	false |
| 6	| visual_user | visual |	false |
