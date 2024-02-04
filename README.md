# LearningSQL

1. Tablels have unique name which is limited to 18 characters
2. Column names are unique in a particular table
3. Rows don't have names nor their position is fixed


# Statements
**There are basic statements**
> Query

```
SELECT        - To display rows of one of more tables

e.g. SELECT columns FROM table WHERE comparisons
```

> Maintainance

```
INSERT        - Add rows to table
UPDATE        - Change rows in table
DELETE        - Remmove rows from a table

DELETE FROM table WHERE comaprisons
```

> Definition

```
CREATE        - Add tables, indices, views
DROP          - Remove tables, indices, views

e.g. CREATE INDEX index ON table (columns)
```

# 1. Create Table

```
CREATE TABLE Customer
(
    CustomerID INT PRIMARY KEY,
    CustomerName VARCHAR(50),
    LastName VARCHAR(50),
    Country VARCHAR(50),
    Age int(2),
    Phone int(10)
);
```

*CREATE table table_name(
Column1 datatype (size),
);*

# 2. Insert Data into table

> Generic Insersion

```
Insert into Table_name
Values (Value1, value2, value3);
```

> Column wise insertion

```
Insert into Table_name(Column1, Column2, Column3)
Values (Value1, value2, value3);
```

> Mutliple Generic insertions

```
Insert into Table_name
Values (Value01, value02, value03),
(Value11, value12, value13),
(Value21, value22, value23),
(ValueN1, valueN2, valueN3)
```

> Example

```
INSERT INTO Customer (CustomerID, CustomerName, LastName, Country, Age, Phone)
VALUES (1, 'Shubham', 'Thakur', 'India','23','xxxxxxxxxx')
```

# 3. Select Data

## No Condition

```
SELECT column1,column2 FROM table_name 
```

> Example

```
SELECT CustomerName, LastName FROM Customer;
```

## Where Clause
Used for setting filters

```
SELECT CustomerName FROM Customer where Age = '21';
```

## GROUP BY
For grouping the data

```
SELECT * FROM Customer GROUP BY Country
```

## HAVING
Works on aggregate statements like MIN, MAX, SUM, COUNT, AVG

```
SELECT Department, sum(Salary) as Salary
FROM employee
GROUP BY department
HAVING SUM(Salary) >= 50000;
```

The above statement will group all the Salary column types and add them and then sum up those groups.
The condition is to satisfy the summation of group wise element addition.

## ORDER BY
If we want to sort a table based on elements of one column:

```
SELECT * FROM File ORDER BY CreatedDateTime DESC
```

