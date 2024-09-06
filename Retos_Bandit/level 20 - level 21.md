## Objetivo 
There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).
## Datos de Acceso al Nivel
user: bandit20
password: 0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO
## Solución
```bash
┌──(kali㉿kali)-[~]
└─$ ssh bandit20@bandit.labs.overthewire.org -p2220
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

bandit20@bandit.labs.overthewire.org's password: 

bandit20@bandit:~$ ls -la
total 36
drwxr-xr-x  2 root     root      4096 Jul 17 15:57 .
drwxr-xr-x 70 root     root      4096 Jul 17 15:58 ..
-rw-r--r--  1 root     root       220 Mar 31 08:41 .bash_logout
-rw-r--r--  1 root     root      3771 Mar 31 08:41 .bashrc
-rw-r--r--  1 root     root       807 Mar 31 08:41 .profile
-rwsr-x---  1 bandit21 bandit20 15604 Jul 17 15:57 suconnect
bandit20@bandit:~$ jobs
[1]+  Done                    nc -lnvp 1503 <<< 0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO
bandit20@bandit:~$ ./suconnect 1503
Connection received on 127.0.0.1 53704
Read: 0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO
Password matches, sending next password
EeoULMCra2q0dSkYj561DX7s1CpBuOBt
bandit20@bandit:~$

```
## Notas Adicionales
& si agregamos un símbolo de estos al final de un comando, lo estamos enviando al segundo plano (backround) jobs - me muestra que comandos están en el segundo plano fg - saca un proceso o comando del segundo plano y lo trae al primer plano (foreground)
## Referencias 