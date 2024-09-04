## Objetivo 
The password for the next level is stored in a file **readme** in the homedirectory. Unfortunately, someone has modified **.bashrc** to log you out when you log in with SSH.

## Datos de Acceso al Nivel
user: bandit18
password: x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO

## Solución
```bash
└─$ ssh bandit18@bandit.labs.overthewire.org -p 2220
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

bandit18@bandit.labs.overthewire.org's password: 

  For more information regarding individual wargames, visit
  http://www.overthewire.org/wargames/

  For support, questions or comments, contact us on discord or IRC.

  Enjoy your stay!

Byebye !
Connection to bandit.labs.overthewire.org closed.
                                                                                                                                                                      
┌──(kali㉿kali)-[~]
└─$ ssh bandit18@bandit.labs.overthewire.org -p2220 /bin/bash
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

bandit18@bandit.labs.overthewire.org's password: 
ls
readme
cat readme
cGWpMaKXVwDUNgPAVJbWYuGHVn9zl3j8
exit
                                                                                                                                                                      
┌──(kali㉿kali)-[~]
└─$ 

```

## Notas Adicionales
El comando ssh bandit18@bandit.labs.overthewire.org -p2220 /bin/bash establece una conexión SSH al servidor bandit.labs.overthewire.org como el usuario bandit18 en el puerto 2220 y ejecuta una sesión de Bash en el servidor remoto.

cat .bashrc --> te permite ver las configuraciones y alias personalizados, variables de entorno, y otras configuraciones que se aplican al entorno del terminal de Bash del usuario.
## Referencias 
