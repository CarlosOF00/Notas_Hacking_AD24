## Descripción 
This image passes LSB statistical analysis, but we can't help but think there must be something to the visual artifacts present in this image...Download the image [here](https://artifacts.picoctf.net/c/306/Ninja-and-Prince-Genji-Ukiyoe-Utagawa-Kunisada.flag.png)

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2]
└─$ mkdir MSB        
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2]
└─$ cd MSB  
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2/MSB]
└─$ wget https://artifacts.picoctf.net/c/306/Ninja-and-Prince-Genji-Ukiyoe-Utagawa-Kunisada.flag.png
--2024-10-16 14:51:02--  https://artifacts.picoctf.net/c/306/Ninja-and-Prince-Genji-Ukiyoe-Utagawa-Kunisada.flag.png
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.64, 3.161.55.61, 3.161.55.26, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.64|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 3354309 (3.2M) [application/octet-stream]
Saving to: ‘Ninja-and-Prince-Genji-Ukiyoe-Utagawa-Kunisada.flag.png’

Ninja-and-Prince-Genji-Ukiyoe-Utagawa-Kun 100%[===================================================================================>]   3.20M  4.61MB/s    in 0.7s    

2024-10-16 14:51:04 (4.61 MB/s) - ‘Ninja-and-Prince-Genji-Ukiyoe-Utagawa-Kunisada.flag.png’ saved [3354309/3354309]

                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2/MSB]
└─$ file Ninja-and-Prince-Genji-Ukiyoe-Utagawa-Kunisada.flag.png 
Ninja-and-Prince-Genji-Ukiyoe-Utagawa-Kunisada.flag.png: PNG image data, 1074 x 1500, 8-bit/color RGB, non-interlaced
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2/MSB]
└─$ open Ninja-and-Prince-Genji-Ukiyoe-Utagawa-Kunisada.flag.png 
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2/MSB]
└─$ exiftool Ninja-and-Prince-Genji-Ukiyoe-Utagawa-Kunisada.flag.png 
ExifTool Version Number         : 12.76
File Name                       : Ninja-and-Prince-Genji-Ukiyoe-Utagawa-Kunisada.flag.png
Directory                       : .
File Size                       : 3.4 MB
File Modification Date/Time     : 2023:08:04 15:26:16-06:00
File Access Date/Time           : 2024:10:16 14:51:12-06:00
File Inode Change Date/Time     : 2024:10:16 14:51:04-06:00
File Permissions                : -rw-rw-r--
File Type                       : PNG
File Type Extension             : png
MIME Type                       : image/png
Image Width                     : 1074
Image Height                    : 1500
Bit Depth                       : 8
Color Type                      : RGB
Compression                     : Deflate/Inflate
Filter                          : Adaptive
Interlace                       : Noninterlaced
Image Size                      : 1074x1500
Megapixels                      : 1.6

┌──(kali㉿kali)-[~/Parcial2/MSB]
└─$ wget https://raw.githubusercontent.com/Pulho/sigBits/master/sigBits.py
--2024-10-16 14:58:07--  https://raw.githubusercontent.com/Pulho/sigBits/master/sigBits.py
Resolving raw.githubusercontent.com (raw.githubusercontent.com)... 185.199.110.133, 185.199.111.133, 185.199.108.133, ...
Connecting to raw.githubusercontent.com (raw.githubusercontent.com)|185.199.110.133|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 7008 (6.8K) [text/plain]
Saving to: ‘sigBits.py’

sigBits.py                                100%[===================================================================================>]   6.84K  --.-KB/s    in 0s      

2024-10-16 14:58:08 (37.5 MB/s) - ‘sigBits.py’ saved [7008/7008]

                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2/MSB]
└─$ python3 sigBits.py -t=msb Ninja-and-Prince-Genji-Ukiyoe-Utagawa-Kunisada.flag.png 
Done, check the output file!
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2/MSB]
└─$ ls
Ninja-and-Prince-Genji-Ukiyoe-Utagawa-Kunisada.flag.png  outputSB.txt  sigBits.py

┌──(kali㉿kali)-[~/Parcial2/MSB]
└─$ cat outputSB.txt | grep -o -E "picoCTF.{0,50}"
picoCTF{15_y0ur_que57_qu1x071c_0r_h3r01c_06326238}"Thou h

```


## Notas Adicionales
`python3 sigBits.py`
Este script de Python (`sigBits.py`) parece ser una herramienta para extraer información de imágenes mediante la manipulación de los bits de los colores RGB, específicamente trabajando con el **Least Significant Bit (LSB)** o el **Most Significant Bit (MSB)** de las imágenes.

```bash
┌──(kali㉿kali)-[~/Parcial2/MSB]
└─$ python3 sigBits.py                                                               
Usage:
        sbPy [OPTIONS] [FILE]

Options:
        -t=<lsb or msb>, --type=<lsb or msb>:
                Choose between read LSB or MSB (Default is LSB)

        -o=<Order sigle>, --order=<Order sigle>:
                Read the lsb or msb in the specify order (Default is RGB)

        -out=<Ouput name>, --output=<Output name>
                Choose the name of the output file (Default is outputSB)

        -e=<Row r Column>, --extract=<Row or Column>
                Choose between extracting by row or column (Default is Column)

        -b=<7 bits of your choice>, --bits=<7 bits of your choice>
                Choose the bits you want to extract info ( Have higher priority than '--type or -t' )

```

`python3 sigBits.py -t=msb Ninja-and-Prince-Genji-Ukiyoe-Utagawa-Kunisada.flag.png`
- **`-t=msb`**: Indica que el script debe extraer los bits más significativos (MSB) de los valores de los píxeles (en vez de los bits menos significativos, LSB que es el valor por defecto).
- **`Ninja-and-Prince-Genji-Ukiyoe-Utagawa-Kunisada.flag.png`**: Es la imagen que se procesará. Esta imagen se leerá píxel por píxel y se extraerán los bits de acuerdo a las opciones dadas.
## Referencias 
https://play.picoctf.org/practice/challenge/359
https://github.com/Pulho/sigBits