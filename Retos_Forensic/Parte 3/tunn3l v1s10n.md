## Descripción 
We found this [file](https://mercury.picoctf.net/static/01be2b38ba97802285a451b94505ea75/tunn3l_v1s10n). Recover the flag.

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
                                                                                 
┌──(kali㉿kali)-[~/retosForensic]
└─$ mkdir tunnel_vision 
                                                                                 
┌──(kali㉿kali)-[~/retosForensic]
└─$ cd tunnel_vision            
                                                                                 
┌──(kali㉿kali)-[~/retosForensic/tunnel_vision]
└─$ wget https://mercury.picoctf.net/static/01be2b38ba97802285a451b94505ea75/tunn3l_v1s10n
--2024-10-08 20:57:03--  https://mercury.picoctf.net/static/01be2b38ba97802285a451b94505ea75/tunn3l_v1s10n
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2893454 (2.8M) [application/octet-stream]
Saving to: ‘tunn3l_v1s10n’

tunn3l_v1s10n        100%[===================>]   2.76M   823KB/s    in 3.4s    

2024-10-08 20:57:07 (823 KB/s) - ‘tunn3l_v1s10n’ saved [2893454/2893454]

                                                                                 
┌──(kali㉿kali)-[~/retosForensic/tunnel_vision]
└─$ ls -la
total 2836
drwxrwxr-x  2 kali kali    4096 Oct  8 20:57 .
drwxrwxr-x 13 kali kali    4096 Oct  8 20:56 ..
-rw-rw-r--  1 kali kali 2893454 Mar 15  2021 tunn3l_v1s10n
                                                                                 
┌──(kali㉿kali)-[~/retosForensic/tunnel_vision]
└─$ file tunn3l_v1s10n 
tunn3l_v1s10n: data
                                                                                 
┌──(kali㉿kali)-[~/retosForensic/tunnel_vision]
└─$ hexeditor tunn3l_v1s10n 
                                                                                 
┌──(kali㉿kali)-[~/retosForensic/tunnel_vision]
└─$ mv tunn3l_v1s10n tunn3l_v1s10n.bmp
                                                                                 
┌──(kali㉿kali)-[~/retosForensic/tunnel_vision]
└─$ hexeditor tunn3l_v1s10n.bmp  
```
- Así debe de quedar el hexadecimal
```bash
00000000  42 4D 8E 26  2C 00 00 00   00 00 28 00  00 00 28 00                                                                                          BM.&,.....(...(.
00000010  00 00 6E 04  00 00 40 04   00 00 01 00  18 00 00 00                                                                                          ..n...@.........
```

```bash
┌──(kali㉿kali)-[~/retosForensic/tunnel_vision]
└─$ exiftool tunn3l_v1s10n.bmp 
ExifTool Version Number         : 12.76
File Name                       : tunn3l_v1s10n.bmp
Directory                       : .
File Size                       : 2.9 MB
File Modification Date/Time     : 2024:10:08 22:36:20-06:00
File Access Date/Time           : 2024:10:08 22:36:25-06:00
File Inode Change Date/Time     : 2024:10:08 22:36:20-06:00
File Permissions                : -rw-rw-r--
File Type                       : BMP
File Type Extension             : bmp
MIME Type                       : image/bmp
BMP Version                     : Windows V3
Image Width                     : 1134
Image Height                    : 1088
Planes                          : 1
Bit Depth                       : 24
Compression                     : None
Image Length                    : 2893400
Pixels Per Meter X              : 5669
Pixels Per Meter Y              : 5669
Num Colors                      : Use BitDepth
Num Important Colors            : All
Image Size                      : 1134x1088
Megapixels                      : 1.2
                                                                                 
┌──(kali㉿kali)-[~/retosForensic/tunnel_vision]
└─$ open tunn3l_v1s10n.bmp    
                                                                                 
┌──(kali㉿kali)-[~/retosForensic/tunnel_vision]
└─$ picoCTF{qu1t3_a_v13w_2020}
picoCTF{qu1t3_a_v13w_2020}: command not found
                                                                                 
┌──(kali㉿kali)-[~/retosForensic/tunnel_vision]
└─$ 

```
## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/112

