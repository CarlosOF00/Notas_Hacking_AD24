## Descripción 
The Network Operations Center (NOC) of your local institution picked up a suspicious file, they're getting conflicting information on what type of file it is. They've brought you in as an external expert to examine the file. Can you extract all the information from this strange file?Download the suspicious file [here](https://artifacts.picoctf.net/c_titan/7/flag2of2-final.pdf).

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Parcial2]
└─$ mkdir Polyglot
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Parcial2]
└─$ cd Polyglot 
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Parcial2/Polyglot]
└─$ wget https://artifacts.picoctf.net/c_titan/7/flag2of2-final.pdf
--2024-10-16 16:38:21--  https://artifacts.picoctf.net/c_titan/7/flag2of2-final.pdf
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.225.11, 3.161.225.3, 3.161.225.62, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.225.11|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 3362 (3.3K) [application/octet-stream]
Saving to: ‘flag2of2-final.pdf’

flag2of2-final.pdf                        100%[====================================================================================>]   3.28K  --.-KB/s    in 0s      

2024-10-16 16:38:22 (35.4 MB/s) - ‘flag2of2-final.pdf’ saved [3362/3362]

                                                                                                                                                                       
┌──(kali㉿kali)-[~/Parcial2/Polyglot]
└─$ ls
flag2of2-final.pdf
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Parcial2/Polyglot]
└─$ open flag2of2-final.pdf 
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Parcial2/Polyglot]
└─$ file flag2of2-final.pdf                                     
flag2of2-final.pdf: PNG image data, 50 x 50, 8-bit/color RGBA, non-interlaced
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Parcial2/Polyglot]
└─$ mv flag2of2-final.pdf flag.png
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Parcial2/Polyglot]
└─$ open flag.png          
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Parcial2/Polyglot]
└─$ open flag2of2-final.pdf
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Parcial2/Polyglot]
└─$ open flag2of2-final.pdf
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Parcial2/Polyglot]
└─$ ls
flag.png
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Parcial2/Polyglot]
└─$ wget https://artifacts.picoctf.net/c_titan/7/flag2of2-final.pdf
--2024-10-16 16:44:21--  https://artifacts.picoctf.net/c_titan/7/flag2of2-final.pdf
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.61, 3.161.55.100, 3.161.55.64, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.61|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 3362 (3.3K) [application/octet-stream]
Saving to: ‘flag2of2-final.pdf’

flag2of2-final.pdf                        100%[====================================================================================>]   3.28K  --.-KB/s    in 0s      

2024-10-16 16:44:22 (35.0 MB/s) - ‘flag2of2-final.pdf’ saved [3362/3362]

                                                                                                                                                                       
┌──(kali㉿kali)-[~/Parcial2/Polyglot]
└─$ open flag2of2-final.pdf
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Parcial2/Polyglot]

```


## Notas Adicionales
- Si abrimos el archivo `pdf` obtenemos el resto de la bandera, entonces al tratar de buscar mas información, vemos que en realidad el archivo es una imagen, así que la copiamos con el formato `.png` y obtenemos el inicio de la bandera.

## Referencias 
https://play.picoctf.org/practice/challenge/423
