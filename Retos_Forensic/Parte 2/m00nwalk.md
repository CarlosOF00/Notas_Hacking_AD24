## Descripción 
Decode this [message](https://jupiter.challenges.picoctf.org/static/14393e18d98fedbaedbc28896d7ef31a/message.wav) from the moon.

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
┌──(kali㉿kali)-[~/retosForensic]
└─$ mkdir m00nwalk
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic]
└─$ cd m00nwalk     
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic/m00nwalk]
└─$ wget https://jupiter.challenges.picoctf.org/static/14393e18d98fedbaedbc28896d7ef31a/message.wav
--2024-10-06 01:25:00--  https://jupiter.challenges.picoctf.org/static/14393e18d98fedbaedbc28896d7ef31a/message.wav
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 11066998 (11M) [application/octet-stream]
Saving to: ‘message.wav’

message.wav                               100%[===================================================================================>]  10.55M  3.53MB/s    in 3.0s    

2024-10-06 01:25:04 (3.53 MB/s) - ‘message.wav’ saved [11066998/11066998]

┌──(kali㉿kali)-[~/retosForensic/m00nwalk]
└─$ ls
message.wav
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic/m00nwalk]
└─$ open message.wav  
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic/m00nwalk]
└─$ cd /opt    
                                                                                                                                                                      
┌──(kali㉿kali)-[/opt]
└─$ sudo git clone https://github.com/colaclanth/sstv.git     
[sudo] password for kali: 
Cloning into 'sstv'...
remote: Enumerating objects: 221, done.
remote: Counting objects: 100% (59/59), done.
remote: Compressing objects: 100% (10/10), done.
remote: Total 221 (delta 51), reused 49 (delta 49), pack-reused 162 (from 1)
Receiving objects: 100% (221/221), 1.01 MiB | 1.81 MiB/s, done.
Resolving deltas: 100% (139/139), done.

┌──(kali㉿kali)-[/opt]
└─$ cd sstv/   

┌──(kali㉿kali)-[/opt]
└─$ cd sstv/   

┌──(kali㉿kali)-[sstv/]
└─$ python3 setup.py install      

┌──(kali㉿kali)-[~/retosForensic/m00nwalk]
└─$ sstv -d message.wav -o result.png  
[sstv] Searching for calibration header... Found!    
[sstv] Detected SSTV mode Scottie 1
[sstv] Decoding image...                                   [####################################################################################################] 100%
[sstv] Drawing image data...
[sstv] ...Done!
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic/m00nwalk]
└─$ open result.png 


picoCTF{beep_boop_im_in_space}
```
## Notas Adicionales
La herramienta **`sstv`** es un programa utilizado para **enviar y recibir imágenes utilizando el protocolo Slow Scan Television (SSTV)** a través de frecuencias de radio o de otros sistemas de comunicación. Este software es utilizado principalmente en el ámbito de la **radioafición**, pero también puede ser útil en otros contextos en los que se necesite transmitir imágenes a través de enlaces de baja velocidad.

## Referencias 
[Best SSTV Software For Ham Radio SSTV Emission (amateur-radio-wiki.net)](https://www.amateur-radio-wiki.net/sstv-software/#:~:text=Software%20allows%20the%20production%20and%20detection%20of%20signals)
https://play.picoctf.org/practice/challenge/26
