## Descripción
I stopped using YellowPages and moved onto WhitePages... but [the page they gave me](https://jupiter.challenges.picoctf.org/static/fa4a277cfa846e07a5981d8a19288a2e/whitepages.txt) is all blank!

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
┌──(kali㉿kali)-[~/retosForensic]
└─$ mkdir WithePages
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic]
└─$ cd WithePages   
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic/WithePages]
└─$ wget https://jupiter.challenges.picoctf.org/static/fa4a277cfa846e07a5981d8a19288a2e/whitepages.txt
--2024-10-01 16:15:58--  https://jupiter.challenges.picoctf.org/static/fa4a277cfa846e07a5981d8a19288a2e/whitepages.txt
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2982 (2.9K) [application/octet-stream]
Saving to: ‘whitepages.txt’

whitepages.txt                            100%[===================================================================================>]   2.91K  --.-KB/s    in 0s      

2024-10-01 16:15:58 (51.7 MB/s) - ‘whitepages.txt’ saved [2982/2982]

                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic/WithePages]
└─$ ls
whitepages.txt
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic/WithePages]
└─$ cat whitepages.txt 
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic/WithePages]
└─$ xxd -l 100  whitepages.txt
00000000: e280 83e2 8083 e280 83e2 8083 20e2 8083  ............ ...
00000010: 20e2 8083 e280 83e2 8083 e280 83e2 8083   ...............
00000020: 20e2 8083 e280 8320 e280 83e2 8083 e280   ...... ........
00000030: 83e2 8083 20e2 8083 e280 8320 e280 8320  .... ...... ... 
00000040: 2020 e280 83e2 8083 e280 83e2 8083 e280    ..............
00000050: 8320 20e2 8083 20e2 8083 e280 8320 e280  .  ... ...... ..
00000060: 8320 20e2                                .  .
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic/WithePages]
└─$ sed 's/\xe2\x80\x83/0/g' whitepages.txt 
0000 0 00000 00 0000 00 0   00000  0 00 0  000  0  0    0 0000  0 0 0 000 000  00000 0 00000 0 00000 00 0000 00 0 0 00  0 000 0 0 000 0 00 000000 0 00000 0 0 0 0 0000 00 00  000 00 00 0 0000  00 000000 0 00 00 000 0 0 0000  0 00    0 0 00 00 000 000 0 00  00 0000000 00  000 000000 0000 00 00000 0 0000  0 00 0  0 000   0 0 00 00 00    0 0 0 0 0 00   00 000 0000 000000 0 00 00 000 0 0 0 00000 00    0 0 00 00 0 0 000000 0 00000 00 0000 00 00  0 0 00  000000  000000  000000 000000 000  00  0    0   00 00  000 00  00 0 0   00  00 000000 00000 0   0  00  00 0 00 0  0000 000000 0 00000  0 00 0   0 000   0 000   00  0  000 00   0 0 0   00 00  00   0  0 00000 0  0000 000000 0 00000 00000 00 0000000  000 00  0 0 00  00 000  000 00  00  0000 0 00000 00 0000 00 0   00000  0 00 0  000  0  0    0 0000  0 0 0 000 000  00    0  0  0   00  0    0   0 000 0     0  0000 0  0  000  0  000 0     0   00  0   00000  0000 0  000  0  00 0 0   00  0 0     0  0000 0   00 00  00 0 0 0     0  000  0   00 00  00 0 0  0000 0   0 000  00 0 0  00 000 0     0  00 0 0   000 0   0 0 0  0000 0  0  000 0     00  00  0  00 0 00  00 000  0 0000  00 000  00  00  000000   00000  000 0  00 000  00  000   00 0  0000 0  00 000  0000 0  000 000  00 00  0000 00   00 0  00 0000   00 00  0  00  0000 0  00  00  00 000  0000 00  0 000  000  0  00  00  0000 0  00 0000  0  00     0 0000 0 00000 00 0000 00                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosForensic/WithePages]
└─$ sed 's/\xe2\x80\x83/0/g' whitepages.txt | sed 's/\x20/1/g'
00001010000010010000100101110000011010010110001101101111010000110101010001000110000010100000101000001001000010010101001101000101010001010010000001010000010101010100001001001100010010010100001100100000010100100100010101000011010011110101001001000100010100110010000000100110001000000100001001000001010000110100101101000111010100100100111101010101010011100100010000100000010100100100010101010000010011110101001001010100000010100000100100001001001101010011000000110000001100000010000001000110011011110111001001100010011001010111001100100000010000010111011001100101001011000010000001010000011010010111010001110100011100110110001001110101011100100110011101101000001011000010000001010000010000010010000000110001001101010011001000110001001100110000101000001001000010010111000001101001011000110110111101000011010101000100011001111011011011100110111101110100010111110110000101101100011011000101111101110011011100000110000101100011011001010111001101011111011000010111001001100101010111110110001101110010011001010110000101110100011001010110010001011111011001010111000101110101011000010110110001011111001100110110010100110010001101000011001000110011001100000011100000110001011001000110011000111001011000010110010001100001011000100011001001100001001110010110010000111001001101100110000101100110011001000110000100110100011000110110011001100001011001000011011001111101000010100000100100001001  

