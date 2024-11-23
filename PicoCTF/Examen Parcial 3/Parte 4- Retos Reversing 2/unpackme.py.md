## Descripción 
Can you get the flag?Reverse engineer this [Python program](https://artifacts.picoctf.net/c/49/unpackme.flag.py).

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial3]
└─$ mkdir unpackme-py
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial3]
└─$ cd unpackme-py 
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial3/unpackme-py]
└─$ wget                                                 
wget: missing URL
Usage: wget [OPTION]... [URL]...

Try `wget --help' for more options.
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial3/unpackme-py]
└─$ wget https://artifacts.picoctf.net/c/49/unpackme.flag.py
--2024-11-17 16:45:08--  https://artifacts.picoctf.net/c/49/unpackme.flag.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.249.21.85, 13.249.21.46, 13.249.21.66, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.249.21.85|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 527 [application/octet-stream]
Saving to: ‘unpackme.flag.py’

unpackme.flag.py                          100%[===================================================================================>]     527  --.-KB/s    in 0s      

2024-11-17 16:45:09 (11.5 MB/s) - ‘unpackme.flag.py’ saved [527/527]

                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial3/unpackme-py]
└─$ ls    
unpackme.flag.py
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial3/unpackme-py]
└─$ python3 unpackme.flag.py 
What's the password? 1234
That password is incorrect.
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial3/unpackme-py]
└─$ cat unpackme.flag.py 
import base64
from cryptography.fernet import Fernet



payload = b'gAAAAABkzWGSzE6VQNTzvRXOXekQeW4CY6NiRkzeImo9LuYBHAYw_hagTJLJL0c-kmNsjY33IUbU2IWlqxA3Fpp9S7RxNkiwMDZgLmRlI9-lGAEW-_i72RSDvylNR3QkpJW2JxubjLUC5VwoVgH62wxDuYu1rRD5KadwTADdABqsx2MkY6fKNTMCYY09Se6yjtRBftfTJUL-LKz2bwgXNd6O-WpbfXEMvCv3gNQ7sW4pgUnb-gDVZvrLNrug_1YFaIe3yKr0Awo0HIN3XMdZYpSE1c9P4G0sMQ=='

key_str = 'correctstaplecorrectstaplecorrec'
key_base64 = base64.b64encode(key_str.encode())
f = Fernet(key_base64)
plain = f.decrypt(payload)
exec(plain.decode())
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial3/unpackme-py]
└─$ nano unpackme.flag.py 
```
- Modificación del código para resolución del reto (solo hay que agregar un `print`)
```bash
import base64
from cryptography.fernet import Fernet

payload = b'gAAAAABkzWGSzE6VQNTzvRXOXekQeW4CY6NiRkzeImo9LuYBHAYw_hagTJLJL0c-kmNsjY33IUbU2IWlqxA3Fpp9S7RxNkiwMDZgLmRlI9-lGAEW-_i72RSDvylNR3QkpJW2JxubjLUC5VwoVgH62wxDu>

key_str = 'correctstaplecorrectstaplecorrec'
key_base64 = base64.b64encode(key_str.encode())
f = Fernet(key_base64)
plain = f.decrypt(payload)
print(plain.decode()) #Aqui se agrega el print
```
- Volvemos a ejecutar el código.
```
┌──(kali㉿kali)-[~/Parcial3/unpackme-py]
└─$ python3 unpackme.flag.py

pw = input('What\'s the password? ')

if pw == 'batteryhorse':
  print('picoCTF{175_chr157m45_cd82f94c}')
else:
  print('That password is incorrect.')

```

- Flag: picoCTF{175_chr157m45_cd82f94c}

## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/314
