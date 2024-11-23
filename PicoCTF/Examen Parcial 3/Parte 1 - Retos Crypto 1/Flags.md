## Descripción 
What do the [flags](https://jupiter.challenges.picoctf.org/static/fbeb5f9040d62b18878d199cdda2d253/flag.png) mean?

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
                                                                                  
┌──(kali㉿kali)-[~/Parcial3]
└─$ mkdir flags
                                                                                   
┌──(kali㉿kali)-[~/Parcial3]
└─$ cd flags 
                                                                                   
┌──(kali㉿kali)-[~/Parcial3/flags]
└─$ wget https://jupiter.challenges.picoctf.org/static/fbeb5f9040d62b18878d199cdda2d253/flag.png
--2024-11-15 22:12:58--  https://jupiter.challenges.picoctf.org/static/fbeb5f9040d62b18878d199cdda2d253/flag.png
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 43257 (42K) [application/octet-stream]
Saving to: ‘flag.png’

flag.png             100%[=====================>]  42.24K  --.-KB/s    in 0.05s   

2024-11-15 22:12:58 (795 KB/s) - ‘flag.png’ saved [43257/43257]

                                                                                   
┌──(kali㉿kali)-[~/Parcial3/flags]
└─$ ls
flag.png
                                                                                   
┌──(kali㉿kali)-[~/Parcial3/flags]
└─$ open flag.png     
                                                                                   
┌──(kali㉿kali)-[~/Parcial3/flags]
└─$ echo ' PICOCTF{F1AG5AND5TUFF}'       
 PICOCTF{F1AG5AND5TUFF}
                                                                                   
┌──(kali㉿kali)-[~/Parcial3/flags]
└─$ 

```
- Flag: PICOCTF{F1AG5AND5TUFF}

## Notas Adicionales
Para poder resolver el reto, debemos ingresar a la pagina [dcode](https://www.dcode.fr/maritime-signals-code)  y comparando la imagen que descargamos, podemos ver que cada bandera tiene un nombre, entonces sustituiremos la inicial del nombre de la bandera, por la bandera.

## Referencias 
https://play.picoctf.org/practice/challenge/31
https://www.dcode.fr/maritime-signals-code
