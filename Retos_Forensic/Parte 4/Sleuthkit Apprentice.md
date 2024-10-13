
## Descripción 
Download this disk image and find the flag.Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

- [Download compressed disk image](https://artifacts.picoctf.net/c/136/disk.flag.img.gz)

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosForensic]
└─$ mkdir Sleuthkit 
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosForensic]
└─$ cd Sleuthkit 
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosForensic/Sleuthkit]
└─$ wget https://artifacts.picoctf.net/c/136/disk.flag.img.gz
--2024-10-13 08:21:45--  https://artifacts.picoctf.net/c/136/disk.flag.img.gz
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.249.21.46, 13.249.21.85, 13.249.21.32, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.249.21.46|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 47534571 (45M) [application/octet-stream]
Saving to: ‘disk.flag.img.gz’

disk.flag.img.gz                          100%[====================================================================================>]  45.33M  5.59MB/s    in 7.9s    

2024-10-13 08:21:53 (5.72 MB/s) - ‘disk.flag.img.gz’ saved [47534571/47534571]

                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosForensic/Sleuthkit]
└─$ gzip -d disk.flag.img.gz 
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosForensic/Sleuthkit]
└─$ mmls disk.flag.img 
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)
003:  000:001   0000206848   0000360447   0000153600   Linux Swap / Solaris x86 (0x82)
004:  000:002   0000360448   0000614399   0000253952   Linux (0x83)
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosForensic/Sleuthkit]
└─$ fls disk.flag.img -o 0000360448
d/d 451:        home
d/d 11: lost+found
d/d 12: boot
d/d 1985:       etc
d/d 1986:       proc
d/d 1987:       dev
d/d 1988:       tmp
d/d 1989:       lib
d/d 1990:       var
d/d 3969:       usr
d/d 3970:       bin
d/d 1991:       sbin
d/d 1992:       media
d/d 1993:       mnt
d/d 1994:       opt
d/d 1995:       root
d/d 1996:       run
d/d 1997:       srv
d/d 1998:       sys
d/d 2358:       swap
V/V 31745:      $OrphanFiles
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosForensic/Sleuthkit]
└─$ fls disk.flag.img -o 0000360448 -r | grep picoCTF
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosForensic/Sleuthkit]
└─$ fls disk.flag.img -o 0000360448 -r | grep flag   
++ r/r * 2082(realloc): flag.txt
++ r/r 2371:    flag.uni.txt
┌──(kali㉿kali)-[~/retosForensic/Sleuthkit]
└─$ icat disk.flag.img -o 360448 2371
picoCTF{by73_5urf3r_3497ae6b}
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosForensic/Sleuthkit]
└─$ 

```
## Notas Adicionales
- **`fls`**: Esta es la herramienta que se usa para listar el contenido de un sistema de archivos en un disco o una imagen de disco.
- **`disk.flag.img`**: Es el archivo de imagen del disco que se va a analizar. Podría ser una copia forense de un disco duro.
- **`-o 0000360448`**: Especifica un **desplazamiento** en el que comienza la lectura del sistema de archivos. Esto es útil cuando el sistema de archivos no está en el principio de la imagen del disco o cuando hay una tabla de particiones antes de la partición del sistema de archivos.

## Referencias 
https://play.picoctf.org/practice/challenge/300
[FLS(1) manual page (sleuthkit.org)](https://sleuthkit.org/sleuthkit/man/fls.html)
