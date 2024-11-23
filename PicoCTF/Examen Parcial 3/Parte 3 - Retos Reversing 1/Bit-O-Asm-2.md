## Descripción 
Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`.Download the assembly dump [here](https://artifacts.picoctf.net/c/510/disassembler-dump0_b.txt).

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
┌──(kali㉿kali)-[~/Parcial3]
└─$ mkdir Bit-O-Asm-2
                                                                                  
┌──(kali㉿kali)-[~/Parcial3]
└─$ cd Bit-O-Asm-2
                                                                                  
┌──(kali㉿kali)-[~/Parcial3/Bit-O-Asm-2]
└─$ wget https://artifacts.picoctf.net/c/510/disassembler-dump0_b.txt
--2024-11-17 11:05:47--  https://artifacts.picoctf.net/c/510/disassembler-dump0_b.
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.249.21.66, 13.249.21
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.249.21.66|:443... c
HTTP request sent, awaiting response... 200 OK
Length: 270 [application/octet-stream]
Saving to: ‘disassembler-dump0_b.txt’

disassembler-dump0_b.txt                  100%[===================================

2024-11-17 11:05:47 (170 MB/s) - ‘disassembler-dump0_b.txt’ saved [270/270]

                                                                                  
┌──(kali㉿kali)-[~/Parcial3/Bit-O-Asm-2]
└─$ cat disassembler-dump0_b.txt 
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x14],edi
<+11>:    mov    QWORD PTR [rbp-0x20],rsi
<+15>:    mov    DWORD PTR [rbp-0x4],0x9fe1a
<+22>:    mov    eax,DWORD PTR [rbp-0x4]
<+25>:    pop    rbp
<+26>:    ret

┌──(kali㉿kali)-[~/Parcial3/Bit-O-Asm-2]
└─$ python3
Python 3.12.6 (main, Sep  7 2024, 14:20:15) [GCC 14.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 0x9fe1a
654874
>>> 
```

- Flag: picoCTF{654874}

## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/392
