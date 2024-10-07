	## Descripción 
This [garden](https://jupiter.challenges.picoctf.org/static/d0e1ffb10fc0017c6a82c57900f3ffe3/garden.jpg) contains more than it seems.

## Datos de Acceso al Nivel
user: carlosof 
password:
## Solución 1
```bash
┌──(kali㉿kali)-[~]
└─$ mkdir retosForensic
                                                                                                                                                                      
┌──(kali㉿kali)-[~]
└─$ cd retosForensic 
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic]
└─$ wget https://jupiter.challenges.picoctf.org/static/d0e1ffb10fc0017c6a82c57900f3ffe3/garden.jpg
--2024-09-29 00:47:20--  https://jupiter.challenges.picoctf.org/static/d0e1ffb10fc0017c6a82c57900f3ffe3/garden.jpg
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2295192 (2.2M) [application/octet-stream]
Saving to: ‘garden.jpg’

garden.jpg                                100%[===================================================================================>]   2.19M  3.48MB/s    in 0.6s    

2024-09-29 00:47:22 (3.48 MB/s) - ‘garden.jpg’ saved [2295192/2295192]

                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic]
└─$ open garden.jpg 
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic]
└─$ hexeditor garden.jpg 
flag "picoCTF{more_than_m33ts_the_3y3eBdBd2cc}". 
```

## Solución 2
```bash
┌──(kali㉿kali)-[~/retosForensic]
└─$ strings garden.jpg | grep picoCTF
Here is a flag "picoCTF{more_than_m33ts_the_3y3eBdBd2cc}"
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic]
└─$ 

```

## Notas Adicionales
Un hexeditor es una herramienta que permite visualizar y editar archivos en formato hexadecimal. En este modo, los datos se presentan en su representación binaria, lo que permite a los usuarios ver y modificar directamente los bytes que componen un archivo. Esto es útil para tareas como la depuración de software, la edición de archivos binarios o la recuperación de datos.

Los hexeditores suelen mostrar el contenido del archivo en dos paneles: uno con la representación hexadecimal y otro con la representación de texto (cuando sea posible). Esto permite a los usuarios identificar y modificar valores específicos de manera precisa. Algunos ejemplos de hexeditores son HxD, Hex Fiend y 010 Editor.

## Referencias 
https://play.picoctf.org/practice/challenge/44?page=1&search=glory%20
https://mh-nexus.de/en/hxd/