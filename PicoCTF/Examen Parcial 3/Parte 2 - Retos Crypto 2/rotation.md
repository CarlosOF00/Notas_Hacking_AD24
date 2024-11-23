## Descripción 
You will find the flag after decrypting this fileDownload the encrypted flag [here](https://artifacts.picoctf.net/c/389/encrypted.txt).

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Parcial3]
└─$ mkdir rotation          
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Parcial3]
└─$ cd rotation          
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Parcial3/rotation]
└─$ wget https://artifacts.picoctf.net/c/389/encrypted.txt  
--2024-11-17 06:49:04--  https://artifacts.picoctf.net/c/389/encrypted.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.249.21.46, 13.249.21.85, 13.249.21.32, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.249.21.46|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 37 [application/octet-stream]
Saving to: ‘encrypted.txt’

encrypted.txt                             100%[====================================================================================>]      37  --.-KB/s    in 0s      

2024-11-17 06:49:05 (55.5 MB/s) - ‘encrypted.txt’ saved [37/37]

                                                                                                                                                                       
┌──(kali㉿kali)-[~/Parcial3/rotation]
└─$ ls
encrypted.txt
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Parcial3/rotation]
└─$ cat encrypted.txt 
xqkwKBN{z0bib1wv_l3kzgxb3l_i4j7l759}
```

- Ingresamos a la pagina de [ROT13 - CyberChef](https://cyberchef.io/#recipe=ROT13(true,true,false,18)&input=eHFrd0tCTnt6MGJpYjF3dl9sM2t6Z3hiM2xfaTRqN2w3NTl9Cg) y usaremos `ROT13` para desencriptar el mensaje.
- En mi caso deje `Amount` en 18 y descifre la bandera.

- Flag: picoCTF{r0tat1on_d3crypt3d_a4b7d759}

## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/373
[ROT13 - CyberChef](https://cyberchef.io/#recipe=ROT13(true,true,false,18)&input=eHFrd0tCTnt6MGJpYjF3dl9sM2t6Z3hiM2xfaTRqN2w3NTl9Cg)

