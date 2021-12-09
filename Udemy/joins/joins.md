# Curso de MYSQL

inner join, pide un numero de cliente en comun para hacer las consultas

left join, quiero mantener los datos de la izquierda y los quiero unir con la tabla derecha

right join, quiero mantener los datos de la tabla derecha, y unir los de la tabla izquierda

**Estructura**

`select f.title, f.description,f.release_year, l.name as language`  

**aqui uso un alias para la tabla **

**como siempre va primero el select**
`from sakila.film f ` **aqui uso otro alias**
`inner join sakila.language l on (f.language_id = l.language_id) ; `

**lo interesante sucede aqui, donde con el segundo alias, hace la junta que seria un valor con el otro**

ojo recuenden que solo va a mostrar cuando haya coincidencia, si no hay coincidencia, pues no puestra nada

*No era tam complicado, cosas a buscar como hacer varios joins en una query** **nota de la nota, solo se concatenan a la brava**

- Consulta la tabla address de la base de datos sakila. Realiza un INNER JOIN con las tablas city y country Mostrar las columnas address, city, country
  
  - `select a.address,c.city,c2.country  
    from address a  
    left join city c  
    
        on a.city_id = c.city_id  
    
    left join country c2  
    
        on c.country_id = c2.country_id;`

- Consulta la tabla customer de la base de datos sakila. Realiza un LEFT JOIN con las tablas store y address Mostrar las columnas first_name, address, store_id
  
  - `select C.first_name,C.last_name,a.address,s.store_id  
    from customer C  
    left join store s  
    
        on C.store_id = s.store_id  
    
    left join address a  
    
        on s.address_id = a.address_id;`

- Consulta la tabla rental de la base de datos sakila. Realiza un INNER JOIN con la tabla staff Mostrar las columnas rental_id, first_name
  
  - `select r.rental_id,s.first_name,s.last_name  
    from rental r  
    inner join staff s on r.staff_id = s.staff_id;`
