## Descripción 
I just recently learnt about the SRA public key cryptosystem... or wait, was it supposed to be RSA? Hmmm, I should probably check...Connect to the program on our server: `nc saturn.picoctf.net 51696`Download the program: [chal.py](https://artifacts.picoctf.net/c/296/chal.py)

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
┌──(kali㉿kali)-[~/Parcial3]
└─$ mkdir SRA     
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial3]
└─$ cd SRA   
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial3/SRA]
└─$ wget https://artifacts.picoctf.net/c/296/chal.py                                    
--2024-11-17 08:37:55--  https://artifacts.picoctf.net/c/296/chal.py
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.249.21.66, 13.249.21.32, 13.249.21.46, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.249.21.66|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 630 [application/octet-stream]
Saving to: ‘chal.py’

chal.py                                   100%[===================================================================================>]     630  --.-KB/s    in 0s      

2024-11-17 08:37:56 (6.01 MB/s) - ‘chal.py’ saved [630/630]

┌──(kali㉿kali)-[~/Parcial3/SRA]
└─$ nc saturn.picoctf.net 51696
anger = 572747942986218146452782797706439814452786452526996159965321000607601243817
envy = 53606626838161026146285316276248637628398831644270242699127068736264760286393
vainglory?
> ^C
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial3/SRA]
└─$ cat chal.py    
from Crypto.Util.number import getPrime, inverse, bytes_to_long
from string import ascii_letters, digits
from random import choice

pride = "".join(choice(ascii_letters + digits) for _ in range(16))
gluttony = getPrime(128)
greed = getPrime(128)
lust = gluttony * greed
sloth = 65537
envy = inverse(sloth, (gluttony - 1) * (greed - 1))

anger = pow(bytes_to_long(pride.encode()), sloth, lust)

print(f"{anger = }")
print(f"{envy = }")

print("vainglory?")
vainglory = input("> ").strip()

if vainglory == pride:
    print("Conquered!")
    with open("/challenge/flag.txt") as f:
        print(f.read())
else:
    print("Hubris!")
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial3/SRA]
└─$ 

```
- Creamos este codigo en python  para la resolucion del reto:
```bash
from pwn import *
import primefac
from itertools import combinations
from Crypto.Util.number import long_to_bytes

#Funcion que genera todas las sublistas
def sub_lists(l):
        #inicializando lista vacia
        comb = []
        #Iterando hasta la longitud de la lista
        for i in range(1, len(l)+1):
                #Generando una sublista
                comb += [list(j) for j in combinations(l, i)]
        #Regresando lista
        return comb

def divisors(phi):
        print("Dame los divisores de", phi-1)
        return(eval(input()))

#Conexion con el servidor
r = remote('saturn.picoctf.net',60657)

#Obtener el texto cifrado
r.recvuntil("anger =")

ciphertext = int(r.recvline())

#Obtener d
r.recvuntil("envy =")
d = int(r.recvline())
print("cipher=", ciphertext)
print("d=", d)
print(r.recvuntil("vainglory?"))
r.recvline()

#Desde d es e^-1 mod (p-1)*(q-1), d*e=k*(p-1)*(q-1)+1
#Asi (p-1)*(q-1)*k = d*e-1
factors = divisors(d*65537)
combos = sub_lists(factors)
primes = set()
#Intenta todas las posibles sublistas de factores para los factores de (p-1)
for l in combos:
        product = 1
        #Multiplicarlos entre ellos para obtener p-1
        for k in l:
                product = product * k
        #Si la longitud correcta y sumar 1 da un numero primo, entonces tal vez
        if product.bit_length()==128 and primefac.isprime(product+1):
                primes.add(product+1)
print(primes)

primelist = list(primes)
#Intenta todos los posibles pares de primos
for p in primelist:
        for q in primelist:
                n=p*q
                #Decodificar con el posible n
                plain = pow(ciphertext, d, n)
                try:
                        plaintext = long_to_bytes(plain)
                        #Ver si corresponde al texto y de ser asi, intentarlo
                        print(plaintext.decode())
                        r.sendline(plaintext.decode())
                        print(r.recvline())
                        print(r.recvline())
                        print(r.recvline())
                except:
                        continue
```
Para encontrar los valores divisibles, entraremos a esta pagina [dcode.fr](https://www.dcode.fr/prime-factors-decomposition) y antes de dar en factorizar, debemos seleccionar la opción `Comman Separate Factors`, los copiamos y los agregamos entre corchetes.

```bash
PS C:\Users\Carlos\Documents\Nueva carpeta> & C:/Users/Carlos/AppData/Local/Programs/Python/Python312/python.exe "c:/Users/Carlos/Documents/Nueva carpeta/SRA.py"
[x] Opening connection to saturn.picoctf.net on port 60657
[x] Opening connection to saturn.picoctf.net on port 60657: Trying 13.59.203.175
[+] Opening connection to saturn.picoctf.net on port 60657: Done
c:\Users\Carlos\Documents\Nueva carpeta\SRA.py:25: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  r.recvuntil("anger =")
c:\Users\Carlos\Documents\Nueva carpeta\SRA.py:28: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  r.recvuntil("envy =")
cipher= 58661340024736355220320353481626167464995338204468613230801662237813339875870
d= 12122962015832405630684480160071438527716155734467506243508113875808657159969
c:\Users\Carlos\Documents\Nueva carpeta\SRA.py:32: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  print(r.recvuntil("vainglory?"))
b'vainglory?'
Dame los divisores de 794502561631608367818168776250601866790933698369796956680791259078871964292888352
[2, 2, 2, 2, 2, 3, 3, 3, 3, 11, 103, 137, 521, 823, 1676837, 62247313, 1800968773, 73744699073357773, 332218506257603731362641983] 
{306349214213268601075600098024895232707, 206745735526634177950123924847841341617, 290444057942993702426981616093289494953, 286823035952550205101136261354110275977}
e5z9Vh1eyR0jm9kW
c:\Users\Carlos\Documents\Nueva carpeta\SRA.py:60: BytesWarning: Text is not bytes; assuming ASCII, no guarantees. See https://docs.pwntools.com/#bytes
  r.sendline(plaintext.decode())
b'> e5z9Vh1eyR0jm9kW\r\n'
b'Conquered!\r\n'
b'picoCTF{7h053_51n5_4r3_n0_m0r3_dd808298}\r\n'
e5z9Vh1eyR0jm9kW
[*] Closed connection to saturn.picoctf.net port 60657
```


- Flag: picoCTF{7h053_51n5_4r3_n0_m0r3_dd808298}
## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/379
https://www.dcode.fr/prime-factors-decomposition
https://gist.github.com/charles-l/fe42ebf5dd5eb70a6c74d71436732e9a