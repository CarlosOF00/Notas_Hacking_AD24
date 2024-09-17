## Descripción 
Unzip this archive and find the file named 'uber-secret.txt'

- [Download zip file](https://artifacts.picoctf.net/c/500/files.zip)

## Datos de Acceso al Nivel
user: carlosof
password:

## Solución
```bash
carlosof-picoctf@webshell:~$ mktemp -d
/tmp/tmp.5RpF8hvCqd
carlosof-picoctf@webshell:~$ cd /tmp/tmp.  
tmp.5RpF8hvCqd/ tmp.6eKvmkNDvp/ 
carlosof-picoctf@webshell:~$ cd /tmp/tmp.5RpF8hvCqd/
carlosof-picoctf@webshell:/tmp/tmp.5RpF8hvCqd$ wget https://artifacts.picoctf.net/c/500/files.zip
--2024-09-14 05:17:47--  https://artifacts.picoctf.net/c/500/files.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.71, 3.160.5.42, 3.160.5.18, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.71|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 3995553 (3.8M) [application/octet-stream]
Saving to: 'files.zip'

files.zip                                       100%[======================================================================================================>]   3.81M  --.-KB/s    in 0.06s   

2024-09-14 05:17:48 (60.7 MB/s) - 'files.zip' saved [3995553/3995553]

carlosof-picoctf@webshell:/tmp/tmp.5RpF8hvCqd$ unzip files.zip 
Archive:  files.zip
   creating: files/
   creating: files/satisfactory_books/
   creating: files/satisfactory_books/more_books/
  inflating: files/satisfactory_books/more_books/37121.txt.utf-8  
  inflating: files/satisfactory_books/23765.txt.utf-8  
  inflating: files/satisfactory_books/16021.txt.utf-8  
  inflating: files/13771.txt.utf-8   
   creating: files/adequate_books/
   creating: files/adequate_books/more_books/
   creating: files/adequate_books/more_books/.secret/
   creating: files/adequate_books/more_books/.secret/deeper_secrets/
   creating: files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/
 extracting: files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt  
  inflating: files/adequate_books/more_books/1023.txt.utf-8  
  inflating: files/adequate_books/46804-0.txt  
  inflating: files/adequate_books/44578.txt.utf-8  
   creating: files/acceptable_books/
   creating: files/acceptable_books/more_books/
  inflating: files/acceptable_books/more_books/40723.txt.utf-8  
  inflating: files/acceptable_books/17880.txt.utf-8  
  inflating: files/acceptable_books/17879.txt.utf-8  
  inflating: files/14789.txt.utf-8   
carlosof-picoctf@webshell:/tmp/tmp.5RpF8hvCqd$ find -name "uber-secret.txt"
./files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt
carlosof-picoctf@webshell:/tmp/tmp.5RpF8hvCqd$ cat ./files/adequate_books/more_books/.secret/deeper_secrets/deepest_secrets/uber-secret.txt
picoCTF{f1nd_15_f457_ab443fd1}
carlosof-picoctf@webshell:/tmp/tmp.5RpF8hvCqd$ 
```


## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/320

