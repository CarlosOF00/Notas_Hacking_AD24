## Descripción
There's something in the [building](https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png). Can you retrieve the flag?

## Datos de Acceso al Nivel
user: carlosof
password:

## Solución
```bash
┌──(kali㉿kali)-[~/retosForensic]
└─$ mkdir whatlieswithin
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosForensic]
└─$ cd whatlieswithin                                                                           
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosForensic/whatlieswithin]
└─$ wget https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png
--2024-09-29 01:34:51--  https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 625219 (611K) [application/octet-stream]
Saving to: ‘buildings.png’

buildings.png                             100%[====================================================================================>] 610.57K  1.65MB/s    in 0.4s    

2024-09-29 01:34:52 (1.65 MB/s) - ‘buildings.png’ saved [625219/625219]

                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosForensic/whatlieswithin]
└─$ file buildings.png 
buildings.png: PNG image data, 657 x 438, 8-bit/color RGBA, non-interlaced
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosForensic/whatlieswithin]
└─$ open buildings.png 
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosForensic/whatlieswithin]
└─$ zteg  
Command 'zteg' not found, did you mean:
  command 'ztee' from deb zmap
Try: sudo apt install <deb name>
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosForensic/whatlieswithin]
└─$ zsteg                              
zsteg: command not found
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosForensic/whatlieswithin]
└─$ sudo gem install zsteg                           
[sudo] password for kali: 
Fetching zsteg-0.2.13.gem
Fetching rainbow-3.1.1.gem
Fetching iostruct-0.1.3.gem
Fetching zpng-0.4.5.gem
Successfully installed rainbow-3.1.1
Successfully installed zpng-0.4.5
Successfully installed iostruct-0.1.3
Successfully installed zsteg-0.2.13
Parsing documentation for rainbow-3.1.1
Installing ri documentation for rainbow-3.1.1
Parsing documentation for zpng-0.4.5
Installing ri documentation for zpng-0.4.5
Parsing documentation for iostruct-0.1.3
Installing ri documentation for iostruct-0.1.3
Parsing documentation for zsteg-0.2.13
Installing ri documentation for zsteg-0.2.13
Done installing documentation for rainbow, zpng, iostruct, zsteg after 4 seconds
4 gems installed
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosForensic/whatlieswithin]
└─$ zsteg  buildings.png 
b1,r,lsb,xy         .. text: "^5>R5YZrG"
b1,rgb,lsb,xy       .. text: "picoCTF{h1d1ng_1n_th3_b1t5}"
b1,abgr,msb,xy      .. file: PGP Secret Sub-key -
b2,b,lsb,xy         .. text: "XuH}p#8Iy="
b3,abgr,msb,xy      .. text: "t@Wp-_tH_v\r"
b4,r,lsb,xy         .. text: "fdD\"\"\"\" "
b4,r,msb,xy         .. text: "%Q#gpSv0c05"
b4,g,lsb,xy         .. text: "fDfffDD\"\""
b4,g,msb,xy         .. text: "f\"fff\"\"DD"
b4,b,lsb,xy         .. text: "\"$BDDDDf"
b4,b,msb,xy         .. text: "wwBDDDfUU53w"
b4,rgb,msb,xy       .. text: "dUcv%F#A`"
b4,bgr,msb,xy       .. text: " V\"c7Ga4"
b4,abgr,msb,xy      .. text: "gOC_$_@o"


```
## Notas Adicionales

La esteganografía es la práctica de ocultar información dentro de otros datos, de manera que la existencia de la información oculta no sea evidente. A diferencia de la criptografía, que se centra en hacer que la información sea ilegible para terceros, la esteganografía busca ocultar la propia existencia de la información.

**Métodos comunes**:
    - **Imágenes**: Se puede ocultar texto o datos dentro de los píxeles de una imagen sin que sea visible a simple vista.
    - **Audio**: Se pueden modificar las ondas sonoras para incluir información oculta.
    - **Video**: Se puede insertar datos en el flujo de video, aprovechando el gran tamaño de los archivos.

## Referencias 
https://play.picoctf.org/practice/challenge/74?page=1&search=lie%20
https://es.wikipedia.org/wiki/Esteganografía
