## Descripción 
What does this `bDNhcm5fdGgzX3IwcDM1` mean? I think it has something to do with bases.

## Datos de Acceso al Nivel
user: carlosof
password:

## Solución
```bash
carlosof-picoctf@webshell:~$ mktemp -d
/tmp/tmp.rTt21AnaIR
carlosof-picoctf@webshell:~$ cd /tmp/tmp.rTt21AnaIR/
carlosof-picoctf@webshell:/tmp/tmp.rTt21AnaIR$ nano
carlosof-picoctf@webshell:/tmp/tmp.rTt21AnaIR$ python3 decodificador.py 
Traceback (most recent call last):
  File "/tmp/tmp.rTt21AnaIR/decodificador.py", line 6, in <module>
    text_bytes = base64.b64decode(base64bytes)
AttributeError: 'str' object has no attribute 'b64decode'
carlosof-picoctf@webshell:/tmp/tmp.rTt21AnaIR$ nano decodificador.py 

import base64

# Cadena base64 sin espacio extra al final
base64_string = "bDNhcm5fdGgzX3IwcDM1"

# No es necesario codificar en utf-8, base64.b64decode acepta una cadena directamente
base64_bytes = base64_string.encode('utf-8')

# Decodificar la cadena base64
text_bytes = base64.b64decode(base64_bytes)

# Convertir los bytes decodificados a texto
text = text_bytes.decode('utf-8')

print(text)

carlosof-picoctf@webshell:/tmp/tmp.rTt21AnaIR$ pyton3 decodificador.py 
-bash: pyton3: command not found
carlosof-picoctf@webshell:/tmp/tmp.rTt21AnaIR$ python3 decodificador.py 
l3arn_th3_r0p35
carlosof-picoctf@webshell:/tmp/tmp.rTt21AnaIR$ nano  decodificador.py 
carlosof-picoctf@webshell:/tmp/tmp.rTt21AnaIR$ 

```

## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/67