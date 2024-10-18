## Descripción 
BookShelf Pico, my premium online book-reading service.I believe that my website is super secure. I challenge you to prove me wrong by reading the 'Flag' book!

Additional details will be available after launching your challenge instance.

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
- Ingresamos al reto y entramos al link de la pagina web.
- Las pistas nos dan datos muy interesantes, sabemos que podemos loggearnos usando `user` tanto en el `username` como en la `password`.
- Una ves dentro, ingresaremos al libro `FLAG`.
- Estando ahí, vamos a inspeccionar la pagina.
- Entramos al apartado de `Storage` o `Almacenamiento`, ahí abriremos el  `Almacenamiento local` y veremos una `Key` con su `Value`.
- Vamos a copiar el `Value` de `auto-token` e ingresaremos a la pagina de JWT (https://jwt.io/)
- Pegamos el contenido en `Encode` y a la derecha en `Decode` en el apartado de `PAYLOAD` cambiaremos:
	- "role": "Free" --------------------> "role": "Admin"
	- "userId": 1,    --------------------> "userId": 2,
	- "email": "user" ------------------>   "email": "Admin"

- Abajo en el apartado de `VERIFY SIGNATURE` cambiaremos el campo que tenga por la numeración `1234`, esto lo hacemos así, ya que al analizar la carpeta que viene junto con el reto, hay un archivo que hace alusión a la seguridad, el cual tras analizarlo, indica este detalle.
- Una vez que hayamos cambiado eso, copiamos el resultado de `Encode` y regresamos a la pagina web, remplazando el valor pasado, por este que obtuvimos.
- El siguiente paso es modificar unos valores para la llave `token-payload` cabiaremos:
{"role":"Free","iss":"bookshelf","exp":1729480879,"iat":1728876079,"userId":1,"email":"user"}
Por lo siguiente:	{"role":"Admin","iss":"bookshelf","exp":1729480879,"iat":1728876079,"userId":2,"Admin":"Admin"}

- Recargamos la pagina.
- Ingresamos al libro `FLAG` y obtenemos la bandera:
	- picoCTF{w34k_jwt_n0t_g00d_d7c2e335}

## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/355
https://jwt.io/