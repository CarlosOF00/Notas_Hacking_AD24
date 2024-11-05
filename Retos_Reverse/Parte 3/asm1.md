## Descripción 
What does asm1(0x8be) return? Submit the flag as a hexadecimal value (starting with '0x'). NOTE: Your submission for this question will NOT be in the normal flag format. [Source](https://jupiter.challenges.picoctf.org/static/66c927e32f3d7be7a62d13a7c2250943/test.S)

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
┌──(kali㉿kali)-[~/retosReverse]
└─$ mkdir asm1                                                                                
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosReverse]
└─$ cd asm1        
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosReverse/asm1]
└─$ wget https://jupiter.challenges.picoctf.org/static/66c927e32f3d7be7a62d13a7c2250943/test.S
--2024-11-03 21:29:03--  https://jupiter.challenges.picoctf.org/static/66c927e32f3d7be7a62d13a7c2250943/test.S
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 638 [application/octet-stream]
Saving to: ‘test.S’

test.S                                    100%[===================================

2024-11-03 21:29:03 (15.2 MB/s) - ‘test.S’ saved [638/638]

                                                                                  
┌──(kali㉿kali)-[~/retosReverse/asm1]
└─$ cat test.S 
asm1:
        <+0>:   push   ebp
        <+1>:   mov    ebp,esp
        <+3>:   cmp    DWORD PTR [ebp+0x8],0x71c
        <+10>:  jg     0x512 <asm1+37>
        <+12>:  cmp    DWORD PTR [ebp+0x8],0x6cf
        <+19>:  jne    0x50a <asm1+29>
        <+21>:  mov    eax,DWORD PTR [ebp+0x8]
        <+24>:  add    eax,0x3
        <+27>:  jmp    0x529 <asm1+60>
        <+29>:  mov    eax,DWORD PTR [ebp+0x8]
        <+32>:  sub    eax,0x3
        <+35>:  jmp    0x529 <asm1+60>
        <+37>:  cmp    DWORD PTR [ebp+0x8],0x8be
        <+44>:  jne    0x523 <asm1+54>
        <+46>:  mov    eax,DWORD PTR [ebp+0x8]
        <+49>:  sub    eax,0x3
        <+52>:  jmp    0x529 <asm1+60>
        <+54>:  mov    eax,DWORD PTR [ebp+0x8]
        <+57>:  add    eax,0x3
        <+60>:  pop    ebp
        <+61>:  ret    

                                                                                  
┌──(kali㉿kali)-[~/retosReverse/asm1]
└─$ 
```

Inicio de la función:
- `push ebp` y `mov ebp, esp`: Se establece el marco de pila para la función.

Comparaciones: 
- `cmp DWORD PTR [ebp+0x8],0x71c`: Se compara  `0x8be` con `0x71c` (que es `1816` en decimal). Como `0x8be` (que es `2270` en decimal) es mayor que `0x71c`, se salta a la instrucción en la dirección `0x512`.

Siguiente comparación: 
- `cmp DWORD PTR [ebp+0x8],0x6cf`: Se compara `0x8be` con `0x6cf` (que es `1759` en decimal). Aquí, `0x8be` es mayor que `0x6cf`, así que se salta a `0x50a`.

No se cumple la condición de igualdad:
- En `0x50a`, se pasa a la instrucción siguiente, donde se ejecuta el siguiente bloque:

Siguiente condición:
- `cmp DWORD PTR [ebp+0x8],0x8be`: Se compara `0x8be` con `0x8be`. Como son iguales, se pasa a la instrucción siguiente.

Resultado:
- `mov eax,DWORD PTR [ebp+0x8]`: Se mueve el valor `0x8be` a `eax`.
- `sub eax,0x3`: Se resta `3` de `eax`. Entonces, `0x8be - 0x3 = 0x8bb`.

Finalmente, después de todas las instrucciones, `eax` contendrá el valor `0x8bb`.
Por lo tanto, el valor que se devuelve al llamar a `asm1(0x8be)` es:
	- Flag: 0x8bb

## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/20