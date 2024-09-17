## Descripción 
To get truly 1337, you must understand different data encodings, such as hexadecimal or binary. Can you get the flag from this program to prove you are on the way to becoming 1337? Connect with `nc jupiter.challenges.picoctf.org 15130`.

## Datos de Acceso al Nivel
user: carlosof
password:

## Solución
```bash
carlosof-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 15130
Let us see how data is stored
table
Please give the 01110100 01100001 01100010 01101100 01100101 as a word.
...
you have 45 seconds.....

Input:
Too slow!
^C
carlosof-picoctf@webshell:~$ nc jupiter.challenges.picoctf.org 15130
Let us see how data is stored
pear
Please give the 01110000 01100101 01100001 01110010 as a word.
...
you have 45 seconds.....

Input:
pear
Please give me the  141 156 151 155 141 164 151 157 156 as a word.
Input:
animation
Please give me the 6c69676874 as a word.
Input:
light
You've beaten the challenge
Flag: picoCTF{learning_about_converting_values_02167de8}
```

## Notas Adicionales
![[BasedCap.png]]

## Referencias 
https://play.picoctf.org/practice/challenge/35
[CyberChef](https://cyberchef.io/#input=MDExMDEwMDE)
