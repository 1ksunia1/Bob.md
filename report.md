## 1 задание

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/5f07aa93-f283-421e-b7bd-a7f566bf690f)

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/798f9653-b93f-4615-98e6-d2b92436a5f1)

## 06/09/23

## 1

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/ca963385-bdfd-4b5e-8862-6b2b781c70b8)

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/d2d1e8c0-6d79-442d-9983-6b5abf6fbb90)

```sql
INSERT INTO "Order_details"(order_detail_id,"Product_id", "Quantity", "Subtotal")
VALUES (1, 4, 2, 2 * (SELECT "Price" FROM "Products" WHERE "Product_id" = 4)),
(1, 1, 5, 5 * (SELECT "Price" FROM "Products" WHERE "Product_id" = 1)),
(2, 3, 4, 4 * (SELECT "Price" FROM "Products" WHERE "Product_id" = 3)),
(2, 5, 1, 1 * (SELECT "Price" FROM "Products" WHERE "Product_id" = 5)),
(2, 3, 2, 2 * (SELECT "Price" FROM "Products" WHERE "Product_id" = 3)),
(3, 7, 5, 5 * (SELECT "Price" FROM "Products" WHERE "Product_id" = 7)),
(4, 5, 3, 3 * (SELECT "Price" FROM "Products" WHERE "Product_id" = 5)),
(4, 12, 7, 7 * (SELECT "Price" FROM "Products" WHERE "Product_id" = 12)),
(4, 13, 2, 2 * (SELECT "Price" FROM "Products" WHERE "Product_id" = 13));
```

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/c4975d6a-6dad-4358-acfd-7bdc1abe5888)

## 12/09/23

## 1 

```sql
INSERT INTO "person"("id", "name", "age","gender", "address")
VALUES (15, 'Kirill', 24, 'male', 'Novosibirsk'),
(16, 'Anton', 54, 'male', 'Moskow'),
(17, 'Maksim', 23, 'male', 'Kazan'),
(18, 'Artem', 14, 'male', 'Samara'),
(19, 'Alise', 25, 'female', 'Novosibirsk');
```

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/34535a22-9e0e-4b3b-a0ae-6bc45195c75a)

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/6c0ab4a1-3d0c-4c9d-868c-9b5801bdd422)

```sql
INSERT INTO "pizzeria"("id", "name", "rating")
VALUES (12, '888Pizza', '2.3'),
(13, 'Shredder Pizza', '3.8'),
(14, 'Park&Pizza', '4.8'),
(15, 'IL Patio', '2.7'),
(16, 'New York Pizza', '4.1');
```

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/c7925272-d36e-4506-9e0d-306174493778)

```sql
INSERT INTO "person_order"("id", "person_id", "menu_id","order_date")
VALUES (26, 12, 1, '2022-01-13'),
(27, 13, 4, '2022-01-13'),
(28, 13, 2, '2022-01-13'),
(29, 13, 12, '2022-01-13'),
(30, 14, 16, '2022-01-16');
```

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/45b51fa6-dfbb-4eb9-bc16-1af9c7c0f0fd)

```sql
INSERT INTO "menu"("id", "pizzeria_id", "pizza_name","price")
VALUES (25, 13, 'cheese pizza', 900),
(26, 14, 'pepperoni pizza', 1200),
(27, 15, 'sausage pizza', 950),
(28, 16, 'cheese pizza', 900);
```

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/52850657-c483-472c-96c9-1d26d9f59a4b)

```sql
insert into person_visits values (20, 7, 1, '2022-01-01');
insert into person_visits values (21, 7, 4, '2022-01-01');
insert into person_visits values (22, 8, 6, '2022-01-02');
insert into person_visits values (23, 8, 4, '2022-01-03');
insert into person_visits values (24, 8, 7, '2022-01-04');
insert into person_visits values (25, 9, 16, '2022-01-07');
insert into person_visits values (26, 10, 2, '2022-01-08');
insert into person_visits values (27, 11, 13, '2022-01-08');
insert into person_visits values (28, 11, 5, '2022-01-09');
insert into person_visits values (29, 11, 14, '2022-01-09');
insert into person_visits values (30, 12, 11, '2022-01-01');
```

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/4de06ff6-6971-4fc2-a9d5-c057c10806dd)

## 2
```sql
SELECT "name", "age" FROM "person"
WHERE "address" = 'Kazan';
```

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/4a716e54-90f6-4eaa-829c-ac74cd920a4c)

