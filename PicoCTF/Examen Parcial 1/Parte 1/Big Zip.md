## Descripción 
Unzip this archive and find the flag.

- [Download zip file](https://artifacts.picoctf.net/c/503/big-zip-files.zip)
## Datos de Acceso al Nivel
user: carlosof

## Solución
```bash
carlosof-picoctf@webshell:~$ mktemp -d
/tmp/tmp.pN11XEAf8z
carlosof-picoctf@webshell:~$ cd /tmp/tmp.pN11XEAf8z
carlosof-picoctf@webshell:/tmp/tmp.pN11XEAf8z$ wget https://artifacts.picoctf.net/c/503/big-zip-files.zip
--2024-09-11 16:50:29--  https://artifacts.picoctf.net/c/503/big-zip-files.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.167.183.66, 3.167.183.29, 3.167.183.84, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.167.183.66|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 3182988 (3.0M) [application/octet-stream]
Saving to: 'big-zip-files.zip'

big-zip-files.zip                               100%[======================================================================================================>]   3.04M  --.-KB/s    in 0.07s   

2024-09-11 16:50:30 (40.5 MB/s) - 'big-zip-files.zip' saved [3182988/3182988]

carlosof-picoctf@webshell:/tmp/tmp.pN11XEAf8z$ unzip big-zip-files.zip 
carlosof-picoctf@webshell:/tmp/tmp.pN11XEAf8z$ grep -r 'picoCTF'
big-zip-files/folder_pmbymkjcya/folder_cawigcwvgv/folder_ltdayfmktr/folder_fnpfclfyee/whzxrpivpqld.txt:information on the record will last a billion years. Genes and brains and books encode picoCTF{gr3p_15_m4g1c_ef8790dc}
carlosof-picoctf@webshell:/tmp/tmp.pN11XEAf8z$ 
```

## Notas Adicionales
El comnado `grep` tiene una opcion con el -r que hace que se busque las palabras entre comillas de manera recursiva, aun que sea dentro de directorios

## Referencias 
https://play.picoctf.org/practice/challenge/322
[Cómo usar el comando grep en Linux (ejemplos prácticos) (hostinger.es)](https://www.hostinger.es/tutoriales/comando-grep-linux)