```

- Buscamos una pagina para traducir el binario que encontramos:
	**Texto resultado:**  
	picoCTF SEE PUBLIC RECORDS & BACKGROUND REPORT 5000 Forbes Ave, Pittsburgh, PA 15213 picoCTF{not_all_spaces_are_created_equal_3e2423081df9adab2a9d96afda4cfad6}
## Notas Adicionales
El comando `xxd -l 100 whitepages.txt` se utiliza en sistemas Unix/Linux para mostrar el contenido del archivo `whitepages.txt` en formato hexadecimal.
-  `xxd`: Es una herramienta que convierte un archivo binario a formato hexadecimal y viceversa.
- `-l 100`: Indica que solo se deben leer los primeros 100 bytes del archivo.
- `whitepages.txt`: Es el archivo que se va a procesar.

El comando `sed 's/\xe2\x80\x83/0/g' whitepages.txt` utiliza la herramienta `sed` para buscar y reemplazar texto en el archivo `whitepages.txt`.
- `sed`: Es un editor de texto de línea de comandos que se utiliza para manipular texto.
    - `s/`: Indica que se va a hacer una sustitución.
    - `\xe2\x80\x83`: Es la representación hexadecimal de un carácter en UTF-8, específicamente un espacio de ancho fijo (también conocido como "en quad space").
    - `/0/`: Indica que se reemplazará el carácter encontrado por el número `0`.
    - `/g`: Significa que la sustitución se aplicará a todas las ocurrencias en cada línea del archivo.
- `whitepages.txt`: Es el archivo que se está procesando.

El comando `sed 's/\xe2\x80\x83/0/g' whitepages.txt | sed 's/\x20/1/g'` consiste en una tubería (pipe) que encadena dos comandos `sed` para procesar el archivo `whitepages.txt`. 

1. **Primer comando:**
    - `sed 's/\xe2\x80\x83/0/g' whitepages.txt`
    - Este comando busca y reemplaza todos los espacios de ancho fijo (representados como `\xe2\x80\x83`) por el carácter `0` en el archivo `whitepages.txt`.
2. **Pipe (`|`):**
    - La salida del primer comando se envía como entrada al segundo comando.
3. **Segundo comando:**
    - `sed 's/\x20/1/g'`
    - Este comando busca todos los espacios en blanco normales (representados como `\x20`, que es el carácter ASCII para un espacio) en la salida del primer comando y los reemplaza por el carácter `1`.

## Referencias 
https://play.picoctf.org/practice/challenge/51?page=1&search=Wh
[Cómo utilizar el comando sed de Linux: ejemplos y casos de uso (hostinger.es)](https://www.hostinger.es/tutoriales/el-comando-sed-de-linux-usos-y-ejemplos/#:~:text=El%20editor%20de%20secuencias%20o%20comando%20sed%20en)
[Traductor Binario | Traduce de binario a texto o de texto a binario fácilmente](https://www.traductorbinario.com/#google_vignette)
