# Примеры SQL-запросов для проверки API

## Сценарий: После создания нового поста через API
Предположим, запрос `POST /posts` вернул `{ "id": 101, "title": "Test", "userId": 1 }`.

### Проверочные запросы:
```sql
-- 1. Проверяем, что запись с таким ID появилась
SELECT * FROM posts WHERE id = 101;

-- 2. Проверяем, что данные совпадают с отправленными
SELECT title, user_id FROM posts
WHERE id = 101
    AND title = 'Test'
    AND user_id = 1;
