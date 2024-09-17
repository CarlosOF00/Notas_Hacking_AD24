## Descripción 
Run the `runme.py` script to get the flag. Download the script with your browser or with `wget` in the webshell.[Download runme.py Python script](https://artifacts.picoctf.net/c/34/runme.py)

## Datos de Acceso al Nivel
user: carlosof
password:

## Solución
```bash
carlosof-picoctf@webshell:~$ mktemp -d
/tmp/tmp.gGmwm3x8y0
carlosof-picoctf@webshell:~$ cd /tmp/tmp.gGmwm3x8y0/
carlosof-picoctf@webshell:/tmp/tmp.gGmwm3x8y0$ wget https://artifacts.picoctf.net/c/34/runme.py
--2024-09-15 07:14:56--  https://artifacts.picoctf.net/c/34/runme.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.43, 3.160.22.92, 3.160.22.128, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.43|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 270 [application/octet-stream]
Saving to: 'runme.py'

runme.py                                        100%[======================================================================================================>]     270  --.-KB/s    in 0s      

2024-09-15 07:14:57 (89.5 MB/s) - 'runme.py' saved [270/270]

carlosof-picoctf@webshell:/tmp/tmp.gGmwm3x8y0$ ls
runme.py
carlosof-picoctf@webshell:/tmp/tmp.gGmwm3x8y0$ python3 runme.py 
picoCTF{run_s4n1ty_run}
carlosof-picoctf@webshell:/tmp/tmp.gGmwm3x8y0$ 


```

## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/250