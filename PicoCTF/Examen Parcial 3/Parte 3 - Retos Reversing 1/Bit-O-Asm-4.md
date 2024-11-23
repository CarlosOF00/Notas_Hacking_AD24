## Descripción 
Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`.Download the assembly dump [here](https://artifacts.picoctf.net/c/511/disassembler-dump0_d.txt).

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
┌──(kali㉿kali)-[~/Parcial3]
└─$ mkdir Bit-O-Asm-4
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Parcial3]
└─$ cd Bit-O-Asm-4
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Parcial3/Bit-O-Asm-4]
└─$ wget https://artifacts.picoctf.net/c/511/disassembler-dump0_d.txt
--2024-11-17 11:14:02--  https://artifacts.picoctf.net/c/511/disassembler-dump0_d.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.249.21.32, 13.249.21.66, 13.249.21.85, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.249.21.32|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 482 [application/octet-stream]
Saving to: ‘disassembler-dump0_d.txt’

disassembler-dump0_d.txt                  100%[====================================================================================>]     482  --.-KB/s    in 0s      

2024-11-17 11:14:02 (4.60 MB/s) - ‘disassembler-dump0_d.txt’ saved [482/482]

                                                                                                                                                                       
┌──(kali㉿kali)-[~/Parcial3/Bit-O-Asm-4]
└─$ cat disassembler-dump0_d.txt 
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x14],edi
<+11>:    mov    QWORD PTR [rbp-0x20],rsi
<+15>:    mov    DWORD PTR [rbp-0x4],0x9fe1a
<+22>:    cmp    DWORD PTR [rbp-0x4],0x2710
<+29>:    jle    0x55555555514e <main+37>
<+31>:    sub    DWORD PTR [rbp-0x4],0x65
<+35>:    jmp    0x555555555152 <main+41>
<+37>:    add    DWORD PTR [rbp-0x4],0x65
<+41>:    mov    eax,DWORD PTR [rbp-0x4]
<+44>:    pop    rbp
<+45>:    ret
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Parcial3/Bit-O-Asm-4]
└─$ python3
Python 3.12.6 (main, Sep  7 2024, 14:20:15) [GCC 14.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 0x2710
10000
>>> 0x9fe1a
654874
>>> 654874 - 0x65
654773
>>> 

```

- picoCTF{654773}

## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/394