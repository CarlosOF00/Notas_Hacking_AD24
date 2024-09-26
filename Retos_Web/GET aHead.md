## Descripción
Find the flag being held on this server to get ahead of the competition [http://mercury.picoctf.net:45028/](http://mercury.picoctf.net:45028/)

## Datos de Acceso al Nivel
user: carlosof
password:

## Solución 
- Ingresar al link de la pagina web.
- Inspeccionamos la pagina y nos vamos al apartado de Red.
- Al dar click en los botones, nos podemos dar cuenta de los métodos que se utilizan, (GET con el botón rojo y POST con el botón azul).
- Si abrimos el apartado de encabezado y además le damos al botón de `reenviar`
- Ahora podemos cambiar la solicitud a `HEAD` y obtenemos la bandera.
- flag
	picoCTF{r3j3ct_th3_du4l1ty_775f2530}

## Notas Adicionales
1. **GET**: Se utiliza para solicitar datos del servidor. Es el método más común y se usa para obtener información sin modificarla.
    
2. **POST**: Se usa para enviar datos al servidor, a menudo para crear o actualizar recursos. Los datos se envían en el cuerpo de la solicitud.
    
3. **PUT**: Similar a POST, se utiliza para actualizar un recurso existente o crear uno nuevo si no existe. Los datos también se envían en el cuerpo.
    
4. **DELETE**: Se utiliza para eliminar un recurso específico en el servidor.
    
5. **HEAD**: Similar a GET, pero solo solicita los encabezados de la respuesta, sin el cuerpo. Se usa para obtener información sobre el recurso sin descargarlo.
    
6. **PATCH**: Se usa para aplicar modificaciones parciales a un recurso existente.

## Referencias 
https://play.picoctf.org/practice/challenge/132
[Métodos de petición HTTP - HTTP | MDN (mozilla.org)](https://developer.mozilla.org/es/docs/Web/HTTP/Methods)