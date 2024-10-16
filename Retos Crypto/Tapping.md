
## Descripción 
Theres tapping coming in from the wires. What's it saying `nc jupiter.challenges.picoctf.org 9422`.

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
┌──(kali㉿kali)-[~/retosCrypto]
└─$ nc jupiter.challenges.picoctf.org 9422
.--. .. -.-. --- -.-. - ..-. { -- ----- .-. ... ...-- -.-. ----- -.. ...-- .---- ... ..-. ..- -. ..--- -.... ---.. ...-- ---.. ..--- ....- -.... .---- ----- } 

```
- Ingresamos a CyberChef y buscamos el apartado de `From morse code`
- Ingresamos lo que obtuvimos y nos devuelve lo suiguiente.
- PICOCTFM0RS3C0D31SFUN2683824610 
- Siguiendo la pista, solo le damos formato y obtenemos
	- PICOCTF{M0RS3C0D31SFUN2683824610}

## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/21?category=2&page=1&search=TAPP
[From Morse Code - CyberChef](https://cyberchef.org/#recipe=From_Morse_Code('Space','Line%20feed')&input=Li0tLiAuLiAtLi0uIC0tLSAtLi0uIC0gLi4tLiB7IC0tIC0tLS0tIC4tLiAuLi4gLi4uLS0gLS4tLiAtLS0tLSAtLi4gLi4uLS0gLi0tLS0gLi4uIC4uLS4gLi4tIC0uIC4uLS0tIC0uLi4uIC0tLS4uIC4uLi0tIC0tLS4uIC4uLS0tIC4uLi4tIC0uLi4uIC4tLS0tIC0tLS0tIH0gDQo)
