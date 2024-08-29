## Objetivo 
The password for the next level is stored in the file **data.txt**, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work. Use mkdir with a hard to guess directory name. Or better, use the command “mktemp -d”. Then copy the datafile using cp, and rename it using mv (read the manpages!)

## Datos de Acceso al Nivel
user: level12
password: 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4
## Solución
```
└─$ ssh bandit12@bandit.labs.overthewire.org -p 2220
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

bandit12@bandit.labs.overthewire.org's password: 

bandit12@bandit:~$ ls -la
total 24
drwxr-xr-x  2 root     root     4096 Jul 17 15:57 .
drwxr-xr-x 70 root     root     4096 Jul 17 15:58 ..
-rw-r--r--  1 root     root      220 Mar 31 08:41 .bash_logout
-rw-r--r--  1 root     root     3771 Mar 31 08:41 .bashrc
-rw-r-----  1 bandit13 bandit12 2638 Jul 17 15:57 data.txt
-rw-r--r--  1 root     root      807 Mar 31 08:41 .profile
bandit12@bandit:~$  xxd -r data.txt | zcat | bzcat | zcat | tar xO | tar xO | bzcat | tar xO | zcat
The password is FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn
bandit12@bandit:~$ 

```
## Notas Adicionales
 **Hexadecimal a Binario**: xxd -r data.txt convierte el archivo hexadecimal a binario.
**Descompresión Gzip**: zcat descomprime los datos en formato gzip.
**Descompresión Bzip2**: bzcat descomprime los datos en formato bzip2.
**Descompresión Gzip**: zcat descomprime nuevamente en formato gzip.
**Extracción Tar**: tar xO extrae el contenido del archivo tar.
**Extracción Tar**: Otro tar xO para extraer el contenido adicional.
**Descompresión Bzip2**: bzcat descomprime el contenido en formato bzip2.
**Extracción Tar**: tar xO para extraer más contenido.
**Descompresión Gzip**: Finalmente, zcat descomprime el contenido en formato gzip
## Referencias 
https://en.wikipedia.org/wiki/Hex_dump
https://mayadevbe.me/posts/overthewire/bandit/level13/