## 3

```sql
SELECT "name", "age" FROM "person"
WHERE "gender" = 'female'
ORDER BY "name" ASC;
```

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/8e4db5d7-6e74-4003-b71d-f1bbe0417c4b)

## 4

```sql
SELECT "name", "rating" FROM "pizzeria"
WHERE "rating" > 3.5
ORDER BY "rating" ASC;
```

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/b375f992-4318-46c3-9496-b4bf7a74dcad)

```sql
SELECT "name", "rating" FROM "pizzeria"
WHERE "rating" BETWEEN 3.5 AND 5
ORDER BY "rating" ASC;
```

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/58c658fe-3d52-40c5-9de7-792dde9a632a)

## 5

```sql
SELECT "person_id" FROM "person_visits"
WHERE "visit_date" BETWEEN '2022-01-05' AND '2022-01-18';
```

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/c2086218-73e9-4d3e-906e-4e206aefc592)

## 6

```sql
SELECT "name" FROM "person" WHERE person.id IN
(SELECT "person_id" FROM "person_order" WHERE "menu_id" = 1 OR "menu_id" = 3 OR "menu_id" = 7);
```

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/e7299e78-1278-40de-9d2c-b07d2e0a9778)

## 7

```sql
SELECT EXISTS(SELECT * FROM "person" WHERE "name" = 'Peter');
```

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/e546d92a-a14d-41e5-9d1c-a064ce408e49)

```sql
SELECT EXISTS(SELECT * FROM "person" WHERE "name" = 'KEter');
```

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/a41eaae3-e7ab-4d38-8312-8bcc7804620c)

## 13/09/23

## 1

```sql
SELECT "id", "pizza_name" FROM "menu" UNION
SELECT "id", "name" FROM "person"
ORDER BY "id", "pizza_name";
```

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/d167bf28-04d5-443a-9f6a-efe7a21ba42f)

## 2

```sql
SELECT "pizza_name" FROM "menu"
UNION
SELECT "name" FROM "person"
ORDER BY "pizza_name";
```

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/72d0c5e6-1be8-40cd-8d05-588d8c53bdd7)

## 3

```sql
SELECT "person_id" FROM "person_order" 
WHERE "order_date" IN (SELECT "visit_date" FROM "person_visits")
ORDER BY "person_id" DESC;
```

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/7716c90b-8d0d-4571-bf7b-bc91663fa949)

## 4

```sql
SELECT ABS (
	(SELECT COUNT("person_id") FROM "person_order" WHERE "order_date" = '2022-01-07') -
	(SELECT COUNT("person_id") FROM "person_visits" WHERE "visit_date" = '2022-01-07')
);

```

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/11050a9e-2569-4b9d-9234-29bd4c83f63c)

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

## 3

```sql
SELECT COALESCE (person.name, '-') AS person_name, COALESCE (person_visits.visit_date, NULL) AS visit_date, COALESCE (pizzeria.name, '-') AS pizzeria_name 
FROM "person_visits"
RIGHT JOIN "person" ON person.id = person_visits.person_id
FULL JOIN "pizzeria" ON pizzeria.id = person_visits.pizzeria_id
ORDER BY "person_name", "visit_date", "pizzeria_name";
```

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/8ae25375-4f2b-47de-9f55-4c8d220a6f76)

## 4

```sql
WITH "m" AS (
	SELECT "missing_date"::date FROM generate_series ('2022-01-01'::timestamp, '2022-01-10', '1 day') AS "missing_date"
)
SELECT "missing_date" FROM "m"
LEFT JOIN "person_visits" ON "visit_date" = "missing_date"
WHERE "visit_date" IS NULL;
```

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/769b8a7b-0d82-4fed-b0bd-88f45309a386)

## 5

```sql
SELECT menu.pizza_name, pizzeria.name AS pizzeria_name, menu.price FROM "menu"
JOIN "pizzeria" ON pizzeria.id = menu.pizzeria_id
WHERE "pizza_name" = 'pepperoni pizza' OR "pizza_name" = 'mushroom pizza'
ORDER BY "pizza_name", "pizzeria_name";
```

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/3d551c32-d708-4afc-9454-e314cb7b2cfc)

## 04/10/23

## 1

```sql
SELECT id FROM menu
EXCEPT ALL
SELECT menu_id FROM person_order
ORDER BY id;
```

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/0cf352cd-2b3c-49bc-83e1-c03db9e1adc0)

