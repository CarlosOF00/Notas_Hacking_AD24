## Objetivo 
In RSA, a small `e` value can be problematic, but what about `N`? Can you decrypt this? [values](https://mercury.picoctf.net/static/38f30029ab93478310e906d3d084a4c1/values)

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosCrypto]
└─$ mkdir mindPsQs 
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosCrypto]
└─$ cd min    
cd: no such file or directory: min
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosCrypto]
└─$ cd mindPsQs 
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosCrypto/mindPsQs]
└─$ wget https://mercury.picoctf.net/static/38f30029ab93478310e906d3d084a4c1/values
--2024-10-23 10:04:49--  https://mercury.picoctf.net/static/38f30029ab93478310e906d3d084a4c1/values
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 205 [application/octet-stream]
Saving to: ‘values’

values                                    100%[====================================================================================>]     205  --.-KB/s    in 0s      

2024-10-23 10:04:49 (279 MB/s) - ‘values’ saved [205/205]

                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosCrypto/mindPsQs]
└─$ cat values       
Decrypt my super sick RSA:
c: 240986837130071017759137533082982207147971245672412893755780400885108149004760496
n: 831416828080417866340504968188990032810316193533653516022175784399720141076262857
e: 65537                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosCrypto/mindPsQs]

```


PsAndQs.py
```bash
from Crypto.Util.number import *

c = 240986837130071017759137533082982207147971245672412893755780400885108149004760496
n = 831416828080417866340504968188990032810316193533653516022175784399720141076262857
e = 65537

p =  1593021310640923782355996681284584012117
q =  521911930824021492581321351826927897005221

n == p*q

tn = (p-1)*(q-1)
d = inverse(e,tn)
m = pow(c,d,n)

print(long_to_bytes(m))
```

Consola:
```bash
PS C:\Users\Carlos\Documents\Nueva carpeta> & C:/Users/Carlos/AppData/Local/Programs/Python/Python312/python.exe "c:/Users/Carlos/Documents/Nueva carpeta/PsAndQs.py"
b'picoCTF{sma11_N_n0_g0od_23540368}'
PS C:\Users\Carlos\Documents\Nueva carpeta> 
```

- Flag:
	- picoCTF{sma11_N_n0_g0od_23540368}
## Notas Adicionales


## Referencias 
https://play.picoctf.org/practice/challenge/162
