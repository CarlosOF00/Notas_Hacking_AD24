## Descripción 
I sent out 2 invitations to all of my friends for my birthday! I'll know if they get stolen because the two invites look similar, and they even have the same md5 hash, but they are slightly different! You wouldn't believe how long it took me to find a collision. Anyway, see if you're invited by submitting 2 PDFs to my website. [http://mercury.picoctf.net:63578/](http://mercury.picoctf.net:63578/)

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
- Ingresamos a esta pagina web https://www.mscs.dal.ca/~selinger/md5collision/ en esta se encuentran dos archivos: `hello` , `erase` y aun que son archivos de ejemplo para ver como funcionan las colisiones md5, nos servirán para obtener la bandera.
- Una vez que hayamos descargado ambos archivos, vamos a cambiar su extension a `.pdf` de esta manera la pagina aceptara los archivos.
- Subimos los archivos a la pagina, damos `Enter` y obtenemos la bandera.

```bash
`<?php      if (isset($_POST["submit"])) {    $type1 = $_FILES["file1"]["type"];    $type2 = $_FILES["file2"]["type"];    $size1 = $_FILES["file1"]["size"];    $size2 = $_FILES["file2"]["size"];    $SIZE_LIMIT = 18 * 1024;          if (($size1 < $SIZE_LIMIT) && ($size2 < $SIZE_LIMIT)) {           if (($type1 == "application/pdf") && ($type2 == "application/pdf")) {            $contents1 = file_get_contents($_FILES["file1"]["tmp_name"]);            $contents2 = file_get_contents($_FILES["file2"]["tmp_name"]);                  if ($contents1 != $contents2) {                   if (md5_file($_FILES["file1"]["tmp_name"]) == md5_file($_FILES["file2"]["tmp_name"])) {                    highlight_file("index.php");                       die();                   } else {                       echo "MD5 hashes do not match!";                       die();                   }               } else {                   echo "Files are not different!";                   die();               }           } else {               echo "Not a PDF!";               die();           }       } else {           echo "File too large!";           die();       }   }      // FLAG: picoCTF{c0ngr4ts_u_r_1nv1t3d_5c8c5ce2}      ?>   <!DOCTYPE html>   <html lang="en">      <head>       <title>It is my Birthday</title>             <link href="https://maxcdn.bootstrapcdn.com/bootstrap/3.2.0/css/bootstrap.min.css" rel="stylesheet">          <link href="https://getbootstrap.com/docs/3.3/examples/jumbotron-narrow/jumbotron-narrow.css" rel="stylesheet">          <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>          <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.7/js/bootstrap.min.js"></script>         </head>      <body>          <div class="container">           <div class="header">               <h3 class="text-muted">It is my Birthday</h3>           </div>           <div class="jumbotron">               <p class="lead"></p>               <div class="row">                   <div class="col-xs-12 col-sm-12 col-md-12">                       <h3>See if you are invited to my party!</h3>                   </div>               </div>               <br/>               <div class="upload-form">                   <form role="form" action="/index.php" method="post" enctype="multipart/form-data">                   <div class="row">                       <div class="form-group">                           <input type="file" name="file1" id="file1" class="form-control input-lg">                           <input type="file" name="file2" id="file2" class="form-control input-lg">                       </div>                   </div>                   <div class="row">                       <div class="col-xs-12 col-sm-12 col-md-12">                           <input type="submit" class="btn btn-lg btn-success btn-block" name="submit" value="Upload">                       </div>                   </div>                   </form>               </div>           </div>       </div>       <footer class="footer">           <p>&copy; PicoCTF</p>       </footer>      </div>      <script>   $(document).ready(function(){       $(".close").click(function(){           $("myAlert").alert("close");       });   });   </script>   </body>      </html>`
```

- FLAG: picoCTF{c0ngr4ts_u_r_1nv1t3d_5c8c5ce2}

## Notas Adicionales
**MD5 Collision** se refiere a una situación en la que dos entradas diferentes generan el mismo valor de **hash** utilizando el algoritmo **MD5 (Message Digest Algorithm 5)**.

***Entendiendo el Hash y MD5***
Un **hash** es el resultado de aplicar una función hash a una entrada de datos (como un archivo, un texto o una cadena de caracteres). La función hash produce un valor de longitud fija (en el caso de MD5, un **hash de 128 bits** o **32 caracteres hexadecimales**). Este valor de hash se utiliza para identificar de manera única los datos de entrada.

El algoritmo **MD5** fue diseñado para ser rápido y eficiente, pero **no es seguro** para aplicaciones críticas, como la verificación de la integridad de datos o la autenticación, debido a la posibilidad de encontrar **colisiones**.

***¿Qué es una Colisión en MD5?***
Una **colisión** ocurre cuando dos entradas diferentes producen el **mismo valor de hash MD5**. En teoría, una función hash debería producir un valor único para cada entrada diferente, pero como el espacio de salida es limitado (128 bits), es inevitable que haya alguna entrada que tenga el mismo valor de hash que otra.

En el caso de **MD5**, las colisiones son **más fáciles de encontrar de lo que se pensaba inicialmente**, lo que hace que este algoritmo sea vulnerable en aplicaciones que dependen de la unicidad de los hashes, como la firma digital, la verificación de integridad de archivos o la autenticación de contraseñas.

***¿Por qué es un problema?***
Si un atacante puede generar dos entradas diferentes que producen el mismo hash MD5, puede:
- **Suplantar documentos o archivos**: Si un atacante genera dos archivos diferentes pero con el mismo hash MD5, puede reemplazar un archivo firmado o verificado sin que la verificación falle.
- **Falsificación de firmas digitales**: Si un atacante encuentra una colisión de hash en un documento firmado digitalmente, puede modificar el documento sin invalidar la firma.
- **Suplantación de contraseñas**: Si se usan valores de hash MD5 para almacenar contraseñas de manera insegura, un atacante podría crear una colisión con una contraseña válida, obteniendo acceso no autorizado.

***Ejemplo de colisión:***
En teoría, un atacante puede generar dos archivos diferentes (o cadenas de texto diferentes) que tienen el mismo valor de hash MD5. Aunque los archivos son diferentes a nivel de contenido, el valor de hash calculado para ambos será el mismo.

Ejemplo:
Archivo A: `"Hola Mundo"` Hash MD5: `b94d27b9934d3e08a52e52d7da7dabfad3`

Archivo B: `"Adiós Mundo"` Hash MD5: `b94d27b9934d3e08a52e52d7da7dabfad3`

En este caso, **Archivo A** y **Archivo B** tienen el mismo valor de hash MD5, lo que constituye una colisión.

## Referencias 
https://play.picoctf.org/practice/challenge/109
https://www.mscs.dal.ca/~selinger/md5collision/
[cryptanalysis - Are there two known strings which have the same MD5 hash value? - Cryptography Stack Exchange](https://crypto.stackexchange.com/questions/1434/are-there-two-known-strings-which-have-the-same-md5-hash-value)