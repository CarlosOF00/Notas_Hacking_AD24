## Objetivo 
The password for the next level is stored in the file **data.txt**, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions
## Datos de Acceso al Nivel
user: bandit11
password: dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr

## Solución
```
└─$ ssh bandit11@bandit.labs.overthewire.org -p 2220
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

bandit11@bandit.labs.overthewire.org's password: 

bandit11@bandit:~$ ls -la
total 24
drwxr-xr-x  2 root     root     4096 Jul 17 15:57 .
drwxr-xr-x 70 root     root     4096 Jul 17 15:58 ..
-rw-r--r--  1 root     root      220 Mar 31 08:41 .bash_logout
-rw-r--r--  1 root     root     3771 Mar 31 08:41 .bashrc
-rw-r-----  1 bandit12 bandit11   49 Jul 17 15:57 data.txt
-rw-r--r--  1 root     root      807 Mar 31 08:41 .profile

bandit11@bandit:~$ cat data.txt 
Gur cnffjbeq vf 7k16JArUVv5LxVuJfsSVdbbtaHGlw9D4
bandit11@bandit:~$  cat data.txt | tr '[A-Za-z]' '[N-ZA-Mn-za-m]'
The password is 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4
bandit11@bandit:~$ 

```
## Notas Adicionales
**tr '[A-Za-z]' '[N-ZA-Mn-za-m]'**:  es una utilidad de línea de comandos que se usa para traducir o reemplazar caracteres. En este caso, se está utilizando para reemplazar caracteres basados en un esquema de cifrado simple.

**'[A-Za-z]'**: Este es el conjunto de caracteres que se desea transformar. Incluye todas las letras mayúsculas y minúsculas del alfabeto inglés.

**'[N-ZA-Mn-za-m]'**: Este es el conjunto de caracteres de reemplazo. Lo que hace es mapear cada letra en A-Z y a-z a otra letra que está 13 posiciones más adelante en el alfabeto, envolviendo al final del alfabeto. Este es un cifrado conocido como **ROT13**.
## Referencias 
[ROT13 - Wikipedia](https://en.wikipedia.org/wiki/ROT13)