
## Descripción 
Download this disk image, find the key and log into the remote machine.Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

Additional details will be available after launching your challenge instance.

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic]
└─$ mkdir operationOni
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic]
└─$ cd operationOni 
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic/operationOni]
└─$ wget https://artifacts.picoctf.net/c/69/disk.img.gz
--2024-10-13 07:53:50--  https://artifacts.picoctf.net/c/69/disk.img.gz
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.249.21.66, 13.249.21.32, 13.249.21.46, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.249.21.66|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 48132743 (46M) [application/octet-stream]
Saving to: ‘disk.img.gz’

disk.img.gz                               100%[===================================================================================>]  45.90M  6.33MB/s    in 7.7s    

2024-10-13 07:53:58 (5.97 MB/s) - ‘disk.img.gz’ saved [48132743/48132743]

                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic/operationOni]
└─$ gzip -d disk.img.gz                         

                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic/operationOni]
└─$ 
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic/operationOni]
└─$ mmls disk.img     
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)
003:  000:001   0000206848   0000471039   0000264192   Linux (0x83)
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic/operationOni]
└─$ fls -o 205848 disk.img                                     
Cannot determine file system type
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic/operationOni]
└─$ fls -o 206848 disk.img
d/d 458:        home
d/d 11: lost+found
d/d 12: boot
d/d 13: etc
d/d 79: proc
d/d 80: dev
d/d 81: tmp
d/d 82: lib
d/d 85: var
d/d 94: usr
d/d 104:        bin
d/d 118:        sbin
d/d 464:        media
d/d 468:        mnt
d/d 469:        opt
d/d 470:        root
d/d 471:        run
d/d 473:        srv
d/d 474:        sys
V/V 33049:      $OrphanFiles
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic/operationOni]
└─$ fls -o 206848 disk.img 470
r/r 2344:       .ash_history
d/d 3916:       .ssh
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic/operationOni]
└─$ fls -o 206848 disk.img 3916
r/r 2345:       id_ed25519
r/r 2346:       id_ed25519.pub
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic/operationOni]
└─$ icat -o 206848 disk.img 2345
-----BEGIN OPENSSH PRIVATE KEY-----
b3BlbnNzaC1rZXktdjEAAAAABG5vbmUAAAAEbm9uZQAAAAAAAAABAAAAMwAAAAtzc2gtZW
QyNTUxOQAAACBgrXe4bKNhOzkCLWOmk4zDMimW9RVZngX51Y8h3BmKLAAAAJgxpYKDMaWC
gwAAAAtzc2gtZWQyNTUxOQAAACBgrXe4bKNhOzkCLWOmk4zDMimW9RVZngX51Y8h3BmKLA
AAAECItu0F8DIjWxTp+KeMDvX1lQwYtUvP2SfSVOfMOChxYGCtd7hso2E7OQItY6aTjMMy
KZb1FVmeBfnVjyHcGYosAAAADnJvb3RAbG9jYWxob3N0AQIDBAUGBw==
-----END OPENSSH PRIVATE KEY-----
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic/operationOni]
└─$ icat -o 206848 disk.img 2345 > key_file 
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic/operationOni]
└─$ chmod 400 key_file 
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic/operationOni]
└─$ ls -la
total 235536
drwxrwxr-x  2 kali kali      4096 Oct 13 07:57 .
drwxrwxr-x 18 kali kali      4096 Oct 13 07:53 ..
-rw-rw-r--  1 kali kali 241172480 Aug  4  2023 disk.img
-r--------  1 kali kali       411 Oct 13 07:57 key_file
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic/operationOni]
└─$ ssh -i key_file -p 57695 ctf-player@saturn.picoctf.net
The authenticity of host '[saturn.picoctf.net]:57695 ([13.59.203.175]:57695)' can't be established.
ED25519 key fingerprint is SHA256:XBSvB1lk28EctsAVdKJtsl0A7C5bonqPrvHCYH8aEy4.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[saturn.picoctf.net]:57695' (ED25519) to the list of known hosts.
Welcome to Ubuntu 20.04.5 LTS (GNU/Linux 6.5.0-1023-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.

The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

ctf-player@challenge:~$ ls
flag.txt
ctf-player@challenge:~$ cat flag.txt 
picoCTF{k3y_5l3u7h_339601ed}ctf-player@challenge:~$ 

```
## Notas Adicionales
El comando **`icat`** es una herramienta del conjunto **The Sleuth Kit (TSK)** que se utiliza para **extraer el contenido de un archivo** a partir de una imagen de disco o una partición. Su función principal es extraer archivos de sistemas de archivos complejos, como los que se encuentran en discos duros, imágenes de disco o particiones específicas, a partir de la información contenida en la imagen del disco.

## Referencias 
https://play.picoctf.org/practice/challenge/284
[ICAT(1) manual page (sleuthkit.org)](https://sleuthkit.org/sleuthkit/man/icat.html)