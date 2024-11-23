## Descripción 
Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`.Download the assembly dump [here](https://artifacts.picoctf.net/c/530/disassembler-dump0_c.txt).

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
┌──(kali㉿kali)-[~/Parcial3]
└─$ mkdir Bit-O-Asm-3
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Parcial3]
└─$ cd Bit-O-Asm-3
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Parcial3/Bit-O-Asm-3]
└─$ wget https://artifacts.picoctf.net/c/530/disassembler-dump0_c.txt
--2024-11-17 11:09:01--  https://artifacts.picoctf.net/c/530/disassembler-dump0_c.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.249.21.85, 13.249.21.46, 13.249.21.66, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.249.21.85|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 461 [application/octet-stream]
Saving to: ‘disassembler-dump0_c.txt’

disassembler-dump0_c.txt                  100%[====================================================================================>]     461  --.-KB/s    in 0s      

2024-11-17 11:09:02 (298 MB/s) - ‘disassembler-dump0_c.txt’ saved [461/461]

                                                                                                                                                                       
┌──(kali㉿kali)-[~/Parcial3/Bit-O-Asm-3]
└─$ cat disassembler-dump0_c.txt 
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x14],edi
<+11>:    mov    QWORD PTR [rbp-0x20],rsi
<+15>:    mov    DWORD PTR [rbp-0xc],0x9fe1a
<+22>:    mov    DWORD PTR [rbp-0x8],0x4
<+29>:    mov    eax,DWORD PTR [rbp-0xc]
<+32>:    imul   eax,DWORD PTR [rbp-0x8]
<+36>:    add    eax,0x1f5
<+41>:    mov    DWORD PTR [rbp-0x4],eax
<+44>:    mov    eax,DWORD PTR [rbp-0x4]
<+47>:    pop    rbp
<+48>:    ret
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Parcial3/Bit-O-Asm-3]
└─$ python3                                                    
Python 3.12.6 (main, Sep  7 2024, 14:20:15) [GCC 14.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 0x4
4
>>> eax = 0x9fe1a
>>> eax
654874
>>> eax = eax*4
>>> eax
2619496
>>> eax += 0x1f5
>>> eax
2619997
>>> 
```


- Flag: picoCTF{2619997}

## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/393
