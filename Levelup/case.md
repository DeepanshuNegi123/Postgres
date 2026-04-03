```SQL
 you have two separate tables users and orders

postgres=# SELECT * FROM USERS;
 id |  name
----+---------
  1 | BOBBY
  2 | Alice
  3 | Bob
  4 | Charlie
  5 | Alice
  6 | meow
  7 | priya
(7 rows)


postgres=# SELECT * FROM orders;
 id | users_id |  product  |   cost
----+----------+-----------+----------
  1 |        1 | cap       | 150.0000
  2 |        4 | wristband |  50.0000
  3 |        1 | socks     | 120.0000
  5 |        6 | bat       | 500.0000
  4 |        6 | ball      | 250.0000
(5 rows)


```

# TASK

## GIVE ME QUERY TO FETCH DATA LIKE BELOW , USE JOIN TO COMBINE BOTH TABLE AND CASE WHEN TO FIND COST PRICE_CATEGORY ALSO GO FOR RIGHT AND LEFT JOIN AND NULL CASES.

```SQL

 users_id |  name   |  product  |   cost   | price_category
----------+---------+-----------+----------+----------------
        1 | BOBBY   | cap       | 150.0000 | AUKAT_AHAR
        4 | Charlie | wristband |  50.0000 | meow_dedo
        1 | BOBBY   | socks     | 120.0000 | AUKAT_AHAR
        6 | meow    | bat       | 500.0000 | AUKAT_AHAR
        6 | meow    | ball      | 250.0000 | AUKAT_AHAR
          | priya   |           |          | PAISE_KHATAM
          | Alice   |           |          | PAISE_KHATAM
          | Alice   |           |          | PAISE_KHATAM
          | Bob     |           |          | PAISE_KHATAM

```

## ANSWER-

```SQL

 SELECT users_id,name,product,cost, CASE WHEN (orders.cost>100) THEN 'AUKAT_BAHAR' WHEN (orders.cost <=100) THEN 'meow_dedo' ELSE 'PAISE_KHATAM' END AS PRICE_CATEGORY FROM users LEFT JOIN orders ON users.id=orders.users_id;

```
