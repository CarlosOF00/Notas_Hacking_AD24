## Descripción 
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/17/level3.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/17/level3.flag.txt.enc) and the [hash](https://artifacts.picoctf.net/c/17/level3.hash.bin) in the same directory too.There are 7 potential passwords with 1 being correct. You can find these by examining the password checker script.

## Datos de Acceso al Nivel
user: carlosof
password:

## Solución
```bash
carlosof-picoctf@webshell:~$ mktemp -d 
/tmp/tmp.QLJtLlReAk
carlosof-picoctf@webshell:~$ cd /tmp/tmp.QLJtLlReAk/
carlosof-picoctf@webshell:/tmp/tmp.QLJtLlReAk$ wget https://artifacts.picoctf.net/c/17/level3.py
--2024-09-16 18:55:31--  https://artifacts.picoctf.net/c/17/level3.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.16, 3.160.22.128, 3.160.22.92, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.16|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1337 (1.3K) [application/octet-stream]
Saving to: 'level3.py'

level3.py               100%[============================>]   1.31K  --.-KB/s    in 0s      

2024-09-16 18:55:31 (636 MB/s) - 'level3.py' saved [1337/1337]

carlosof-picoctf@webshell:/tmp/tmp.QLJtLlReAk$ wget https://artifacts.picoctf.net/c/17/level3.flag.txt.enc
--2024-09-16 18:55:40--  https://artifacts.picoctf.net/c/17/level3.flag.txt.enc
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.167.183.84, 3.167.183.29, 3.167.183.74, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.167.183.84|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 31 [application/octet-stream]
Saving to: 'level3.flag.txt.enc'

level3.flag.txt.enc     100%[============================>]      31  --.-KB/s    in 0s      

2024-09-16 18:55:41 (9.89 MB/s) - 'level3.flag.txt.enc' saved [31/31]

carlosof-picoctf@webshell:/tmp/tmp.QLJtLlReAk$ wget https://artifacts.picoctf.net/c/17/level3.hash.bin
--2024-09-16 18:56:06--  https://artifacts.picoctf.net/c/17/level3.hash.bin
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.16, 3.160.22.92, 3.160.22.128, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.16|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 16 [application/octet-stream]
Saving to: 'level3.hash.bin'

level3.hash.bin         100%[============================>]      16  --.-KB/s    in 0s      

2024-09-16 18:56:06 (8.66 MB/s) - 'level3.hash.bin' saved [16/16]

carlosof-picoctf@webshell:/tmp/tmp.QLJtLlReAk$ ls
level3.flag.txt.enc  level3.hash.bin  level3.py
carlosof-picoctf@webshell:/tmp/tmp.QLJtLlReAk$ python3 level3.py 
Please enter correct password for flag: hello
That password is incorrect
carlosof-picoctf@webshell:/tmp/tmp.QLJtLlReAk$ cat level3.
level3.flag.txt.enc  level3.hash.bin      level3.py            
carlosof-picoctf@webshell:/tmp/tmp.QLJtLlReAk$ cat level3.flag.txt.enc 
{c'UT
SVPP
carlosof-picoctf@webshell:/tmp/tmp.QLJtLlReAk$ cat level3.hash.bin     
mU]R>W+{carlosof-picoctf@webshell:/tmp/tmp.QLJtLlReAk$ 
carlosof-picoctf@webshell:/tmp/tmp.QLJtLlReAk$ bvi level3.hash.bin

bvi version 1.4.0 Copyright (C) 1996-2014 by Gerhard Buergmann
carlosof-picoctf@webshell:/tmp/tmp.QLJtLlReAk$ nan  
nanddump      nandflipbits  nandtest      nandwrite     nano          
carlosof-picoctf@webshell:/tmp/tmp.QLJtLlReAk$ nan
nanddump      nandflipbits  nandtest      nandwrite     nano          
carlosof-picoctf@webshell:/tmp/tmp.QLJtLlReAk$ nano level3.py  
carlosof-picoctf@webshell:/tmp/tmp.QLJtLlReAk$ pyth
python             python2            python2.7          python3            python3-config     python3.10         python3.10-config  pythran            pythran-config     
carlosof-picoctf@webshell:/tmp/tmp.QLJtLlReAk$ nano level3.py 
	import hashlib

### THIS FUNCTION WILL NOT HELP YOU FIND THE FLAG --LT ########################
def str_xor(secret, key):
    #extend key to secret length
    new_key = key
    i = 0
    while len(new_key) < len(secret):
        new_key = new_key + key[i]
        i = (i + 1) % len(key)        
    return "".join([chr(ord(secret_c) ^ ord(new_key_c)) for (secret_c,new_key_c) in zip(secret,new_key)])
###############################################################################

flag_enc = open('level3.flag.txt.enc', 'rb').read()
correct_pw_hash = open('level3.hash.bin', 'rb').read()


def hash_pw(pw_str):
    pw_bytes = bytearray()
    pw_bytes.extend(pw_str.encode())
    m = hashlib.md5()
    m.update(pw_bytes)
    return m.digest()
    
pos_pw_list = ["f09e", "4dcf", "87ab", "dba8", "752e", "3961", "f159"]


def level_3_pw_check():
    #user_pw = input("Please enter correct password for flag: ")
    for user_pw in pos_pw_list:
        user_pw_hash = hash_pw(user_pw)
        
        if( user_pw_hash == correct_pw_hash ):
            print("Welcome back... your flag, user:")
            decryption = str_xor(flag_enc.decode(), user_pw)
            print(decryption)
            return
        print("That password is incorrect")



level_3_pw_check()


# The strings below are 7 possibilities for the correct password. 
#   (Only 1 is correct)

carlosof-picoctf@webshell:/tmp/tmp.QLJtLlReAk$ python3 level3.py 
That password is incorrect
That password is incorrect
Welcome back... your flag, user:
picoCTF{m45h_fl1ng1ng_cd6ed2eb}
carlosof-picoctf@webshell:/tmp/tmp.QLJtLlReAk$ 
```

## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/247
