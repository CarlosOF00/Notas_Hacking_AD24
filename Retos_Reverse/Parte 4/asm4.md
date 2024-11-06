## Descripción 
What will asm4("picoCTF_724a2") return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://jupiter.challenges.picoctf.org/static/14acd1667eb7ce6f16355b2256c945b7/test.S)

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
┌──(kali㉿kali)-[~/retosReverse]
└─$ mkdir asm4         
                                                                                 
┌──(kali㉿kali)-[~/retosReverse]
└─$ cd asm4
                                                                                 
┌──(kali㉿kali)-[~/retosReverse/asm4]
└─$ wget https://jupiter.challenges.picoctf.org/static/14acd1667eb7ce6f16355b2256c945b7/test.S
--2024-11-05 18:12:54--  https://jupiter.challenges.picoctf.org/static/14acd1667eb7ce6f16355b2256c945b7/test.S
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1743 (1.7K) [application/octet-stream]
Saving to: ‘test.S’

test.S               100%[===================>]   1.70K  --.-KB/s    in 0s      

2024-11-05 18:12:55 (43.1 MB/s) - ‘test.S’ saved [1743/1743]

                                                                                 
┌──(kali㉿kali)-[~/retosReverse/asm4]
└─$ cat test.S 
asm4:
        <+0>:   push   ebp
        <+1>:   mov    ebp,esp
        <+3>:   push   ebx
        <+4>:   sub    esp,0x10
        <+7>:   mov    DWORD PTR [ebp-0x10],0x252
        <+14>:  mov    DWORD PTR [ebp-0xc],0x0
        <+21>:  jmp    0x518 <asm4+27>
        <+23>:  add    DWORD PTR [ebp-0xc],0x1
        <+27>:  mov    edx,DWORD PTR [ebp-0xc]
        <+30>:  mov    eax,DWORD PTR [ebp+0x8]
        <+33>:  add    eax,edx
        <+35>:  movzx  eax,BYTE PTR [eax]
        <+38>:  test   al,al
        <+40>:  jne    0x514 <asm4+23>
        <+42>:  mov    DWORD PTR [ebp-0x8],0x1
        <+49>:  jmp    0x587 <asm4+138>
        <+51>:  mov    edx,DWORD PTR [ebp-0x8]
        <+54>:  mov    eax,DWORD PTR [ebp+0x8]
        <+57>:  add    eax,edx
        <+59>:  movzx  eax,BYTE PTR [eax]
        <+62>:  movsx  edx,al
        <+65>:  mov    eax,DWORD PTR [ebp-0x8]
        <+68>:  lea    ecx,[eax-0x1]
        <+71>:  mov    eax,DWORD PTR [ebp+0x8]
        <+74>:  add    eax,ecx
        <+76>:  movzx  eax,BYTE PTR [eax]
        <+79>:  movsx  eax,al
        <+82>:  sub    edx,eax
        <+84>:  mov    eax,edx
        <+86>:  mov    edx,eax
        <+88>:  mov    eax,DWORD PTR [ebp-0x10]
        <+91>:  lea    ebx,[edx+eax*1]
        <+94>:  mov    eax,DWORD PTR [ebp-0x8]
        <+97>:  lea    edx,[eax+0x1]
        <+100>: mov    eax,DWORD PTR [ebp+0x8]
        <+103>: add    eax,edx
        <+105>: movzx  eax,BYTE PTR [eax]
        <+108>: movsx  edx,al
        <+111>: mov    ecx,DWORD PTR [ebp-0x8]
        <+114>: mov    eax,DWORD PTR [ebp+0x8]
        <+117>: add    eax,ecx
        <+119>: movzx  eax,BYTE PTR [eax]
        <+122>: movsx  eax,al
        <+125>: sub    edx,eax
        <+127>: mov    eax,edx
        <+129>: add    eax,ebx
        <+131>: mov    DWORD PTR [ebp-0x10],eax
        <+134>: add    DWORD PTR [ebp-0x8],0x1
        <+138>: mov    eax,DWORD PTR [ebp-0xc]
        <+141>: sub    eax,0x1
        <+144>: cmp    DWORD PTR [ebp-0x8],eax
        <+147>: jl     0x530 <asm4+51>
        <+149>: mov    eax,DWORD PTR [ebp-0x10]
        <+152>: add    esp,0x10
        <+155>: pop    ebx
        <+156>: pop    ebp
        <+157>: ret  
        ┌──(kali㉿kali)-[~/retosReverse/asm4]
└─$ cat test.S | cut -d ':' -f2 > chal.s
                                                                                 