## 2

```sql
WITH ids AS (
	SELECT id FROM menu
	EXCEPT ALL
	SELECT menu_id FROM person_order
	ORDER BY id
)
SELECT pizza_name, price, pizzeria.name AS pizzeria_name FROM menu
JOIN pizzeria ON pizzeria_id = pizzeria.id
WHERE menu.id IN (SELECT * FROM ids)
ORDER BY pizza_name, price;
```

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/6ad47192-61b3-44c8-ab89-fbd4a899f7cb)

## 3

```sql
WITH man AS (
	SELECT pizzeria.name FROM pizzeria
	JOIN person_visits ON pizzeria.id = pizzeria_id
	JOIN person ON person_id = person.id
	WHERE gender = 'male'
), woman AS (
	SELECT pizzeria.name FROM pizzeria
	JOIN person_visits ON pizzeria.id = pizzeria_id
	JOIN person ON person_id = person.id
	WHERE gender = 'female'
)
(SELECT name FROM man EXCEPT ALL SELECT name FROM woman)
UNION
(SELECT name FROM woman EXCEPT ALL SELECT name FROM man)
ORDER BY name;
```

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/6ba603e1-89b2-434f-bfcf-8e16dc5c91d2)

## 4

```sql
WITH man AS (
	SELECT pizzeria.name FROM pizzeria
	JOIN menu ON pizzeria.id = pizzeria_id
	JOIN person_order ON menu.id = menu_id
	JOIN person ON person_id = person.id
	WHERE gender = 'male'
), woman AS (
	SELECT pizzeria.name FROM pizzeria
	JOIN menu ON pizzeria.id = pizzeria_id
	JOIN person_order ON menu.id = menu_id
	JOIN person ON person_id = person.id
	WHERE gender = 'female'
)
(SELECT name FROM man EXCEPT SELECT name FROM woman)
UNION
(SELECT name FROM woman EXCEPT SELECT name FROM man)
ORDER BY name; 
```

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/107d728c-b6c3-4f0a-bfbd-0079fbf34561)

## 10/10/23

## 1

```sql
CREATE VIEW v_persons_male AS
	SELECT * FROM person 
	WHERE gender = 'male';
CREATE VIEW v_persons_female AS
	SELECT * FROM person 
	WHERE gender = 'female';
SELECT * FROM v_persons_male, v_persons_female
```

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/8a032060-1ee2-48ea-a833-eac2459e2668)

## 2

```sql
DROP VIEW IF EXISTS v_persons_male, v_persons_female;

CREATE VIEW v_persons_male AS
	SELECT * FROM person 
	WHERE gender = 'male';
CREATE VIEW v_persons_female AS
	SELECT * FROM person 
	WHERE gender = 'female';

SELECT "name" FROM v_persons_male
UNION
SELECT "name" FROM v_persons_female
ORDER BY name;
```

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/c669cea1-81ea-46b0-95f9-df66c3439dcb)

## 3

```sql
DROP VIEW IF EXISTS v_gen_dates;
CREATE VIEW v_gen_dates AS 
	SELECT generate_series('2022-01-01'::timestamp, '2022-01-31', '1 day')::date AS dates;
SELECT dates FROM v_gen_dates
ORDER BY dates;
```

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/1b664ca1-468a-4e2b-b728-34e34f402903)

## 4

```sql
DROP VIEW IF EXISTS v_gen_dates;

CREATE VIEW v_gen_dates AS 
	SELECT generate_series('2022-01-01'::timestamp, '2022-01-31', '1 day')::date AS dates;
	
SELECT dates FROM v_gen_dates
LEFT JOIN person_visits ON dates = visit_date
WHERE visit_date IS NULL;
```

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/53b9271e-baa2-4a4e-bb38-57525996a2a0)

## BONUS LVL

```sql
SELECT p1.name AS name1, p2.name AS name2, p1.address FROM person p1
JOIN person p2 ON p1.address = p2.address
WHERE p1.id < p2.id
```

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/dfd00ef9-7a13-4c4f-9dc7-ad3819719ba6)

## 5

