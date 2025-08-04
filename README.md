# Домашнее задание к занятию "`Введение в SQL`" - `Егоян Андрея`

### Задание 1

1.1. Использую локальный сервер, который уже был установлен.

1.2. Создал учётную запись sys_temp.

Вход в mysql:

```shell
sudo mysql
```

Создание нового пользователя:

```shell
CREATE USER 'sys_temp'@'localhost' IDENTIFIED BY '12345';
```

Ответ:

```shell
Query OK, 0 rows affected (0,01 sec)
```

1.3. Выполнил запрос на получение списка пользователей в базе данных. (скриншот)

```shell
SELECT user, host FROM mysql.user;
```

[Список пользователей](https://github.com/electr0n4ik/db-homework-2/blob/main/images/image.png)

1.4. Дал все права для пользователя sys_temp.

```shell
GRANT ALL PRIVILEGES ON *.* TO 'sys_temp'@'localhost' WITH GRANT OPTION;
FLUSH PRIVILEGES;
```

Ответ:

```shell
Query OK, 0 rows affected (0,00 sec)

Query OK, 0 rows affected (0,00 sec)
```

1.5. Выполнил запрос на получение списка прав для пользователя sys_temp. (скриншот)
[Список прав sys_temp](https://github.com/electr0n4ik/db-homework-2/blob/main/images/image2.png)

1.6. Переподключился к базе данных от имени sys_temp. Перед этим сделал смену аутентификации.

```shell
mysql -u sys_temp -p
```

Для смены типа аутентификации с sha2 используйте запрос:

```sql
ALTER USER 'sys_test'@'localhost' IDENTIFIED WITH mysql_native_password BY 'password';
```

1.6. По ссылке https://downloads.mysql.com/docs/sakila-db.zip скачал дамп базы данных.

1.7. Восстановил дамп в базу данных.

```shell
SOURCE ./db-homework-2/sakila-db/sakila-schema.sql;
```

```shell
SOURCE ./db-homework-2/sakila-db/sakila-data.sql;
```

1.8. При работе в командной строке использовал команду для получения всех таблиц базы данных. (скриншот)

```shell
SHOW TABLES;
```

[Список таблиц](https://github.com/electr0n4ik/db-homework-2/blob/main/images/image3.png)

### Задание 2

Составил таблицу, в которой два столбца: в первом названия таблиц восстановленной базы, во втором названия первичных ключей этих таблиц.

| Название таблицы | Название первичного ключа |
| :--------------- | :------------------------ |
| customer         | customer_id               |
| actor            | actor_id                  |
| address          | address_id                |
| category         | category_id               |
| city             | city_id                   |
| country          | country_id                |
| customer         | customer_id               |
| film             | film_id                   |
| film_actor       | actor_id                  |
| film_actor       | film_id                   |
| film_category    | film_id                   |
| film_category    | category_id               |
| film_text        | film_id                   |
| inventory        | inventory_id              |
| language         | language_id               |
| payment          | payment_id                |
| rental           | rental_id                 |
| staff            | staff_id                  |
| store            | store_id                  |
