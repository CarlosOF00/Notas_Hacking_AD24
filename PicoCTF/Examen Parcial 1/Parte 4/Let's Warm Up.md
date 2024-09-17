## Descripción 
If I told you a word started with 0x70 in hexadecimal, what would it start with in ASCII?

## Datos de Acceso al Nivel
user: carlosof
password:

## Solución
```bash
carlosof-picoctf@webshell:~$ python3
Python 3.10.12 (main, Nov 20 2023, 15:14:05) [GCC 11.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> valorH = 0x70
>>> valorD = int(0x70)
>>> print(valorD)
112
>>> print ("picoCTF{",valorD,"}")
picoCTF{ 112 }
>>> 
KeyboardInterrupt
>>> ascii = chr(valorD)
>>> print(as
as       ascii    assert   async    
>>> print(as
as       ascii    assert   async    
>>> print(ascii)
p
>>> 
KeyboardInterrupt
>>> print ("picoCTF{",ascii,"}")
picoCTF{ p }
>>> 
```
## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/22