```sql
DROP VIEW IF EXISTS v_price_with_discount;

CREATE VIEW v_price_with_discount AS
	SELECT p.name, m.pizza_name, m.price, round(SUM(m.price * 0.9)) AS discount_price FROM person_order po
	JOIN person p ON p.id = po.person_id
	JOIN menu m ON m.id = po.menu_id
	GROUP BY p.name, m.pizza_name, m.price
	ORDER BY p.name;
	
SELECT * FROM v_price_with_discount;
```sql
![image](https://github.com/1ksunia1/Bob.md/assets/145553959/419b574a-d777-41d3-8017-70841315adf0)

## 6

```sql
DROP MATERIALIZED VIEW IF EXISTS mv_dmitriy_visits_and_eats;

CREATE MATERIALIZED VIEW mv_dmitriy_visits_and_eats AS
	SELECT pi.name FROM person_visits pv
	JOIN pizzeria pi ON pi.id = pv.pizzeria_id
	JOIN menu m ON m.pizzeria_id = pv.pizzeria_id
	JOIN person p ON pv.person_id = p.id
	WHERE p.name = 'Dmitriy' AND pv.visit_date = '2022-01-08' AND m.price < 800;
	
SELECT * FROM mv_dmitriy_visits_and_eats;
```

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/54471256-7fed-47da-8933-03a8214ad0d2)

## 7

```sql
DROP MATERIALIZED VIEW IF EXISTS mv_dmitriy_visits_and_eats;

DELETE FROM person_visits pv
WHERE pv.id = 20;

CREATE MATERIALIZED VIEW mv_dmitriy_visits_and_eats AS
	SELECT pi.name FROM person_visits pv
	JOIN pizzeria pi ON pi.id = pv.pizzeria_id
	JOIN menu m ON m.pizzeria_id = pv.pizzeria_id
	JOIN person p ON pv.person_id = p.id
	WHERE p.name = 'Dmitriy' AND pv.visit_date = '2022-01-08' AND m.price < 800;

INSERT INTO person_visits(id, person_id, pizzeria_id, visit_date)
VALUES (20, 9, 3, '2022-01-08');

REFRESH MATERIALIZED VIEW mv_dmitriy_visits_and_eats;

SELECT * FROM mv_dmitriy_visits_and_eats;
```

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/69d86d65-5f8f-4611-a353-be35b35ec2a6)

## 17.10.2023

##1

```sql
create table person_discounts
(id bigint primary key ,
 person_id bigint not null ,
 pizzeria_id bigint not null ,
 discount numeric not null ,
 constraint uk_person_discounts unique (person_id, pizzeria_id, discount),
 constraint fk_person_discounts_person_id foreign key  (person_id) references person(id),
 constraint fk_person_discounts_pizzeria_id foreign key  (pizzeria_id) references pizzeria(id));
```
![image](https://github.com/1ksunia1/Bob.md/assets/145553959/d3640ae1-a423-4e79-9357-cf6ac737f4f4)


## 2

```sql
DROP VIEW aoo;
CREATE VIEW aoo AS (
	WITH disc AS (
	SELECT pr.person_id, menu.pizzeria_id FROM person_order pr
	JOIN menu ON menu.id = pr.menu_id)
	 SELECT person_id, pizzeria_id, COUNT(*) AS amount_of_orders FROM disc
	 GROUP BY person_id, pizzeria_id
	 ORDER BY 1
);

INSERT INTO person_discounts(id, person_id, pizzeria_id, discount)
SELECT ROW_NUMBER() OVER (ORDER BY 1), person_id, pizzeria_id,
CASE
	WHEN (SELECT amount_of_orders) = 1 THEN 10.5
	WHEN (SELECT amount_of_orders) = 2 THEN 22
	ELSE 30
END AS discount FROM aoo;

SELECT * FROM person_discounts
```

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/b92e27f2-6c51-4ac3-8682-02a48254605f)

## 3

```sql
SELECT p.name, menu.pizza_name, menu.price, ROUND(SUM(menu.price - ((menu.price / 100) * pd.discount))) AS discount_price, pz.name FROM person_discounts pd
JOIN person p ON p.id = pd.person_id
JOIN menu ON menu.pizzeria_id = pd.pizzeria_id
JOIN pizzeria pz ON pz.id = pd.pizzeria_id
GROUP BY p.name, menu.pizza_name, menu.price, pz.name
ORDER BY 1
```

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/2ee37880-6d79-4559-ac83-ae955b94bca0)

## 4

