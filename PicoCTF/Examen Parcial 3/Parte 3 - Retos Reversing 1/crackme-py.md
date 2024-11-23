## Descripción 
[crackme.py](https://mercury.picoctf.net/static/2ff6c888060f14af5db1232e319547c9/crackme.py)

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
┌──(kali㉿kali)-[~/Parcial3]
└─$ mkdir crackme-py
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial3]
└─$ cd crackme-py
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial3/crackme-py]
└─$ wget https://mercury.picoctf.net/static/2ff6c888060f14af5db1232e319547c9/crackme.py
--2024-11-17 11:41:17--  https://mercury.picoctf.net/static/2ff6c888060f14af5db1232e319547c9/crackme.py
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1463 (1.4K) [application/octet-stream]
Saving to: ‘crackme.py’

crackme.py                                100%[===================================================================================>]   1.43K  --.-KB/s    in 0s      

2024-11-17 11:41:17 (41.0 MB/s) - ‘crackme.py’ saved [1463/1463]

                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial3/crackme-py]
└─$ cat crackme.py 
# Hiding this really important number in an obscure piece of code is brilliant!
# AND it's encrypted!
# We want our biggest client to know his information is safe with us.
bezos_cc_secret = "A:4@r%uL`M-^M0c0AbcM-MFE067d3eh2bN"

# Reference alphabet
alphabet = "!\"#$%&'()*+,-./0123456789:;<=>?@ABCDEFGHIJKLMNOPQRSTUVWXYZ"+ \
            "[\\]^_`abcdefghijklmnopqrstuvwxyz{|}~"



def decode_secret(secret):
    """ROT47 decode

    NOTE: encode and decode are the same operation in the ROT cipher family.
    """

    # Encryption key
    rotate_const = 47

    # Storage for decoded secret
    decoded = ""

    # decode loop
    for c in secret:
        index = alphabet.find(c)
        original_index = (index + rotate_const) % len(alphabet)
        decoded = decoded + alphabet[original_index]

    print(decoded)



def choose_greatest():
    """Echo the largest of the two numbers given by the user to the program

    Warning: this function was written quickly and needs proper error handling
    """

    user_value_1 = input("What's your first number? ")
    user_value_2 = input("What's your second number? ")
    greatest_value = user_value_1 # need a value to return if 1 & 2 are equal

    if user_value_1 > user_value_2:
        greatest_value = user_value_1
    elif user_value_1 < user_value_2:
        greatest_value = user_value_2

    print( "The number with largest positive magnitude is "
        + str(greatest_value) )



choose_greatest()

```

- Ingresamos a [CyberChef-ROT47](https://gchq.github.io/CyberChef/#recipe=ROT47(47)&input=QTo0QHIldUxgTS1eTTBjMEFiY00tTUZFMDY3ZDNlaDJiTg) y colocaremos el contenido de la variable `bezos_cc_secret =` "A:4@r%uL`M-^M0c0AbcM-MFE067d3eh2bN" ` y obtenemos la bandera:

- Flag: picoCTF{1|\/|_4_p34|\|ut_ef5b69a3}
## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/175
