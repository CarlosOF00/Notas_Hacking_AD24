## Objetivo 
I have these 2 images, can you make a flag out of them? [scrambled1.png](https://mercury.picoctf.net/static/75e646e4ad19967ca1811f895fb40465/scrambled1.png) [scrambled2.png](https://mercury.picoctf.net/static/75e646e4ad19967ca1811f895fb40465/scrambled2.png)

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosCrypto]
└─$ mkdir pixelated                        
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosCrypto]
└─$ cd pixelated 
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosCrypto/pixelated]
└─$ wget https://mercury.picoctf.net/static/75e646e4ad19967ca1811f895fb40465/scrambled1.png
--2024-10-23 10:25:16--  https://mercury.picoctf.net/static/75e646e4ad19967ca1811f895fb40465/scrambled1.png
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 197176 (193K) [application/octet-stream]
Saving to: ‘scrambled1.png’

scrambled1.png                            100%[====================================================================================>] 192.55K  1.08MB/s    in 0.2s    

2024-10-23 10:25:17 (1.08 MB/s) - ‘scrambled1.png’ saved [197176/197176]

                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosCrypto/pixelated]
└─$ wget https://mercury.picoctf.net/static/75e646e4ad19967ca1811f895fb40465/scrambled2.png
--2024-10-23 10:25:23--  https://mercury.picoctf.net/static/75e646e4ad19967ca1811f895fb40465/scrambled2.png
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... con
HTTP request sent, awaiting response... 200 OK
Length: 197174 (193K) [application/octet-stream]
Saving to: ‘scrambled2.png’

scrambled2.png                            100%[===================================

2024-10-23 10:25:23 (1.12 MB/s) - ‘scrambled2.png’ saved [197174/197174]

                                                                                  
┌──(kali㉿kali)-[~/retosCrypto/pixelated]
└─$ ls
scrambled1.png  scrambled2.png

┌──(kali㉿kali)-[~/retosCrypto/pixelated]
└─$ nano script.py                         
                                                                                  
┌──(kali㉿kali)-[~/retosCrypto/pixelated]
└─$ python3 script.py               
                                                                                  
┌──(kali㉿kali)-[~/retosCrypto/pixelated]
└─$ ls
nueva.png  scrambled1.png  scrambled2.png  script.py
                                                                                  
┌──(kali㉿kali)-[~/retosCrypto/pixelated]
└─$ open nueva.png 
                                                                                  
┌──(kali㉿kali)-[~/retosCrypto/pixelated]
└─$ echo 'picoCTF{d562333d}'                
picoCTF{d562333d}

```

script.py
```bash
from PIL import Image
import numpy as np

imagen1 = np.asarray(Image.open("scrambled1.png"))
imagen2 = np.asarray(Image.open("scrambled2.png"))

datos = imagen1.copy() + imagen2.copy()

nueva = Image.fromarray(datos)

nueva.save("nueva.png", "PNG")

```
## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/100
