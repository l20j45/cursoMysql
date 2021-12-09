base de datos la pondre en un archivo zip y el link aqui

[Base de datos](https://1drv.ms/u/s!AhleYsrK8kyokbM6wDGvJEtJYvV9Mw?e=L8AURy)

### SELECT

nos muestra la informacion de base de datos

#### Sintaxis

`SELECT *column1*, *column2, ...*  
FROM *table_name*;`

#### Ejemplos

`select * from Customers;  `

`select CustomerName,City from Customers;`

### DISTINC

nos muestra solo los registros unicos que hay en las consultas

#### Sintaxis

`SELECT DISTINCT *column1*, *column2, ...*  
FROM *table_name*;`

#### Ejemplos

`SELECT DISTINCT Country FROM Customers;  `

`SELECT count( DISTINCT Country) FROM Customers;`

### WHERE

sirve para meter una clausula en las querys de select para poder tomar bien los registros

#### Sintaxis

`SELECT *column1*, *column2, ...*  
FROM *table_name*  
WHERE *condition*;`

#### Ejemplos

`select * from Customers where Country="Mexico";`

`select * from Customers where CustomerID=1;`

| Operator | Description                                                          |
| -------- | -------------------------------------------------------------------- |
| =        | igual                                                                |
| >        | mayor que                                                            |
| <        | menor que                                                            |
| >=       | mayor igual que                                                      |
| <=       | menor igual que                                                      |
| <>       | diferente a, aunque en algunas versiones se escribe como !=          |
| BETWEEN  | entre los valores                                                    |
| LIKE     | busca patrones                                                       |
| IN       | puede buscar muchos valores en la columna o para hacer sub consultas |

`select * from Customers where Country="Mexico";  `
`select * from Customers where CustomerID=1;`

`SELECT * FROM Customers  
WHERE Country='Germany' AND City='Berlin';`

`SELECT * FROM Customers  
WHERE City='Berlin' OR City='München';`

### And y or

#### Sintaxis

`SELECT *column1*, *column2, ...*  
FROM *table_name*  
WHERE *condition1* AND *condition2* AND *condition3 ...*;`

`SELECT *column1*, *column2, ...*  
FROM *table_name*  
WHERE *condition1* OR *condition2* OR *condition3 ...*;`

`SELECT *column1*, *column2, ...*  
FROM *table_name*  
WHERE NOT *condition*;`

#### Ejemplos

`SELECT * FROM Customers  
WHERE Country='Germany' AND City='Berlin';`

`SELECT * FROM Customers  
WHERE City='Berlin' OR City='München';`

`SELECT * FROM Customers  
WHERE NOT Country='Germany';`

Se pueden combinar

### ORDER BY

ESTO SIRVE PARA ORDENAR LOS SELECT DE MAYOR A MENOR, EN CASO DE SER NECESARIO

#### sintaxis

`SELECT *column1*, *column2, ...*  
FROM *table_name*  
ORDER BY *column1, column2, ...* ASC|DESC;`

#### Ejemplos

`select * from Customers  
order by Country;`

### Insert

Sirve para insertar valores en una base de datos

#### Sintaxis

`INSERT INTO *table_name* (*column1*, *column2*, *column3*, ...)  
VALUES (*value1*, *value2*, *value3*, ...);`

#### Ejemplos

`insert into Customers  
VALUES ('6','Cardinal', 'Tom B. Erichsen', 'Skagen 21', 'Stavanger', '4006', 'Norway');`

### NULL, NOT NULL

en ocasiones los campos de las tablas bajan o se pasan en nulo para esto existe, is not null, o null

#### Sintaxis

`SELECT *column_names  
*FROM *table_name*  
WHERE *column_name* IS NULL;`

`SELECT *column_names  
*FROM *table_name*  
WHERE *column_name* IS NOT NULL;`

#### Ejemplos

`SELECT CustomerName, ContactName, Address  
FROM Customers  
WHERE Address IS NOT NULL;`

### Update

sirve para poder modificar algun registro dentro de la base de datos, esto se puede combinar con el where para solo modificar un valor, **IMPORTANTE, SI NO SE LE PONE EL WHERE, SE MODIFICA TODO**

#### Sintaxis

`UPDATE *table_name*  
SET *column1* = *value1*, *column2* = *value2*, ...  
WHERE *condition*;`

#### Ejemplos

`UPDATE Customers  
SET ContactName="JUAN"  
WHERE Country="Mexico";`

### Delete

esto sirve para borrar registros de una base de datos

#### Sintaxis

`DELETE FROM *table_name* WHERE *condition*;`

#### Ejemplos

`delete from Customers  
where CustomerName="Alfreds Futterkiste";`

### MAX Y MIN



#### Sintaxis

#### Ejemplos

### And y or

#### Sintaxis

#### Ejemplos

### And y or

#### Sintaxis

#### Ejemplos

### And y or

#### Sintaxis

#### Ejemplos

### And y or

#### Sintaxis

#### Ejemplos### And y or

#### Sintaxis

#### Ejemplos

### And y or

#### Sintaxis

#### Ejemplos

### And y or

#### Sintaxis

#### Ejemplos

### And y or

#### Sintaxis

#### Ejemplos

### And y or

#### Sintaxis

#### Ejemplos

### And y or

#### Sintaxis

#### Ejemplos

### And y or

#### Sintaxis

#### Ejemplos

### And y or

#### Sintaxis

#### Ejemplos




























