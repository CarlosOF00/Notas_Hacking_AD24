## Descripción 
Let me in. Let me iiiiiiinnnnnnnnnnnnnnnnnnnn [http://mercury.picoctf.net:36622/](http://mercury.picoctf.net:36622/)

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
- Ingresamos al link de la pagina web.
- En el navegador FireFox (este nos permite hacer muchas modificaciones que necesitaremos adelante).
- Inspeccionamos la pagina y nos vamos al apartado de `Network` y recargamos la pagina para ver las peticiones, a la derecha podremos renviar el formulario.
- Aparecerá un nuevo apartado a la izquierda y haremos lo siguiente:
	- `User-Agent` cambiaremos el contenido por `picoBrowser`
	- Agregaremos un nuevo encabezado que se llamara `Referer` y su valor será `http://mercury.picoctf.net:36622`
	- Agregaremos un encabezado llamado `DNT` y su valor será `1`
	- Agregaremos un encabezado llamado `X-Forwarded-For` y su valor será `102.177.146.1` 
	- Agregaremos un encabezado llamado `Accept-Language` y su valor será `sv-sv,sv;q=0.5`
	- Daremos click en `Enviar` y  a la derecha buscaremos un apartado de `Respuesta` ahí encontraremos la bandera:

```bash
What can I say except, you are welcome
picoCTF{http_h34d3rs_v3ry_c0Ol_much_w0w_0da16bb2}
```

## Notas Adicionales
- Los encabezados (headers) son parte de la solicitud HTTP y sirven para enviar información adicional que el servidor puede usar para decidir cómo responder. Al cambiar algunos de estos valores, puedes manipular cómo el servidor responde a tu solicitud. 

- **`User-Agent` → `picoBrowser`:**
    - **¿Qué hace esto?**  
        El **User-Agent** le dice al servidor qué tipo de navegador está haciendo la solicitud. Cambiarlo a `picoBrowser` es una forma de engañar al servidor para que piense que la solicitud proviene de un navegador diferente. A veces, los servidores responden de manera diferente dependiendo del `User-Agent` para realizar alguna validación o seguridad.
    
- **`Referer` → `http://mercury.picoctf.net:36622`:**
    - **¿Qué hace esto?**  
        El encabezado **Referer** le indica al servidor desde qué página proviene la solicitud. Al cambiar el referer, el servidor podría estar validando si la solicitud proviene de una fuente específica, por lo que modificar este valor podría permitirte evadir restricciones de origen.

- **`DNT` → `1`:**
    - **¿Qué hace esto?**  
        El encabezado **DNT** significa "Do Not Track" (No rastrear). Al ponerlo en `1`, estás indicando que no deseas que se rastree tu actividad. Sin embargo, en este reto, podría estar relacionado con una restricción o una validación en el servidor que se activa solo si envías este encabezado.
    
- **`X-Forwarded-For` → `102.177.146.1`:**
    - **¿Qué hace esto?**  
        Este encabezado se utiliza para falsificar la dirección IP del cliente. **`X-Forwarded-For`** se utiliza a menudo en configuraciones de servidores para determinar la IP original de un cliente, pero si lo modificas, puedes hacerle creer al servidor que la solicitud proviene de una IP diferente. Esto puede ser útil en algunos retos para eludir bloqueos basados en IP o simplemente engañar al servidor sobre la ubicación del cliente

- **`Accept-Language` → `sv-sv,sv;q=0.5`:**
    - **¿Qué hace esto?**  
        Este encabezado indica el idioma preferido por el cliente para la respuesta. `sv` es el código de idioma para sueco. Al establecer este valor en sueco, estás diciendo que prefieres recibir la respuesta en sueco. Esto podría ser un cambio que el servidor usa para determinar diferentes respuestas dependiendo del idioma. Tal vez, si el servidor detecta que el encabezado `Accept-Language` está en sueco, podría mostrar una página diferente o una respuesta diferente.

## Referencias 
https://play.picoctf.org/practice/challenge/142
https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Date
https://medium.com/@prasanna44455/who-are-you-picoctf-f12d081a5852