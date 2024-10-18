## Descripción 
Why search for the flag when I can make a bookmarklet to print it for me?

Additional details will be available after launching your challenge instance.

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
- Iniciamos el launcher e ingresamos al link que nos proporciona el reto.
- En el `textbox` que aparece, podemos percatarnos que contiene código de java script, lo copiamos y damos click derecho en alguna parte de la pagina para poder entrar a la opción de `inspeccionar`.
- Del los apartados que nos aparecen, ingresamos al de `Consola` ahí debemos pegar el código del `textbox`
```bash
        javascript:(function() {
            var encryptedFlag = "àÒÆÞ¦È¬ëÙ£ÖÓÚåÛÑ¢ÕÓÔÅÐÙí";
            var key = "picoctf";
            var decryptedFlag = "";
            for (var i = 0; i < encryptedFlag.length; i++) {
                decryptedFlag += String.fromCharCode((encryptedFlag.charCodeAt(i) - key.charCodeAt(i % key.length) + 256) % 256);
            }
            alert(decryptedFlag);
        })();
    
```
- Damos `Enter` y nos aparecerá un mensaje de `alert` con la bandera:
	- picoCTF{p@g3_turn3r_1d1ba7e0}

## Notas Adicionales
- En algunos navegadores no tienes permitido usar la consola. por lo que hay que habilitar la opción.

## Referencias 
https://play.picoctf.org/practice/challenge/406

