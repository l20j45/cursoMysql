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


























