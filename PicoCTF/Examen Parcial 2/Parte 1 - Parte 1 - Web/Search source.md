## Descripción 
The developer of this website mistakenly left an important artifact in the website source, can you find it?

Additional details will be available after launching your challenge instance.
## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
┌──(kali㉿kali)-[~/Parcial2/Search]
└─$ wget -r http://saturn.picoctf.net:54958
--2024-10-13 15:15:57--  http://saturn.picoctf.net:54958/
Resolving saturn.picoctf.net (saturn.picoctf.net)... 13.59.203.175
Connecting to saturn.picoctf.net (saturn.picoctf.net)|13.59.203.175|:54958... connected.
HTTP request sent, awaiting response... 200 OK
Length: 15920 (16K) [text/html]
Saving to: ‘saturn.picoctf.net:54958/index.html’

saturn.picoctf.net:54958/index.html       100%[===================================================================================>]  15.55K  --.-KB/s    in 0.05s   

2024-10-13 15:15:57 (326 KB/s) - ‘saturn.picoctf.net:54958/index.html’ saved [15920/15920]

Loading robots.txt; please ignore errors.
--2024-10-13 15:15:57--  http://saturn.picoctf.net:54958/robots.txt
Reusing existing connection to saturn.picoctf.net:54958.
HTTP request sent, awaiting response... 404 Not Found
2024-10-13 15:15:57 ERROR 404: Not Found.

--2024-10-13 15:15:57--  http://saturn.picoctf.net:54958/css/bootstrap.min.css
Reusing existing connection to saturn.picoctf.net:54958.
HTTP request sent, awaiting response... 200 OK
Length: 140421 (137K) [text/css]
Saving to: ‘saturn.picoctf.net:54958/css/bootstrap.min.css’

saturn.picoctf.net:54958/css/bootstrap.mi 100%[===================================================================================>] 137.13K  --.-KB/s    in 0.1s    

2024-10-13 15:15:57 (919 KB/s) - ‘saturn.picoctf.net:54958/css/bootstrap.min.css’ saved [140421/140421]

--2024-10-13 15:15:57--  http://saturn.picoctf.net:54958/css/owl.carousel.min.css
Reusing existing connection to saturn.picoctf.net:54958.
HTTP request sent, awaiting response... 200 OK
Length: 3351 (3.3K) [text/css]
Saving to: ‘saturn.picoctf.net:54958/css/owl.carousel.min.css’

saturn.picoctf.net:54958/css/owl.carousel 100%[===================================================================================>]   3.27K  --.-KB/s    in 0.005s  

2024-10-13 15:15:57 (621 KB/s) - ‘saturn.picoctf.net:54958/css/owl.carousel.min.css’ saved [3351/3351]

--2024-10-13 15:15:57--  http://saturn.picoctf.net:54958/css/style.css
Reusing existing connection to saturn.picoctf.net:54958.
HTTP request sent, awaiting response... 200 OK
Length: 10449 (10K) [text/css]
Saving to: ‘saturn.picoctf.net:54958/css/style.css’

saturn.picoctf.net:54958/css/style.css    100%[===================================================================================>]  10.20K  --.-KB/s    in 0.007s  

2024-10-13 15:15:57 (1.33 MB/s) - ‘saturn.picoctf.net:54958/css/style.css’ saved [10449/10449]

--2024-10-13 15:15:57--  http://saturn.picoctf.net:54958/css/responsive.css
Reusing existing connection to saturn.picoctf.net:54958.
HTTP request sent, awaiting response... 200 OK
Length: 8660 (8.5K) [text/css]
Saving to: ‘saturn.picoctf.net:54958/css/responsive.css’

saturn.picoctf.net:54958/css/responsive.c 100%[===================================================================================>]   8.46K  --.-KB/s    in 0.009s  

2024-10-13 15:15:57 (976 KB/s) - ‘saturn.picoctf.net:54958/css/responsive.css’ saved [8660/8660]

