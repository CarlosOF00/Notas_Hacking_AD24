## Descripción 
Download this packet capture and find the flag.

- [Download packet capture](https://artifacts.picoctf.net/c/135/capture.flag.pcap)

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
┌──(kali㉿kali)-[~/Parcial2/retosForensic]
└─$ mkdir Eavesdrop  
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Parcial2/retosForensic]
└─$ cd Eavesdrop 
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Parcial2/retosForensic/Eavesdrop]
└─$ wget https://artifacts.picoctf.net/c/135/capture.flag.pcap 
--2024-10-14 19:56:15--  https://artifacts.picoctf.net/c/135/capture.flag.pcap
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.64, 3.161.55.100, 3.161.55.61, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.64|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 7518 (7.3K) [application/octet-stream]
Saving to: ‘capture.flag.pcap’

capture.flag.pcap                         100%[====================================================================================>]   7.34K  --.-KB/s    in 0s      

2024-10-14 19:56:17 (118 MB/s) - ‘capture.flag.pcap’ saved [7518/7518]

                                                                                                                                                                       
┌──(kali㉿kali)-[~/Parcial2/retosForensic/Eavesdrop]
└─$ wireshark capture.flag.pcap                               


```

- Dentro de la herramienta de `WireShark` daremos clic derecho en un paquete `TCP` y daremos clic en la opción de `Follow` y ahí en la opción de `TCP Steam`.
- Encontraremos un mensaje oculto con la siguiente información.

```bash
Hey, how do you decrypt this file again?

You're serious?

Yeah, I'm serious

*sigh* openssl des3 -d -salt -in file.des3 -out file.txt -k supersecretpassword123

Ok, great, thanks.

Let's use Discord next time, it's more secure.

C'mon, no one knows we use this program like this!

Whatever.

Hey.

Yeah?

Could you transfer the file to me again?

Oh great. Ok, over 9002?

Yeah, listening.

Sent it

Got it.

You're unbelievable
```
- Ahora haremos un seguimiento en el paquete que indica el mensaje, con información `9002`
- Ahí encontraremos un mensaje extraño, cambiaremos la opción `Show data as` y cambiaremos el `ASCII` a `Raw`, el resultante lo guardaremos como nos indica el mensaje interceptado, con el nombre `file.des3`
- Abrimos otra terminal, entramos al directorio donde estamos trabajando y hacemos lo siguiente:
```bash
┌──(kali㉿kali)-[~]
└─$ cd Parcial2/retosForensic/Eavesdrop 
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2/retosForensic/Eavesdrop]
└─$ ls
capture.flag.pcap  file.des3
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2/retosForensic/Eavesdrop]
└─$ openssl des3 -d -salt -in file.des3 -out file.txt -k supersecretpassword123
*** WARNING : deprecated key derivation used.
Using -iter or -pbkdf2 would be better.
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2/retosForensic/Eavesdrop]
└─$ ls
capture.flag.pcap  file.des3  file.txt
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2/retosForensic/Eavesdrop]
└─$ cat file.          
cat: file.: No such file or directory
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2/retosForensic/Eavesdrop]
└─$ cat file.txt 
picoCTF{nc_73115_411_0ee7267a}                                                          

```
## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/264
