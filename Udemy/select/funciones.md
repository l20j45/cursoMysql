# funciones en mysql

funcion count cuenta las filas devuletas

funcion avr, devuelve un promedio de las filas

funcion sum, suma los valores de la colum

funcion max, devuelve el valor maximo de la columna

funcion min, devuelve el valor minimo de la columna

**ejercicios**

- Consulta la tabla rental de la base de datos sakila. Realiza un COUNT de  la columna rental_id
  
  - `select count(rental_id) from rental;`

- Consulta la tabla payment de la base de datos sakila. Realiza un MAX de  la columna amount
  
  - `select max(amount) from payment;`

- Consulta la tabla rental de la base de datos sakila.Realiza un MAX de  la columna rental_date
  
  - `select customer_id, max(rental_date) from rental group by 1;`

- Consulta la tabla actor de la base de datos sakila. Realiza un COUNT de  last_name Mostrar cuando el COUNT sea mayor de 2
  
  - `select last_name,count(last_name)  
    from actor  
    group by 1  
    having count(last_name)>2;`
  
  - 
