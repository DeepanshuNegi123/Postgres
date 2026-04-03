# USE OF DATES IN PSQL

```sql

SELECT memid, surname,firstname,joindate FROM cd.members WHERE joindate>'2012-09-01';

SELECT memid, surname,firstname,joindate FROM cd.members WHERE joindate>'2012-09-01 00:00:00'; --- CAN BE WRITTEN AS THIS ALSO IN PSQL

```

# USE OF LIKE AND ILIKE

```SQL

-- HERE WE HAVE TO FIND ANME THAT CONTAINS 0 IN IT SMALL O AS LIKE IS CASE SENSETIVE AND ILIKE IS CASE-INCESITIVE.

SELECT * FROM users WHERE name LIKE '%o%';
 id | name
----+------
  3 | Bob
  6 | meow
(2 rows)

-- USAGE OF ILIKE.
SELECT * FROM users WHERE name ILIKE '%O%';
 id | name
----+-------
  1 | BOBBY
  3 | Bob
  6 | meow
(3 rows)


```

# USAGE OF LIMIT AND DISTINCT

```SQL

-- HERE I WAS TOLD TO CATEGORISE NAMES DISTINCTIVELY AND LIMIT NAMES TO ONLY 4

SELECT DISTINCT name FROM users LIMIT 4;
 name
-------
 meow
 priya
 BOBBY
 Alice
(4 rows)



-- here again i did same but now i want to go for distinct and order by to give names in order.

SELECT DISTINCT name FROM users ORDER BY
-- HERE BELOW NAMES ARE IN ASCENDING ORDER.
name LIMIT 4;
  name
---------
 Alice
 Bob
 BOBBY
 Charlie
(4 rows)

```
