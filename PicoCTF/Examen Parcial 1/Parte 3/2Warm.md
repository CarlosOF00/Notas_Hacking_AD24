## Descripción 
Can you convert the number 42 (base 10) to binary (base 2)?

## Datos de Acceso al Nivel
user: carlosof
password:

## Solución
```bash
carlosof-picoctf@webshell:~$ python3
Python 3.10.12 (main, Nov 20 2023, 15:14:05) [GCC 11.4.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> var1 = 42
>>> var 2 = bin(var1)
  File "<stdin>", line 1
    var 2 = bin(var1)
        ^
SyntaxError: invalid syntax
>>> var2 = bin(var1)
>>> print(var2)
0b101010
>>> 

```


## Notas Adicionales
- `bin` convierte el numero a binario

## Referencias 
https://play.picoctf.org/practice/challenge/86