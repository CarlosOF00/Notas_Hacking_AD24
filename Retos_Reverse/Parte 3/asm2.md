
## Descripción 
What does asm2(0xb,0x2e) return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://jupiter.challenges.picoctf.org/static/717467c8c8b4332ea5873ad8fe7b2dad/test.S)

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash 
┌──(kali㉿kali)-[~/retosReverse]
└─$ mkdir asm2     
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosReverse]
└─$ cd asm2
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosReverse/asm2]
└─$ wget https://jupiter.challenges.picoctf.org/static/717467c8c8b4332ea5873ad8fe7b2dad/test.S
--2024-11-05 16:01:54--  https://jupiter.challenges.picoctf.org/static/717467c8c8b4332ea5873ad8fe7b2dad/test.S
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 484 [application/octet-stream]
Saving to: ‘test.S’

test.S                                    100%[==================================

2024-11-05 16:01:55 (13.1 MB/s) - ‘test.S’ saved [484/484]

                                                                                 
┌──(kali㉿kali)-[~/retosReverse/asm2]
└─$ cat test.S               
asm2:
        <+0>:   push   ebp
        <+1>:   mov    ebp,esp
        <+3>:   sub    esp,0x10
        <+6>:   mov    eax,DWORD PTR [ebp+0xc]
        <+9>:   mov    DWORD PTR [ebp-0x4],eax
        <+12>:  mov    eax,DWORD PTR [ebp+0x8]
        <+15>:  mov    DWORD PTR [ebp-0x8],eax
        <+18>:  jmp    0x509 <asm2+28>
        <+20>:  add    DWORD PTR [ebp-0x4],0x1
        <+24>:  sub    DWORD PTR [ebp-0x8],0xffffff80
        <+28>:  cmp    DWORD PTR [ebp-0x8],0x63f3
        <+35>:  jle    0x501 <asm2+20>
        <+37>:  mov    eax,DWORD PTR [ebp-0x4]
        <+40>:  leave  
        <+41>:  ret    

                                                                                 
┌──(kali㉿kali)-[~/retosReverse/asm2]
nano test.S
[    ] < esp
[    ] ebp - 0xc
[0x8b] ebp - 0x8
[0x2f] ebp - 0x4
[ebp ] < ebp
[ret ] ebp + 0x4
[0xb ] ebp + 0x8
[0x2e] ebp + 0xc

[0xb ] eax

asm2(0xb,0x2e)
```

```bash
Python 3.8.5 (default, Jul 20 2020, 23:11:29) [GCC 9.3.0] on linuxType "help", "copyright", "credits" or "license" for more information.>>> 0xb <= 0x63f3
>>> import numpy
>>> numpy.int32(0xffffff80)
<stdin>:1: DeprecationWarning: NumPy will stop allowing conversion of out-of-bound Python integers to integer arrays.  The conversion of 4294967168 to int32 will fail in the future.
For the old behavior, usually:
    np.array(value).astype(dtype)
will give the desired result (the cast overflows).
-128
>>> 0x63f3 / 128
199.8984375
>>> int(0xb)
11
>>> hex(246)
'0xf6'
>>>

```

- Flag : 0xf6

## Notas Adicionales
## Referencias 
https://play.picoctf.org/practice/challenge/16

