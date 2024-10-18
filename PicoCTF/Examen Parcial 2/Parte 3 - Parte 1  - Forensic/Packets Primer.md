## Descripción 
Download the packet capture file and use packet analysis software to find the flag.

- [Download packet capture](https://artifacts.picoctf.net/c/196/network-dump.flag.pcap)

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2]
└─$ mkdir Packets
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2]
└─$ cd Packets 
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2/Packets]
└─$ wget https://artifacts.picoctf.net/c/196/network-dump.flag.pcap       
--2024-10-16 16:09:21--  https://artifacts.picoctf.net/c/196/network-dump.flag.pcap
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.100, 3.161.55.64, 3.161.55.26, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.100|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 778 [application/octet-stream]
Saving to: ‘network-dump.flag.pcap’

network-dump.flag.pcap                    100%[===================================================================================>]     778  --.-KB/s    in 0s      

2024-10-16 16:09:22 (13.4 MB/s) - ‘network-dump.flag.pcap’ saved [778/778]

                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2/Packets]
└─$ ls
network-dump.flag.pcap
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2/Packets]
└─$ wireshark network-dump.flag.pcap  
```
- En `Wireshark` analizaremos los paquetes y en el paquete 4, en el apartado de la derecha podremos ver la bandera.
- Copiamos el texto en la opción de `As printable text`
```bash
'Îs'¯9EpPÂ@@Ñ³

¾n#('ìÔ·½&¼öu
ÏéehðñÃp i c o C T F { p 4 c k 3 7 _ 5 h 4 r k _ 0 1 b 0 a 0 d 6 }

```
- Flag: picoCTF{p4ck37_5h4rk_01b0a0d6}
## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/286