--2024-10-13 15:15:57--  http://saturn.picoctf.net:54958/images/loading.gif
Reusing existing connection to saturn.picoctf.net:54958.
HTTP request sent, awaiting response... 200 OK
Length: 35499 (35K) [image/gif]
Saving to: ‘saturn.picoctf.net:54958/images/loading.gif’

saturn.picoctf.net:54958/images/loading.g 100%[===================================================================================>]  34.67K  --.-KB/s    in 0.005s  

2024-10-13 15:15:58 (6.16 MB/s) - ‘saturn.picoctf.net:54958/images/loading.gif’ saved [35499/35499]

--2024-10-13 15:15:58--  http://saturn.picoctf.net:54958/images/mail_icon.png
Reusing existing connection to saturn.picoctf.net:54958.
HTTP request sent, awaiting response... 200 OK
Length: 1717 (1.7K) [image/png]
Saving to: ‘saturn.picoctf.net:54958/images/mail_icon.png’

saturn.picoctf.net:54958/images/mail_icon 100%[===================================================================================>]   1.68K  --.-KB/s    in 0.008s  

2024-10-13 15:15:58 (201 KB/s) - ‘saturn.picoctf.net:54958/images/mail_icon.png’ saved [1717/1717]

--2024-10-13 15:15:58--  http://saturn.picoctf.net:54958/index.html
Reusing existing connection to saturn.picoctf.net:54958.
HTTP request sent, awaiting response... 200 OK
Length: 15920 (16K) [text/html]
Saving to: ‘saturn.picoctf.net:54958/index.html’

saturn.picoctf.net:54958/index.html       100%[===================================================================================>]  15.55K  --.-KB/s    in 0.01s   

2024-10-13 15:15:58 (1.33 MB/s) - ‘saturn.picoctf.net:54958/index.html’ saved [15920/15920]

--2024-10-13 15:15:58--  http://saturn.picoctf.net:54958/images/logo.png
Reusing existing connection to saturn.picoctf.net:54958.
HTTP request sent, awaiting response... 200 OK
Length: 5009 (4.9K) [image/png]
Saving to: ‘saturn.picoctf.net:54958/images/logo.png’

saturn.picoctf.net:54958/images/logo.png  100%[===================================================================================>]   4.89K  --.-KB/s    in 0.006s  

2024-10-13 15:15:58 (884 KB/s) - ‘saturn.picoctf.net:54958/images/logo.png’ saved [5009/5009]

--2024-10-13 15:15:58--  http://saturn.picoctf.net:54958/images/phone_icon.png
Reusing existing connection to saturn.picoctf.net:54958.
HTTP request sent, awaiting response... 200 OK
Length: 2277 (2.2K) [image/png]
Saving to: ‘saturn.picoctf.net:54958/images/phone_icon.png’

saturn.picoctf.net:54958/images/phone_ico 100%[===================================================================================>]   2.22K  --.-KB/s    in 0.004s  

2024-10-13 15:15:58 (541 KB/s) - ‘saturn.picoctf.net:54958/images/phone_icon.png’ saved [2277/2277]

--2024-10-13 15:15:58--  http://saturn.picoctf.net:54958/images/banner.jpg
Reusing existing connection to saturn.picoctf.net:54958.
HTTP request sent, awaiting response... 200 OK
Length: 62595 (61K) [image/jpeg]
Saving to: ‘saturn.picoctf.net:54958/images/banner.jpg’

saturn.picoctf.net:54958/images/banner.jp 100%[===================================================================================>]  61.13K  --.-KB/s    in 0.02s   

2024-10-13 15:15:58 (3.70 MB/s) - ‘saturn.picoctf.net:54958/images/banner.jpg’ saved [62595/62595]

--2024-10-13 15:15:58--  http://saturn.picoctf.net:54958/images/1.png
Reusing existing connection to saturn.picoctf.net:54958.
HTTP request sent, awaiting response... 200 OK
Length: 23667 (23K) [image/png]
Saving to: ‘saturn.picoctf.net:54958/images/1.png’

