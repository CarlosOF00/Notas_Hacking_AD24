## Descripción 
This website can be rendered only by **picobrowser**, go and catch the flag! `https://jupiter.challenges.picoctf.org/problem/50522/` ([link](https://jupiter.challenges.picoctf.org/problem/50522/)) or http://jupiter.challenges.picoctf.org:50522

## Datos de Acceso al Nivel
user: 
password:

## Solución 1
- Inspeccionamos la pagina web, de preferencia con el navegador de FireFox ya que nos permite hacer unos cambios importantes.
- Nos vamos al apartado de Red
- Hacemos la petición para que nos muestre datos importantes.
![[picobrowserCap1.png]]
- Damos click en el archivo flag, que tiene un método get, esto nos abrirá un panel a la derecha que nos mostrara el header.
![[picobrowserCap2.png]]
- Debemos buscar las nuevas solicitudes y ahí cambiar el user-agent por `picobrowser`.
![[picobrowserCap3.png]]
- Enviamos la petición y checamos el resultado. ![[picobrowserCap4.png]]

## Solución 2 
```bash
carlosof-picoctf@webshell:~$ curl -s http://jupiter.challenges.picoctf.org:50522 -H 'User-Agent: picobrowser' | grep picoCTF
            <p style="text-align:center; font-size:30px;"><b>Flag</b>: <code>picoCTF{p1c0_s3cr3t_ag3nt_51414fa7}</code></p>
```
## Notas Adicionales

El **user-agent** es una cadena de texto que identifica a un navegador web, un motor de búsqueda o cualquier cliente que accede a un servidor web. Esta información es enviada en la cabecera de la solicitud HTTP y permite al servidor entender qué tipo de dispositivo o software está realizando la solicitud.

**Componentes del user-agent**
Un user-agent generalmente incluye información como:

1. **Nombre del navegador**: Por ejemplo, Chrome, Firefox, Safari.
2. **Versión del navegador**: Indica la versión específica que se está utilizando.
3. **Sistema operativo**: Puede incluir información sobre el sistema operativo, como Windows, macOS, Linux o Android.
4. **Plataforma**: Información adicional sobre la plataforma en la que se está ejecutando el navegador (por ejemplo, móvil o de escritorio).

## Referencias 
https://play.picoctf.org/practice/challenge/9
https://developer.mozilla.org/es/docs/Web/HTTP/Headers/User-Agent
