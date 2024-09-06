## Objetivo 
A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

**NOTE:** Looking at shell scripts written by other people is a very useful skill. The script for this level is intentionally made easy to read. If you are having problems understanding what it does, try executing it to see the debug information it prints.

## Datos de Acceso al Nivel
user: bandit22
password: tRae0UfB9v0UzbCdn9cY0gQnds9GF58Q

## Solución
```bash
└─$ ssh bandit22@bandit.labs.overthewire.org -p2220 
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

bandit22@bandit.labs.overthewire.org's password: 

bandit22@bandit:~$ cat /etc/cron.d/cronjob_bandit23
@reboot bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
* * * * * bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
bandit22@bandit:~$ cat /usr/bin/cronjob_bandit23.sh
#!/bin/bash

myname=$(whoami)
mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)

echo "Copying passwordfile /etc/bandit_pass/$myname to /tmp/$mytarget"

cat /etc/bandit_pass/$myname > /tmp/$mytarget
bandit22@bandit:~$ myname=bandit23
bandit22@bandit:~$ mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)
bandit22@bandit:~$ echo $mytarget
8ca319486bfbbc3663ea0fbe81326349
bandit22@bandit:~$ cat /tmp/8ca319486bfbbc3663ea0fbe81326349
0Zf11ioIjMVN551jX3CmStKLYqjk54Ga
bandit22@bandit:~$ 


```
## Notas Adicionales
Cuando ejecutas el comando cat /etc/cron.d/cronjob_bandit23, el sistema mostrará el contenido del archivo cronjob_bandit23 en el terminal. 

**myname**=bandit23: este comando está asignando el valor bandit23 a una variable llamada myname.

**mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)**
Realiza varias operaciones encadenadas para calcular un valor y asignarlo a la variable mytarget.

**echo I am user $myname:** Este comando genera una cadena de texto. La variable $myname se expande a bandit23, por lo que el comando echo produce la cadena I am user bandit23.

**| md5sum:** El símbolo | toma la salida del comando anterior (en este caso, I am user bandit23) y la pasa como entrada al siguiente comando. md5sum calcula el hash MD5 de la cadena de texto que recibe. El hash MD5 es una cadena de 32 caracteres hexadecimales que representa el valor hash de la entrada.

**| cut -d ' ' -f 1:** Otro | toma la salida del comando md5sum y la pasa al comando cut. cut está configurado para dividir la entrada en campos utilizando el espacio ' ' como delimitador (-d ' '), y selecciona el primer campo (-f 1). En el caso de md5sum, el primer campo es el valor hash MD5, y el segundo campo es un guion (-), que indica la entrada estándar. Así que cut -d ' ' -f 1 extrae solo el hash MD5.

Finalmente, el resultado de esta operación (el hash MD5) se asigna a la variable mytarget.


## Referencias 
[OverTheWire Bandit Level 22 -> 23 - Walkthrough - MayADevBe Blog](https://mayadevbe.me/posts/overthewire/bandit/level23/)
