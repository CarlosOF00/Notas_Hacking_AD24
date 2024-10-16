
## Descripción 
The [numbers](https://jupiter.challenges.picoctf.org/static/f209a32253affb6f547a585649ba4fda/the_numbers.png)... what do they mean?

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosCrypto]
└─$ mkdir theNumbers 
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosCrypto]
└─$ cd theNumbers 
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosCrypto/theNumbers]
└─$ wget https://jupiter.challenges.picoctf.org/static/f209a32253affb6f547a585649ba4fda/the_numbers.png
--2024-10-10 22:16:56--  https://jupiter.challenges.picoctf.org/static/f209a32253affb6f547a585649ba4fda/the_numbers.png
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 100721 (98K) [application/octet-stream]
Saving to: ‘the_numbers.png’

the_numbers.png                           100%[====================================================================================>]  98.36K   640KB/s    in 0.2s    

2024-10-10 22:16:56 (640 KB/s) - ‘the_numbers.png’ saved [100721/100721]

                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosCrypto/theNumbers]
└─$ file the_numbers.png                                       
the_numbers.png: PNG image data, 774 x 433, 8-bit/color RGB, non-interlaced
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosCrypto/theNumbers]
└─$ open the_numbers.png 
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosCrypto/theNumbers]
└─$ echo 16 9 3 15 3 20 6 { 20 8 5 14 21 13 2 5 18 19 13 1 19 15 14 }
zsh: parse error near `}'
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosCrypto/theNumbers]
└─$ 

```
- Los números obtenidos, están cifrados, podemos usar esta pagina para detectar de que manera están encriptados [Descifrar un Mensaje - Identificador de Cifrado o Código Online (dcode.fr)](https://www.dcode.fr/identificador-cifrado).
- De esta manera obtenemos la bandera:  `PICOCTF{THENUMBERSMASON}`

## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/68?category=2&page=1
[Descifrar un Mensaje - Identificador de Cifrado o Código Online (dcode.fr)](https://www.dcode.fr/identificador-cifrado)