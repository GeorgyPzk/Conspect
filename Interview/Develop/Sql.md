# PRIMARY, FOREGIN KEYS

PRIMARY KEY (Первичный ключ) — уникальный Id для записи в БД.

FOREIGN KEY - это ключ, используемый для соединения двух таблиц вместе. При создании надо сослаться на Id в другой таблице.

`CREATE TABLE Orders (OrderID int NOT NULL, PersonID int, PRIMARY KEY (OrderID), FOREIGN KEY (PersonID) REFERENCES Persons(PersonID));`

# SELECT

`SELECT name FROM lampdb2.Musicboxs WHERE dep_id IN ('1','5') ORDER BY id DESC;`

Удалит повторяющиеся данные:

`SELECT DISTINCT`

# INSERT

Добавить данные в в таблицу:

`INSERT INTO <table_name> (<col_name1>, <col_name2>) VALUES (<value1>, <value2>);`

# JOIN

## (INNER) JOIN 
Join — оператор для объединения данных из нескольких таблиц с общим ключом. Выдаст строки только с общими значениями CustomerID

Table Orders: OrderID CustomerID OrderDate

Table Customers: CustomerID	CustomerName ContactName

`SELECT Orders.OrderID, Customers.CustomerName, Orders.OrderDate`
`FROM Orders`
`JOIN Customers` или `INNER JOIN Customers`
`ON Orders.CustomerID=Customers.CustomerID;`

## LEFT (OUTER) JOIN

LEFT JOIN - В финальный результат попадут все записи из левой, первой таблицы. Даже если не будет ни одного совпадения с правой. И записи из второй таблицы, для которых выполняется условие объединения. В сточках первой, левой таблицы, где нет совпадения с правой, пустой столбец будет null.

`SELECT Orders.OrderID, Customers.CustomerName, Orders.OrderDate`
`FROM Orders`
`LEFT JOIN Customers`
`ON Orders.CustomerID=Customers.CustomerID;`

## RIGHT (OUTER) JOIN

RIGHT JOIN - В финальный результат попадут все записи из правой, второй таблицы. Даже если не будет ни одного совпадения с левой. И записи из первой таблицы, для которых выполняется условие объединения. В сточках второй, правой таблицы, где нет совпадения с левой, пустой столбец будет null.

`SELECT Orders.OrderID, Customers.CustomerName, Orders.OrderDate `
`FROM Orders`
`RIGHT JOIN Customers`
`ON Orders.CustomerID=Customers.CustomerID;`

## FULL (OUTER) JOIN

FULL (OUTER) JOIN - В финальный результат такого соединения попадут все записи из обеих таблиц. Независимо от того, выполняется условие объединения или нет.

SELECT Orders.OrderID, Customers.CustomerName, Orders.OrderDate 
FROM Orders 
FULL JOIN Customers 
ON Orders.CustomerID=Customers.CustomerID;

(INNER) JOIN: возвращает записи, которые имеют совпадающие значения в обеих таблицах.
LEFT (OUTER) JOIN: возвращает все записи из левой таблицы и совпадающие записи из правой таблицы.
RIGHT (OUTER) JOIN: Возвращает все записи из правой таблицы и совпадающие записи из левой таблицы.


SQL-инъекция (SQLi) - это уязвимость веб-безопасности, которая позволяет злоумышленнику вмешиваться в запросы, которые приложение делает к своей базе данных. Обычно это позволяет злоумышленнику просматривать данные, которые он обычно не может получить.

Суть таких инъекций – внедрение в данные (передаваемые через GET, POST запросы или значения Cookie) произвольного SQL кода. Если сайт уязвим и выполняет такие инъекции, то по сути есть возможность творить с БД (чаще всего это MySQL) что угодно.

`test.ru/?detail=1`
`test.ru/?detail=4+UNION+SELECT+*+FROM+news+WHERE+id=4`
