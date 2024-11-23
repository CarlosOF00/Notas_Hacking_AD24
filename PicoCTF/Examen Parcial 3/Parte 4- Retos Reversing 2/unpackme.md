## Descripción 
Can you get the flag?Reverse engineer this [binary](https://artifacts.picoctf.net/c/203/unpackme-upx).

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
┌──(kali㉿kali)-[~/Parcial3]
└─$ mkdir unpackme   
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial3]
└─$ cd unpackme 
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial3/unpackme]
└─$ wget https://artifacts.picoctf.net/c/203/unpackme-upx
--2024-11-17 15:54:38--  https://artifacts.picoctf.net/c/203/unpackme-upx
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.249.21.85, 13.249.21.66, 13.249.21.46, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.249.21.85|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 379188 (370K) [application/octet-stream]
Saving to: ‘unpackme-upx’

unpackme-upx                              100%[===================================================================================>] 370.30K  2.30MB/s    in 0.2s    

2024-11-17 15:54:39 (2.30 MB/s) - ‘unpackme-upx’ saved [379188/379188]

                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial3/unpackme]
└─$ ls    
unpackme-upx
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial3/unpackme]
└─$ chmod +x unpackme-upx                                
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial3/unpackme]
└─$ upx -kd unpackme-upx                                                                                        
                       Ultimate Packer for eXecutables
                          Copyright (C) 1996 - 2024
UPX 4.2.2       Markus Oberhumer, Laszlo Molnar & John Reiser    Jan 3rd 2024

        File size         Ratio      Format      Name
   --------------------   ------   -----------   -----------
   1006445 <-    379188   37.68%   linux/amd64   unpackme-upx

Unpacked 1 file.
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial3/unpackme]
└─$ ~/Tools/Cutter.AppImage unpackme-upx&
[1] 7339
zsh: no such file or directory: /home/kali/Tools/Cutter.AppImage
[1]  + exit 127   ~/Tools/Cutter.AppImage unpackme-upx                                                                                                                

┌──(kali㉿kali)-[~/Parcial3/unpackme]
└─$ ls -la                                                                                     
total 1360
drwxrwxr-x  2 kali kali    4096 Nov 17 15:55 .
drwxrwxr-x 27 kali kali    4096 Nov 17 15:50 ..
-rwxrwxr-x  1 kali kali 1002528 Aug  4  2023 unpackme-upx
-rwxrwxr-x  1 kali kali  379188 Aug  4  2023 unpackme-upx.~
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial3/unpackme]
└─$ cutter unpackme-upx&   
[1] 8130
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial3/unpackme]
└─$ MESA: error: ZINK: failed to choose pdev
glx: failed to create drisw screen
"0.7.3" "0.7.3"
Plugins are loaded from "/home/kali/.local/share/rizin/cutter/plugins"
Native plugins are loaded from "/home/kali/.local/share/rizin/cutter/plugins/native"
Python plugins are loaded from "/home/kali/.local/share/rizin/cutter/plugins/python"
Loaded 0 plugin(s).
Plugins are loaded from "/usr/share/xfce4/rizin/cutter/plugins"
Plugins are loaded from "/home/kali/.local/share/flatpak/exports/share/rizin/cutter/plugins"
Plugins are loaded from "/var/lib/flatpak/exports/share/rizin/cutter/plugins"
Plugins are loaded from "/usr/local/share/rizin/cutter/plugins"
Plugins are loaded from "/usr/share/rizin/cutter/plugins"
Plugins are loaded from "/usr/lib/rizin/cutter/plugins"
[x] Analyze all flags starting with sym. and entry0 (aa)
[x] Analyze function calls
[x] Analyze len bytes of instructions for references
[x] Check for classes
[x] Analyze local variables and arguments
[x] Type matching analysis for all functions
[x] Applied 0 FLIRT signatures via sigdb
[x] Propagate noreturn information
[x] Integrate dwarf function information.
[x] Resolve pointers to data sections
[x] Use -AA or aaaa to perform additional experimental analysis.

[1]  + done       cutter unpackme-upx
```
- Se abrirá la herramienta de `Cutter`, en el aparatado de la izquierda en las `Functions` buscaremos el `Main` en caso de que se se dificulte, podemos usar la barra superior para buscar mas fácil.
- Una vez que la encontremos y la seleccionemos en el apartado de la derecha `Decompiler(main)` analizaremos el código.
- Nos podemos percatar del siguiente fragmento de código, ya que la condición que se esta haciendo, es una comparación.
```bash
if ((int32_t)var_3ch == 0xb83cb) {
    *(void ***)0x0;
    rotate_encrypt(e, (int64_t)&var_30h);
    arg2stdout;
    _10_fputs((void ***)0xB, (int64_t)_stdout);
}

```

```
┌──(kali㉿kali)-[~/Parcial3/unpackme]
└─$ python3
Python 3.12.6 (main, Sep  7 2024, 14:20:15) [GCC 14.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> 0xb83cb
754635
>>
┌──(kali㉿kali)-[~/Parcial3/unpackme]
└─$ ./unpackme-upx
What's my favorite number? 754635
picoCTF{up><_m3_f7w_77ad107e}
                                    
```

- Flag: picoCTF{up><_m3_f7w_77ad107e}
## Notas Adicionales
- **`upx`**: Es la herramienta que se usa para comprimir y descomprimir archivos ejecutables. UPX es comúnmente utilizada para reducir el tamaño de los binarios sin afectar su funcionalidad.
    
- **`-k`**: Esta opción le indica a UPX que **no realice la compresión**, sino que se limite a verificar si el archivo está comprimido y descomprimirlo en caso afirmativo.
    
- **`-d`**: Esta opción le dice a UPX que **desempaquete** o **descomprima** el archivo, es decir, que revierta la compresión realizada previamente sobre el archivo ejecutable.

## Referencias 
https://play.picoctf.org/practice/challenge/313
https://www.youtube.com/watch?v=jAVYAvmEzj0
[UPX review (executable packer) - Linux Security Expert](https://linuxsecurity.expert/tools/upx/#:~:text=UPX%20is%20the%20abbreviation%20for%20%22Ultimate%20Packer%20for,low%20overhead%20of%20memory%20due%20to%20in-place%20decompression.)