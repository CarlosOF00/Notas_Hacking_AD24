## Objetivo 
We found this weird message being passed around on the servers, we think we have a working decryption scheme.Download the message [here](https://artifacts.picoctf.net/c/129/message.txt).Take each number mod 37 and map it to the following character set: 0-25 is the alphabet (uppercase), 26-35 are the decimal digits, and 36 is an underscore.Wrap your decrypted message in the picoCTF flag format (i.e. `picoCTF{decrypted_message}`)

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosCrypto]
└─$ mkdir basic-mod1
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosCrypto]
└─$ cd basic-mod1 
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosCrypto/basic-mod1]
└─$ wget https://artifacts.picoctf.net/c/129/message.txt                                          
--2024-10-23 09:25:11--  https://artifacts.picoctf.net/c/129/message.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.225.60, 3.161.225.62, 3.161.225.3, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.225.60|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 86 [application/octet-stream]
Saving to: ‘message.txt’

message.txt                               100%[====================================================================================>]      86  --.-KB/s    in 0s      

2024-10-23 09:25:12 (58.8 MB/s) - ‘message.txt’ saved [86/86]

                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosCrypto/basic-mod1]
└─$ ls
message.txt
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosCrypto/basic-mod1]
└─$ cat message.txt 
350 63 353 198 114 369 346 184 202 322 94 235 114 110 185 188 225 212 366 374 261 213                                                                                                                                                                        
┌──(kali㉿kali)-[~/retosCrypto/basic-mod1]
└─$ nano script.py                         
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosCrypto/basic-mod1]
└─$ python3 script.py               
picoCTF{R0UND_N_R0UND_ADD17EC2}

```

Script.py
```bash
datos = open("message.txt").read().split()

flag = ""

for n in datos:
        r = int(n) % 37
        if(r >= 0 and r <= 25):
                s = chr(r+65)
                flag += s
        elif(r >= 26 and r <= 35):
                s = chr(r+22)
                flag += s
        else:
                s = "_"
                flag += s

print("picoCTF{"+flag+"}")

```

- Flag:
	  picoCTF{R0UND_N_R0UND_ADD17EC2}
## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/253
