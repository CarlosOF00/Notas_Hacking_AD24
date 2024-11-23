## Descripción 
Can you decrypt this message?Decrypt this [message](https://artifacts.picoctf.net/c/160/cipher.txt) using this key "CYLAB".

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
┌──(kali㉿kali)-[~/Parcial3]
└─$ mkdir vigenere     
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Parcial3]
└─$ cd vigenere 
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Parcial3/vigenere]
└─$ wget https://artifacts.picoctf.net/c/160/cipher.txt 
--2024-11-17 07:14:59--  https://artifacts.picoctf.net/c/160/cipher.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.249.21.85, 13.249.21.32, 13.249.21.46, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.249.21.85|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 43 [application/octet-stream]
Saving to: ‘cipher.txt’

cipher.txt                                100%[====================================================================================>]      43  --.-KB/s    in 0s      

2024-11-17 07:14:59 (27.2 MB/s) - ‘cipher.txt’ saved [43/43]

                                                                                                                                                                       
┌──(kali㉿kali)-[~/Parcial3/vigenere]
└─$ cat cipher.txt 
rgnoDVD{O0NU_WQ3_G1G3O3T3_A1AH3S_2951c89f}

```

- Ingresamos a la pagina [Vigenère Decode - CyberChef](https://cyberchef.io/#recipe=Vigen%C3%A8re_Decode('CYLAB')&input=cmdub0RWRHtPME5VX1dRM19HMUczTzNUM19BMUFIM1NfMjk1MWM4OWZ9Cg) y pegamos el mensaje que obtuvimos junto con la clave que se nos dio en la pista y obtenemos la bandear.

- Flag: picoCTF{D0NT_US3_V1G3N3R3_C1PH3R_2951a89h}

## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/316
[Vigenère Decode - CyberChef](https://cyberchef.io/#recipe=Vigen%C3%A8re_Decode('CYLAB')&input=cmdub0RWRHtPME5VX1dRM19HMUczTzNUM19BMUFIM1NfMjk1MWM4OWZ9Cg)