saturn.picoctf.net:54958/images/1.png     100%[===================================================================================>]  23.11K  --.-KB/s    in 0.01s   

2024-10-13 15:15:58 (2.25 MB/s) - ‘saturn.picoctf.net:54958/images/1.png’ saved [23667/23667]

--2024-10-13 15:15:58--  http://saturn.picoctf.net:54958/images/2.png
Reusing existing connection to saturn.picoctf.net:54958.
HTTP request sent, awaiting response... 200 OK
Length: 23992 (23K) [image/png]
Saving to: ‘saturn.picoctf.net:54958/images/2.png’

saturn.picoctf.net:54958/images/2.png     100%[===================================================================================>]  23.43K  --.-KB/s    in 0.01s   

2024-10-13 15:15:58 (2.12 MB/s) - ‘saturn.picoctf.net:54958/images/2.png’ saved [23992/23992]

--2024-10-13 15:15:58--  http://saturn.picoctf.net:54958/images/3.png
Reusing existing connection to saturn.picoctf.net:54958.
HTTP request sent, awaiting response... 200 OK
Length: 50839 (50K) [image/png]
Saving to: ‘saturn.picoctf.net:54958/images/3.png’

saturn.picoctf.net:54958/images/3.png     100%[===================================================================================>]  49.65K  --.-KB/s    in 0.02s   

2024-10-13 15:15:58 (2.46 MB/s) - ‘saturn.picoctf.net:54958/images/3.png’ saved [50839/50839]

--2024-10-13 15:15:58--  http://saturn.picoctf.net:54958/js/jquery.min.js
Reusing existing connection to saturn.picoctf.net:54958.
HTTP request sent, awaiting response... 200 OK
Length: 87088 (85K) [application/javascript]
Saving to: ‘saturn.picoctf.net:54958/js/jquery.min.js’

saturn.picoctf.net:54958/js/jquery.min.js 100%[===================================================================================>]  85.05K  --.-KB/s    in 0.03s   

2024-10-13 15:15:58 (2.64 MB/s) - ‘saturn.picoctf.net:54958/js/jquery.min.js’ saved [87088/87088]

--2024-10-13 15:15:58--  http://saturn.picoctf.net:54958/js/popper.min.js
Reusing existing connection to saturn.picoctf.net:54958.
HTTP request sent, awaiting response... 200 OK
Length: 19190 (19K) [application/javascript]
Saving to: ‘saturn.picoctf.net:54958/js/popper.min.js’

saturn.picoctf.net:54958/js/popper.min.js 100%[===================================================================================>]  18.74K  --.-KB/s    in 0.01s   

2024-10-13 15:15:58 (1.38 MB/s) - ‘saturn.picoctf.net:54958/js/popper.min.js’ saved [19190/19190]

--2024-10-13 15:15:58--  http://saturn.picoctf.net:54958/js/bootstrap.bundle.min.js
Reusing existing connection to saturn.picoctf.net:54958.
HTTP request sent, awaiting response... 200 OK
Length: 70808 (69K) [application/javascript]
Saving to: ‘saturn.picoctf.net:54958/js/bootstrap.bundle.min.js’

saturn.picoctf.net:54958/js/bootstrap.bun 100%[===================================================================================>]  69.15K  --.-KB/s    in 0.03s   

2024-10-13 15:15:58 (2.61 MB/s) - ‘saturn.picoctf.net:54958/js/bootstrap.bundle.min.js’ saved [70808/70808]

--2024-10-13 15:15:58--  http://saturn.picoctf.net:54958/js/owl.carousel.min.js
Reusing existing connection to saturn.picoctf.net:54958.
HTTP request sent, awaiting response... 200 OK
Length: 44342 (43K) [application/javascript]
Saving to: ‘saturn.picoctf.net:54958/js/owl.carousel.min.js’

saturn.picoctf.net:54958/js/owl.carousel. 100%[===================================================================================>]  43.30K  --.-KB/s    in 0.02s   

2024-10-13 15:15:59 (2.26 MB/s) - ‘saturn.picoctf.net:54958/js/owl.carousel.min.js’ saved [44342/44342]

