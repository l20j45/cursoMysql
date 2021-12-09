# ahora avanzado de sql

- se ven tres funciones
  
  - CHAR_LEGHT(): regresa el numero de caracteres de una columna
  
  - CONCAT(): concatena columnas, como el concat de excel
  
  - CONCAT_WS(): concatena varias columnas con un signo intermedio
  
  - ROUND(): redondea el valor
  
  - UCASE(): convierte a mayusculas una palabra
  
  - LCASE(): convierte a minusculas una palabra

**ejercicios**

- Usa la función CHAR_LENGTH() en la tabla customer y calcula la longitud de la columna email.
  
  - `select CHAR_LENGTH(email) from customer;`

- Usa la función CONCAT() en la tabla customer y has un concatenado entre first_name, last_name y email.
  
  - `select concat(first_name," ",last_name," ",email) from customer;`

- Usa la función CONCAT_WS() en la tabla film y has un concatenado de todas las columnas.
  
  - `select concat_ws(" - ",film_id,title,description,release_year,language_id,original_language_id,rental_duration,rental_rate,length,replacement_cost,rating,special_features,last_update) from film;`

- Consulta la tabla payment y has un group by por customer_id para el promedio de amount, después usa la función ROUND() para redondear a cero decimales el promedio.
  
  - `select customer_id,round(avg(amount),2) from payment group by 1;`

- Usa la función UCASE() en la tabla city y convierte la columna city en mayúsculas.
  
  - `select UCASE(city) from city;`

### Insert into

el insert into sirve para meter valores a una tabla mediante sql, se puede hacer de dos formas

`INSERT INTO city(city, country_id)  
VALUE ("prueba","100");` especificando los campos donde estan dados de alta

`INSERT INTO city 
VALUE ("prueba","100"); ` metiendo todos los datos que tienen que ser pero debe de coincidir el numero de datos con el numero de columnas

**ejercicios**

- Usa la función INSER INTO y agrega un registro a la tabla actor.
  
  - `insert into address(address, address2, district, city_id, postal_code, phone) values("luis g caballero 3572","no hay","guadalajara","2","44720","331823108");`

- Usa la función INSER INTO y agrega un registro a la tabla address.
  
  - `insert into category(name) values ("thriller psicologico");`

- Usa la función INSER INTO y agrega un registro a la tabla category.
  
  - `insert into customer(store_id, first_name, last_name, email, address_id, active)  
    VALUE ("1","daniel","rojas","prueba.prueba","606","1");`

- Usa la función INSER INTO y agrega un registro a la tabla customer.
  
  - `insert into customer(store_id, first_name, last_name, email, address_id, active)  
    VALUE ("1","daniel","rojas","prueba.prueba","606","1");`

- Usa la función INSER INTO y agrega un registro a la tabla film_text.
  
  - `insert into film_text(film_id,title,description) value ("1001","fight club","a clkub where the people goes to fight")`

### Update

en los updates funcionan parecidos a los select, entonces recomiendo hacer primero el select bien estructurado de lo que quieres cambiar para despues hacer el update, la sintaxis seria:

Update (tabla) set (columna a cambiar) = (valor a cambiar) **where** cosa a buscar

ejemplo 

`UPDATE Customers  SET ContactName = 'Alfred Schmidt', City= 'Frankfurt'  
WHERE CustomerID = 1;`

Los ejercicios la neta no los hice porque me dio flojera

### Alter table

Los alter table sirven para modificar la estructura de la tabla, con esto podemos cambiar el tipo de dato, agregar columnas y mas cosas

**Agregando una columna**

- `ALTER TABLE actor ADD COLUMN (nombre de la columna) (tipo de la columna);`

- `ALTER TABLE actor ADD COLUMN genero_actor char(1);`

Eliminando columnas

- ALTER TABLE ACTOR DROP COLUM

Igual hay que ver en los demas tutoriales como lo llevan

### CASE

El case es algo interesante pues puedes hacer validaciones deacuerdo a si hay valores o devolver alguna valor, basicamente es como un if sql y creo que si ayuda a verificar mas rapido la informacion

**sintaxis**

- Select (lo que queremos mostrar) CASE WHEN (de donde traemos la informacion) IS NULL THEN (QUE ES LO QUE SE HACE SI ES CIERTO) ELSE (LO QUE HACE SI NO ES CIERTO) END AS (NUEVA COLUMNA) FROM (DE DONDE TRAE LOS DATOS)

- `select address,address2,  
  case  
   when address2 IS NULL THEN "sin direccion dos"  
  
      else "con direccion"  
      END AS Comentario  
      FROM address;`

- `select payment_id,amount,  
   casewhen amount<1 THEN "Precio minimo"  
  when amount between 1 and 3 then "Precio intermedio"  
  else "Precio maximo"  
  end as Comentario  
  from payment;`

### Consultas multitablas

esto es con joins papa

### sub querys

un subquery es una forma de meter mas querys dentro de otra, nos sirve para tener un proceso mas claro en las consultas, sobre la informacion que se une, de esta forma podemos tener valores de ambas tablas.



- ``SELECT CONCAT(first_name, " ", last_name) AS name, email`
  
  `FROM customer`
  
  `WHERE customer_id IN`
  
  `(SELECT customer_id FROM rental WHERE inventory_id IN`
  
  `(SELECT inventory_id FROM inventory WHERE film_id IN`
  
  `(SELECT film_id FROM film_category JOIN category USING (category_id)`
  
  `WHERE category.name="Action")));`

esta va definida por el select, posterior va dentro una funcion y por asi decirlo vamos haciendo el filtrado por pasos hasta el final

- `SELECT customer_id, CONCAT(first_name, " ", last_name) AS name, amount, COUNT(amount) FROM customer JOIN payment p1 USING(customer_id) WHERE amount > (SELECT AVG(amount) FROM payment p2 WHERE p2.customer_id=p1.customer_id) GROUP BY customer_id;`

### view

esto esta itneresante porque la view es solo una consulta que se toma en base de datos por asi decirlo es una macro de una consulta que se esta haciendo y solo se quiere consultar, asi en lugar de ejecutar la consulta completa solo ejecutas la vista.

`CREATE VIEW top_revenues_by_genre AS   SELECT name, SUM(amount)   FROM category   INNER JOIN film_category   ON category.category_id = film_category.category_id   INNER JOIN inventory   ON film_category.film_id = inventory.film_id   INNER JOIN rental   ON inventory.inventory_id = rental.inventory_id   INNER JOIN payment   ON rental.rental_id = payment.rental_id   GROUP BY name   ORDER BY SUM(amount) DESC LIMIT 5;`



aqui terminamos los cursos de udemy, sera conveniente ver otro curso.
