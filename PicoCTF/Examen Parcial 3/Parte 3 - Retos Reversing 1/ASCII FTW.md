## Descripción 
This program has constructed the flag using hex ascii values. Identify the flag text by disassembling the program.You can download the file from [here](https://artifacts.picoctf.net/c/508/asciiftw).

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
┌──(kali㉿kali)-[~/Parcial3]
└─$ mkdir asciiftw 
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial3]
└─$ cd asciiftw 
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial3/asciiftw]
└─$ wget https://artifacts.picoctf.net/c/508/asciiftw
--2024-11-17 10:13:40--  https://artifacts.picoctf.net/c/508/asciiftw
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.249.21.46, 13.249.21.32, 13.249.21.85, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.249.21.46|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 16752 (16K) [application/octet-stream]
Saving to: ‘asciiftw’

asciiftw                                  100%[===================================================================================>]  16.36K  --.-KB/s    in 0s      

2024-11-17 10:13:40 (141 MB/s) - ‘asciiftw’ saved [16752/16752]

                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial3/asciiftw]
└─$ ls 
asciiftw
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial3/asciiftw]
└─$ file asciiftw      
asciiftw: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, BuildID[sha1]=e1c32dace8ac1516160b771e493f5ebffcac9855, for GNU/Linux 3.2.0, not stripped
┌──(kali㉿kali)-[~/Parcial3/asciiftw]
└─$ chmod +x asciiftw      
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial3/asciiftw]
└─$ ./asciiftw 
The flag starts with 

┌──(kali㉿kali)-[~/Parcial3/asciiftw]
└─$ cutter asciiftw&
[1] 71093
                   
```

- Se abrirá la herramienta de `Cutter`  y nos iremos al apartado izquierdo de funciones, ingresaremos a `Main` y abajo seleccionaremos la opción de `Disassembly`, navegando encontraremos la bandera de la siguiente manera:

```bash
0x00001184      mov     byte [var_38h], 0x70 ; 'p'
0x00001188      mov     byte [var_37h], 0x69 ; 'i'
0x0000118c      mov     byte [var_36h], 0x63 ; 'c'
0x00001190      mov     byte [var_35h], 0x6f ; 'o'
0x00001194      mov     byte [var_34h], 0x43 ; 'C'
0x00001198      mov     byte [var_33h], 0x54 ; 'T'
0x0000119c      mov     byte [var_32h], 0x46 ; 'F'
0x000011a0      mov     byte [var_31h], 0x7b ; '{'
0x000011a4      mov     byte [var_30h], 0x41 ; 'A'
0x000011a8      mov     byte [var_2fh], 0x53 ; 'S'
0x000011ac      mov     byte [var_2eh], 0x43 ; 'C'
0x000011b0      mov     byte [var_2dh], 0x49 ; 'I'
0x000011b4      mov     byte [var_2ch], 0x49 ; 'I'
0x000011b8      mov     byte [var_2bh], 0x5f ; '_'
0x000011bc      mov     byte [var_2ah], 0x49 ; 'I'
0x000011c0      mov     byte [var_29h], 0x53 ; 'S'
0x000011c4      mov     byte [var_28h], 0x5f ; '_'
0x000011c8      mov     byte [var_27h], 0x45 ; 'E'
0x000011cc      mov     byte [var_26h], 0x41 ; 'A'
0x000011d0      mov     byte [var_25h], 0x53 ; 'S'
0x000011d4      mov     byte [var_24h], 0x59 ; 'Y'
0x000011d8      mov     byte [var_23h], 0x5f ; '_'
0x000011dc      mov     byte [var_22h], 0x38 ; '8'
0x000011e0      mov     byte [var_21h], 0x39 ; '9'
0x000011e4      mov     byte [var_20h], 0x36 ; '6'
0x000011e8      mov     byte [var_1fh], 0x30 ; '0'
0x000011ec      mov     byte [var_1eh], 0x46 ; 'F'
0x000011f0      mov     byte [var_1dh], 0x30 ; '0'
0x000011f4      mov     byte [var_1ch], 0x41 ; 'A'
0x000011f8      mov     byte [var_1bh], 0x46 ; 'F'
0x000011fc      mov     byte [var_1ah], 0x7d ; '}'
```

- Flag: picoCTF{ASCII_IS_EASY_8960F0AF}

## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/389
