## Descripción 
Can you make sense of this file?Download the file [here](https://artifacts.picoctf.net/c/476/enc_flag).

## Datos de Acceso al Nivel
user: carlosof
password:

## Solución
```bash
carlosof-picoctf@webshell:~$ mktemp -d
/tmp/tmp.dDu5SWHo5P
carlosof-picoctf@webshell:~$ cd /tmp/tmp.dDu5SWHo5P/
carlosof-picoctf@webshell:/tmp/tmp.dDu5SWHo5P$ wget https://artifacts.picoctf.net/c/476/enc_flag
--2024-09-14 05:26:35--  https://artifacts.picoctf.net/c/476/enc_flag
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.71, 3.160.5.42, 3.160.5.18, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.71|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 349 [application/octet-stream]
Saving to: 'enc_flag'

enc_flag                                        100%[======================================================================================================>]     349  --.-KB/s    in 0s      

2024-09-14 05:26:35 (14.9 MB/s) - 'enc_flag' saved [349/349]

carlosof-picoctf@webshell:/tmp/tmp.dDu5SWHo5P$ ls -la
total 4
drwx------ 2 carlosof-picoctf carlosof-picoctf  22 Sep 14 05:26 .
drwxrwxrwt 1 root             root              72 Sep 14 05:26 ..
-rw-rw-r-- 1 carlosof-picoctf carlosof-picoctf 349 Mar 16  2023 enc_flag
carlosof-picoctf@webshell:/tmp/tmp.dDu5SWHo5P$ cat enc_flag 
VmpGU1EyRXlUWGxTYmxKVVYwZFNWbGxyV21GV1JteDBUbFpPYWxKdFVsaFpWVlUxWVZaS1ZWWnVh
RmRXZWtab1dWWmtSMk5yTlZWWApiVVpUVm10d1VWZFdVa2RpYlZaWFZtNVdVZ3BpU0VKeldWUkNk
MlZXVlhoWGJYQk9VbFJXU0ZkcVRuTldaM0JZVWpGS2VWWkdaSGRXCk1sWnpWV3hhVm1KRk5XOVVW
VkpEVGxaYVdFMVhSbFZrTTBKVVZXMTRWMDVHV2toalJYUlhDazFyV25sVVZXaHpWakpHZEdWRlZs
aGkKYlRrelZERldUMkpzUWxWTlJYTkxDZz09Cg==
carlosof-picoctf@webshell:/tmp/tmp.dDu5SWHo5P$ base64 -d enc_flag > decodificado.bin
carlosof-picoctf@webshell:/tmp/tmp.dDu5SWHo5P$ cat 
decodificado.bin  enc_flag          
carlosof-picoctf@webshell:/tmp/tmp.dDu5SWHo5P$ cat decodificado.bin 
VjFSQ2EyTXlSblJUV0dSVllrWmFWRmx0TlZOalJtUlhZVVU1YVZKVVZuaFdWekZoWVZkR2NrNVVX
bUZTVmtwUVdWUkdibVZXVm5WUgpiSEJzWVRCd2VWVXhXbXBOUlRWSFdqTnNWZ3BYUjFKeVZGZHdW
MlZzVWxaVmJFNW9UVVJDTlZaWE1XRlVkM0JUVW14V05GWkhjRXRXCk1rWnlUVWhzVjJGdGVFVlhi
bTkzVDFWT2JsQlVNRXNLCg==
carlosof-picoctf@webshell:/tmp/tmp.dDu5SWHo5P$ openssl base64 -d -in enc_flag -out decodificado.bin
carlosof-picoctf@webshell:/tmp/tmp.dDu5SWHo5P$ ls -la
total 8
drwx------ 2 carlosof-picoctf carlosof-picoctf  46 Sep 14 05:29 .
drwxrwxrwt 1 root             root              72 Sep 14 05:26 ..
-rw-rw-r-- 1 carlosof-picoctf carlosof-picoctf 256 Sep 14 05:30 decodificado.bin
-rw-rw-r-- 1 carlosof-picoctf carlosof-picoctf 349 Mar 16  2023 enc_flag
carlosof-picoctf@webshell:/tmp/tmp.dDu5SWHo5P$ less 
decodificado.bin  enc_flag          
carlosof-picoctf@webshell:/tmp/tmp.dDu5SWHo5P$ less decodificado.bin 
carlosof-picoctf@webshell:/tmp/tmp.dDu5SWHo5P$ base64 -d enc_flag | base64 -d |base64 -d
WTBkc2FtSXdUbFZTYm5ScFdWaE9iRTVxVW1aaWFrNTZaRVJPYTFneVVuQlpla0pyU1ZjME5GZ3lV
WGRrTWpWelRVUlNhMDB5VW1aTwpSRlV4VGpKV2FrMHlWamxEWnowOUNnPT0K
carlosof-picoctf@webshell:/tmp/tmp.dDu5SWHo5P$ base64 -d enc_flag | base64 -d |base64 -d| base64 -d| base64 -d
cGljb0NURntiYXNlNjRfbjNzdDNkX2RpYzBkIW44X2Qwd25sMDRkM2RfNDU1N2VjM2V9Cg==
carlosof-picoctf@webshell:/tmp/tmp.dDu5SWHo5P$ base64 -d enc_flag | base64 -d |base64 -d| base64 -d| base64 -d| base64 -d
picoCTF{base64_n3st3d_dic0d!n8_d0wnl04d3d_4557ec3e}
carlosof-picoctf@webshell:/tmp/tmp.dDu5SWHo5P$ 
```


## Notas Adicionales
- El comando `base64 -d enc_flag > decodificado.bin` realiza una decodificación de un archivo codificado en Base64 y guarda el resultado en un archivo binario.
- El comando `openssl base64 -d -in enc_flag -out decodificado.bin` utiliza la herramienta `openssl` para decodificar datos que están en formato Base64
- El comando `base64 -d enc_flag | base64 -d | base64 -d | base64 -d | base64 -d | base64 -d` utiliza el comando `base64` para decodificar el contenido de un archivo de forma repetitiva.

## Referencias 
https://play.picoctf.org/practice/challenge/371
[Conceptos básicos de la línea de comandos de Linux: Codificación y decodificación de cadenas Base64 - Blog - HostZealot](https://es.hostzealot.com/blog/how-to/conceptos-basicos-de-la-linea-de-comandos-de-linux-codificacion-y-decodificacion-de-cadenas-base64#:~:text=Uso%20de%20Base64%201%201.1.%20Codificaci%C3%B3n%20con%20Base64,Codificaci%C3%B3n%3A%20echo%20-n%20%22Hello%2C%20Base64%21%22%20%7C%20base64%20)