```sql
DROP INDEX IF EXISTS idx_person_discounts_unique;
CREATE UNIQUE INDEX idx_person_discounts_unique ON person_discounts(person_id, pizzeria_id);

EXPLAIN ANALYZE
SELECT p.name, menu.pizza_name, menu.price, ROUND(SUM(menu.price - ((menu.price / 100) * pd.discount))) AS discount_price, pz.name FROM person_discounts pd
JOIN person p ON p.id = pd.person_id
JOIN menu ON menu.pizzeria_id = pd.pizzeria_id
JOIN pizzeria pz ON pz.id = pd.pizzeria_id
GROUP BY p.name, menu.pizza_name, menu.price, pz.name
ORDER BY 1
```

## Before

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/01dc96f2-cf98-4c38-baee-5742fd250e14)

## After

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/820d733a-ad84-480f-ba39-3ae266ff1130)

## 5

```sql
DROP TABLE person_discounts;
create table person_discounts
(id bigint primary key ,
 person_id bigint not null ,
 pizzeria_id bigint not null ,
 discount numeric not null default 0 CHECK(discount >= 0 AND discount <= 100),
 constraint uk_person_discounts unique (person_id, pizzeria_id, discount),
 constraint fk_person_discounts_person_id foreign key  (person_id) references person(id),
 constraint fk_person_discounts_pizzeria_id foreign key  (pizzeria_id) references pizzeria(id));
```

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/91d0235a-9cc0-466f-b489-944fa4efc407)

## 6

```sql
COMMENT ON TABLE person_discounts IS 'Table is useless for me'
```

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/50a7cb2a-4eed-4c04-be2b-213a791a0bf2)

## 7

```sql
DROP SEQUENCE IF EXISTS seq_person_discounts;
CREATE SEQUENCE seq_person_discounts
MINVALUE 1 START WITH 1 INCREMENT BY 1;

SELECT setval('seq_person_discounts', (SELECT COUNT(*) FROM person_discounts))

ALTER TABLE person_discounts ALTER COLUMN id SET DEFAULT NEXTVAL('seq_person_discounts');

INSERT INTO person_discounts(person_id, pizzeria_id, discount)
VALUES (3, 1, 0),
		(2, 4, 0);
	
SELECT * FROM person_discounts
```

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/e359b529-f1e9-4c6f-b527-61fb5c4df4c4)


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

## 4 

```sql
WITH sum_price AS (
	SELECT ord.order_id, ord.customer_id, ord.product_id, ord.quantity, SUM(prd.price) AS summa FROM orders ord
	JOIN products prd ON prd.product_id = ord.product_id
	GROUP BY ord.order_id
	HAVING SUM(prd.price) >= 1000
)

SELECT cus.first_name, cus.last_name FROM customers cus
JOIN sum_price spr ON spr.customer_id = cus.customer_id
JOIN products prd ON prd.product_id = spr.product_id
WHERE category != 'Electronics'
```

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/793f3bea-47a1-4bf0-a822-1635e1ebb558)\

## 5 

```sql
DROP VIEW IF EXISTS v_avg_order;

CREATE VIEW v_avg_order AS (
	WITH sum_order_id AS (
		SELECT ord.order_id, ord.customer_id, ord.quantity, SUM(prd.price) AS summa FROM orders ord
		JOIN products prd ON prd.product_id = ord.product_id
		GROUP BY ord.order_id
	), avg_sum_customer AS (
		SELECT soid.customer_id, ROUND(AVG(soid.summa), 2) AS avg_summa FROM sum_order_id soid
		GROUP BY soid.customer_id
	), avg_all_sum AS (
		SELECT ROUND(AVG(soid.summa), 2) AS avg_all FROM sum_order_id soid
	)
	
	SELECT cus.first_name, cus.last_name, ascus.avg_summa, (ascus.avg_summa - (SELECT avg_all FROM avg_all_sum)) AS difference FROM avg_sum_customer ascus
	JOIN customers cus ON cus.customer_id = ascus.customer_id
	JOIN sum_order_id soid ON soid.customer_id = ascus.customer_id
	GROUP BY cus.first_name, cus.last_name, ascus.avg_summa
);

SELECT * FROM v_avg_order
```

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/20ad1340-1f38-4203-a4b1-c7f5b2fc95cb)

## 24/10/23

## 1

```sql
SELECT p.id AS p_id, COUNT(pv.id) AS count_of_visits FROM person p
JOIN person_visits pv ON pv.person_id = p.id
GROUP BY 1
ORDER BY p_id ASC, count_of_visits DESC
```

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/56bd9ebc-54dc-43e1-9092-737c154081fb)

## 2

