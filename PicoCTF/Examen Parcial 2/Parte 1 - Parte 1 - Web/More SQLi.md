## Descripción 
Can you find the flag on this website.

Additional details will be available after launching your challenge instance.

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
- Iniciamos el launcher del reto e ingresamos a la pagina web.
- Para acceder, hacemos una inyección sql:
	- En el username escribimos `admin`
	- En la password escribimos `' or 1= 1;`
- De esta manera podemos ingresar a la pagina web.
- En el buscador del `Search Office` escribimos la siguiente inyección: 
```bash
Algiers' union select sql,1,1 from sqlite_master--
```

De esta manera obtenemos información de las tablas y ahora escribimos esta inyección:
```bash
Algiers' union select flag,id,1 from more_table;--
```

De esta manera obtenemos la bandera:
	Flag: picoCTF{G3tting_5QL_1nJ3c7I0N_l1k3_y0u_sh0ulD_e3e46aae}

## Notas Adicionales
`Algiers' union select sql,1,1 from sqlite_master--`
- **`Algiers'`**:  
    El `'` (comilla simple) cierra una cadena de texto que estaba abierta en la consulta original.
    
- **`union select`**:  
    El `UNION SELECT` es usado para combinar el resultado de dos consultas. Si la primera parte de la consulta no devuelve el resultado esperado, la segunda consulta se ejecuta y sus resultados se combinan con la primera. 
    
- **`sql, 1, 1`**:  
    Aquí parece que la consulta está seleccionando tres columnas. El valor `1, 1` son valores literales (constantes), y `sql` probablemente es el nombre de una columna. 
    
- **`from sqlite_master`**:  
    `sqlite_master` es una tabla interna de SQLite que contiene metadatos sobre la base de datos, como las tablas y vistas que están presentes. 
- **`--`**:  
    Los dos guiones `--` son un comentario en SQL. Cualquier cosa después de estos caracteres será ignorada por el motor de la base de datos. 

`Algiers' union select flag,id,1 from more_table;--`
- **`Algiers'`**:
    - El `'` (comilla simple) cierra una cadena de texto que podría estar abierta en la consulta original. 
    
- **`union select`**:
    - `UNION SELECT` permite combinar el resultado de la consulta original con el resultado de una consulta propia.
    
- **`flag, id, 1`**
	- `flag`: Es una columna de la tabla `more_table`. 
    - `id`: Otra columna de la tabla `more_table`, probablemente el identificador de algún registro.

- **`from more_table`**:
    - Especifica la tabla `more_table` de la cual el estamos intentando extraer datos.
    
- **`;--`**:
    - **`;`**: Termina la consulta SQL.
    - **`--`**: Es un comentario en SQL. Cualquier cosa que venga después de `--` será ignorada por el motor de la base de datos. 
## Referencias 
https://play.picoctf.org/practice/challenge/358
[The Schema Table (sqlite.org)](https://sqlite.org/schematab.html#:~:text=Every%20SQLite%20database%20contains%20a%20single%20%22schema%20table%22,and%20views%20that%20are%20contained%20within%20the%20database.)
[Vulnerabilities (sqlite.org)](https://sqlite.org/cves.html)