## Descripción 
Now for something a little different. `0x2262c96b` is loaded into memory in the `main` function. Examine byte-wise the memory that the constant is loaded in by using the GDB command `x/4xb addr`. The flag is the four bytes as they are stored in memory. If you find the bytes `0x11 0x22 0x33 0x44` in the memory location, your flag would be: `picoCTF{0x11223344}`.Debug [this](https://artifacts.picoctf.net/c/531/debugger0_c).

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
                                                                                  
┌──(kali㉿kali)-[~/Parcial3]
└─$ mkdir gdbBabyStep3
                                                                                  
┌──(kali㉿kali)-[~/Parcial3]
└─$ cd gdbBabyStep3
                                                                                  
┌──(kali㉿kali)-[~/Parcial3/gdbBabyStep3]
└─$ wget https://artifacts.picoctf.net/c/531/debugger0_c
--2024-11-17 13:31:47--  https://artifacts.picoctf.net/c/531/debugger0_c
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.249.21.32, 13.249.21
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.249.21.32|:443... c
HTTP request sent, awaiting response... 200 OK
Length: 16304 (16K) [application/octet-stream]
Saving to: ‘debugger0_c’

debugger0_c                               100%[===================================

2024-11-17 13:31:48 (13.9 MB/s) - ‘debugger0_c’ saved [16304/16304]

                                                                                  
┌──(kali㉿kali)-[~/Parcial3/gdbBabyStep3]
└─$ chmod +x debugger0_c
                                                                                  
┌──(kali㉿kali)-[~/Parcial3/gdbBabyStep3]
└─$ ./debugger0_c 
                                                                                  
┌──(kali㉿kali)-[~/Parcial3/gdbBabyStep3]
└─$ ghidra debugger0_c                             
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true

┌──(kali㉿kali)-[~/Parcial3/gdbBabyStep3]
└─$ gdb debugger0_c 
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
Reading symbols from debugger0_c...
(No debugging symbols found in debugger0_c)
(gdb) break main
Breakpoint 1 at 0x40110e
(gdb)  start
Temporary breakpoint 2 at 0x40110e
Starting program: /home/kali/Parcial3/gdbBabyStep3/debugger0_c 
[Thread debugging using libthread_db enabled]
Using host libthread_db library "/lib/x86_64-linux-gnu/libthread_db.so.1".

Breakpoint 1, 0x000000000040110e in main ()
(gdb) disas main
Dump of assembler code for function main:
   0x0000000000401106 <+0>:     endbr64
   0x000000000040110a <+4>:     push   %rbp
   0x000000000040110b <+5>:     mov    %rsp,%rbp
=> 0x000000000040110e <+8>:     mov    %edi,-0x14(%rbp)
   0x0000000000401111 <+11>:    mov    %rsi,-0x20(%rbp)
   0x0000000000401115 <+15>:    movl   $0x2262c96b,-0x4(%rbp)
   0x000000000040111c <+22>:    mov    -0x4(%rbp),%eax
   0x000000000040111f <+25>:    pop    %rbp
   0x0000000000401120 <+26>:    ret
End of assembler dump.
(gdb) break * 0x000000000040111f
Breakpoint 3 at 0x40111f
(gdb) c
Continuing.

Breakpoint 3, 0x000000000040111f in main ()
(gdb) x/4xb $rbp-4
quit
0x7fffffffdd4c: 0x6b    0xc9    0x62    0x22
(gdb) 

```

- Flag: picoCTF{0x6bc96222}

## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/397
https://www.youtube.com/watch?v=lYfv6uR8uFA
https://ftp.gnu.org/old-gnu/Manuals/gdb/html_node/gdb_55.html
https://en.wikipedia.org/wiki/Endianness
