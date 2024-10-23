## Objetivo 
Let's decrypt this: [ciphertext](https://jupiter.challenges.picoctf.org/static/d21037ad23ed84cfff20a84768a0f2b2/ciphertext)? Something seems a bit small.

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosCrypto]
└─$ mkdir miniRsa  
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosCrypto]
└─$ cd miniRsa    
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosCrypto/miniRsa]
└─$ wget https://jupiter.challenges.picoctf.org/static/d21037ad23ed84cfff20a84768a0f2b2/ciphertext
--2024-10-22 21:47:33--  https://jupiter.challenges.picoctf.org/static/d21037ad23ed84cfff20a84768a0f2b2/ciphertext
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 884 [application/octet-stream]
Saving to: ‘ciphertext’

ciphertext                                100%[====================================================================================>]     884  --.-KB/s    in 0s      

2024-10-22 21:47:33 (11.6 MB/s) - ‘ciphertext’ saved [884/884]

                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosCrypto/miniRsa]
└─$ cat ciphertext 

N: 29331922499794985782735976045591164936683059380558950386560160105740343201513369939006307531165922708949619162698623675349030430859547825708994708321803705309459438099340427770580064400911431856656901982789948285309956111848686906152664473350940486507451771223435835260168971210087470894448460745593956840586530527915802541450092946574694809584880896601317519794442862977471129319781313161842056501715040555964011899589002863730868679527184420789010551475067862907739054966183120621407246398518098981106431219207697870293412176440482900183550467375190239898455201170831410460483829448603477361305838743852756938687673
e: 3

ciphertext (c): 2205316413931134031074603746928247799030155221252519872650073010782049179856976080512716237308882294226369300412719995904064931819531456392957957122459640736424089744772221933500860936331459280832211445548332429338572369823704784625368933 

```

Python:
```bash
from gmpy2 import *

gmpy2.get_context().precision = 2048

n = 29331922499794985782735976045591164936683059380558950386560160105740343201513369939006307531165922708949619162698623675349030430859547825708994708321803705309459438099340427770580064400911431856656901982789948285309956111848686906152664473350940486507451771223435835260168971210087470894448460745593956840586530527915802541450092946574694809584880896601317519794442862977471129319781313161842056501715040555964011899589002863730868679527184420789010551475067862907739054966183120621407246398518098981106431219207697870293412176440482900183550467375190239898455201170831410460483829448603477361305838743852756938687673

e = 3

c = 2205316413931134031074603746928247799030155221252519872650073010782049179856976080512716237308882294226369300412719995904064931819531456392957957122459640736424089744772221933500860936331459280832211445548332429338572369823704784625368933

  

for t in range(10000):

    m, r = iroot(t*n + c , e)

    if r :

        print('Encontre t : ' + str(t))

        print('Flag       : ' + str(bytes.fromhex(hex(m)[2:]).decode()))
```

Terminal
```bash
PS C:\Users\Carlos\Documents\Nueva carpeta> & C:/Users/Carlos/AppData/Local/Programs/Python/Python312/python.exe "c:/Users/Carlos/Documents/Nueva carpeta/miniRSA.py"
Encontre t : 0
Flag       : picoCTF{n33d_a_lArg3r_e_ccaa7776}
PS C:\Users\Carlos\Documents\Nueva carpeta> 
```
## Notas Adicionales


## Referencias 
https://play.picoctf.org/practice/challenge/73