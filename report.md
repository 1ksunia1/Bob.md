### 19/09/23

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










