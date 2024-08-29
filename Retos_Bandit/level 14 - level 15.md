## Objetivo 
The password for the next level can be retrieved by submitting the password of the current level to **port 30000 on localhost**.
## Datos de Acceso al Nivel
user: bandit14
password:MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS
## Solución
```
└─$ ssh bandit14@bandit.labs.overthewire.org -p 2220

bandit14@bandit:~$ which nc
/usr/bin/nc
bandit14@bandit:~$ nc localhost 30000
MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS
Correct!
8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo

^C
bandit14@bandit:~$ 

```
## Notas Adicionales
**which**: es una utilidad de línea de comandos que busca en los directorios listados en la variable de entorno PATH para encontrar la ubicación de un programa ejecutable. Retorna la ruta completa del ejecutable si se encuentra.

**nc**: es la abreviatura de **Netcat**, una herramienta de red versátil que se utiliza para leer y escribir datos a través de conexiones de red utilizando el protocolo TCP o UDP. Es conocida como la "navaja suiza" de las herramientas de red debido a su amplia gama de usos, que incluyen la prueba de conexiones, la transferencia de archivos, y la depuración de redes.
## Referencias 
https://www.youtube.com/watch?v=7_LPdttKXPc
https://computer.howstuffworks.com/web-server5.htm
https://en.wikipedia.org/wiki/IP_address
https://en.wikipedia.org/wiki/Localhost
https://computer.howstuffworks.com/web-server8.htm
https://en.wikipedia.org/wiki/Port_(computer_networking)