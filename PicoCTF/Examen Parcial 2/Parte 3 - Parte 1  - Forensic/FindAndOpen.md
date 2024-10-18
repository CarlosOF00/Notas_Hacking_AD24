## Descripción 
Someone might have hidden the password in the trace file.Find the key to unlock [this file](https://artifacts.picoctf.net/c/492/flag.zip). [This tracefile](https://artifacts.picoctf.net/c/492/dump.pcap) might be good to analyze.

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
┌──(kali㉿kali)-[~/Parcial2]
└─$ mkdir findAndOpen  
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2]
└─$ cd findAndOpen 
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2/findAndOpen]
└─$ https://artifacts.picoctf.net/c/492/flag.zip
zsh: no such file or directory: https://artifacts.picoctf.net/c/492/flag.zip
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2/findAndOpen]
└─$ wget https://artifacts.picoctf.net/c/492/flag.zip
--2024-10-16 14:16:17--  https://artifacts.picoctf.net/c/492/flag.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.61, 3.161.55.64, 3.161.55.100, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.61|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 231 [application/octet-stream]
Saving to: ‘flag.zip’

flag.zip                                  100%[===================================================================================>]     231  --.-KB/s    in 0s      

2024-10-16 14:16:18 (178 MB/s) - ‘flag.zip’ saved [231/231]

                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2/findAndOpen]
└─$ wget https://artifacts.picoctf.net/c/492/dump.pcap
--2024-10-16 14:16:35--  https://artifacts.picoctf.net/c/492/dump.pcap
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.61, 3.161.55.64, 3.161.55.100, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.61|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 7413 (7.2K) [application/octet-stream]
Saving to: ‘dump.pcap’

dump.pcap                                 100%[===================================================================================>]   7.24K  --.-KB/s    in 0s      

2024-10-16 14:16:36 (179 MB/s) - ‘dump.pcap’ saved [7413/7413]

                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2/findAndOpen]
└─$ ls
dump.pcap  flag.zip
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2/findAndOpen]
└─$ wireshark dump.pcap   
```
- En `wireshark` debemos analizar los paquetes ya que a la derecha nos proporciona información.
- El paquete 48, vamos a extraer la `Data` y nos iremos a cyberchef y pegaremos el contenido `564768706379427063794230614755676332566a636d56304f69427761574e76513152476531497a4e45524a546b64665445394c5a46383d`.
- En cyberchef usaremos el filtro de `From Hex` y `From Base 64` obteniendo esto: `This is the secret: picoCTF{R34DING_LOKd_` que es la contraseña del archivo .zip
```bash
┌──(kali㉿kali)-[~/Parcial2/findAndOpen]
└─$ wireshark dump.pcap        
^C
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2/findAndOpen]
└─$ unzip flag.zip                                                                                                          
Archive:  flag.zip
[flag.zip] flag password: 
password incorrect--reenter: 
 extracting: flag                    
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2/findAndOpen]
└─$ ls
dump.pcap  flag  flag.zip
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2/findAndOpen]
└─$ cat flag               
picoCTF{R34DING_LOKd_fil56_succ3ss_cbf2ebf6}

```
## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/348
https://gchq.github.io/CyberChef/#recipe=From_Hex('Auto')From_Base64('A-Za-z0-9%2B/%3D',true,false)&input=NTY0NzY4NzA2Mzc5NDI3MDYzNzk0MjMwNjE0NzU1Njc2MzMyNTY2YTYzNmQ1NjMwNGY2OTQyNzc2MTU3NGU3NjUxMzE1MjQ3NjUzMTQ5N2E0ZTQ1NTI0YTU0NmI2NDY2NTQ0NTM5NGM1YTQ2MzgzZA