## Objetivo 
How about some hide and seek heh?Look at this image [here](https://artifacts.picoctf.net/c/236/atbash.jpg).

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosCrypto]
└─$ mkdir hideToSee 
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosCrypto]
└─$ cd hideToSee 
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosCrypto/hideToSee]
└─$ wget https://artifacts.picoctf.net/c/236/atbash.jpg 
--2024-10-23 09:44:30--  https://artifacts.picoctf.net/c/236/atbash.jpg
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.225.62, 3.161.225.60, 3.161.225.3, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.225.62|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 51512 (50K) [application/octet-stream]
Saving to: ‘atbash.jpg’

atbash.jpg                                100%[====================================================================================>]  50.30K  --.-KB/s    in 0s      

2024-10-23 09:44:31 (175 MB/s) - ‘atbash.jpg’ saved [51512/51512]

                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosCrypto/hideToSee]
└─$ ls
atbash.jpg
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosCrypto/hideToSee]
└─$ open atbash.jpg            
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosCrypto/hideToSee]
└─$ steghide extract -sf atbash.jpg 
Enter passphrase: 
wrote extracted data to "encrypted.txt".
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosCrypto/hideToSee]
└─$ ls
atbash.jpg  encrypted.txt
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosCrypto/hideToSee]
└─$ cat encrypted.txt 
krxlXGU{zgyzhs_xizxp_zx751vx6}
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosCrypto/hideToSee]
└─$ 

```

- Ingresamos a la página de `CyberCher` e introducimos el texto que obtuvimos con el cifrado `Atbash Cipper` [Atbash Cipher - CyberChef](https://cyberchef.org/#recipe=Atbash_Cipher()&input=a3J4bFhHVXt6Z3l6aHNfeGl6eHBfeng3NTF2eDZ9ICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgICAgIAo)
- Flag:
	- picoCTF{atbash_crack_ac751ec6}                                                                      
## Notas Adicionales
## Referencias 
https://play.picoctf.org/practice/challenge/351
