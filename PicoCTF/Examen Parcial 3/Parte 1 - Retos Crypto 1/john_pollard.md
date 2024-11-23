## Descripción 
Sometimes RSA [certificates](https://jupiter.challenges.picoctf.org/static/c882787a19ed5d627eea50f318d87ac5/cert) are breakable

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
                                                                                   
┌──(kali㉿kali)-[~/Parcial3]
└─$ mkdir johnpollard
                                                                                   
┌──(kali㉿kali)-[~/Parcial3]
└─$ cd johnpollard 
                                                                                   
┌──(kali㉿kali)-[~/Parcial3/johnpollard]
└─$ wget https://jupiter.challenges.picoctf.org/static/c882787a19ed5d627eea50f318d87ac5/cert    
--2024-11-15 22:21:22--  https://jupiter.challenges.picoctf.org/static/c882787a19ed5d627eea50f318d87ac5/cert
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 725 [application/octet-stream]
Saving to: ‘cert’

cert                 100%[=====================>]     725  --.-KB/s    in 0s      

2024-11-15 22:21:23 (2.87 MB/s) - ‘cert’ saved [725/725]

                                                                                   
┌──(kali㉿kali)-[~/Parcial3/johnpollard]
└─$ ls
cert
                                                                                   
┌──(kali㉿kali)-[~/Parcial3/johnpollard]
└─$ file cert          
cert: PEM certificate
                                                                                   
┌──(kali㉿kali)-[~/Parcial3/johnpollard]
└─$ cat cert       
-----BEGIN CERTIFICATE-----
MIIB6zCB1AICMDkwDQYJKoZIhvcNAQECBQAwEjEQMA4GA1UEAxMHUGljb0NURjAe
Fw0xOTA3MDgwNzIxMThaFw0xOTA2MjYxNzM0MzhaMGcxEDAOBgNVBAsTB1BpY29D
VEYxEDAOBgNVBAoTB1BpY29DVEYxEDAOBgNVBAcTB1BpY29DVEYxEDAOBgNVBAgT
B1BpY29DVEYxCzAJBgNVBAYTAlVTMRAwDgYDVQQDEwdQaWNvQ1RGMCIwDQYJKoZI
hvcNAQEBBQADEQAwDgIHEaTUUhKxfwIDAQABMA0GCSqGSIb3DQEBAgUAA4IBAQAH
al1hMsGeBb3rd/Oq+7uDguueopOvDC864hrpdGubgtjv/hrIsph7FtxM2B4rkkyA
eIV708y31HIplCLruxFdspqvfGvLsCynkYfsY70i6I/dOA6l4Qq/NdmkPDx7edqO
T/zK4jhnRafebqJucXFH8Ak+G6ASNRWhKfFZJTWj5CoyTMIutLU9lDiTXng3rDU1
BhXg04ei1jvAf0UrtpeOA6jUyeCLaKDFRbrOm35xI79r28yO8ng1UAzTRclvkORt
b8LMxw7e+vdIntBGqf7T25PLn/MycGPPvNXyIsTzvvY/MXXJHnAqpI5DlqwzbRHz
q16/S1WLvzg4PsElmv1f
-----END CERTIFICATE-----
                                                                                   
┌──(kali㉿kali)-[~/Parcial3/johnpollard]
└─$ openssl x509 -pubkey -in cert -out cert.pub 
                                                                            
┌──(kali㉿kali)-[~/Parcial3/johnpollard]
└─$ openssl rsa -pubin -in cert.pub -text       
Public-Key: (53 bit)
Modulus: 4966306421059967 (0x11a4d45212b17f)
Exponent: 65537 (0x10001)
writing RSA key
-----BEGIN PUBLIC KEY-----
MCIwDQYJKoZIhvcNAQEBBQADEQAwDgIHEaTUUhKxfwIDAQAB
-----END PUBLIC KEY-----

```
- Copiamos el valor de `Modulus` e ingresamos a la siguiente pagina: [Alpertron](https://www.alpertron.com.ar/ECM.HTM) para factorizar el valor, obteniendo lo siguiente, `4966 306421 059967 = 67 867967 × 73 176001`.

```
┌──(kali㉿kali)-[~/Parcial3/johnpollard]
└─$ echo '73176001,67867967'            
73176001,67867967
                                                                            
┌──(kali㉿kali)-[~/Parcial3/johnpollard]
└─$ echo 'picoCTF{73176001,67867967}'
picoCTF{73176001,67867967}
                                                                            
┌──(kali㉿kali)-[~/Parcial3/johnpollard]
└─$ 

```

- Flag: picoCTF{73176001,67867967}

## Notas Adicionales

Extraer la clave pública del certificado: `openssl x509 -pubkey -in cert -out cert.pub`

- **`openssl x509`**: Se utiliza para trabajar con certificados X.509.
- **`-pubkey`**: Este parámetro le indica a OpenSSL que debe extraer la clave pública del certificado.
- **`-in cert`**: Especifica el archivo de entrada, en este caso, el certificado `cert`.
- **`-out cert.pub`**: Especifica el archivo de salida donde se guardará la clave pública extraída, llamado `cert.pub`.

Tras ejecutar este comando, obtenemos un archivo `cert.pub` que contiene la clave pública en formato PEM.

Ver la clave pública en formato legible: `openssl rsa -pubin -in cert.pub -text`
- **`openssl rsa`**: Se utiliza para trabajar con claves RSA.
- **`-pubin`**: Le indica a OpenSSL que el archivo de entrada es una clave pública.
- **`-in cert.pub`**: Especifica el archivo que contiene la clave pública (el archivo `cert.pub` que acabas de generar).
- **`-text`**: Muestra la clave en formato de texto legible.
## Referencias 
https://play.picoctf.org/practice/challenge/6
https://www.alpertron.com.ar/ECM.HTM
