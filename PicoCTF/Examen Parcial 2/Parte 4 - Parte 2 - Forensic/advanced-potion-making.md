## Descripción 
Ron just found his own copy of advanced potion making, but its been corrupted by some kind of spell. Help him recover it!
## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2]
└─$ mkdir advanced-potion
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2]
└─$ cd advanced-potion 
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2/advanced-potion]
└─$ wget https://artifacts.picoctf.net/picoMini+by+redpwn/Forensics/advanced-potion-making/advanced-potion-making
--2024-10-16 21:05:57--  https://artifacts.picoctf.net/picoMini+by+redpwn/Forensics/advanced-potion-making/advanced-potion-making
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.61, 3.161.55.64, 3.161.55.26, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.61|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 30372 (30K) [binary/octet-stream]
Saving to: ‘advanced-potion-making’

advanced-potion-making                    100%[===================================================================================>]  29.66K  --.-KB/s    in 0.02s   

2024-10-16 21:05:58 (1.35 MB/s) - ‘advanced-potion-making’ saved [30372/30372]

                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2/advanced-potion]
└─$ file advanced-potion-making                                                                                                                
advanced-potion-making: data
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2/advanced-potion]
└─$ hexeditor advanced-potion-making 

```

```bash
00000000  89 50 4E 47  0D 0A 1A 0A   00 00 00 0D  49 48 44 52                                                                                         .PNG........IHDR
```

```
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2/advanced-potion]
└─$ open advanced-potion-making     
```

- En la siguiente pagina (https://www.online-image-editor.com/) podemos aplicar un filtro "lo cambiamos a blanco y negro" y obtenemos la bandera, yo descargue la nueva imagen desde el navegador.

```
┌──(kali㉿kali)-[~/Parcial2/advanced-potion]
└─$ open imagenBN.png          
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2/advanced-potion]
└─$ picoCTF{w1z4rdvy}               
picoCTF{w1z4rdvy}: command not found
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2/advanced-potion]
└─$ picoCTF{w1z4rdry}
picoCTF{w1z4rdry}: command not found

```

## Notas Adicionales


## Referencias 
https://play.picoctf.org/practice/challenge/205
https://www.online-image-editor.com/