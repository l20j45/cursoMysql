### Intrucciones con el select

**Este es un select basico**

`select * from sakila.actor;  `

**Notese que el select con el asterisco es todos los campos**

`select actor_id,actor.first_name,last_name,last_update from sakila.actor;  `

**podemos cambiar los nombre con el as**
`select actor_id, first_name as Nombre, last_name as Apellido, last_update from sakila.actor;`

Nos muestra valores unicos

`select distinct(customer_id) from sakila.payment;  `

igual que el de arriba
`select distinct (store_id) from sakila.customer;`

### Ejercicios 1

- Consulta store_id, first_name y last_name de la tabla customer de la base de datos sakila.
  
  - `select store_id,first_name,last_update from sakila.customer;`

- Cambia el nombre de las columnas store_id, first_name y last_name a Tienda, Nombre y Apellido respectivamente.
  
  - `select store_id as tienda,first_name as Nombre,last_update as Apellido from sakila.customer;`

- Ordena de manera descendente la columna Apellido
  
  - `select store_id as tienda,first_name as Nombre,last_name as Apellido from sakila.customer order by Apellido desc;`

- Consulta la tabla payment de la base de datos sakila.
  
  - `select * from sakila.payment;`

- ¿Cuál es la cantidad mas baja y mas alta de la columna amount?
  
  - `select distinct (amount) from payment order by amount;`

### where

el where nos sirve para filtrar resultados en el select (sirve para mas cosas pero por el momento asi va bien)

**se filtro por nombre**

`select * from sakila.actor where first_name ="DAN";  `

`select * from sakila.city;  ****`

**igual se filtro por nombre**
`select * from sakila.city where city="LONDON";`

**si filtramos por numero no ponemos comillas**

`select * from sakila.city where country_id=102;  `
`SELECT * FROM sakila.customer;  `
`SELECT * FROM sakila.customer where store_id=1;`

usar comparaciones matematicas para mostrar cosas

`select * from sakila.inventory where film_id>50;`

`select distinct amount from sakila.payment where amount < 3;`

### ejercicios 2

- Consulta description, release_year de la tabla film de la base de datos sakila.
  
  - `select description,release_year from sakila.film;`

- Filtra la información donde title sea IMPACT ALADDIN
  
  - `select description,release_year from sakila.film where title ="IMPACT ALADDIN";`

- Consulta la tabla payment de la base de datos sakila.
  
  - `select * from payment;`

- Filtra la información donde amount sea mayor a 0.99.
  
  - `select * from payment where amount > 0.99 order by amount;`
  
  ### ejercicio 3

- aqui se ven cosas del and or not
  
  - Consulta la tabla payment de la base de datos sakila.
    
    - `select * from payment;`
  
  - Filtra la información donde customer_id sea igual a 36, amount sea mayor a 0.99 y staff_id sea igual a 1.
    
    - `select * from payment where customer_id = 36 and amount > .99 and staff_id =1;`
  
  - Consulta la tabla rental de la base de datos sakila.
    
    - `select * from rental;`
  
  - Filtra la información donde staff_id no sea 1, customer_id sea mayor a 250 y inventory_id sea menor de 100.
    
    - `select * from rental where not staff_id = 1 and customer_id > 250 and inventory_id < 100;`

**Leccion del IN**

el comando in nos permite hacer consultas de multivalores en el select, se puede ver en el siguiente codigo

- `select * from customer where first_name ="mary" or first_name ="patricia";  `

- `select * from customer where first_name in ("mary" ,"patricia");`

Se pueden hacer anidaciones del IN

- `SELECT * FROM film where special_features in("Trailers","Trailers,Deleted Scenes") and rating in("G","17") AND length> 50;`

Tambien se puede combinar con el operador not

- `select * from category where name not in("Action","Animation","Children");`

**ejercicios**

- Filtra la información donde title  sea ZORRO ARK, VIRGIN DAISY, UNITED PILOT, del film text
  
  - `select * from film_text where title in ("ZORRO ARK","VIRGIN DAISY", "UNITED PILOT");`

- Filtra la información donde city sea Chiayi, Dongying, Fukuyama y Kilis.
  
  - `$select * from city where city in("Chiayi", "Dongying", "Fukuyama" , "Kilis");$`

Between

Esto busca entre dos valores, es la tabla y luego las condicionales numericas

ejemplo

- `select * from payment where amount between 3 and 5;`

**Ejercicios**

- Filtra la información donde amount esté entre 2.99 y 4.99,  staff_id sea igual a 2 y customer_id sea 1 y 2 de la tabla payment;
  
  -  `select * from payment where (amount between 3 and 5) and (staff_id = 2) and customer_id in(1, 2);`

- Filtra la información donde city_id esté entre 300 y 350 de la tabla city
  
  - `select * from address where city_id between 300 and 350;`

- Filtra la información donde rental_rate esté entre 0.99 y 2.99, length sea menor igual de 50  y replacement_cost sea menor de 20. de la tabla film
  
  - `select * from film where rental_rate between .99 and 2.99 and length <= 50 and replacement_cost < 20;`

like 

el comando like refiere a algo parecido a, entonces podemos buscar patrones de letras, y usando comodines, el comodin en sql es %

**Ejemplo**

- `select * from actor where first_name like "C%N" and last_name like "G%"`

- en el ejemplo de arriba comienza con c el nombre, luego termina con N y su apellido tiene que comenzar con g

**Ejercicios**

- Filtra la información donde release_year sea igual a 2006  y title empiece con ALI.
  
  - `select * from film  where release_year = 2006 and title like "ALI%";`
