## Descripción 
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key). Recover the flag.

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
                                                                                 
┌──(kali㉿kali)-[~/retosForensic]
└─$ mkdir webnet1
                                                                                 
┌──(kali㉿kali)-[~/retosForensic]
└─$ cd webnet1      
                                                                                 
┌──(kali㉿kali)-[~/retosForensic/webnet1]
└─$ wget https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap
--2024-10-09 10:20:52--  https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 92525 (90K) [application/octet-stream]
Saving to: ‘capture.pcap’

capture.pcap         100%[===================>]  90.36K  --.-KB/s    in 0.09s   

2024-10-09 10:20:53 (954 KB/s) - ‘capture.pcap’ saved [92525/92525]

                                                                                 
┌──(kali㉿kali)-[~/retosForensic/webnet1]
└─$ wget https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key
--2024-10-09 10:21:01--  https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1704 (1.7K) [application/octet-stream]
Saving to: ‘picopico.key’

picopico.key         100%[===================>]   1.66K  --.-KB/s    in 0s      

2024-10-09 10:21:01 (53.0 MB/s) - ‘picopico.key’ saved [1704/1704]

                                                                                 
┌──(kali㉿kali)-[~/retosForensic/webnet1]
└─$ wireshark capture.pcap 


```

- En la herramienta `wireshark` nos vamos al apartado de `Edit` ahí buscamos la opción de `preferencias`, ingresamos a `RSA Keys` agregamos una nueva key (la que descargamos junto con el paquete del reto, además de eso, en caso de que aun tengamos la key del reto pasado, es mejor removerla, ya que puede generar algunos problemas.)
- Podremos notar que ahora hay algunas filas que se resaltan de color verde, debemos inspeccionar dentro de ellas.
- En el protocolo HTTP de longitud 532, damos click derecho, le damos a `follow` y elegimos el `TLS Stream` ahi encontraremos la bandera.
```bash
GET /starter-template.css HTTP/1.1
Host: ec2-18-223-184-200.us-east-2.compute.amazonaws.com
User-Agent: Mozilla/5.0 (Macintosh; Intel Mac OS X 10.14; rv:68.0) Gecko/20100101 Firefox/68.0
Accept: text/css,*/*;q=0.1
Accept-Language: en-US,en;q=0.5
Accept-Encoding: gzip, deflate, br
Connection: keep-alive
Referer: https://ec2-18-223-184-200.us-east-2.compute.amazonaws.com/second.html
Pragma: no-cache
Cache-Control: no-cache

HTTP/1.1 200 OK
Date: Fri, 23 Aug 2019 16:27:04 GMT
Server: Apache/2.4.29 (Ubuntu)
Last-Modified: Mon, 12 Aug 2019 16:47:05 GMT
ETag: "62-58fee462bf227-gzip"
Accept-Ranges: bytes
Vary: Accept-Encoding
Content-Encoding: gzip
Pico-Flag: picoCTF{this.is.not.your.flag.anymore}
Content-Length: 100
Keep-Alive: timeout=5, max=100
Connection: Keep-Alive
Content-Type: text/css

......JFIF..............Exif..MM.*.................J...........R.(...........;.........Z................................picoCTF{honey.roasted.peanuts}......ICC_PROFILE.......lcms....mntrRGB XYZ .........).9acspAPPL...................................-lcms...............................................

desc.......^cprt...\....wtpt...h....bkpt...|....rXYZ........gXYZ........bXYZ........rTRC.......@gTRC.......@bTRC.......@desc........c2..................................................................................text....FB..XYZ ...............-XYZ ...........3....XYZ ......o...8.....XYZ ......b.........XYZ ......$.........curv...............c...k...?.Q.4!.).2.;.F.Qw].kpz....|.i.}...0.....C.................

...

.
```
- picoCTF{honey.roasted.peanuts}
## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/42
