## Descripción 
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap). Recover the flag.

## Datos de Acceso al Nivel
user: carlosof
password:

## Solución
```bash
┌──(kali㉿kali)-[~/retosForensic]
└─$ mkdir sharkonwire1 
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic]
└─$ cd sharkonwire1 
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic/sharkonwire1]
└─$ wget https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap
--2024-09-29 01:06:21--  https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 239455 (234K) [application/octet-stream]
Saving to: ‘capture.pcap’

capture.pcap                              100%[===================================================================================>] 233.84K   974KB/s    in 0.2s    

2024-09-29 01:06:21 (974 KB/s) - ‘capture.pcap’ saved [239455/239455]

                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic/sharkonwire1]
└─$ file capture.pcap 
capture.pcap: pcap capture file, microsecond ts (little-endian) - version 2.4 (Ethernet, capture length 262144)
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic/sharkonwire1]
└─$ 

```
- Abrimos una herramienta llamada wireshark, dentro de la herramienta abrimos el archivo que descargamos.
- Seguimos los paquetes UTP.
- Navegamos por los streams hasta localizar la bandera.
- picoCTF{StaT31355_636f6e6e}

## Notas Adicionales
PCAP (Packet Capture) es un formato de archivo utilizado para almacenar datos de red capturados durante el tráfico de una red. Es ampliamente utilizado por herramientas de análisis de redes, como Wireshark, para capturar y analizar paquetes de datos que circulan por una red.

Los archivos PCAP contienen información sobre los paquetes, como las direcciones IP de origen y destino, protocolos utilizados, puertos, y los datos del paquete en sí.

## Referencias 
https://play.picoctf.org/practice/challenge/30?page=1&search=shark%20on%20wir
[Pcap (interfaz) - Wikipedia, la enciclopedia libre](https://es.wikipedia.org/wiki/Pcap_(interfaz))