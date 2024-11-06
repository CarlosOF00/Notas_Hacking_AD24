## Descripción 
Can you get the flag?Download this [binary](https://artifacts.picoctf.net/c/85/gdbme).Here's the test drive instructions:

- `$ chmod +x gdbme`
- `$ gdb gdbme`
- `(gdb) layout asm`
- `(gdb) break *(main+99)`
- `(gdb) run`
- `(gdb) jump *(main+104)`

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
carlosof-picoctf@webshell:~$ mkdir GDB
carlosof-picoctf@webshell:~$ cd GDB/
carlosof-picoctf@webshell:~/GDB$ wget https://artifacts.picoctf.net/c/85/gdbme
--2024-11-06 00:05:59--  https://artifacts.picoctf.net/c/85/gdbme
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.71, 3.160.5.42, 3.160.5.93, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.71|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 17048 (17K) [application/octet-stream]
Saving to: 'gdbme'

gdbme                   100%[============================>]  16.65K  --.-KB/s    in 0.006s  

2024-11-06 00:05:59 (2.56 MB/s) - 'gdbme' saved [17048/17048]

carlosof-picoctf@webshell:~/GDB$ chmod +x gdbme

carlosof-picoctf@webshell:~/GDB$ gdb gdbme

GNU gdb (Ubuntu 12.1-0ubuntu1~22.04.2) 12.1
Copyright (C) 2022 Free Software Foundation, Inc.
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
Reading symbols from gdbme...
(No debugging symbols found in gdbme)
(gdb) layout asm

```


```bash
multi-thre No process In:
(gdb) break (main+99)
Breakpoint 1 at 0x1328
(gdb) run
Starting program: /home/carlosof-picoctf/GDB/gdbme
warning: Error disabling address space randomization: Operation not permitted
[Thread debugging using libthread_db enabled]
Using host libthread_db library "/lib/x86_64-linux-gnu/libthread_db.so.1".
Breakpoint 1, 0x000055e92ce9032a in main ()
(gdb) jump (main+104)
Continuing at 0x55e92ce9032f.
picoCTF{d3bugg3r_dr1v3_197c378a}
(gdb) for 1 (process 282) exited normally]
```

- Flag: picoCTF{d3bugg3r_dr1v3_197c378a}
## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/273