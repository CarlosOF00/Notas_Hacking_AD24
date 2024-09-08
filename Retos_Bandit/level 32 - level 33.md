## Objetivo 
After all this `git` stuff, it’s time for another escape. Good luck!

## Datos de Acceso al Nivel
user: bandit33
password: 3O9RfhqyAlVBEZpVb6LYStshZoqoSx5K

## Solución
```bash
┌──(kali㉿kali)-[~]
└─$ ssh bandit32@bandit.labs.overthewire.org -p2220 
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

bandit32@bandit.labs.overthewire.org's password: 

WELCOME TO THE UPPERCASE SHELL
>> ls -la
sh: 1: LS: Permission denied
>> $0
$ ls -la
total 36
drwxr-xr-x  2 root     root      4096 Jul 17 15:57 .
drwxr-xr-x 70 root     root      4096 Jul 17 15:58 ..
-rw-r--r--  1 root     root       220 Mar 31 08:41 .bash_logout
-rw-r--r--  1 root     root      3771 Mar 31 08:41 .bashrc
-rw-r--r--  1 root     root       807 Mar 31 08:41 .profile
-rwsr-x---  1 bandit33 bandit32 15136 Jul 17 15:57 uppershell
$ whoami
bandit33
$ cat /etc/bandit\_pass/bandit33
tQdtbs5D5i2vJwkO8mEyYEyTL8izoeJ0
$ 

```


## Notas Adicionales
- En lugar de simplemente imprimir la salida del comando, `>> $0` redirige la salida estándar al archivo cuyo nombre es el del propio script o shell. En este caso, parece que el entorno o shell se está ejecutando de una forma que permite manipular su propio archivo de script.
- El comando `cat /etc/bandit_pass/bandit33` se utiliza para mostrar el contenido del archivo ubicado en `/etc/bandit_pass/bandit33`.

## Referencias 

[Bash Shell Convert Uppercase to Lowercase in Linux - nixCraft (cyberciti.biz)](https://www.cyberciti.biz/faq/linux-unix-shell-programming-converting-lowercase-uppercase/)