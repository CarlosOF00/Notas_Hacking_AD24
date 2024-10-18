## Descripción 
Download this image and find the flag.

- [Download image](https://artifacts.picoctf.net/c/217/pico.flag.png)

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
┌──(kali㉿kali)-[~/Parcial2]
└─$ mkdir stego       
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2]
└─$ cd stego 
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2/stego]
└─$ wget https://artifacts.picoctf.net/c/217/pico.flag.png                   
--2024-10-16 22:44:44--  https://artifacts.picoctf.net/c/217/pico.flag.png
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.100, 3.161.55.26, 3.161.55.64, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.100|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 13443 (13K) [application/octet-stream]
Saving to: ‘pico.flag.png’

pico.flag.png                             100%[===================================================================================>]  13.13K  --.-KB/s    in 0s      

2024-10-16 22:44:45 (85.4 MB/s) - ‘pico.flag.png’ saved [13443/13443]

                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2/stego]
└─$ opne pico.flag.png                    
Command 'opne' not found, did you mean:
  command 'opnk' from deb offpunk
Try: sudo apt install <deb name>
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2/stego]
└─$ open pico.flag.png                    
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2/stego]
└─$ exiftool pico.flag.png                                                        
ExifTool Version Number         : 12.76
File Name                       : pico.flag.png
Directory                       : .
File Size                       : 13 kB
File Modification Date/Time     : 2023:08:04 14:36:21-06:00
File Access Date/Time           : 2024:10:16 22:44:58-06:00
File Inode Change Date/Time     : 2024:10:16 22:44:45-06:00
File Permissions                : -rw-rw-r--
File Type                       : PNG
File Type Extension             : png
MIME Type                       : image/png
Image Width                     : 585
Image Height                    : 172
Bit Depth                       : 8
Color Type                      : RGB with Alpha
Compression                     : Deflate/Inflate
Filter                          : Adaptive
Interlace                       : Noninterlaced
Image Size                      : 585x172
Megapixels                      : 0.101
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2/stego]
└─$ zsteg pico.flag.png                                                                                                                  
b1,r,lsb,xy         .. text: "~__B>VG?G@"
b1,rgb,lsb,xy       .. text: "picoCTF{7h3r3_15_n0_5p00n_a9a181eb}$t3g0"
b1,abgr,lsb,xy      .. text: "E2A5q4E%uSA"
b2,b,lsb,xy         .. text: "AAPAAQTAAA"
b2,b,msb,xy         .. text: "HWUUUUUU"
b3,r,lsb,xy         .. file: gfxboot compiled html help file
b4,r,lsb,xy         .. file: Targa image data (16-273) 65536 x 4097 x 1 +4352 +4369 - 1-bit alpha - right "\021\020\001\001\021\021\001\001\021\021\001"
b4,g,lsb,xy         .. file: 0420 Alliant virtual executable not stripped
b4,b,lsb,xy         .. file: Targa image data - Map 272 x 17 x 16 +257 +272 - 1-bit alpha "\020\001\021\001\021\020\020\001\020\001\020\001"
b4,bgr,lsb,xy       .. file: Targa image data - Map 273 x 272 x 16 +1 +4113 - 1-bit alpha "\020\001\001\001"
b4,rgba,msb,xy      .. file: Applesoft BASIC program data, first line number 8
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2/stego]

```
- Flag: picoCTF{7h3r3_15_n0_5p00n_a9a181eb}
## Notas Adicionales

## Referencias 

