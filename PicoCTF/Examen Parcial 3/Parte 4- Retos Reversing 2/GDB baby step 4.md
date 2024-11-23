## Descripción 
`main` calls a function that multiplies `eax` by a constant. The flag for this challenge is that constant in decimal base. If the constant you find is 0x1000, the flag will be `picoCTF{4096}`.Debug [this](https://artifacts.picoctf.net/c/532/debugger0_d).

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
┌──(kali㉿kali)-[~/Parcial3]
└─$ mkdir gdbBabyStep4
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Parcial3]
└─$ cd gdbBabyStep4
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Parcial3/gdbBabyStep4]
└─$ wget https://artifacts.picoctf.net/c/532/debugger0_d
--2024-11-17 13:54:56--  https://artifacts.picoctf.net/c/532/debugger0_d
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.249.21.85, 13.249.21.46, 13.249.21.32, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.249.21.85|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 16328 (16K) [application/octet-stream]
Saving to: ‘debugger0_d’

debugger0_d                               100%[====================================================================================>]  15.95K  --.-KB/s    in 0.009s  

2024-11-17 13:54:57 (1.83 MB/s) - ‘debugger0_d’ saved [16328/16328]

                                                                                                                                                                       
┌──(kali㉿kali)-[~/Parcial3/gdbBabyStep4]
└─$ chmod +x debugger0_d 
┌──(kali㉿kali)-[~/Parcial3/gdbBabyStep4]
└─$ gdb debugger0_d 
GNU gdb (Debian 15.1-1) 15.1
Copyright (C) 2024 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.
Type "show copying" and "show warranty" for details.
This GDB was configured as "x86_64-linux-gnu".
Type "show configuration" for configuration details.
For bug reporting instructions, please see:
<https://www.gnu.org/software/gdb/bugs/>.
Find the GDB manual and other documentation resources online at:
    <http://www.gnu.org/software/gdb/documentation/>.

For help, type "help".
Type "apropos word" to search for commands related to "word"...
Reading symbols from debugger0_d...
(No debugging symbols found in debugger0_d)
(gdb) set disassembly-flavor intel
(gdb) info functions
All defined functions:

Non-debugging symbols:
0x0000000000401000  _init
0x0000000000401020  _start
0x0000000000401050  _dl_relocate_static_pie
0x0000000000401060  deregister_tm_clones
0x0000000000401090  register_tm_clones
0x00000000004010d0  __do_global_dtors_aux
0x0000000000401100  frame_dummy
0x0000000000401106  func1
0x000000000040111c  main
0x0000000000401150  __libc_csu_init
0x00000000004011c0  __libc_csu_fini
0x00000000004011c8  _fini
(gdb) disas main
Dump of assembler code for function main:
   0x000000000040111c <+0>:     endbr64
   0x0000000000401120 <+4>:     push   rbp
   0x0000000000401121 <+5>:     mov    rbp,rsp
   0x0000000000401124 <+8>:     sub    rsp,0x20
   0x0000000000401128 <+12>:    mov    DWORD PTR [rbp-0x14],edi
   0x000000000040112b <+15>:    mov    QWORD PTR [rbp-0x20],rsi
   0x000000000040112f <+19>:    mov    DWORD PTR [rbp-0x4],0x28e
   0x0000000000401136 <+26>:    mov    DWORD PTR [rbp-0x8],0x0
   0x000000000040113d <+33>:    mov    eax,DWORD PTR [rbp-0x4]
   0x0000000000401140 <+36>:    mov    edi,eax
   0x0000000000401142 <+38>:    call   0x401106 <func1>
   0x0000000000401147 <+43>:    mov    DWORD PTR [rbp-0x8],eax
   0x000000000040114a <+46>:    mov    eax,DWORD PTR [rbp-0x4]
   0x000000000040114d <+49>:    leave
   0x000000000040114e <+50>:    ret
End of assembler dump.
(gdb) break main
Breakpoint 1 at 0x401124
(gdb) break func1
Breakpoint 2 at 0x40110e
(gdb) run
Starting program: /home/kali/Parcial3/gdbBabyStep4/debugger0_d 
[Thread debugging using libthread_db enabled]
Using host libthread_db library "/lib/x86_64-linux-gnu/libthread_db.so.1".

Breakpoint 1, 0x0000000000401124 in main ()
(gdb) layout asm
                         
```

![[GDBbabystep4.png]]

```bash
Python 3.12.5 (tags/v3.12.5:ff3bc82, Aug  6 2024, 20:45:27) [MSC v.1940 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>> 0x3269
12905
>>>  
```

- Flag: picoCTF{12905}

## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/398
https://www.youtube.com/watch?v=LstE5o0rZEw
