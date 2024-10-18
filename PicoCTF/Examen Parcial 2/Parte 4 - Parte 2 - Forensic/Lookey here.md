## Descripción 
Attackers have hidden information in a very large mass of data in the past, maybe they are still doing it.Download the data [here](https://artifacts.picoctf.net/c/126/anthem.flag.txt).

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2]
└─$ mkdir lookeyHere         
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2]
└─$ 
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2]
└─$ cd lookeyHere 
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2/lookeyHere]
└─$ wget https://artifacts.picoctf.net/c/126/anthem.flag.txt                                        
--2024-10-16 22:13:04--  https://artifacts.picoctf.net/c/126/anthem.flag.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.100, 3.161.55.26, 3.161.55.64, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.100|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 108668 (106K) [application/octet-stream]
Saving to: ‘anthem.flag.txt’

anthem.flag.txt                           100%[===================================================================================>] 106.12K   349KB/s    in 0.3s    

2024-10-16 22:13:05 (349 KB/s) - ‘anthem.flag.txt’ saved [108668/108668]

                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2/lookeyHere]
└─$ ls
anthem.flag.txt
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2/lookeyHere]
└─$ cat anthem.flag.txt | grep "picoCTF"
      we think that the men of picoCTF{gr3p_15_@w3s0m3_2116b979}

```
## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/279
