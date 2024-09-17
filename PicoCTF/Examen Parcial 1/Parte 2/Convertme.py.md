## Descripción 
Run the Python script and convert the given number from decimal to binary to get the flag.[Download Python script](https://artifacts.picoctf.net/c/24/convertme.py)

## Datos de Acceso al Nivel
user: carlosof
password:

## Solución
```bash
carlosof-picoctf@webshell:/tmp/tmp.LpLB2b249R$ mktemp -d
/tmp/tmp.VXyOnwQ55i
carlosof-picoctf@webshell:/tmp/tmp.LpLB2b249R$ cd /tmp/tmp.VXyOnwQ55i/
carlosof-picoctf@webshell:/tmp/tmp.VXyOnwQ55i$ https://artifacts.picoctf.net/c/24/convertme.py
-bash: https://artifacts.picoctf.net/c/24/convertme.py: No such file or directory
carlosof-picoctf@webshell:/tmp/tmp.VXyOnwQ55i$ wget https://artifacts.picoctf.net/c/24/convertme.py
--2024-09-15 06:34:17--  https://artifacts.picoctf.net/c/24/convertme.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.92, 3.160.22.128, 3.160.22.16, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.92|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1189 (1.2K) [application/octet-stream]
Saving to: 'convertme.py'

convertme.py                                    100%[======================================================================================================>]   1.16K  --.-KB/s    in 0s      

2024-09-15 06:34:17 (47.4 MB/s) - 'convertme.py' saved [1189/1189]

carlosof-picoctf@webshell:/tmp/tmp.VXyOnwQ55i$ ls
convertme.py
carlosof-picoctf@webshell:/tmp/tmp.VXyOnwQ55i$ python3 convertme.py 
If 20 is in decimal base, what is it in binary base?
Answer: 10100
That is correct! Here's your flag: picoCTF{4ll_y0ur_b4535_722f6b39}
carlosof-picoctf@webshell:/tmp/tmp.VXyOnwQ55i$ 
```


## Notas Adicionales
![[ConvertmeCap.png]]

## Referencias 
https://play.picoctf.org/practice/challenge/239