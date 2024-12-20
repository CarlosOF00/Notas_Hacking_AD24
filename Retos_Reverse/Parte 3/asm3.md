## Descripción 
What does asm3(0xba6c5a02,0xd101e3dd,0xbb86a173) return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://jupiter.challenges.picoctf.org/static/cb753ae52bca4aa303deca5fbfb01bfb/test.S)

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
                                                                                 
┌──(kali㉿kali)-[~/retosReverse]
└─$ mkdir asm3
                                                                                 
┌──(kali㉿kali)-[~/retosReverse]
└─$ cd asm3
                                                                                 
┌──(kali㉿kali)-[~/retosReverse/asm3]
└─$ wget https://jupiter.challenges.picoctf.org/static/cb753ae52bca4aa303deca5fbfb01bfb/test.S
--2024-11-05 16:17:47--  https://jupiter.challenges.picoctf.org/static/cb753ae52bca4aa303deca5fbfb01bfb/test.S
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 286 [application/octet-stream]
Saving to: ‘test.S’

test.S               100%[===================>]     286  --.-KB/s    in 0s      

2024-11-05 16:17:47 (7.64 MB/s) - ‘test.S’ saved [286/286]

                                                                                 
┌──(kali㉿kali)-[~/retosReverse/asm3]
└─$ cat test.S 
asm3:
        <+0>:   push   ebp
        <+1>:   mov    ebp,esp
        <+3>:   xor    eax,eax
        <+5>:   mov    ah,BYTE PTR [ebp+0xb]
        <+8>:   shl    ax,0x10
        <+12>:  sub    al,BYTE PTR [ebp+0xd]
        <+15>:  add    ah,BYTE PTR [ebp+0xc]
        <+18>:  xor    ax,WORD PTR [ebp+0x12]
        <+22>:  nop
        <+23>:  pop    ebp
        <+24>:  ret    

                                                                                 
┌──(kali㉿kali)-[~/retosReverse/asm3]

```

- ingresamos a la siguiente página https://carlosrafaelgn.com.br/Asm86/?language=en y adaptamos el código para poder compilarlo: 
```bash
push 0xbb86a173
push 0xd101e3dd
push 0xba6c5a02
call asm3


asm3:
        push   ebp
        mov    ebp,esp
        xor    eax,eax
        mov    ah,BYTE PTR [ebp+0xb]
        shl    ax,0x10
        sub    al,BYTE PTR [ebp+0xd]
        add    ah,BYTE PTR [ebp+0xc]
        xor    ax,WORD PTR [ebp+0x12]
        nop
        pop    ebp
        ret  
```
- En el apartado de la derecha daremos clic en el botón de `Windows` y seleccionaremos la que dice `Registers`, después de eso iremos paso por paso hasta llegar al ultimo y ahí obtendremos la bandera de la variable `EAX`

- Flag: 0x669B
## Notas Adicionales
## Referencias 
https://play.picoctf.org/practice/challenge/72
 https://carlosrafaelgn.com.br/Asm86/?language=en