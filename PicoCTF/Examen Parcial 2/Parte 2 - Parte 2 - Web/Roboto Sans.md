## Descripción 
The flag is somewhere on this web application not necessarily on the website. Find it.

Additional details will be available after launching your challenge instance.

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
- Iniciamos el launcher del reto e ingresamos al link.
- En la URL, agregaremos `\robots.txt` quedando así: `http://saturn.picoctf.net:58777/robots.txt` nos muestra lo siguiente:

```bash
User-agent *
Disallow: /cgi-bin/
Think you have seen your flag or want to keep looking.

ZmxhZzEudHh0;anMvbXlmaW
anMvbXlmaWxlLnR4dA==
svssshjweuiwl;oiho.bsvdaslejg
Disallow: /wp-admin/
```

- Ahora decodificamos el mensaje (por alguna razón, el archivo no se descifra correctamente, por lo que podemos utilizar una herramienta online)
```bash
┌──(kali㉿kali)-[~]
└─$ echo 'anMvbXlmaW                                
anMvbXlmaWxlLnR4dA==
svssshjweuiwl' | base64 -d
js/myfif�2�זf��R�G�@base64: invalid input
```

- Obtenemos `js/myfile.txt` y al ingresarlo a la URL, obtenemos la bandera:
	- picoCTF{Who_D03sN7_L1k5_90B0T5_22ce1f22}

## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/291
http://saturn.picoctf.net:49167/
[Base64 Converter - Base 64 Cipher - Online Decoder, Encoder (dcode.fr)](https://www.dcode.fr/base-64-encoding?__r=1.0115193cedb67ef370206d426d612e6e)