┌──(kali㉿kali)-[~/retosReverse/asm4]
└─$ cat chal.s                          

        push   ebp
        mov    ebp,esp
        push   ebx
        sub    esp,0x10
        mov    DWORD PTR [ebp-0x10],0x252
        mov    DWORD PTR [ebp-0xc],0x0
        jmp    0x518 <asm4+27>
        add    DWORD PTR [ebp-0xc],0x1
        mov    edx,DWORD PTR [ebp-0xc]
        mov    eax,DWORD PTR [ebp+0x8]
        add    eax,edx
        movzx  eax,BYTE PTR [eax]
        test   al,al
        jne    0x514 <asm4+23>
        mov    DWORD PTR [ebp-0x8],0x1
        jmp    0x587 <asm4+138>
        mov    edx,DWORD PTR [ebp-0x8]
        mov    eax,DWORD PTR [ebp+0x8]
        add    eax,edx
        movzx  eax,BYTE PTR [eax]
        movsx  edx,al
        mov    eax,DWORD PTR [ebp-0x8]
        lea    ecx,[eax-0x1]
        mov    eax,DWORD PTR [ebp+0x8]
        add    eax,ecx
        movzx  eax,BYTE PTR [eax]
        movsx  eax,al
        sub    edx,eax
        mov    eax,edx
        mov    edx,eax
        mov    eax,DWORD PTR [ebp-0x10]
        lea    ebx,[edx+eax*1]
        mov    eax,DWORD PTR [ebp-0x8]
        lea    edx,[eax+0x1]
        mov    eax,DWORD PTR [ebp+0x8]
        add    eax,edx
        movzx  eax,BYTE PTR [eax]
        movsx  edx,al
        mov    ecx,DWORD PTR [ebp-0x8]
        mov    eax,DWORD PTR [ebp+0x8]
        add    eax,ecx
        movzx  eax,BYTE PTR [eax]
        movsx  eax,al
        sub    edx,eax
        mov    eax,edx
        add    eax,ebx
        mov    DWORD PTR [ebp-0x10],eax
        add    DWORD PTR [ebp-0x8],0x1
        mov    eax,DWORD PTR [ebp-0xc]
        sub    eax,0x1
        cmp    DWORD PTR [ebp-0x8],eax
        jl     0x530 <asm4+51>
        mov    eax,DWORD PTR [ebp-0x10]
        add    esp,0x10
        pop    ebx
        pop    ebp
        ret    

                                                                                 
┌──(kali㉿kali)-[~/retosReverse/asm4]
└─$ nano chal.s 
                                                                                 
┌──(kali㉿kali)-[~/retosReverse/asm4]
└─$ cat chal.s 
.intel_syntax noprefix
.global asm4

asm4:
        push   ebp
        mov    ebp,esp
        push   ebx
        sub    esp,0x10
        mov    DWORD PTR [ebp-0x10],0x252
        mov    DWORD PTR [ebp-0xc],0x0
        jmp    asm4+27
        add    DWORD PTR [ebp-0xc],0x1
        mov    edx,DWORD PTR [ebp-0xc]
        mov    eax,DWORD PTR [ebp+0x8]
        add    eax,edx
        movzx  eax,BYTE PTR [eax]
        test   al,al
        jne    asm4+23
        mov    DWORD PTR [ebp-0x8],0x1
        jmp    asm4+138
        mov    edx,DWORD PTR [ebp-0x8]
        mov    eax,DWORD PTR [ebp+0x8]
        add    eax,edx
        movzx  eax,BYTE PTR [eax]
        movsx  edx,al
        mov    eax,DWORD PTR [ebp-0x8]
        lea    ecx,[eax-0x1]
        mov    eax,DWORD PTR [ebp+0x8]
        add    eax,ecx
        movzx  eax,BYTE PTR [eax]
        movsx  eax,al
        sub    edx,eax
        mov    eax,edx
        mov    edx,eax
        mov    eax,DWORD PTR [ebp-0x10]
        lea    ebx,[edx+eax*1]
        mov    eax,DWORD PTR [ebp-0x8]
        lea    edx,[eax+0x1]
        mov    eax,DWORD PTR [ebp+0x8]
        add    eax,edx
        movzx  eax,BYTE PTR [eax]
        movsx  edx,al
        mov    ecx,DWORD PTR [ebp-0x8]
        mov    eax,DWORD PTR [ebp+0x8]
        add    eax,ecx
        movzx  eax,BYTE PTR [eax]
        movsx  eax,al
        sub    edx,eax
        mov    eax,edx
        add    eax,ebx
        mov    DWORD PTR [ebp-0x10],eax
        add    DWORD PTR [ebp-0x8],0x1
        mov    eax,DWORD PTR [ebp-0xc]
        sub    eax,0x1
        cmp    DWORD PTR [ebp-0x8],eax
        jl     asm4+51
        mov    eax,DWORD PTR [ebp-0x10]
        add    esp,0x10
        pop    ebx
        pop    ebp
        ret    


┌──(kali㉿kali)-[~/retosReverse/asm4]
└─$ nano solve.c

GNU nano 8.0                         solve.c                                   
#include <stdio.h>
int main() {
        printf("Flag: 0x%x\n", asm4("picoCTF_724a2"));
}
                                                                                                                                                                       
┌──(kali㉿kali)-[~/retosReverse/asm4]
└─$ gcc -m32 -c chal.s -o chal.o
                                                                                
└─$ gcc -m32 -c solve.c -o solve.o -w
In file included from solve.c:1:
compilation terminated.
                                                                                 
┌──(kali㉿kali)-[~/retosReverse/asm4]
└─$ ./a.out
 Flag: 0x20c

```

## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/5