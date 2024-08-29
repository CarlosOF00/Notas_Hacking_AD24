## Objetivo
The password for the next level can be retrieved by submitting the password of the current level to **port 30001 on localhost** using SSL/TLS encryption.

**Helpful note: Getting “DONE”, “RENEGOTIATING” or “KEYUPDATE”? Read the “CONNECTED COMMANDS” section in the manpage**
## Datos de Acceso al Nivel
user: bandit15
password: 8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo

## Solución
```
└─$ ssh bandit15@bandit.labs.overthewire.org -p 2220
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

bandit15@bandit.labs.overthewire.org's password: 

bandit15@bandit:~$ openssl s_client -connect localhost:30001
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = SnakeOil
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = SnakeOil
verify return:1
---
Certificate chain
 0 s:CN = SnakeOil
   i:CN = SnakeOil
   a:PKEY: rsaEncryption, 4096 (bit); sigalg: RSA-SHA256
   v:NotBefore: Jun 10 03:59:50 2024 GMT; NotAfter: Jun  8 03:59:50 2034 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIFBzCCAu+gAwIBAgIUBLz7DBxA0IfojaL/WaJzE6Sbz7cwDQYJKoZIhvcNAQEL
BQAwEzERMA8GA1UEAwwIU25ha2VPaWwwHhcNMjQwNjEwMDM1OTUwWhcNMzQwNjA4
MDM1OTUwWjATMREwDwYDVQQDDAhTbmFrZU9pbDCCAiIwDQYJKoZIhvcNAQEBBQAD
ggIPADCCAgoCggIBANI+P5QXm9Bj21FIPsQqbqZRb5XmSZZJYaam7EIJ16Fxedf+
jXAv4d/FVqiEM4BuSNsNMeBMx2Gq0lAfN33h+RMTjRoMb8yBsZsC063MLfXCk4p+
09gtGP7BS6Iy5XdmfY/fPHvA3JDEScdlDDmd6Lsbdwhv93Q8M6POVO9sv4HuS4t/
jEjr+NhE+Bjr/wDbyg7GL71BP1WPZpQnRE4OzoSrt5+bZVLvODWUFwinB0fLaGRk
GmI0r5EUOUd7HpYyoIQbiNlePGfPpHRKnmdXTTEZEoxeWWAaM1VhPGqfrB/Pnca+
vAJX7iBOb3kHinmfVOScsG/YAUR94wSELeY+UlEWJaELVUntrJ5HeRDiTChiVQ++
wnnjNbepaW6shopybUF3XXfhIb4NvwLWpvoKFXVtcVjlOujF0snVvpE+MRT0wacy
tHtjZs7Ao7GYxDz6H8AdBLKJW67uQon37a4MI260ADFMS+2vEAbNSFP+f6ii5mrB
18cY64ZaF6oU8bjGK7BArDx56bRc3WFyuBIGWAFHEuB948BcshXY7baf5jjzPmgz
mq1zdRthQB31MOM2ii6vuTkheAvKfFf+llH4M9SnES4NSF2hj9NnHga9V08wfhYc
x0W6qu+S8HUdVF+V23yTvUNgz4Q+UoGs4sHSDEsIBFqNvInnpUmtNgcR2L5PAgMB
AAGjUzBRMB0GA1UdDgQWBBTPo8kfze4P9EgxNuyk7+xDGFtAYzAfBgNVHSMEGDAW
gBTPo8kfze4P9EgxNuyk7+xDGFtAYzAPBgNVHRMBAf8EBTADAQH/MA0GCSqGSIb3
DQEBCwUAA4ICAQAKHomtmcGqyiLnhziLe97Mq2+Sul5QgYVwfx/KYOXxv2T8ZmcR
Ae9XFhZT4jsAOUDK1OXx9aZgDGJHJLNEVTe9zWv1ONFfNxEBxQgP7hhmDBWdtj6d
taqEW/Jp06X+08BtnYK9NZsvDg2YRcvOHConeMjwvEL7tQK0m+GVyQfLYg6jnrhx
egH+abucTKxabFcWSE+Vk0uJYMqcbXvB4WNKz9vj4V5Hn7/DN4xIjFko+nREw6Oa
/AUFjNnO/FPjap+d68H1LdzMH3PSs+yjGid+6Zx9FCnt9qZydW13Miqg3nDnODXw
+Z682mQFjVlGPCA5ZOQbyMKY4tNazG2n8qy2famQT3+jF8Lb6a4NGbnpeWnLMkIu
jWLWIkA9MlbdNXuajiPNVyYIK9gdoBzbfaKwoOfSsLxEqlf8rio1GGcEV5Hlz5S2
txwI0xdW9MWeGWoiLbZSbRJH4TIBFFtoBG0LoEJi0C+UPwS8CDngJB4TyrZqEld3
rH87W+Et1t/Nepoc/Eoaux9PFp5VPXP+qwQGmhir/hv7OsgBhrkYuhkjxZ8+1uk7
tUWC/XM0mpLoxsq6vVl3AJaJe1ivdA9xLytsuG4iv02Juc593HXYR8yOpow0Eq2T
U5EyeuFg5RXYwAPi7ykw1PW7zAPL4MlonEVz+QXOSx6eyhimp1VZC11SCg==
-----END CERTIFICATE-----
subject=CN = SnakeOil
issuer=CN = SnakeOil
---
No client certificate CA names sent
Peer signing digest: SHA256
Peer signature type: RSA-PSS
Server Temp Key: X25519, 253 bits
---
SSL handshake has read 2103 bytes and written 373 bytes
Verification error: self-signed certificate
---
New, TLSv1.3, Cipher is TLS_AES_256_GCM_SHA384
Server public key is 4096 bit
Secure Renegotiation IS NOT supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
Early data was not sent
Verify return code: 18 (self-signed certificate)
---
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: D85EAABD62C6B4497B4DE81D136E94E3F034CFB3232441F5E99BDAE69376AC34
    Session-ID-ctx: 
    Resumption PSK: CFEF0E316BECCAB0BF8B63BAF12DF47511BC58B9565BA02C2332D1F0639B448913784C37BD6DFED95BA9ECA4320A3E63
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 300 (seconds)
    TLS session ticket:
    0000 - 43 87 d0 c4 a5 49 95 26-c8 3e eb 08 d7 47 78 ca   C....I.&.>...Gx.
    0010 - 76 7b f8 02 d0 38 74 57-a8 85 a5 11 e9 b9 28 1d   v{...8tW......(.
    0020 - 69 74 b9 c1 3a 65 68 1a-05 ff 23 b6 6e 19 a1 fb   it..:eh...#.n...
    0030 - 3d 9a 44 91 7f 80 a3 42-85 5c cc c2 b9 88 8e 8f   =.D....B.\......
    0040 - de 32 cb 7b c7 66 54 3a-6d 87 1b 07 f6 5b 43 0e   .2.{.fT:m....[C.
    0050 - 1a e6 33 04 28 11 d0 0a-b4 66 37 2a d1 03 82 4e   ..3.(....f7*...N
    0060 - 7f a6 bb 42 95 44 c4 65-42 27 dd 62 0c 68 84 d2   ...B.D.eB'.b.h..
    0070 - f3 04 91 78 2d 05 5e b7-0c b9 a2 55 05 25 bd f5   ...x-.^....U.%..
    0080 - d4 3f ee 0e 1b 03 0b 3c-6b b5 07 48 c9 34 ae 4e   .?.....<k..H.4.N
    0090 - e3 97 b1 04 99 4e 5b 2c-99 09 a9 be ef 40 12 42   .....N[,.....@.B
    00a0 - c6 7d bc 10 08 76 77 5f-8f d1 4c 77 a0 fd 95 ee   .}...vw_..Lw....
    00b0 - c5 d4 2b 9f dd e2 fb 63-dc 21 0e 4a 4f 13 ad fd   ..+....c.!.JO...
    00c0 - 4f 22 c3 f9 ff 62 45 07-88 75 61 d0 36 ee 38 04   O"...bE..ua.6.8.
    00d0 - d1 1f a8 5f e9 01 36 14-dc dc c7 62 b4 fb 96 74   ..._..6....b...t

    Start Time: 1724951701
    Timeout   : 7200 (sec)
    Verify return code: 18 (self-signed certificate)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: 65E53F75C70B23177236FB8012CC33DF8E68E677BCEDB72F1FEE585A63E09F5E
    Session-ID-ctx: 
    Resumption PSK: B69BC39FB52A6699C3FE6CC321C7DBA27F902DFCA0719A4CB3F099C2B8910F0BD51AC8418D34D5E1AF12AD8502AC8339
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 300 (seconds)
    TLS session ticket:
    0000 - 43 87 d0 c4 a5 49 95 26-c8 3e eb 08 d7 47 78 ca   C....I.&.>...Gx.
    0010 - f4 16 18 44 a7 66 51 aa-a9 b5 ad 2f 6b ca 48 8d   ...D.fQ..../k.H.
    0020 - 68 d6 5c 66 eb 8f ef 04-fe 46 5e 88 86 82 04 07   h.\f.....F^.....
    0030 - 4d c1 4c 4e 35 93 57 0b-45 bc bd 5e 53 9b 01 30   M.LN5.W.E..^S..0
    0040 - 2b f7 19 a3 f0 01 02 61-84 4b 4e 4f ce e7 6b 0f   +......a.KNO..k.
    0050 - 02 5e 6d da 4f 3f ba bc-6e c8 66 5c e7 24 5a 2d   .^m.O?..n.f\.$Z-
    0060 - 6c 5c d7 4b 9b 48 ab 80-8b ad 8c b1 05 e3 02 1b   l\.K.H..........
    0070 - c2 60 9f f8 3b 14 27 79-a3 e2 84 63 d8 13 9f 74   .`..;.'y...c...t
    0080 - 1d 03 cb 26 fa 38 7f eb-95 a7 cc e9 4a 99 dd 43   ...&.8......J..C
    0090 - ee 98 b2 d9 26 2a 6f 4d-31 b1 62 6a cc 11 e5 9b   ....&*oM1.bj....
    00a0 - 6a 31 78 b5 c6 5d 53 8f-36 6c ee ae 79 e0 20 af   j1x..]S.6l..y. .
    00b0 - 41 8e a0 81 98 d5 02 b2-65 e9 e8 43 53 70 f4 3f   A.......e..CSp.?
    00c0 - 8c a1 06 f7 ec 00 c8 1a-b0 c1 6b 35 45 69 85 d4   ..........k5Ei..
    00d0 - 23 24 e5 f2 06 26 bb 40-b7 43 0f dd 18 33 5c 18   #$...&.@.C...3\.

    Start Time: 1724951702
    Timeout   : 7200 (sec)
    Verify return code: 18 (self-signed certificate)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo
Correct!
kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx

closed
bandit15@bandit:~$ 

```
## Notas Adicionales
**openssl**:  es una herramienta de línea de comandos que proporciona una variedad de funciones criptográficas, incluyendo la generación de claves, certificados, y el manejo de conexiones seguras con SSL/TLS.

**s_client**: es un subcomando de openssl que actúa como un cliente SSL/TLS. Se utiliza para conectarse a servidores que utilizan SSL/TLS para cifrar las comunicaciones. Esto es útil para probar y depurar la configuración de SSL/TLS de un servidor.

**connect localhost:30001**:
- connect es una opción que especifica el destino al que se debe conectar. En este caso, el destino es localhost en el puerto 30001.
- localhost se refiere a la máquina local en la que se está ejecutando el comando.
- 30001 es el número de puerto al que openssl s_client intentará conectarse en localhost.
## Referencias 
https://en.wikipedia.org/wiki/Transport_Layer_Security
https://www.feistyduck.com/library/openssl-cookbook/online/testing-with-openssl/index.html