## Descripción 
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap). Recover the flag that was pilfered from the network.

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
                                                                                 
┌──(kali㉿kali)-[~/retosForensic]
└─$ mkdir sharkonwire2
                                                                                 
┌──(kali㉿kali)-[~/retosForensic]
└─$ cd sharkonwire2
                                                                                 
┌──(kali㉿kali)-[~/retosForensic/sharkonwire2]
└─$ wget https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap
--2024-10-07 09:32:02--  https://jupiter.challenges.picoctf.org/static/b506393b6f9d53b94011df000c534759/capture.pcap
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 112318 (110K) [application/octet-stream]
Saving to: ‘capture.pcap’

capture.pcap         100%[===================>] 109.69K   484KB/s    in 0.2s    

2024-10-07 09:32:03 (484 KB/s) - ‘capture.pcap’ saved [112318/112318]

                                                                                 
┌──(kali㉿kali)-[~/retosForensic/sharkonwire2]
└─$ ls    
capture.pcap
                                                                                 
┌──(kali㉿kali)-[~/retosForensic/sharkonwire2]
└─$ wireshark capture.pcap 

```
- Con la herramienta `wireshark` podemos filtrar los paquetes `UDP`, y tras un breve análisis nos podemos dar cuenta de que el el `stream 32`  encontramos la palabra `start` y en el `stream60` encontramos la palabra `end`.
- Si analizamos el rango de paquetes que se encuentran, podemos darnos cuenta de que todos comparten la ip `10.0.0.66` , por lo que podemos filtrarlos.
- Una vez filtrados, podemos notar que la información, tiene código ASCII.
```bash
112
105
099
111
067
084
070
123
112
049
076
076
102
051
114
051
100
095
100
097
116
097
095
118
049
097
095
115
116
051
103
048
125
```
- Usando una pagina que nos sirva de conversor, podemos pasar la bandera.
```
picoCTF{p1LLf3r3d_data_v1a_st3g0}
```
## Notas Adicionales

## Referencias 
https://es.rakko.tools/tools/76/#google_vignette
https://play.picoctf.org/practice/challenge/84
https://www.youtube.com/watch?v=e_k9fFqu-BU
