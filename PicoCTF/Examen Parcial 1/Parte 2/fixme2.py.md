## Descripción 
Fix the syntax error in the Python script to print the flag.[Download Python script](https://artifacts.picoctf.net/c/5/fixme2.py) 
## Datos de Acceso al Nivel
user: carlosof
password:

## Solución
```bash
carlosof-picoctf@webshell:/tmp/tmp.LeKDv3ikVX$ mktemp -d
/tmp/tmp.9BoLDO4ZKu
carlosof-picoctf@webshell:/tmp/tmp.LeKDv3ikVX$ cd /tmp/tmp.9BoLDO4ZKu/
carlosof-picoctf@webshell:/tmp/tmp.9BoLDO4ZKu$ wget https://artifacts.picoctf.net/c/5/fixme2.py
--2024-09-15 06:42:06--  https://artifacts.picoctf.net/c/5/fixme2.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.128, 3.160.22.16, 3.160.22.92, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.128|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1029 (1.0K) [application/octet-stream]
Saving to: 'fixme2.py'

fixme2.py                                       100%[======================================================================================================>]   1.00K  --.-KB/s    in 0s      

2024-09-15 06:42:06 (380 MB/s) - 'fixme2.py' saved [1029/1029]

carlosof-picoctf@webshell:/tmp/tmp.9BoLDO4ZKu$ ls
fixme2.py
carlosof-picoctf@webshell:/tmp/tmp.9BoLDO4ZKu$ python3 fixme2.py 
  File "/tmp/tmp.9BoLDO4ZKu/fixme2.py", line 22
    if flag = "":
       ^^^^^^^^^
SyntaxError: invalid syntax. Maybe you meant '==' or ':=' instead of '='?
carlosof-picoctf@webshell:/tmp/tmp.9BoLDO4ZKu$ vim fixme2.py 

[1]+  Stopped                 vim fixme2.py
carlosof-picoctf@webshell:/tmp/tmp.9BoLDO4ZKu$ nano  
.fixme2.py.swp  fixme2.py       
carlosof-picoctf@webshell:/tmp/tmp.9BoLDO4ZKu$ nano 
.fixme2.py.swp  fixme2.py       
carlosof-picoctf@webshell:/tmp/tmp.9BoLDO4ZKu$ nano fixme2.py 
carlosof-picoctf@webshell:/tmp/tmp.9BoLDO4ZKu$ python3 fixme2.py 
  File "/tmp/tmp.9BoLDO4ZKu/fixme2.py", line 22
    if flag = ""
       ^^^^^^^^^
SyntaxError: invalid syntax. Maybe you meant '==' or ':=' instead of '='?
carlosof-picoctf@webshell:/tmp/tmp.9BoLDO4ZKu$ nano fixme2.py 
carlosof-picoctf@webshell:/tmp/tmp.9BoLDO4ZKu$ python3 fixme2.py 
  File "/tmp/tmp.9BoLDO4ZKu/fixme2.py", line 22
    if flag == ""
                 ^
SyntaxError: expected ':'
carlosof-picoctf@webshell:/tmp/tmp.9BoLDO4ZKu$ python3 fixme2.py 
  File "/tmp/tmp.9BoLDO4ZKu/fixme2.py", line 22
    if flag == ""
                 ^
SyntaxError: expected ':'
carlosof-picoctf@webshell:/tmp/tmp.9BoLDO4ZKu$ nano fixme2.py 
carlosof-picoctf@webshell:/tmp/tmp.9BoLDO4ZKu$ python3 fixme2.py 
That is correct! Here's your flag: picoCTF{3qu4l1ty_n0t_4551gnm3nt_4863e11b}
carlosof-picoctf@webshell:/tmp/tmp.9BoLDO4ZKu$ 
```

## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/241