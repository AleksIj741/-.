Задание 1:
SELECT PC.model, PC.speed, PC.hd
FROM PC
JOIN Product ON PC.model = Product.model
WHERE Product.type = 'PC' AND PC.price < 500
Ответ сервера: Правильно.

Задание 2:
SELECT DISTINCT maker
FROM Product
WHERE type = 'Printer'
Ответ сервера: Правильно.

Задание 3:
SELECT model, ram, screen
FROM Laptop
WHERE price > 1000
Ответ сервера: Правильно.

Задание 4:
SELECT code, model, color, type, price
FROM Printer
WHERE color = 'y'
Ответ сервера: Правильно.

Задание 5:
SELECT model, speed, hd
FROM PC
WHERE (cd = '12x' OR cd = '24x') AND price < 600
Ответ сервера: Правильно.

Задание 6:
SELECT DISTINCT Product.maker, Laptop.speed
FROM Product
JOIN Laptop ON Product.model = Laptop.model
WHERE Laptop.hd >= 10
ORDER BY Product.maker, Laptop.speed
Ответ сервера: Правильно.

Задание 7:
SELECT Product.model, PC.price
FROM Product
JOIN PC ON Product.model = PC.model
WHERE Product.maker = 'B'
UNION
SELECT Product.model, Laptop.price
FROM Product
JOIN Laptop ON Product.model = Laptop.model
WHERE Product.maker = 'B'
UNION
SELECT Product.model, Printer.price
FROM Product
JOIN Printer ON Product.model = Printer.model
WHERE Product.maker = 'B'
Ответ сервера: Правильно.

Задание 8:
SELECT DISTINCT maker
FROM Product
WHERE type = 'PC'
AND maker NOT IN (
    SELECT DISTINCT maker
    FROM Product
    WHERE type = 'Laptop'
)
Ответ сервера: Правильно.

Задание 9:
SELECT DISTINCT Product.maker
FROM Product
JOIN PC ON Product.model = PC.model
WHERE PC.speed >= 450
Ответ сервера: Правильно.

Задание 10:
SELECT model, price
FROM Printer
WHERE price = (SELECT MAX(price) FROM Printer)
Ответ сервера: Правильно.

Задание 11:
SELECT AVG(speed) AS Avg_speed
FROM PC
Ответ сервера: Правильно.

Задание 12:
SELECT AVG(speed) AS Avg_speed
FROM Laptop
WHERE price > 1000
Ответ сервера: Правильно.

Задание 13:
SELECT AVG(PC.speed) AS Avg_speed
FROM PC
JOIN Product ON PC.model = Product.model
WHERE Product.maker = 'A'
Ответ сервера: Правильно.

Задание 14:
SELECT Classes.class, Ships.name, Classes.country
FROM Ships
JOIN Classes ON Ships.class = Classes.class
WHERE Classes.numGuns >= 10
Ответ сервера: Правильно.

Задание 15:
SELECT hd
FROM PC
GROUP BY hd
HAVING COUNT(*) >= 2
Ответ сервера: Правильно.
