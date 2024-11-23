## Descripción 
We found a brand new type of encryption, can you break the secret code? (Wrap with picoCTF{}) `mlnklfnknljflfjljnjijjmmjkmljnjhmhjgjnjjjmmkjjmijhmkjhjpmkmkmljkjijnjpmhmjjgjj` [new_caesar.py](https://mercury.picoctf.net/static/43182e6d4527ef0916b2ce43883227b7/new_caesar.py)

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
                                                                            
┌──(kali㉿kali)-[~/Parcial3]
└─$ mkdir newCaesar   
                                                                            
┌──(kali㉿kali)-[~/Parcial3]
└─$ cd newCaesar   
                                                                            
┌──(kali㉿kali)-[~/Parcial3/newCaesar]
└─$ wget https://mercury.picoctf.net/static/43182e6d4527ef0916b2ce43883227b7/new_caesar.py         
--2024-11-15 22:54:48--  https://mercury.picoctf.net/static/43182e6d4527ef0916b2ce43883227b7/new_caesar.py
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 589 [application/octet-stream]
Saving to: ‘new_caesar.py’

new_caesar.py      100%[================>]     589  --.-KB/s    in 0s      

2024-11-15 22:54:48 (12.3 MB/s) - ‘new_caesar.py’ saved [589/589]

                                                                            
┌──(kali㉿kali)-[~/Parcial3/newCaesar]
└─$ cat new_caesar.py 
import string

LOWERCASE_OFFSET = ord("a")
ALPHABET = string.ascii_lowercase[:16]

def b16_encode(plain):
        enc = ""
        for c in plain:
                binary = "{0:08b}".format(ord(c))
                enc += ALPHABET[int(binary[:4], 2)]
                enc += ALPHABET[int(binary[4:], 2)]
        return enc

def shift(c, k):
        t1 = ord(c) - LOWERCASE_OFFSET
        t2 = ord(k) - LOWERCASE_OFFSET
        return ALPHABET[(t1 + t2) % len(ALPHABET)]

flag = "redacted"
key = "redacted"
assert all([k in ALPHABET for k in key])
assert len(key) == 1

b16 = b16_encode(flag)
enc = ""
for i, c in enumerate(b16):
        enc += shift(c, key[i % len(key)])
print(enc)
                     
```

Con el siguiente codigo en pyhton podremos decifras el reto:
```bash
import string
# Inicialización de las variables

ALPHABET = string.ascii_lowercase[:16]  # Solo primeras 16 letras
combined = ""
result = ""
enc = ""

# Función para descifrar el mensaje
def decryptFlag(encl):
    global combined, result, enc
    # Iteramos con distintos valores de desplazamiento (a de 0 a 15)
    for a in range(16):
        enc = encl  # Empezamos con el mensaje cifrado
        # Desplazamiento de las letras
        shifted_text = ""
        for char in enc:
            t1 = ord(char)
            t2 = a
            shifted_char = ALPHABET[(t1 - t2) % len(ALPHABET)]
            shifted_text += shifted_char
            
        # Proceso de descifrado en binario
        combined = ""  # Limpiar la variable combined al inicio
        x = 0
        while x < len(shifted_text) - 1:
            firstChar = ord(shifted_text[x]) - 97
            fBitl = "{0:04b}".format(firstChar)  # Convertir a binario
            secondChar = ord(shifted_text[x + 1]) - 97
            fBit2 = "{0:04b}".format(secondChar)  # Convertir a binario

            # Combinar los dos bits y obtener el carácter correspondiente
            tempCombine = fBitl + fBit2
            combined += str(chr(int(tempCombine, 2)))
            x += 2
            
        # Mostrar el resultado para cada desplazamiento
        print(combined)
        print('---------------------')

# Mensaje a descifrar
flag = 'mlnklfnknljflfjljnjijjmmjkmljnjhmhjgjnjjjmmkjjmijhmkjhjpmkmkmljkjijnjpmhmjjgjj'

# Llamada a la función
decryptFlag(flag)
```

Salida
```bash
ÜëÆëì¦Æ¬®©ªÝ«Ü®¨Ø§®ª­ÛªÙ¨Û¨ ÛÛÜ«©® ØÚ§ª
µÌËÇÊÈÊÊËÉ-----------
---------------------
ºÉ¤ÉÊ
     ¤»º¶
¹·¹¹¹º¶¸

---------------------
©¸¸¹sy{vwªx©{u¥t{wz¨w¦u¨u}¨¨©xv{}¥§tw
---------------------
§¨bhjefgcjfifddlcf
---------------------
qQqWYTUVYSRYUXU
               SS[VTY[
RU
---------------------
v
`
@`FHCDwEvHBrAHDGuDsBuBJuuvECHJrtAD
---------------------
et_tu?_5723f4e71a0736d3b1d19dde4279ac03
---------------------
TcNcd.N$&!"U#T& P/&"%S"Q S (SST#!&(PR/"
---------------------
CR=RS↔=‼§►◄D↕C§▼O▲§◄¶B◄@▼B▼↨BBC↕►§↨OA▲◄
---------------------
♦♥1?♫1♫♠112☺☼♦♠>0
---------------------
!01ûóþÿ"ð!óý-üóÿò ÿ.ý ýõ  !ðþóõ-/üÿ
---------------------
►/
/ ê
àâíî◄ï►âì∟ëâîá▼î↔ì▼ìä▼▼►ïíâä∟▲ëî
---------------------
ÚÝù▲▼ÙùßÑÜÝÞ☼ÑÛ♂ÚÑÝÐ♫Ý♀Û♫ÛÓ♫♫☼ÞÜÑÓ♂
---------------------
♫ÈèÎÀËÌÿÍþÀÊúÉÀÌÏýÌûÊýÊÂýýþÍËÀÂúüÉÌ
---------------------
íü×üý·×½¿º»î¼í¿¹é¸¿»¾ì»ê¹ì¹±ììí¼º¿±éë¸»
---------------------
```

- Flag: picoCTF{et_tu?_5723f4e71a0736d3b1d19dde4279ac03}

## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/158
