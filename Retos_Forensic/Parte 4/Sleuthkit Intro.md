
## Descripción 
Download the disk image and use `mmls` on it to find the size of the Linux partition. Connect to the remote checker service to check your answer and get the flag.Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.[Download disk image](https://artifacts.picoctf.net/c/164/disk.img.gz)

Additional details will be available after launching your challenge instance.

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosForensic]
└─$ mkdir /tmp/SleuthkitIntro 
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosForensic]
└─$ cd /tmp/SleuthkitIntro 
                                                                                                                                                                       
┌──(kali㉿kali)-[/tmp/SleuthkitIntro]
└─$ wget https://artifacts.picoctf.net/c/164/disk.img.gz     
--2024-10-13 08:32:05--  https://artifacts.picoctf.net/c/164/disk.img.gz
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.249.21.46, 13.249.21.66, 13.249.21.32, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.249.21.46|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 29714372 (28M) [application/octet-stream]
Saving to: ‘disk.img.gz’

disk.img.gz                               100%[====================================================================================>]  28.34M  5.47MB/s    in 5.4s    

2024-10-13 08:32:11 (5.22 MB/s) - ‘disk.img.gz’ saved [29714372/29714372]

                                                                                                                                                                       
┌──(kali㉿kali)-[/tmp/SleuthkitIntro]
└─$ ls
disk.img.gz
                                                                                                                                                                       
┌──(kali㉿kali)-[/tmp/SleuthkitIntro]
└─$ gzip -d disk.img.gz     
                                                                                                                                                                       
┌──(kali㉿kali)-[/tmp/SleuthkitIntro]
└─$ mmls disk.img             
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000204799   0000202752   Linux (0x83)
                                                                                                                                                                        
┌──(kali㉿kali)-[/tmp/SleuthkitIntro]
└─$ nc saturn.picoctf.net 53725
What is the size of the Linux partition in the given disk image?
Length in sectors: 202752 
202752 
Great work!
picoCTF{mm15_f7w!}

```

## Notas Adicionales
El comando **`mmls`** es una herramienta de **The Sleuth Kit (TSK)**, un conjunto de herramientas de análisis forense digital que se utiliza para examinar discos y sistemas de archivos. En particular, **`mmls`** se emplea para **mostrar la tabla de particiones** de un disco o una imagen de disco.

## Referencias 
https://play.picoctf.org/practice/challenge/301
[Mmls - SleuthKitWiki](https://wiki.sleuthkit.org/index.php?title=Mmls#:~:text=mmls%20displays%20the%20contents%20of%20a%20volume%20system,easy%20to%20use%20%27dd%27%20to%20extract%20the%20partitions.)