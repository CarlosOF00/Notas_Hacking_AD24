## Descripción 
Run the Python script `code.py` in the same directory as `codebook.txt`.

- [Download code.py](https://artifacts.picoctf.net/c/1/code.py)
- [Download codebook.txt](https://artifacts.picoctf.net/c/1/codebook.txt)

## Datos de Acceso al Nivel
user: carlosof
password:

## Solución
```bash
carlosof-picoctf@webshell:~$ mktemp -d
/tmp/tmp.LpLB2b249R
carlosof-picoctf@webshell:~$ cd /tmp/tmp.LpLB2b249R/
carlosof-picoctf@webshell:/tmp/tmp.LpLB2b249R$ wget https://artifacts.picoctf.net/c/1/code.py
--2024-09-15 06:19:25--  https://artifacts.picoctf.net/c/1/code.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.92, 3.160.22.128, 3.160.22.43, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.92|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1278 (1.2K) [application/octet-stream]
Saving to: 'code.py'

code.py                                         100%[======================================================================================================>]   1.25K  --.-KB/s    in 0s      

2024-09-15 06:19:26 (60.4 MB/s) - 'code.py' saved [1278/1278]

carlosof-picoctf@webshell:/tmp/tmp.LpLB2b249R$ wget https://artifacts.picoctf.net/c/1/codebook.txt
--2024-09-15 06:19:33--  https://artifacts.picoctf.net/c/1/codebook.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.92, 3.160.22.43, 3.160.22.16, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.92|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 27 [application/octet-stream]
Saving to: 'codebook.txt'

codebook.txt                                    100%[======================================================================================================>]      27  --.-KB/s    in 0s      

2024-09-15 06:19:33 (7.74 MB/s) - 'codebook.txt' saved [27/27]

carlosof-picoctf@webshell:/tmp/tmp.LpLB2b249R$ python3 code.py 
picoCTF{c0d3b00k_455157_d9aa2df2}
carlosof-picoctf@webshell:/tmp/tmp.LpLB2b249R$ 
```

## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/238