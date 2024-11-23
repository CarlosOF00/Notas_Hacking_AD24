## Descripción 
Can you figure out what is in the `eax` register at the end of the `main` function? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`.Debug [this](https://artifacts.picoctf.net/c/520/debugger0_b).

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
┌──(kali㉿kali)-[~/Parcial3]
└─$ cd gdbBabyStep2
                                                                                 
┌──(kali㉿kali)-[~/Parcial3/gdbBabyStep2]
└─$ wget https://artifacts.picoctf.net/c/520/debugger0_b                        
--2024-11-17 13:17:21--  https://artifacts.picoctf.net/c/520/debugger0_b
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.249.21.85, 13.249.21.46, 13.249.21.66, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.249.21.85|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 16304 (16K) [application/octet-stream]
Saving to: ‘debugger0_b’

debugger0_b          100%[===================>]  15.92K  --.-KB/s    in 0s      

2024-11-17 13:17:22 (157 MB/s) - ‘debugger0_b’ saved [16304/16304]

                                                                                 
┌──(kali㉿kali)-[~/Parcial3/gdbBabyStep2]
└─$ ls
debugger0_b
                                                                                 
┌──(kali㉿kali)-[~/Parcial3/gdbBabyStep2]
└─$ chmod +x debugger0_b
                                                                                 
┌──(kali㉿kali)-[~/Parcial3/gdbBabyStep2]
└─$ ./debugger0_b 
                                                                                 
┌──(kali㉿kali)-[~/Parcial3/gdbBabyStep2]
└─$ ghidra debugger0_b 
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true
Picked up _JAVA_OPTIONS: -Dawt.useSystemAAFontSettings=on -Dswing.aatext=true

```

- Se abrirá le herramienta de `Hidra` en caso de no tener un proyecto, debemos de crear uno, después de tenerlo, en el apartado superior izquierdo `File` daremos clic en la opción de `Import File` buscamos el archivo que descargamos y lo seleccionamos.
- Pasara un tiempo en lo que lo analiza y se abrirá una nueva ventana.
- En el apartado izquierdo de `Symbol Tree` buscaremos las `Functions` y abriremos `Main`, se abrirá un apartado a la derecha llamado `Decompile` donde observaremos esto:
```bash
int main(void)

{
  int local_10;
  int local_c;
  
  local_c = 0x1e0da;
  for (local_10 = 0; local_10 < 0x25f; local_10 = local_10 + 1) {
    local_c = local_c + local_10;
  }
  return local_c;
}
```

- Lo editaremos un poco para pasarlo a Python quedando así:

```bash
def main():
    local_c = 0x1e0da  # Valor inicial de local_c
    for local_10 in range(0, 0x25f):  # El bucle va de 0 hasta 0x25f-1
        local_c += local_10  # Sumar local_10 a local_c
    return local_c  # Devolver el resultado final
    
# Llamar a la función y imprimir el resultado
result = main()
print(result)

#Salida
307019
```

- Flag: picoCTF{307019}

## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/396
