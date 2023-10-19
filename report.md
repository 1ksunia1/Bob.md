## 19/09/23

## 1
```sql
SELECT person.id, person.name, "age", "gender", "address", pizzeria.id, pizzeria.name, "rating" FROM "person", "pizzeria"
ORDER BY pizzeria.id ASC;
```
![image](https://github.com/1ksunia1/Bob.md/assets/145553959/94478374-53d9-4436-a35b-5d920a4fbfed)
```sql
SELECT person.id, person.name, "age", "gender", "address", pizzeria.id, pizzeria.name, "rating" FROM "person", "pizzeria"
ORDER BY person.id ASC;
```
![image](https://github.com/1ksunia1/Bob.md/assets/145553959/3b3060b7-66c2-4f5f-8c32-846d2ce39e31)

## 2
```sql
SELECT "order_date" AS action_date, "name" FROM "person_order", "person"
WHERE "order_date" IN (SELECT "visit_date" FROM "person_visits") AND person_order.person_id = person.id
ORDER BY "order_date" ASC;
```
![image](https://github.com/1ksunia1/Bob.md/assets/145553959/76dd9d30-43a1-445a-9236-5f94d50206f2)
```sql
SELECT "order_date" AS action_date, "name" FROM "person_order", "person"
WHERE "order_date" IN (SELECT "visit_date" FROM "person_visits") AND person_order.person_id = person.id
ORDER BY "name" DESC;
```
![image](https://github.com/1ksunia1/Bob.md/assets/145553959/48341149-9067-47f0-9ab8-9110db68715f)

## 3
```sql
SELECT "order_date", ("name" || ' (age:' || "age" || ')') AS person_information FROM "person_order"
JOIN "person" ON "person_id" = person.id
ORDER BY "order_date" ASC, "person_information" ASC;
```

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/203f6fad-a050-4093-89f3-c837964a3718)

## 4
```sql
SELECT order_date, (name || ' (age:' || age || ')') AS person_information FROM person_order NATURAL JOIN person
ORDER BY order_date ASC, person_information ASC;
```
![image](https://github.com/1ksunia1/Bob.md/assets/145553959/2fde21f9-4860-4d02-bf7c-dd8fbd6de1d8)

## 5
```sql
SELECT name FROM pizzeria
WHERE id NOT IN
(SELECT pizzeria_id FROM person_visits);
```

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/05a9c04b-62e3-4d84-a113-b0e215ef3752)

## 6
```sql
SELECT person.name AS person_name, menu.pizza_name, pizzeria.name AS pizzeria_name FROM "person_order"
JOIN "person" ON person.id = person_order.person_id
LEFT JOIN "menu" ON menu.id = person_order.menu_id
LEFT JOIN "pizzeria" ON pizzeria.id = menu.pizzeria_id
ORDER BY "person_name", "pizza_name", "pizzeria_name";
```

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/b98186a6-0e9c-4201-8bd2-2b6f93c6ba15)

## 20/09/23

## 1

```sql
SELECT "name", "rating" FROM "pizzeria"
LEFT JOIN "person_visits" ON "pizzeria_id" = pizzeria.id
WHERE "pizzeria_id" IS NULL;
```

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/4d953492-3560-4b49-bc2d-702905a16896)

## 2

```sql
SELECT missing_date::date FROM generate_series ('2022-01-01'::timestamp, '2022-01-10', '1 day') AS "missing_date"
LEFT JOIN "person_visits" ON "visit_date" = "missing_date"
WHERE "visit_date" IS NULL;
```

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/5ebae32a-1b8b-47b3-a7ef-670e2ddd3f70)

## 18.10.2023 

## 1

```sql
SELECT cus.first_name, cus.last_name FROM customers cus
JOIN orders ord ON cus.customer_id = ord.customer_id
GROUP BY cus.first_name, cus.last_name, ord.order_date
HAVING COUNT(*) >= 2 AND ord.order_date BETWEEN '2023-07-17' AND '2023-10-17'
ORDER BY 1, 2
```

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/d052780d-1473-47f3-ad93-3221d5826035)

## 2

```sql
SELECT AVG(ord.quantity) AS average, prd.category FROM orders ord
JOIN products prd ON prd.product_id = ord.product_id
WHERE price >= 50
GROUP BY prd.category
ORDER BY 2
```

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/20e22f12-1ebb-4c10-9c87-1aee4c2253b8)

## 3

```sql
WITH sum_customers AS (
	SELECT ord.customer_id, SUM(prd.price) AS summa FROM orders ord
	JOIN products prd ON prd.product_id = ord.product_id
	GROUP BY ord.customer_id
), avg_sum AS (
	SELECT ord.order_id, ord.customer_id, ord.quantity, SUM(prd.price) AS summa FROM orders ord
	JOIN products prd ON prd.product_id = ord.product_id
	GROUP BY ord.order_id
)

SELECT cus.first_name, cus.last_name, cus.email FROM customers cus
JOIN sum_customers scus ON scus.customer_id = cus.customer_id
JOIN avg_sum asum ON asum.customer_id = cus.customer_id
GROUP BY cus.first_name, cus.last_name, cus.email, scus.summa
HAVING scus.summa > AVG(asum.summa)
```

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/ea49ca15-230e-4fbb-8307-4f909a3e6094)





















