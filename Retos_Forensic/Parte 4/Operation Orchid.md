
## Descripción 
Download this disk image and find the flag.Note: if you are using the webshell, download and extract the disk image into `/tmp` not your home directory.

- [Download compressed disk image](https://artifacts.picoctf.net/c/214/disk.flag.img.gz)
## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic]
└─$ mkdir operationOrchid
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic]
└─$ cd operationOrchid 
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic/operationOrchid]
└─$ wget https://artifacts.picoctf.net/c/214/disk.flag.img.gz
--2024-10-13 08:05:31--  https://artifacts.picoctf.net/c/214/disk.flag.img.gz
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.249.21.32, 13.249.21.66, 13.249.21.85, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.249.21.32|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 44360927 (42M) [application/octet-stream]
Saving to: ‘disk.flag.img.gz’

disk.flag.img.gz                          100%[===================================================================================>]  42.31M  6.25MB/s    in 7.0s    

2024-10-13 08:05:39 (6.01 MB/s) - ‘disk.flag.img.gz’ saved [44360927/44360927]

                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic/operationOrchid]
└─$ ls    
disk.flag.img.gz
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic/operationOrchid]
└─$ gzip -d disk.flag.img.gz 
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic/operationOrchid]
└─$ mmls disk.flag.img   
DOS Partition Table
Offset Sector: 0
Units are in 512-byte sectors

      Slot      Start        End          Length       Description
000:  Meta      0000000000   0000000000   0000000001   Primary Table (#0)
001:  -------   0000000000   0000002047   0000002048   Unallocated
002:  000:000   0000002048   0000206847   0000204800   Linux (0x83)
003:  000:001   0000206848   0000411647   0000204800   Linux Swap / Solaris x86 (0x82)
004:  000:002   0000411648   0000819199   0000407552   Linux (0x83)
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic/operationOrchid]
└─$ ls /tmp                 
ssh-ymWX3K1uRF5s                                                              systemd-private-32c0dc8af9d74df297282baf8d0a9b2e-polkit.service-5Yt29w
systemd-private-32c0dc8af9d74df297282baf8d0a9b2e-ModemManager.service-EO7dZi  systemd-private-32c0dc8af9d74df297282baf8d0a9b2e-systemd-logind.service-hGXOI3
systemd-private-32c0dc8af9d74df297282baf8d0a9b2e-colord.service-j31QXu        systemd-private-32c0dc8af9d74df297282baf8d0a9b2e-upower.service-909hwv
systemd-private-32c0dc8af9d74df297282baf8d0a9b2e-haveged.service-sxsnrE
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic/operationOrchid]
└─$ mkdir /tmp/foo       
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic/operationOrchid]
└─$ sudo mount disk.flag.img /tmp/foo -o offset=$((411648*512))
[sudo] password for kali: 
Sorry, try again.
[sudo] password for kali: 
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic/operationOrchid]
└─$ cd /tmp/foo       
                                                                                                                                                                      
┌──(kali㉿kali)-[/tmp/foo]
└─$ ls     
bin  boot  dev  etc  home  lib  lost+found  media  mnt  opt  proc  root  run  sbin  srv  swap  sys  tmp  usr  var
                                                                                                                                                                      
┌──(kali㉿kali)-[/tmp/foo]
└─$ cd root         
cd: permission denied: root
                                                                                                                                                                      
┌──(kali㉿kali)-[/tmp/foo]
└─$ sudo su                                                    
┌──(root㉿kali)-[/tmp/foo]
└─# cd root 
                                                                                                                                                                      
┌──(root㉿kali)-[/tmp/foo/root]
└─# ls
flag.txt.enc
                                                                                                                                                                      
┌──(root㉿kali)-[/tmp/foo/root]
└─# cat flag.txt.enc 
Salted__S�+%���+�O��k�ђ(A����c��
                                @]ԣ
L�ޢȤ7� ���؎$�'%                                                                                                                                                                      
┌──(root㉿kali)-[/tmp/foo/root]
└─# cat .ash_history 
touch flag.txt
nano flag.txt 
apk get nano
apk --help
apk add nano
nano flag.txt 
openssl
openssl aes256 -salt -in flag.txt -out flag.txt.enc -k unbreakablepassword1234567
shred -u flag.txt
ls -al
halt
                                                                                                                                                                      
┌──(root㉿kali)-[/tmp/foo/root]
└─# openssl aes256 -d -in flag.txt.enc          
enter AES-256-CBC decryption password:
*** WARNING : deprecated key derivation used.
Using -iter or -pbkdf2 would be better.
bad decrypt
407745F8757F0000:error:1C800064:Provider routines:ossl_cipher_unpadblock:bad decrypt:../providers/implementations/ciphers/ciphercommon_block.c:107:
picoCTF{h4un71ng_p457_1d02081e}                                                                                                                                                                      
┌──(root㉿kali)-[/tmp/foo/root]
└─# 

```
## Notas Adicionales
**`.ash_history`**: Es un archivo que contiene el historial de comandos de un intérprete de comandos, en este caso, **`ash`** (Almquist Shell), que es un shell ligero utilizado en sistemas basados en Unix, como **BusyBox** o algunas distribuciones de Linux embebidas.

## Referencias 
https://play.picoctf.org/practice/challenge/285
[history - Alpine Linux - How to prevent .ash_history from being saved? - Unix & Linux Stack Exchange](https://unix.stackexchange.com/questions/667842/alpine-linux-how-to-prevent-ash-history-from-being-saved)