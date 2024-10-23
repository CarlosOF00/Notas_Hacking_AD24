## Descripción 
The one time pad can be cryptographically secure, but not when you know the key. Can you solve this? We've given you the encrypted flag, key, and a table to help `UFJKXQZQUNB` with the key of `SOLVECRYPTO`. Can you use this [table](https://jupiter.challenges.picoctf.org/static/1fd21547c154c678d2dab145c29f1d79/table.txt) to solve it?.

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosCrypto]
└─$ mkdir easy1      
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosCrypto]
└─$ cd easy1     
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosCrypto/easy1]
└─$ wget https://jupiter.challenges.picoctf.org/static/1fd21547c154c678d2dab145c29f1d79/table.txt      
--2024-10-10 23:12:16--  https://jupiter.challenges.picoctf.org/static/1fd21547c154c678d2dab145c29f1d79/table.txt
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1571 (1.5K) [application/octet-stream]
Saving to: ‘table.txt’

table.txt                                 100%[====================================================================================>]   1.53K  --.-KB/s    in 0s      

2024-10-10 23:12:16 (37.1 MB/s) - ‘table.txt’ saved [1571/1571]

                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosCrypto/easy1]
└─$ cat table.txt       
    A B C D E F G H I J K L M N O P Q R S T U V W X Y Z 
   +----------------------------------------------------
A | A B C D E F G H I J K L M N O P Q R S T U V W X Y Z
B | B C D E F G H I J K L M N O P Q R S T U V W X Y Z A
C | C D E F G H I J K L M N O P Q R S T U V W X Y Z A B
D | D E F G H I J K L M N O P Q R S T U V W X Y Z A B C
E | E F G H I J K L M N O P Q R S T U V W X Y Z A B C D
F | F G H I J K L M N O P Q R S T U V W X Y Z A B C D E
G | G H I J K L M N O P Q R S T U V W X Y Z A B C D E F
H | H I J K L M N O P Q R S T U V W X Y Z A B C D E F G
I | I J K L M N O P Q R S T U V W X Y Z A B C D E F G H
J | J K L M N O P Q R S T U V W X Y Z A B C D E F G H I
K | K L M N O P Q R S T U V W X Y Z A B C D E F G H I J
L | L M N O P Q R S T U V W X Y Z A B C D E F G H I J K
M | M N O P Q R S T U V W X Y Z A B C D E F G H I J K L
N | N O P Q R S T U V W X Y Z A B C D E F G H I J K L M
O | O P Q R S T U V W X Y Z A B C D E F G H I J K L M N
P | P Q R S T U V W X Y Z A B C D E F G H I J K L M N O
Q | Q R S T U V W X Y Z A B C D E F G H I J K L M N O P
R | R S T U V W X Y Z A B C D E F G H I J K L M N O P Q
S | S T U V W X Y Z A B C D E F G H I J K L M N O P Q R
T | T U V W X Y Z A B C D E F G H I J K L M N O P Q R S
U | U V W X Y Z A B C D E F G H I J K L M N O P Q R S T
V | V W X Y Z A B C D E F G H I J K L M N O P Q R S T U
W | W X Y Z A B C D E F G H I J K L M N O P Q R S T U V
X | X Y Z A B C D E F G H I J K L M N O P Q R S T U V W
Y | Y Z A B C D E F G H I J K L M N O P Q R S T U V W X
Z | Z A B C D E F G H I J K L M N O P Q R S T U V W X Y

                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosCrypto/easy1]
└─$ 

```
- Si ingresamos a la pagina [Descifrar un Mensaje - Identificador de Cifrado o Código Online (dcode.fr)](https://www.dcode.fr/identificador-cifrado) nos podemos dar cuenta de que el mensaje esta cifrado en Vigenere.
- Entramos a CyberChef y decodificamos el mensaje, obteniendo:
	- CRYPTOISFUN
- Siguiendo las pistas, podemos finalizar escribiendo lo obtenido entre picoCTF{}
- Flag: picoCTF{CRYPTOISFUN}

## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/43?category=2&page=1&search=eas
[Descifrar un Mensaje - Identificador de Cifrado o Código Online (dcode.fr)](https://www.dcode.fr/identificador-cifrado)
[Vigenère Decode - CyberChef](https://cyberchef.org/#recipe=Vigen%C3%A8re_Decode('SOLVECRYPTO')&input=VUZKS1hRWlFVTkIg)
