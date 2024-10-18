## Descripción 
We have several pages hidden. Can you find the one with the flag?

Additional details will be available after launching your challenge instance.

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
- Usaremos la herramienta `ffuf` para encontrar los demás directorios.
```bash
┌──(kali㉿kali)-[~/Parcial2/tmp]
└─$ ffuf -u http://saturn.picoctf.net:51331/FUZZ -w /usr/share/wordlists/dirbuster/directory-list-lowercase-2.3-small.txt -ic

        /'___\  /'___\           /'___\       
       /\ \__/ /\ \__/  __  __  /\ \__/       
       \ \ ,__\\ \ ,__\/\ \/\ \ \ \ ,__\      
        \ \ \_/ \ \ \_/\ \ \_\ \ \ \ \_/      
         \ \_\   \ \_\  \ \____/  \ \_\       
          \/_/    \/_/   \/___/    \/_/       

       v2.1.0-dev
________________________________________________

 :: Method           : GET
 :: URL              : http://saturn.picoctf.net:51331/FUZZ
 :: Wordlist         : FUZZ: /usr/share/wordlists/dirbuster/directory-list-lowercase-2.3-small.txt
 :: Follow redirects : false
 :: Calibration      : false
 :: Timeout          : 10
 :: Threads          : 40
 :: Matcher          : Response status: 200-299,301,302,307,401,403,405,500
________________________________________________

                        [Status: 200, Size: 1023, Words: 201, Lines: 37, Duration: 169ms]
secret                  [Status: 301, Size: 169, Words: 5, Lines: 8, Duration: 249ms]
[WARN] Caught keyboard interrupt (Ctrl-C)

```
- Encontramos el directorio `secret/` ingresamos y repetimos el proceso.
```bash
┌──(kali㉿kali)-[~/Parcial2/tmp]
└─$ ffuf -u http://saturn.picoctf.net:51331/secret/FUZZ -w /usr/share/wordlists/dirbuster/directory-list-lowercase-2.3-small.txt -ic

        /'___\  /'___\           /'___\       
       /\ \__/ /\ \__/  __  __  /\ \__/       
       \ \ ,__\\ \ ,__\/\ \/\ \ \ \ ,__\      
        \ \ \_/ \ \ \_/\ \ \_\ \ \ \ \_/      
         \ \_\   \ \_\  \ \____/  \ \_\       
          \/_/    \/_/   \/___/    \/_/       

       v2.1.0-dev
________________________________________________

 :: Method           : GET
 :: URL              : http://saturn.picoctf.net:51331/secret/FUZZ
 :: Wordlist         : FUZZ: /usr/share/wordlists/dirbuster/directory-list-lowercase-2.3-small.txt
 :: Follow redirects : false
 :: Calibration      : false
 :: Timeout          : 10
 :: Threads          : 40
 :: Matcher          : Response status: 200-299,301,302,307,401,403,405,500
________________________________________________

                        [Status: 200, Size: 468, Words: 55, Lines: 13, Duration: 101ms]
assets                  [Status: 301, Size: 169, Words: 5, Lines: 8, Duration: 170ms]
hidden                  [Status: 301, Size: 169, Words: 5, Lines: 8, Duration: 165ms]

```
- Ahora encontramos el directorio `hidden/`
- Si estando en este directorio inspeccionamos la pagina, podremos encontrarnos con lo siguiente
```bash
|   |
|---|
|<input|
||type="password"|
||name="password"|
||placeholder="Password"|
||required|
||/>|
||<input type="hidden" name="db" value="superhidden/xdfgwd.html" />|
|||
||<input|
||type="submit"|
||value="Login"|
```
- Si intentamos poner la ruta completa, no encontraremos nada, pero si solo usamos `superhidden/` entraremos a la ultima pagina.
- Inspeccionamos la pagina y obtenemos la bandera.
	- Flag: picoCTF{succ3ss_@h3n1c@10n_39849bcf}
## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/296
