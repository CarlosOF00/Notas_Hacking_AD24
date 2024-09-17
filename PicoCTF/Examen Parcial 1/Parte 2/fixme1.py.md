## Descripción 
Fix the syntax error in this Python script to print the flag.[Download Python script](https://artifacts.picoctf.net/c/26/fixme1.py)

## Datos de Acceso al Nivel
user: carlosof
password:

## Solución
```bash
carlosof-picoctf@webshell:~$ mktemp -d
/tmp/tmp.LeKDv3ikVX
carlosof-picoctf@webshell:~$ cd /tmp/tmp.LeKDv3ikVX/
carlosof-picoctf@webshell:/tmp/tmp.LeKDv3ikVX$ wget https://artifacts.picoctf.net/c/26/fixme1.py
--2024-09-15 06:39:35--  https://artifacts.picoctf.net/c/26/fixme1.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.128, 3.160.22.92, 3.160.22.43, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.128|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 837 [application/octet-stream]
Saving to: 'fixme1.py'

fixme1.py                                       100%[======================================================================================================>]     837  --.-KB/s    in 0s      

2024-09-15 06:39:35 (329 MB/s) - 'fixme1.py' saved [837/837]

carlosof-picoctf@webshell:/tmp/tmp.LeKDv3ikVX$ python3 fixme1.py 
  File "/tmp/tmp.LeKDv3ikVX/fixme1.py", line 20
    print('That is correct! Here\'s your flag: ' + flag)
IndentationError: unexpected indent
carlosof-picoctf@webshell:/tmp/tmp.LeKDv3ikVX$ nano fixme1.py 
carlosof-picoctf@webshell:/tmp/tmp.LeKDv3ikVX$ nano fixme1.py 
carlosof-picoctf@webshell:/tmp/tmp.LeKDv3ikVX$ python3 fixme1.py 
That is correct! Here's your flag: picoCTF{1nd3nt1ty_cr1515_09ee727a}
carlosof-picoctf@webshell:/tmp/tmp.LeKDv3ikVX$ 
```

## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/240