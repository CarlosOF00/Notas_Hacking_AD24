## Descripción 
Can you find the flag? [shark2.pcapng](https://mercury.picoctf.net/static/719e81d6fbb6b3157624268588fc0de8/shark2.pcapng).

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
┌──(kali㉿kali)-[~/Parcial2]
└─$ mkdir wireshark          
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2]
└─$ cd wireshark 
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2/wireshark]
└─$ wget https://mercury.picoctf.net/static/719e81d6fbb6b3157624268588fc0de8/shark2.pcapng          
--2024-10-17 18:25:00--  https://mercury.picoctf.net/static/719e81d6fbb6b3157624268588fc0de8/shark2.pcapng
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 3520112 (3.4M) [application/octet-stream]
Saving to: ‘shark2.pcapng’

shark2.pcapng                             100%[===================================================================================>]   3.36M  2.99MB/s    in 1.1s    

2024-10-17 18:25:02 (2.99 MB/s) - ‘shark2.pcapng’ saved [3520112/3520112]

                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2/wireshark]
└─$ ls
shark2.pcapng
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2/wireshark]
└─$ wireshark shark2.pcapng    
```
- Abrimos otra terminal 
```bash
┌──(kali㉿kali)-[~/Parcial2/wireshark]
└─$ tshark -nr shark2.pcapng -Y 'dns' | grep -v '8.8.8.8' | grep -v response | grep local | awk -e '{print $12}' | sed -e 's/\..*//'
cGljb0NU
RntkbnNf
M3hmMWxf
ZnR3X2Rl
YWRiZWVm
fQ==
fQ==
                                                                                                                                                  
┌──(kali㉿kali)-[~/Parcial2/wireshark]
└─$ echo 'cGljb0NU                                                 
RntkbnNf
M3hmMWxf
ZnR3X2Rl
YWRiZWVm
fQ==
fQ==
' | base64 -d
picoCTF{dns_3xf1l_ftw_deadbeef}}    
```

## Notas Adicionales
`tshark -nr shark2.pcapng -Y 'dns' | grep -v '8.8.8.8' | grep -v response | grep local | awk -e '{print $12}' | sed -e 's/\..*//'`

- **`tshark -nr shark2.pcapng -Y 'dns'`**:
    - `tshark`: Es una herramienta de línea de comandos que permite capturar y analizar tráfico de red. Es una versión en línea de comandos de Wireshark.
    - `-nr shark2.pcapng`: Este parámetro le dice a `tshark` que lea el archivo de captura `shark2.pcapng` sin realizar ninguna captura nueva.
    - `-Y 'dns'`: Aplica un filtro de display para mostrar solo los paquetes DNS (Domain Name System).
    
- **`grep -v '8.8.8.8'`**:
    - `grep -v`: Este comando filtra las líneas que **no** contienen la cadena `8.8.8.8`. En este caso, está excluyendo los paquetes que se refieren al servidor DNS público de Google (que normalmente tiene la IP `8.8.8.8`).
    
- **`grep -v response`**:
    - Filtra las líneas que no contienen la palabra `response`, es decir, elimina las respuestas DNS, dejando solo las solicitudes (queries).
    
- **`grep local`**:
    - Filtra las líneas que contienen la palabra `local`. Esto podría estar buscando solicitudes DNS que estén relacionadas con nombres de dominio locales (por ejemplo, una solicitud para un nombre de host interno en una red local).
    
- **`awk -e '{print $12}'`**:
    - Este comando `awk` toma el output de los comandos anteriores y selecciona la 12ª columna de cada línea. Aquí, se asume que el nombre del dominio solicitado por el cliente DNS aparece en la 12ª columna.
    
- **`sed -e 's/\..*//'`**:
    - El comando `sed` elimina cualquier cosa que esté después del primer punto (`.`) en cada línea. Esto es útil para obtener solo el nombre base del dominio (sin la parte del dominio de nivel superior como `.com`, `.net`, etc.). Por ejemplo, si se captura un nombre como `host.example.com`, este comando lo transformará en `host`.
## Referencias 
https://play.picoctf.org/practice/challenge/110
[Tshark ](https://tshark.dev/setup/install/)
[Medium](https://medium.com/@matus.vaclav1/picoctf-wireshark-twoo-twooo-two-twoo-7f00d1a923b4)
https://www.youtube.com/watch?v=mQB_yoAY0gg