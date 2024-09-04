## Objetivo 
A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

**NOTE:** Looking at shell scripts written by other people is a very useful skill. The script for this level is intentionally made easy to read. If you are having problems understanding what it does, try executing it to see the debug information it prints.
## Datos de Acceso al Nivel
user: bandit21
password: EeoULMCra2q0dSkYj561DX7s1CpBuOBt

## Solución
```bash
└─$ ssh bandit21@bandit.labs.overthewire.org -p2220
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

bandit21@bandit.labs.overthewire.org's password: 
Permission denied, please try again.
bandit21@bandit.labs.overthewire.org's password: 


bandit21@bandit:~$ ls /etc/cron.d
cronjob_bandit22  cronjob_bandit23  cronjob_bandit24  e2scrub_all  otw-tmp-dir  sysstat
bandit21@bandit:~$ cat /etc/cron.d/cronjob_bandit22
@reboot bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
* * * * * bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
@reboot bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
* * * * * bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
bandit21@bandit:~$ cat /usr/bin/cronjob_bandit22.sh
#!/bin/bash
chmod 644 /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
cat /etc/bandit_pass/bandit22 > /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
bandit21@bandit:~$ cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
tRae0UfB9v0UzbCdn9cY0gQnds9GF58Q
bandit21@bandit:~$
```
## Notas Adicionales

- Cron Job en linux es una **herramienta que permite programar y ejecutar tareas específicas dentro de nuestro sistema operativo Linux de forma automática**.
- /etc/cron.d - ahí ponemos los cronjobs, o dicho de otra forma, los archivos que quiero se ejecuten cada vez que arranca la computadora
## Referencias 
[CRON](https://guias.donweb.com/guia-completa-de-cron-job-en-linux/#:~:text=Cron%20Job%20en%20linux%20es,tiempo%20determinado%20por%20el%20usuario.)