--2024-10-13 15:15:59--  http://saturn.picoctf.net:54958/js/custom.js
Reusing existing connection to saturn.picoctf.net:54958.
HTTP request sent, awaiting response... 200 OK
Length: 7781 (7.6K) [application/javascript]
Saving to: ‘saturn.picoctf.net:54958/js/custom.js’

saturn.picoctf.net:54958/js/custom.js     100%[===================================================================================>]   7.60K  --.-KB/s    in 0.007s  

2024-10-13 15:15:59 (1.03 MB/s) - ‘saturn.picoctf.net:54958/js/custom.js’ saved [7781/7781]

--2024-10-13 15:15:59--  http://saturn.picoctf.net:54958/js/jquery.mCustomScrollbar.concat.min.js
Reusing existing connection to saturn.picoctf.net:54958.
HTTP request sent, awaiting response... 200 OK
Length: 45479 (44K) [application/javascript]
Saving to: ‘saturn.picoctf.net:54958/js/jquery.mCustomScrollbar.concat.min.js’

saturn.picoctf.net:54958/js/jquery.mCusto 100%[===================================================================================>]  44.41K  --.-KB/s    in 0.02s   

2024-10-13 15:15:59 (2.24 MB/s) - ‘saturn.picoctf.net:54958/js/jquery.mCustomScrollbar.concat.min.js’ saved [45479/45479]

--2024-10-13 15:15:59--  http://saturn.picoctf.net:54958/js/jquery-3.0.0.min.js
Reusing existing connection to saturn.picoctf.net:54958.
HTTP request sent, awaiting response... 200 OK
Length: 11324 (11K) [application/javascript]
Saving to: ‘saturn.picoctf.net:54958/js/jquery-3.0.0.min.js’

saturn.picoctf.net:54958/js/jquery-3.0.0. 100%[===================================================================================>]  11.06K  --.-KB/s    in 0.02s   

2024-10-13 15:15:59 (707 KB/s) - ‘saturn.picoctf.net:54958/js/jquery-3.0.0.min.js’ saved [11324/11324]

--2024-10-13 15:15:59--  http://saturn.picoctf.net:54958/css/owl.video.play.png
Reusing existing connection to saturn.picoctf.net:54958.
HTTP request sent, awaiting response... 404 Not Found
2024-10-13 15:15:59 ERROR 404: Not Found.

--2024-10-13 15:15:59--  http://saturn.picoctf.net:54958/images/fevicon.png
Reusing existing connection to saturn.picoctf.net:54958.
HTTP request sent, awaiting response... 404 Not Found
2024-10-13 15:15:59 ERROR 404: Not Found.

FINISHED --2024-10-13 15:15:59--
Total wall clock time: 2.3s
Downloaded: 21 files, 670K in 0.4s (1.48 MB/s)
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2/Search]
└─$ ls
saturn.picoctf.net:54958
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2/Search]
└─$ cat saturn.picoctf.net:54958 | grep picoCTF
cat: 'saturn.picoctf.net:54958': Is a directory
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2/Search]
└─$ cat saturn.picoctf.net:54958 | grep -R picoCTF
cat: 'saturn.picoctf.net:54958': Is a directory
saturn.picoctf.net:54958/css/style.css:/** banner_main picoCTF{1nsp3ti0n_0f_w3bpag3s_587d12b8} **/
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2/Search]
└─$ 

```
## Notas Adicionales
El comando `wget -r` se utiliza para descargar recursivamente sitios web o directorios completos. La opción `-r` indica que la descarga se debe realizar de manera **recursiva**, lo que significa que `wget` no solo descargará la página principal, sino también las páginas relacionadas y otros archivos que se encuentren en el sitio web (por ejemplo, imágenes, hojas de estilo, scripts, etc.).

## Referencias 
https://play.picoctf.org/practice/challenge/295
[Wget Command in Linux with Examples | Linuxize](https://linuxize.com/post/wget-command-examples/)