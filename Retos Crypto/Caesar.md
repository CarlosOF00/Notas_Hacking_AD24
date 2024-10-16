
## Descripción 
Decrypt this [message](https://jupiter.challenges.picoctf.org/static/49f31c8f17817dc2d367428c9e5ab0bc/ciphertext).

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
(kali@kali)-(~/retosCrypto] $ mkdir caesar
(kali@kali)-[~/retosCrypto cd caesar
(kali@kali)-(-/retosCrypto/caesar
$ wget https:/ //jupiter.challenges.picoctf.org/static/49f31c8f17817dc2d367428c9e5ab@bc/ciphertext -2024-10-10 23:37:10- https://jupiter.challenges.picoctf.org/static/49f31c8f17817dc2d367428c9e5ab@bc/ciphertext Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)13.131.60.81:443... connected..
HTTP request sent, awaiting response... 200 OK Length: 35 [application/octet-stream]
Saving to: 'ciphertext'
ciphertext
100%[
2024-10-10 23:37:11 (15.3 MB/s) 'ciphertext saved [35/35]
35-KB/s
in es
(kali@kali)-(-/retosCrypto/caesar]
ciphertext
(kali@kali)-[~/retosCrypto/caesar] cat ciphertext picoCTF(ynkooejcpdanqxeykjrbdofgkq)
(kali@kali)-[~/retosCrypto/caesar]
```
- Ingresamos a la siguiente pagina (https://cryptii.com/pipes/caesar-cipher) y tras rotar 4 veces obtenemos la bandera
- picoCTF{crossingtherubiconvfhsjkou}  
## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/64?category=2&difficulty=2&page=1&search=c
https://cryptii.com/pipes/caesar-cipher
