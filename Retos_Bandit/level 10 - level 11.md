## Objetivo 
The password for the next level is stored in the file **data.txt**, which contains base64 encoded data
## Datos de Acceso al Nivel
user: bandit10
password: FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey
## Solución
```
└─$ ssh bandit10@bandit.labs.overthewire.org -p 2220
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

bandit10@bandit.labs.overthewire.org's password: 

bandit10@bandit:~$ ls -la
total 24
drwxr-xr-x  2 root     root     4096 Jul 17 15:57 .
drwxr-xr-x 70 root     root     4096 Jul 17 15:58 ..
-rw-r--r--  1 root     root      220 Mar 31 08:41 .bash_logout
-rw-r--r--  1 root     root     3771 Mar 31 08:41 .bashrc
-rw-r-----  1 bandit11 bandit10   69 Jul 17 15:57 data.txt
-rw-r--r--  1 root     root      807 Mar 31 08:41 .profile
bandit10@bandit:~$ cat data.txt 
VGhlIHBhc3N3b3JkIGlzIGR0UjE3M2ZaS2IwUlJzREZTR3NnMlJXbnBOVmozcVJyCg==
bandit10@bandit:~$ file data.txt 
data.txt: ASCII text
bandit10@bandit:~$ base64 -d data.txt
The password is dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr
bandit10@bandit:~$ 

```
## Notas Adicionales
**base64**: Es una herramienta de línea de comandos que se utiliza para codificar y decodificar datos en base64. Base64 es un sistema de codificación que convierte datos binarios en una cadena de texto ASCII, que es más fácil de manejar en ciertos contextos, como en correos electrónicos o en URLs.

**-d**: Es una opción que le dice a la herramienta `base64` que realice la decodificación en lugar de la codificación. En algunos sistemas, esta opción puede ser --decode en lugar de -d.

## Referencias 
[Base64 - Wikipedia](https://en.wikipedia.org/wiki/Base64)