## Descripción 
Can you figure out what is in the `eax` register at the end of the `main` function? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`.Disassemble [this](https://artifacts.picoctf.net/c/512/debugger0_a).

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
┌──(kali㉿kali)-[~/Parcial3]
└─$ mkdir gdbBabyStep1
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial3]
└─$ cd gdbBabyStep1 
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial3/gdbBabyStep1]
└─$ wget https://artifacts.picoctf.net/c/512/debugger0_a
--2024-11-17 12:12:42--  https://artifacts.picoctf.net/c/512/debugger0_a
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.249.21.85, 13.249.21.66, 13.249.21.32, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.249.21.85|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 16472 (16K) [application/octet-stream]
Saving to: ‘debugger0_a’

debugger0_a                               100%[===================================================================================>]  16.09K  --.-KB/s    in 0.009s  

2024-11-17 12:12:43 (1.85 MB/s) - ‘debugger0_a’ saved [16472/16472]

                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial3/gdbBabyStep1]
└─$ ls
debugger0_a
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial3/gdbBabyStep1]
└─$ file debugger0_a 
debugger0_a: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, BuildID[sha1]=15a10290db2cd2ec0c123cf80b88ed7d7f5cf9ff, for GNU/Linux 3.2.0, not stripped
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial3/gdbBabyStep1]
└─$ ls
debugger0_a
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial3/gdbBabyStep1]
└─$ chmod +x debugger0_a
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial3/gdbBabyStep1]
└─$ ghidra debugger0_a                             
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true

```
- Se abrirá le herramienta de `Hidra` en caso de no tener un proyecto, debemos de crear uno, después de tenerlo, en el apartado superior izquierdo `File` daremos clic en la opción de `Import File` buscamos el archivo que descargamos y lo seleccionamos.
- Pasara un tiempo en lo que lo analiza y se abrirá una nueva ventana.
- En el apartado izquierdo de `Symbol Tree` buscaremos las `Functions` y abriremos `Main`, se abrirá un apartado a la derecha llamado `Decompile` donde observaremos esto:
```bash
undefined8 main(void)

{
  return 0x86342;
}

```

- Lo pasamos por la terminal de Python y obtenemos la bandera:
``` bash
Python 3.12.5 (tags/v3.12.5:ff3bc82, Aug  6 2024, 20:45:27) [MSC v.1940 64 bit (AMD64)] on win32
Type "help", "copyright", "credits" or "license" for more information.
>>> 0x86342
549698
>>>
```

Flag: picoCTF{549698}

## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/395