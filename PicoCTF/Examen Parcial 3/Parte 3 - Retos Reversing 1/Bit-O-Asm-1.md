## Descripción 
Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`.Download the assembly dump [here](https://artifacts.picoctf.net/c/509/disassembler-dump0_a.txt).

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
┌──(kali㉿kali)-[~/Parcial3]
└─$ mkdir Bit-O-Asm-1
                                                                                  
┌──(kali㉿kali)-[~/Parcial3]
└─$ cd Bit-O-Asm-1 
                                                                                  
┌──(kali㉿kali)-[~/Parcial3/Bit-O-Asm-1]
└─$ wget https://artifacts.picoctf.net/c/509/disassembler-dump0_a.txt
--2024-11-17 10:59:11--  https://artifacts.picoctf.net/c/509/disassembler-dump0_a.
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.249.21.32, 13.249.21
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.249.21.32|:443... c
HTTP request sent, awaiting response... 200 OK
Length: 209 [application/octet-stream]
Saving to: ‘disassembler-dump0_a.txt’

disassembler-dump0_a.txt                  100%[===================================

2024-11-17 10:59:11 (152 MB/s) - ‘disassembler-dump0_a.txt’ saved [209/209]

                                                                                  
┌──(kali㉿kali)-[~/Parcial3/Bit-O-Asm-1]
└─$ cat disassembler-dump0_a.txt 
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x4],edi
<+11>:    mov    QWORD PTR [rbp-0x10],rsi
<+15>:    mov    eax,0x30
<+20>:    pop    rbp
<+21>:    ret
                                         
┌──(kali㉿kali)-[~/Parcial3/Bit-O-Asm-1]
└─$ python3                                                    
Python 3.12.6 (main, Sep  7 2024, 14:20:15) [GCC 14.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 0x30
48
>>> 
```

- Flag: picoCTF{48}

## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/391
