## Descripción 
We found this [file](https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery). Recover the flag.

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
┌──(kali㉿kali)-[~/retosForensic/c0rrupt]
└─$ file mystery | head 
mystery: data
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosForensic/c0rrupt]
└─$ xxd mystery | head
00000000: 8965 4e34 0d0a b0aa 0000 000d 4322 4452  .eN4........C"DR
00000010: 0000 066a 0000 0447 0802 0000 007c 8bab  ...j...G.....|..
00000020: 7800 0000 0173 5247 4200 aece 1ce9 0000  x....sRGB.......
00000030: 0004 6741 4d41 0000 b18f 0bfc 6105 0000  ..gAMA......a...
00000040: 0009 7048 5973 aa00 1625 0000 1625 0149  ..pHYs...%...%.I
00000050: 5224 f0aa aaff a5ab 4445 5478 5eec bd3f  R$......DETx^..?
00000060: 8e64 cd71 bd2d 8b20 2080 9041 8302 08d0  .d.q.-.  ..A....
00000070: f9ed 40a0 f36e 407b 9023 8f1e d720 8b3e  ..@..n@{.#... .>
00000080: b7c1 0d70 0374 b503 ae41 6bf8 bea8 fbdc  ...p.t...Ak.....
00000090: 3e7d 2a22 336f de5b 55dd 3d3d f920 9188  >}*"3o.[U.==. ..
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosForensic/c0rrupt]
└─$ hexeditor mystery   
                                                                                 
┌──(kali㉿kali)-[~/retosForensic/c0rrupt]
└─$ file mystery        
mystery: data
                                                                                 
┌──(kali㉿kali)-[~/retosForensic/c0rrupt]
└─$ hexeditor mystery
                                                                                 
┌──(kali㉿kali)-[~/retosForensic/c0rrupt]
└─$ file mystery     
mystery: PNG image data, 1642 x 1095, 8-bit/color RGB, non-interlaced
                                                                                 
┌──(kali㉿kali)-[~/retosForensic/c0rrupt]
└─$ open mistery
                                                                                 
┌──(kali㉿kali)-[~/retosForensic/c0rrupt]
└─$ sudo apt install pngcheck        
[sudo] password for kali: 
The following packages were automatically installed and are no longer required:
  ibverbs-providers        libglusterfs0     python3.11-dev
  libboost-iostreams1.83.0 libibverbs1       python3.11-minimal
  libboost-thread1.83.0    libpython3.11-dev samba-ad-provision
  libcephfs2               librados2         samba-dsdb-modules
  libgfapi0                librdmacm1t64     samba-vfs-modules
  libgfrpc0                python3-lib2to3
  libgfxdr0                python3.11
Use 'sudo apt autoremove' to remove them.

Installing:
  pngcheck
                                                                                 
Summary:
  Upgrading: 0, Installing: 1, Removing: 0, Not Upgrading: 1261
  Download size: 68.6 kB
  Space needed: 208 kB / 9101 MB available

Get:1 http://kali.download/kali kali-rolling/main amd64 pngcheck amd64 3.0.3-3 [68.6 kB]
Fetched 68.6 kB in 1s (49.9 kB/s)
Selecting previously unselected package pngcheck.
(Reading database ... 395358 files and directories currently installed.)
Preparing to unpack .../pngcheck_3.0.3-3_amd64.deb ...
Unpacking pngcheck (3.0.3-3) ...
Setting up pngcheck (3.0.3-3) ...
Processing triggers for man-db (2.12.1-1) ...
Processing triggers for kali-menu (2023.4.7) ...
                                                                                 
┌──(kali㉿kali)-[~/retosForensic/c0rrupt]
└─$ pngcheck -v mystery 
zlib warning:  different version (expected 1.2.13, using 1.3)

File: mystery (202940 bytes)
  chunk IHDR at offset 0x0000c, length 13
    1642 x 1095 image, 24-bit RGB, non-interlaced
  chunk sRGB at offset 0x00025, length 1
    rendering intent = perceptual
  chunk gAMA at offset 0x00032, length 4: 0.45455
  chunk pHYs at offset 0x00042, length 9: 2852132389x5669 pixels/meter
  CRC error in chunk pHYs (computed 38d82c82, expected 495224f0)
ERRORS DETECTED in mystery
                                                                                 
┌──(kali㉿kali)-[~/retosForensic/c0rrupt]
└─$ hexeditor mystery        
                                                                                 
┌──(kali㉿kali)-[~/retosForensic/c0rrupt]
└─$ hexeditor mystery
                                                                                 
┌──(kali㉿kali)-[~/retosForensic/c0rrupt]
└─$ open mystery 
                                                                                 
┌──(kali㉿kali)-[~/retosForensic/c0rrupt]
└─$ hexeditor mystery

```
- Así es como queda el hexadecimal del archivo
```bash
00000000  89 50 4E 47  0D 0A 1A 0A   00 00 00 0D  49 48 44 52    .PNG........IHDR
00000010  00 00 06 6A  00 00 04 47   08 02 00 00  00 7C 8B AB    ...j...G.....|..
00000020  78 00 00 00  01 73 52 47   42 00 AE CE  1C E9 00 00    x....sRGB.......
00000030  00 04 67 41  4D 41 00 00   B1 8F 0B FC  61 05 00 00    ..gAMA......a...
00000040  00 09 70 48  59 73 00 00   16 25 00 00  16 25 01 49    ..pHYs...%...%.I
00000050  52 24 F0 00  00 FF A5 49   44 41 54 78  5E EC BD 3F    R$.....IDATx^..?
```
- Flag
	```bash
	┌──(kali㉿kali)-[~/retosForensic/c0rrupt]
	└─$ picoCTF{c0rrupt10n_1847995}           
	picoCTF{c0rrupt10n_1847995}: command not found

	```
## Notas Adicionales
`pngcheck` es una herramienta de línea de comandos utilizada para verificar y analizar archivos PNG (Portable Network Graphics). Su propósito principal es asegurarse de que un archivo PNG sea válido y esté libre de errores, así como proporcionar detalles técnicos sobre la estructura interna del archivo. Algunas de sus funciones más comunes incluyen:

1. **Verificación de integridad**: `pngcheck` analiza si el archivo PNG está correctamente formado, es decir, si su encabezado, bloques de datos y estructura están bien construidos, sin corrupción.
    
2. **Mostrar información del archivo**: Proporciona detalles sobre el archivo PNG, como el tipo de color (por ejemplo, RGB, índice de color), la profundidad de bits, el ancho y la altura de la imagen, entre otros.
    
3. **Detectar errores o daños**: Si un archivo PNG está dañado o incompleto, `pngcheck` puede identificar problemas específicos, como errores en los bloques de datos, en la tabla de colores, etc.

## Referencias 
https://play.picoctf.org/practice/challenge/53
https://www.youtube.com/watch?v=7zY4VkiWbBI&list=PLDo9DMLZyP6kTZ8Td37-LdbAx4-yNfHBl&index=21&t=433s
