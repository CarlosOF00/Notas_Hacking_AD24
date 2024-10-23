## Objetivo 
How about we take you on an adventure on exploring certificate signing requestsTake a look at this CSR file [here](https://artifacts.picoctf.net/c/420/readmycert.csr).

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosCrypto]
└─$ mkdir readmycert   
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosCrypto]
└─$ cd readmycert 
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosCrypto/readmycert]
└─$ wget https://artifacts.picoctf.net/c/420/readmycert.csr                                
--2024-10-23 10:40:23--  https://artifacts.picoctf.net/c/420/readmycert.csr
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.225.62, 3.161.225.3, 3.161.225.11, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.225.62|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 997 [application/octet-stream]
Saving to: ‘readmycert.csr’

readmycert.csr                            100%[====================================================================================>]     997  --.-KB/s    in 0s      

2024-10-23 10:40:24 (20.3 MB/s) - ‘readmycert.csr’ saved [997/997]

                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosCrypto/readmycert]
└─$ ls
readmycert.csr
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosCrypto/readmycert]
└─$ cat readmycert.csr 
-----BEGIN CERTIFICATE REQUEST-----
MIICpzCCAY8CAQAwPDEmMCQGA1UEAwwdcGljb0NURntyZWFkX215Y2VydF9hNzE2
M2JlOH0xEjAQBgNVBCkMCWN0ZlBsYXllcjCCASIwDQYJKoZIhvcNAQEBBQADggEP
ADCCAQoCggEBAL6KBBqiFmUHDwT3NtVw+Ozveo9uAZ+c47X5n+MEsWPowsNIz9fG
kpLf9rgu9kR4ZR1H5IEddOGEsTA9qRUc1mwBuZeld5o9ltDU+6YzCKANDnwS61sB
w4FV54LTy33T1+1bc11o++3LM34pFCGWI3lwoj8GWDRJdxvvp5Iwh5kz4ki6Mwp/
HAKyyG9i9KMOXAm/Zw0FkL1UZppHa00cbdCieen7lZgeVpFlIs3uo8tL6fGmpYww
Ard6ZFzL1zCwgZukSHsul20gi9Ba4Uz3R4f6zA/PL0S7haAif96yyi/REREKUZGt
76Gt8zv2xVAqhZYYpFqOmv1ycRmZSyF8GWkCAwEAAaAmMCQGCSqGSIb3DQEJDjEX
MBUwEwYDVR0lBAwwCgYIKwYBBQUHAwIwDQYJKoZIhvcNAQELBQADggEBAI4mtS0h
2HQseRJfnySGJdsnquMyLSV1EdvAfb2qTosXuQH0vunk5NbnR9yjXKej0I2Uu6DW
f9UehV+QsgW1tmZKpjGXj602nESDBVwiyNw84AXaW74+vH1lVKu9YFf08GI40Fee
jYYjQLz6DatXL0Qsuyjjo/MF1W1z/N7ErLvox7tj+dIOfEs14LYx61JrwwcAw8Ak
1lo4gwusg/+aEpAhDcw62Bjh2iGfwydHV7vh04vWBzPoSz5xyrNG+w8kALKKRUTh
Z9wKzilfeMGpobC7at6ys5cMdrC3ePVxn0XWTQEWfjQwtr+UtOoOWlP8eJEstWQU
qbdZveR4nsgbnkU=
-----END CERTIFICATE REQUEST-----

```
- Copiamos lo que obtuvimos con el `cat` del archivo `readmycert.csr` e ingresamos a la pagina https://www.sslshopper.com/csr-decoder.html , pegamos el contenido y obtenemos la bandera.
	- Flag: picoCTF{read_mycert_a7163be8}
## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/367
