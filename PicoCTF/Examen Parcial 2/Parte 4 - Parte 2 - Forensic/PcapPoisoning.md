## Descripción 
How about some hide and seek heh?Download this [file](https://artifacts.picoctf.net/c/373/trace.pcap) and find the flag.

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Parcial2]
└─$ mkdir pCap   
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Parcial2]
└─$ cd pCap 
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Parcial2/pCap]
└─$ wget https://artifacts.picoctf.net/c/373/trace.pcap            
--2024-10-16 16:23:38--  https://artifacts.picoctf.net/c/373/trace.pcap
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.61, 3.161.55.100, 3.161.55.64, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.61|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 106715 (104K) [application/octet-stream]
Saving to: ‘trace.pcap’

trace.pcap                                100%[====================================================================================>] 104.21K  --.-KB/s    in 0.1s    

2024-10-16 16:23:38 (899 KB/s) - ‘trace.pcap’ saved [106715/106715]

                                                                                                                                                                       
┌──(kali㉿kali)-[~/Parcial2/pCap]
└─$ ls
trace.pcap
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Parcial2/pCap]
└─$ wireshark p
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Parcial2/pCap]
└─$ wireshark trace.pcap 
^C
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Parcial2/pCap]
└─$ strings trace.pcap | grep "picoCTF"
picoCTF{P64P_4N4L7S1S_SU55355FUL_4d72dfcc}9~

```

## Notas Adicionales
- El comando `strings` escanea el archivo `trace.pcap` en busca de **cadenas de texto legibles**.
    
- Como el archivo PCAP es binario, normalmente contiene datos en formato de paquetes, pero a menudo también incluye **información legible por humanos** como direcciones IP, nombres de dominio, URL, comandos, o incluso datos de aplicaciones (por ejemplo, información HTTP, parámetros de la solicitud, etc.).
    
- El comando muestra todas las cadenas de texto que puedan ser legibles (secuencias de caracteres alfanuméricos, símbolos, etc.) que están contenidas en los paquetes de red.

## Referencias 
https://play.picoctf.org/practice/challenge/362
https://es.wikipedia.org/wiki/Pcap_(interfaz)#:~:text=El%20pcap%20es%20una%20interfaz,recibe%20el%20nombre%20de%20WinPcap.
https://askubuntu.com/questions/391274/grep-string-from-a-pcap-file
