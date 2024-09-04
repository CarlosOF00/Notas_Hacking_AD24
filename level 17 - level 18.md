## Objetivo 
There are 2 files in the homedirectory: **passwords.old and passwords.new**. The password for the next level is in **passwords.new** and is the only line that has been changed between **passwords.old and passwords.new**

**NOTE: if you have solved this level and see ‘Byebye!’ when trying to log into bandit18, this is related to the next level, bandit19**
## Datos de Acceso al Nivel
user: bandit17
password: EReVavePLFHtFlFsjn3hyzMlvSuSAcRD
## Solución
```bash
└─$ ssh bandit17@bandit.labs.overthewire.org -p 2220
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

bandit17@bandit.labs.overthewire.org's password: 

bandit17@bandit:~$ ls -la
total 36
drwxr-xr-x  3 root     root     4096 Jul 17 15:57 .
drwxr-xr-x 70 root     root     4096 Jul 17 15:58 ..
-rw-r-----  1 bandit17 bandit17   33 Jul 17 15:57 .bandit16.password
-rw-r--r--  1 root     root      220 Mar 31 08:41 .bash_logout
-rw-r--r--  1 root     root     3771 Mar 31 08:41 .bashrc
-rw-r-----  1 bandit18 bandit17 3300 Jul 17 15:57 passwords.new
-rw-r-----  1 bandit18 bandit17 3300 Jul 17 15:57 passwords.old
-rw-r--r--  1 root     root      807 Mar 31 08:41 .profile
drwxr-xr-x  2 root     root     4096 Jul 17 15:57 .ssh
bandit17@bandit:~$ wc -l passwords.old
100 passwords.old
bandit17@bandit:~$ wc -l passwords.new
100 passwords.new
bandit17@bandit:~$ diff passwords.old passwords.new
42c42
< bSrACvJvvBSxEM2SGsV5sn09vc3xgqyp
---
> x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO
bandit17@bandit:~$ diff passwords.old passwords.new --color
42c42
< bSrACvJvvBSxEM2SGsV5sn09vc3xgqyp
---
> x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO
bandit17@bandit:~$ 

```
## Notas Adicionales

## Referencias 