```sql
SELECT p.name, COUNT(pv.id) AS count_of_visits FROM person p
JOIN person_visits pv ON pv.person_id = p.id
GROUP BY 1
ORDER BY count_of_visits DESC
LIMIT 4
```

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/2452fa44-426d-4d7e-84ef-31792d8d072c)

## 3

```sql
WITH fav_rest_visit AS (
	SELECT pzz.name, COUNT(pv.id) AS count_of_visits FROM pizzeria pzz
	JOIN person_visits pv ON pv.pizzeria_id = pzz.id
	GROUP BY 1
	ORDER BY count_of_visits DESC
	LIMIT 3
), fav_rest_order AS (
	SELECT pzz.name, COUNT(pd.id) AS count_of_orders FROM pizzeria pzz
	JOIN menu ON menu.pizzeria_id = pzz.id
	JOIN person_order pd ON pd.menu_id = menu.id
	GROUP BY 1
	ORDER BY count_of_orders DESC
	LIMIT 3
)

SELECT fro.name, count_of_orders AS count, ('order') AS action_type FROM fav_rest_order fro
UNION
SELECT frv.name, count_of_visits AS count, ('visit') AS action_type FROM fav_rest_visit frv
ORDER BY 3 ASC, 2 DESC
```

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/605686fe-c522-409b-bb42-581567ccdfd5)

## 4

```sql
WITH fav_rest_visit AS (
	SELECT pzz.name, COUNT(pv.id) AS count_of_visits FROM pizzeria pzz
	JOIN person_visits pv ON pv.pizzeria_id = pzz.id
	GROUP BY 1
	ORDER BY count_of_visits DESC
), fav_rest_order AS (
	SELECT pzz.name, COUNT(pd.id) AS count_of_orders FROM pizzeria pzz
	JOIN menu ON menu.pizzeria_id = pzz.id
	JOIN person_order pd ON pd.menu_id = menu.id
	GROUP BY 1
	ORDER BY count_of_orders DESC
)

SELECT frv.name, (frv.count_of_visits + fro.count_of_orders) AS total_count FROM fav_rest_visit frv
JOIN fav_rest_order fro ON fro.name = frv.name
```

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/c4029a9d-468b-492e-bde4-684934eff6bb)

## 5

```sql
SELECT p.name, COUNT(pv.id) AS count_of_visits FROM person p
JOIN person_visits pv ON pv.person_id = p.id
GROUP BY 1
HAVING COUNT(pv.id) > 3
```

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/2c78990f-4b00-4dc9-adde-834734580c11)

## 6

```sql
SELECT DISTINCT p.name FROM person p
LEFT JOIN person_order pd ON pd.person_id = p.id
ORDER BY 1
```

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/7155c172-d46f-4633-b94d-2ce6968dc847)

## 7

```sql
WITH fav_rest_order AS (
	SELECT pzz.name, COUNT(pd.id) AS count_of_orders FROM pizzeria pzz
	JOIN menu ON menu.pizzeria_id = pzz.id
	JOIN person_order pd ON pd.menu_id = menu.id
	GROUP BY 1
	ORDER BY count_of_orders DESC
)

SELECT pzz.name, fro.count_of_orders, ROUND(AVG(menu.price), 2) AS avg, MAX(menu.price), MIN(menu.price) FROM pizzeria pzz
JOIN fav_rest_order fro ON fro.name = pzz.name
JOIN menu ON menu.pizzeria_id = pzz.id
GROUP BY 1, 2
ORDER BY 1
```

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/b986fae8-a8dc-4daa-af1c-77ebe0d07b26)

## 8

```sql
SELECT ROUND(AVG(pzz.rating), 4) FROM pizzeria pzz
```

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/7c57f193-88c9-4b5c-97e4-7adc198c55c9)

## 10

```sql
WITH formula_average AS (
	SELECT p.address, (MAX(p.age) - (MIN(p.age) / MAX(p.age))) AS formula, ROUND(AVG(p.age), 2) AS average FROM person p
	GROUP BY 1
)

SELECT fa.address, fa.formula, fa.average, (fa.formula>fa.average) AS comparison FROM formula_average fa
```

![image](https://github.com/1ksunia1/Bob.md/assets/145553959/245c9034-23be-4c17-a2c5-1f6028f4c5b1)

create table profile
( id bigint primary key ,
  name varchar (11),
  sername varchar (11),
  email varchar (64),
  phone number varchar (11),
  roel_id INT,
 constraint fk_roel_roel_id foreign key  (roel_id) references roel(id)
);


