## Descripción 
Can you invoke help flags for a tool or binary? [This program](https://mercury.picoctf.net/static/beec4f433e5ee5bfcd71bba8d5863faf/warm) has extraordinarily helpful information...

## Datos de Acceso al Nivel
user: carlosof
password:

## Solución
```bash
carlosof-picoctf@webshell:~$ mktemp -d
/tmp/tmp.5WO5BokRin
carlosof-picoctf@webshell:~$ cd /tmp/tmp.5WO5BokRin/
carlosof-picoctf@webshell:/tmp/tmp.5WO5BokRin$ wget https://mercury.picoctf.net/static/beec4f433e5ee5bfcd71bba8d5863faf/warm
--2024-09-15 21:57:38--  https://mercury.picoctf.net/static/beec4f433e5ee5bfcd71bba8d5863faf/warm
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 10936 (11K) [application/octet-stream]
Saving to: 'warm'

warm                                            100%[======================================================================================================>]  10.68K  --.-KB/s    in 0s      

2024-09-15 21:57:38 (286 MB/s) - 'warm' saved [10936/10936]

carlosof-picoctf@webshell:/tmp/tmp.5WO5BokRin$ ls
warm
carlosof-picoctf@webshell:/tmp/tmp.5WO5BokRin$ ls -la
total 12
drwx------ 2 carlosof-picoctf carlosof-picoctf    18 Sep 15 21:57 .
drwxrwxrwt 1 root             root                28 Sep 15 21:57 ..
-rw-rw-r-- 1 carlosof-picoctf carlosof-picoctf 10936 Mar 16  2021 warm
carlosof-picoctf@webshell:/tmp/tmp.5WO5BokRin$ chmod u+x warm 
carlosof-picoctf@webshell:/tmp/tmp.5WO5BokRin$ ls -la
total 12
drwx------ 2 carlosof-picoctf carlosof-picoctf    18 Sep 15 21:57 .
drwxrwxrwt 1 root             root                28 Sep 15 21:57 ..
-rwxrw-r-- 1 carlosof-picoctf carlosof-picoctf 10936 Mar 16  2021 warm
carlosof-picoctf@webshell:/tmp/tmp.5WO5BokRin$ . warm 
-bash: .: warm: cannot execute binary file
carlosof-picoctf@webshell:/tmp/tmp.5WO5BokRin$ file warm 
warm: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 3.2.0, BuildID[sha1]=506b7be935d8940c672ab0d40d2e03ebd746155b, with debug_info, not stripped
carlosof-picoctf@webshell:/tmp/tmp.5WO5BokRin$ ./warm 
Hello user! Pass me a -h to learn what I can do!
carlosof-picoctf@webshell:/tmp/tmp.5WO5BokRin$ ^C
carlosof-picoctf@webshell:/tmp/tmp.5WO5BokRin$ ./warm 
Hello user! Pass me a -h to learn what I can do!
carlosof-picoctf@webshell:/tmp/tmp.5WO5BokRin$ -h
-bash: -h: command not found
carlosof-picoctf@webshell:/tmp/tmp.5WO5BokRin$ ./warm -h
Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_616f7182}
carlosof-picoctf@webshell:/tmp/tmp.5WO5BokRin$ 
```


## Notas Adicionales
- `chmod` sirve para cambiar los permisos.

## Referencias 
https://play.picoctf.org/practice/challenge/170