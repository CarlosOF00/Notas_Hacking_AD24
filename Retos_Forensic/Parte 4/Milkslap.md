
## Descripción 
http://mercury.picoctf.net:48380/

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución 
- Ingresamos al emoji del reto.
- Nos podemos dar cuenta de que es una pagina web, pero en el navegador de Fire Fox, teniendo habilitada la opción de menú bar, podemos irnos al apartado de `Tools` ahí elegimos la opción de `Page info`, se abrirá un menú que contiene varias opciones, pero si ingresamos a `Media`, podemos observar que hay una imagen que es posible descargar.

```bash
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosForensic]
└─$ mkdir milkslap       
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosForensic]
└─$ cd milkslap                                       
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosForensic/milkslap]
└─$ wget http://mercury.picoctf.net:48380/            
--2024-10-12 22:39:13--  http://mercury.picoctf.net:48380/
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:48380... connected.
HTTP request sent, awaiting response... 200 OK
Length: unspecified [text/html]
Saving to: ‘index.html’

index.html                                    [ <=>                                                                                 ]     517  --.-KB/s    in 0s      

2024-10-12 22:39:13 (14.3 MB/s) - ‘index.html’ saved [517]

                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosForensic/milkslap]
└─$ wget http://mercury.picoctf.net:48380/concat_v.png
--2024-10-12 22:43:57--  http://mercury.picoctf.net:48380/concat_v.png
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:48380... connected.
HTTP request sent, awaiting response... 200 OK
Length: 18095920 (17M) [image/png]
Saving to: ‘concat_v.png’

concat_v.png                              100%[====================================================================================>]  17.26M   333KB/s    in 55s     

2024-10-12 22:44:52 (322 KB/s) - ‘concat_v.png’ saved [18095920/18095920]

                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosForensic/milkslap]
└─$ ls
concat_v.png  index.html
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosForensic/milkslap]
└─$ zsteg concat_v.png  
```
- Y así obtenemos la bandera:
	- Flag : picoCTF{imag3_m4n1pul4t10n_sl4p5}

## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/139
http://mercury.picoctf.net:48380/
