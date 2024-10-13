
## Descripción 
Use `srch_strings` from the sleuthkit and some terminal-fu to find a flag in this disk image: [dds1-alpine.flag.img.gz](https://mercury.picoctf.net/static/ac394d24f88e51a09cc909687cf6d853/dds1-alpine.flag.img.gz)

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic]
└─$ mkdir Disk    
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic]
└─$ cd Disk   
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic/Disk]
└─$ wget https://mercury.picoctf.net/static/ac394d24f88e51a09cc909687cf6d853/dds1-alpine.flag.img.gz
--2024-10-12 23:23:35--  https://mercury.picoctf.net/static/ac394d24f88e51a09cc909687cf6d853/dds1-alpine.flag.img.gz
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 29768910 (28M) [application/octet-stream]
Saving to: ‘dds1-alpine.flag.img.gz’

dds1-alpine.flag.img.gz                   100%[===================================================================================>]  28.39M  3.75MB/s    in 17s     

2024-10-12 23:23:53 (1.65 MB/s) - ‘dds1-alpine.flag.img.gz’ saved [29768910/29768910]
┌──(kali㉿kali)-[~/retosForensic/Disk]
└─$ gzip -d dds*.gz
┌──(kali㉿kali)-[~/retosForensic/Disk]
└─$ ls
dds1-alpine.flag.img
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic/Disk]
└─$ file dds1-alpine.flag.img                                  
dds1-alpine.flag.img: DOS/MBR boot sector; partition 1 : ID=0x83, active, start-CHS (0x0,32,33), end-CHS (0x10,81,1), startsector 2048, 260096 sectors
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic/Disk]
└─$ open dds1-alpine.flag.img 
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic/Disk]
└─$ strings dds1-alpine.flag.img | grep picoCTF
  SAY picoCTF{f0r3ns1c4t0r_n30phyt3_dcbf5942}

```
## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/113
https://mercury.picoctf.net/static/ac394d24f88e51a09cc909687cf6d853/dds1-alpine.flag.img.gz