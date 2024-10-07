## Descripción 
This is a really weird text file [TXT](https://jupiter.challenges.picoctf.org/static/e7e5d188621ee705ceeb0452525412ef/flag.txt)? Can you find the flag?

## Datos de Acceso al Nivel
user: carlosof
password:

## Solución
```bash
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic]
└─$ mkdir extensions  
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic]
└─$ cd extensions 
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic/extensions]
└─$ wget https://jupiter.challenges.picoctf.org/static/e7e5d188621ee705ceeb0452525412ef/flag.txt    
--2024-09-29 01:20:47--  https://jupiter.challenges.picoctf.org/static/e7e5d188621ee705ceeb0452525412ef/flag.txt
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 9984 (9.8K) [application/octet-stream]
Saving to: ‘flag.txt’

flag.txt                                  100%[===================================================================================>]   9.75K  --.-KB/s    in 0s      

2024-09-29 01:20:47 (172 MB/s) - ‘flag.txt’ saved [9984/9984]

                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic/extensions]
└─$ file flag.txt    
flag.txt: PNG image data, 1697 x 608, 8-bit/color RGB, non-interlaced
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic/extensions]
└─$ xxd -l 100  flag.txt
00000000: 8950 4e47 0d0a 1a0a 0000 000d 4948 4452  .PNG........IHDR
00000010: 0000 06a1 0000 0260 0802 0000 0085 ad5e  .......`.......^
00000020: 9a00 0000 0173 5247 4200 aece 1ce9 0000  .....sRGB.......
00000030: 0004 6741 4d41 0000 b18f 0bfc 6105 0000  ..gAMA......a...
00000040: 0009 7048 5973 0000 1625 0000 1625 0149  ..pHYs...%...%.I
00000050: 5224 f000 0026 9549 4441 5478 5eed dd6b  R$...&.IDATx^..k
00000060: 421b 39b7                                B.9.
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic/extensions]
└─$ mv flag.txt flag.png
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic/extensions]
└─$ open flag.png  
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic/extensions]
└─$ picoCTF{now_you_know_about_extensions}
picoCTF{now_you_know_about_extensions}: command not found
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosForensic/extensions]
└─$ 

```
-  Al ser una imagen, hay que transcribir la bandera

## Notas Adicionales
- Las extensiones de archivo son sufijos que se añaden al nombre de un archivo para indicar su formato o tipo.

- **`xxd`**: Es una herramienta que crea una representación hexadecimal de un archivo. También puede convertir archivos hexadecimales de nuevo a su forma original.

- `flag.txt` parece ser un archivo de imagen en formato PNG, ya que los primeros bytes corresponden a la cabecera típica de un archivo PNG (`8950 4e47`).

## Referencias 
https://play.picoctf.org/practice/challenge/52?page=1&search=extens
