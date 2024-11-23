## Descripción 
A musician left us a [message](https://jupiter.challenges.picoctf.org/static/d5570d48262dbba2a31f2a940409ad9d/message.txt). What's it mean?

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
                                                                            
┌──(kali㉿kali)-[~/Parcial3]
└─$ mkdir mrWorldWide
                                                                            
┌──(kali㉿kali)-[~/Parcial3]
└─$ cd mrWorldWide 
                                                                            
┌──(kali㉿kali)-[~/Parcial3/mrWorldWide]
└─$ wget https://jupiter.challenges.picoctf.org/static/d5570d48262dbba2a31f2a940409ad9d/message.txt
--2024-11-15 22:45:43--  https://jupiter.challenges.picoctf.org/static/d5570d48262dbba2a31f2a940409ad9d/message.txt
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 278 [application/octet-stream]
Saving to: ‘message.txt’

message.txt        100%[================>]     278  --.-KB/s    in 0s      

2024-11-15 22:45:44 (5.91 MB/s) - ‘message.txt’ saved [278/278]

                                                                            
┌──(kali㉿kali)-[~/Parcial3/mrWorldWide]
└─$ cat message.txt 
picoCTF{(35.028309, 135.753082)(46.469391, 30.740883)(39.758949, -84.191605)(41.015137, 28.979530)(24.466667, 54.366669)(3.140853, 101.693207)_(9.005401, 38.763611)(-3.989038, -79.203560)(52.377956, 4.897070)(41.085651, -73.858467)(57.790001, -152.407227)(31.205753, 29.924526)}                                                                            
┌──(kali㉿kali)-[~/Parcial3/mrWorldWide]
└─$ 
```
- Tras un breve análisis podemos darnos cuenta de que son ubicaciones, por lo cual ingresamos a la siguiente pagina [Google Maps](https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=&ved=2ahUKEwio8o63h-CJAxVqTTABHTzJCBwQFnoECAoQAQ&url=https%3A%2F%2Fwww.google.com.mx%2Fmaps%2Fpreview&usg=AOvVaw1Sj277Bf_x-3B6plfKqRFY&opi=89978449) e ingresamos de una por una las coordenadas que nos han dado, así que nos quedamos con la inicial y así formamos la bandera.

```bash
35.028309, 135.753082    K yoto
46.469391, 30.740883     O desa
39.758949, -84.191605    D ayton
41.015137, 28.979530     I stanbul
24.466667, 54.366669     A bu Dhabi
3.140853, 101.693207     K uala Lumpur
_
9.005401, 38.763611      A ddis Ababa
-3.989038, -79.203560    L oja
52.377956, 4.897070      A msterdam
41.085651, -73.858467    S leepy Hollow
57.790001, -152.407227   K odiak
31.205753, 29.924526     A lexandria Governorate
```

Flag: picoCTF{KODIAK_ALASKA}

## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/40
[Google Maps](https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=&ved=2ahUKEwio8o63h-CJAxVqTTABHTzJCBwQFnoECAoQAQ&url=https%3A%2F%2Fwww.google.com.mx%2Fmaps%2Fpreview&usg=AOvVaw1Sj277Bf_x-3B6plfKqRFY&opi=89978449)
