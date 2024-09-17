## Descripción 
This file has a flag in plain sight (aka "in-the-clear"). [Download flag](https://mercury.picoctf.net/static/704f877da185904ec3992e7255a15c6c/flag).

## Datos de Acceso al Nivel
user: carlosof
password:

## Solución
```bash
carlosof-picoctf@webshell:~$ mktemp -d
/tmp/tmp.43i3saupqg
carlosof-picoctf@webshell:~$ cd /tmp/tmp.43i3saupqg/
carlosof-picoctf@webshell:/tmp/tmp.43i3saupqg$ wget https://mercury.picoctf.net/static/704f877da185904ec3992e7255a15c6c/flag
--2024-09-15 20:37:08--  https://mercury.picoctf.net/static/704f877da185904ec3992e7255a15c6c/flag
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 34 [application/octet-stream]
Saving to: 'flag'

flag                                            100%[======================================================================================================>]      34  --.-KB/s    in 0s      

2024-09-15 20:37:08 (14.6 MB/s) - 'flag' saved [34/34]

carlosof-picoctf@webshell:/tmp/tmp.43i3saupqg$ ls
flag
carlosof-picoctf@webshell:/tmp/tmp.43i3saupqg$ cat flag 
picoCTF{s4n1ty_v3r1f13d_1a94e0f9}
carlosof-picoctf@webshell:/tmp/tmp.43i3saupqg$ 

```

## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/147
