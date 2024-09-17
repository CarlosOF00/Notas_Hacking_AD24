## Descripción 
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/11/level1.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/11/level1.flag.txt.enc) in the same directory too.

## Datos de Acceso al Nivel
user: carlosof
password:

## Solución
```bash
carlosof-picoctf@webshell:~$ mktemp -d
/tmp/tmp.MbyHmD1SDX
carlosof-picoctf@webshell:~$ cd /tmp/tmp.MbyHmD1SDX/
carlosof-picoctf@webshell:/tmp/tmp.MbyHmD1SDX$ wget https://artifacts.picoctf.net/c/11/level1.py
--2024-09-15 07:07:19--  https://artifacts.picoctf.net/c/11/level1.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.92, 3.160.22.16, 3.160.22.43, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.92|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 876 [application/octet-stream]
Saving to: 'level1.py'

level1.py                                       100%[======================================================================================================>]     876  --.-KB/s    in 0s      

2024-09-15 07:07:20 (325 MB/s) - 'level1.py' saved [876/876]

carlosof-picoctf@webshell:/tmp/tmp.MbyHmD1SDX$ wget https://artifacts.picoctf.net/c/11/level1.flag.txt.enc
--2024-09-15 07:07:37--  https://artifacts.picoctf.net/c/11/level1.flag.txt.enc
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.128, 3.160.22.43, 3.160.22.16, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.128|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 30 [application/octet-stream]
Saving to: 'level1.flag.txt.enc'

level1.flag.txt.enc                             100%[======================================================================================================>]      30  --.-KB/s    in 0s      

2024-09-15 07:07:37 (1.43 MB/s) - 'level1.flag.txt.enc' saved [30/30]

carlosof-picoctf@webshell:/tmp/tmp.MbyHmD1SDX$ ls -la
total 8
drwx------ 2 carlosof-picoctf carlosof-picoctf  50 Sep 15 07:07 .
drwxrwxrwt 1 root             root              72 Sep 15 07:07 ..
-rw-rw-r-- 1 carlosof-picoctf carlosof-picoctf  30 Mar 16  2023 level1.flag.txt.enc
-rw-rw-r-- 1 carlosof-picoctf carlosof-picoctf 876 Mar 16  2023 level1.py
carlosof-picoctf@webshell:/tmp/tmp.MbyHmD1SDX$ cat level1.
level1.flag.txt.enc  level1.py            
carlosof-picoctf@webshell:/tmp/tmp.MbyHmD1SDX$ cat level1.
level1.flag.txt.enc  level1.py            
carlosof-picoctf@webshell:/tmp/tmp.MbyHmD1SDX$ cat level1.flag.txt.enc 
A
 Rr1wQ  nVT_nPRVWcarlosof-picoctf@webshell:/tmp/tmp.MbyHmD1SDX$ python3 level1.py 
Please enter correct password for flag: ^CTraceback (most recent call last):
  File "/tmp/tmp.MbyHmD1SDX/level1.py", line 28, in <module>
    level_1_pw_check()
  File "/tmp/tmp.MbyHmD1SDX/level1.py", line 18, in level_1_pw_check
    user_pw = input("Please enter correct password for flag: ")
KeyboardInterrupt

carlosof-picoctf@webshell:/tmp/tmp.MbyHmD1SDX$ python3 level1.py 
Please enter correct password for flag: A
 Rr1wQ  nVT_nPRVWThat password is incorrect
carlosof-picoctf@webshell:/tmp/tmp.MbyHmD1SDX$ nano level1.py   
carlosof-picoctf@webshell:/tmp/tmp.MbyHmD1SDX$ python3 level1.py 
Please enter correct password for flag: 1e1a
Welcome back... your flag, user:
picoCTF{545h_r1ng1ng_fa343060}
carlosof-picoctf@webshell:/tmp/tmp.MbyHmD1SDX$ 
```

## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/245