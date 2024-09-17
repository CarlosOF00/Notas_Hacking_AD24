## Descripción 
Using a Secure Shell (SSH) is going to be pretty important.

Additional details will be available after launching your challenge instance.

## Datos de Acceso al Nivel
user: carlosof
password:

## Solución
```bash
carlosof-picoctf@webshell:/tmp/tmp.dDu5SWHo5P$ ssh ctf-player@titan.picoctf.net -p 52828
The authenticity of host '[titan.picoctf.net]:52828 ([3.139.174.234]:52828)' can't be established.
ED25519 key fingerprint is SHA256:4S9EbTSSRZm32I+cdM5TyzthpQryv5kudRP9PIKT7XQ.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[titan.picoctf.net]:52828' (ED25519) to the list of known hosts.
ctf-player@titan.picoctf.net's password: 
Welcome ctf-player, here's your flag: picoCTF{s3cur3_c0nn3ct10n_3e293eea}
Connection to titan.picoctf.net closed.
carlosof-picoctf@webshell:/tmp/tmp.dDu5SWHo5P$ 
```

## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/424