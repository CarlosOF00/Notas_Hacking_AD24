## Descripción 
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/13/level2.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/13/level2.flag.txt.enc) in the same directory too.

## Datos de Acceso al Nivel
user: carlosof
password:

## Solución
```bash
carlosof-picoctf@webshell:~$ mktemp -d
/tmp/tmp.P5Vpo4HCNr
carlosof-picoctf@webshell:~$ cd /tmp/tmp.P5Vpo4HCNr/
carlosof-picoctf@webshell:/tmp/tmp.P5Vpo4HCNr$ wget https://artifacts.picoctf.net/c/13/level2.py
--2024-09-15 07:10:47--  https://artifacts.picoctf.net/c/13/level2.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.128, 3.160.22.16, 3.160.22.43, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.128|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 914 [application/octet-stream]
Saving to: 'level2.py'

level2.py                                       100%[======================================================================================================>]     914  --.-KB/s    in 0s      

2024-09-15 07:10:47 (373 MB/s) - 'level2.py' saved [914/914]

carlosof-picoctf@webshell:/tmp/tmp.P5Vpo4HCNr$ wget https://artifacts.picoctf.net/c/13/level2.flag.txt.enc 
--2024-09-15 07:10:59--  https://artifacts.picoctf.net/c/13/level2.flag.txt.enc
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.92, 3.160.22.43, 3.160.22.16, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.92|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 31 [application/octet-stream]
Saving to: 'level2.flag.txt.enc'

level2.flag.txt.enc                             100%[======================================================================================================>]      31  --.-KB/s    in 0s      

2024-09-15 07:10:59 (11.8 MB/s) - 'level2.flag.txt.enc' saved [31/31]

carlosof-picoctf@webshell:/tmp/tmp.P5Vpo4HCNr$ ls
level2.flag.txt.enc  level2.py
carlosof-picoctf@webshell:/tmp/tmp.P5Vpo4HCNr$ nano level2.
carlosof-picoctf@webshell:/tmp/tmp.P5Vpo4HCNr$ nano level2.py 
carlosof-picoctf@webshell:/tmp/tmp.P5Vpo4HCNr$ python3 level2.py 
Please enter correct password for flag: de7e
That password is incorrect
carlosof-picoctf@webshell:/tmp/tmp.P5Vpo4HCNr$ python3 level2.py 
Please enter correct password for flag: de76
Welcome back... your flag, user:
picoCTF{tr45h_51ng1ng_489dea9a}
carlosof-picoctf@webshell:/tmp/tmp.P5Vpo4HCNr$ 

```

## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/246