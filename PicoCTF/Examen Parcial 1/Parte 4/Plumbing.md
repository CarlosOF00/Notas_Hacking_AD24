## Descripción 
Sometimes you need to handle process data outside of a file. Can you find a way to keep the output from this program and search for the flag? Connect to `jupiter.challenges.picoctf.org 14291`.

## Datos de Acceso al Nivel
user: carlosof
password:

## Solución
```bash
carlosof-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 14291
I don't think this is a flag either
I don't think this is a flag either
Not a flag either
I don't think this is a flag either
I don't think this is a flag either
Not a flag either
This is defintely not a flag
Not a flag either
Not a flag either
Again, I really don't think this is a flag
Not a flag either
I don't think this is a flag either
I don't think this is a flag either
Not a flag either
Not a flag either
I don't think this is a flag either
Not a flag either
Not a flag either
Again, I really don't think this is a flag
Not a flag either
Not a flag either
Not a flag either
This is defintely not a flag
This is defintely not a flag
Not a flag either
Not a flag either
Not a flag either
I don't think this is a flag either
This is defintely not a flag
This is defintely not a flag
I don't think this is a flag either
Not a flag either
I don't think this is a flag either
Not a flag either
I don't think this is a flag either
Not a flag either
Not a flag either
I don't think this is a flag either
Not a flag either
I don't think this is a flag either
Not a flag either
Again, I really don't think this is a flag
I don't think this is a flag either
I don't think this is a flag either
Not a flag either
Not a flag either
Not a flag either
I don't think this is a flag either
I don't think this is a flag either
This is defintely not a flag
This is defintely not a flag
Again, I really don't think this is a flag
Again, I really don't think this is a flag
I don't think this is a flag either
Not a flag either
Not a flag either
Not a flag either
I don't think this is a flag either
I don't think this is a flag either
I don't think this is a flag either
Not a flag either
This is defintely not a flag
Not a flag either
Not a flag either
Again, I really don't think this is a flag
Not a flag either
Not a flag either
Not a flag either
Not a flag either
Not a flag either
I don't think this is a flag either
This is defintely not a flag
This is defintely not a flag
This is defintely not a flag
This is defintely not a flag
I don't think this is a flag either
Not a flag either
I don't think this is a flag either
Not a flag either
Again, I really don't think this is a flag
Again, I really don't think this is a flag
I don't think this is a flag either
Not a flag either
This is defintely not a flag
Not a flag either
This is defintely not a flag
I don't think this is a flag either
Not a flag either
Again, I really don't think this is a flag
Again, I really don't think this is a flag
Not a flag either
I don't think this is a flag either
Not a flag either
Again, I really don't think this is a flag
I don't think this is a flag either
This is defintely not a flag
Not a flag either
This is defintely not a flag
Not a flag either
This is defintely not a flag
Not a flag either
I don't think this is a flag either
Again, I really don't think this is a flag
Again, I really don't think this is a flag
Again, I really don't think this is a flag
This is defintely not a flag
Not a flag either
I don't think this is a flag either
Not a flag either
Not a flag either
Again, I really don't think this is a flag
Again, I really don't think this is a flag
This is defintely not a flag
Not a flag either
Not a flag either
Again, I really don't think this is a flag
Not a flag either
Not a flag either
Not a flag either
Again, I really don't think this is a flag
I don't think this is a flag either
This is defintely not a flag
Again, I really don't think this is a flag
This is defintely not a flag
I don't think this is a flag either
This is defintely not a flag
Not a flag either
Not a flag either
Again, I really don't think this is a flag
This is defintely not a flag
^C
carlosof-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 14291 | grep picoCTF
picoCTF{digital_plumb3r_ea8bfec7}
```

## Notas Adicionales
- Se pueden utilizar funciones adicionales, con el net cat.

## Referencias 
https://play.picoctf.org/practice/challenge/48
