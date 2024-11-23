## Descripción 
I wonder what this really is... [enc](https://mercury.picoctf.net/static/e47483f88b12f2ab0c46315afc12f64d/enc) `''.join([chr((ord(flag[i]) << 8) + ord(flag[i + 1])) for i in range(0, len(flag), 2)])`

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
┌──(kali㉿kali)-[~/Parcial3]
└─$ mkdir Transformation
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial3]
└─$ cd Transformation 
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial3/Transformation]
└─$ wget https://mercury.picoctf.net/static/e47483f88b12f2ab0c46315afc12f64d/enc
--2024-11-17 13:09:11--  https://mercury.picoctf.net/static/e47483f88b12f2ab0c46315afc12f64d/enc
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 57 [application/octet-stream]
Saving to: ‘enc’

enc                                       100%[===================================================================================>]      57  --.-KB/s    in 0s      

2024-11-17 13:09:11 (60.2 MB/s) - ‘enc’ saved [57/57]

                                                                                 
┌──(kali㉿kali)-[~/Parcial3/Transformation]
└─$ ls
enc
                                                                                 
┌──(kali㉿kali)-[~/Parcial3/Transformation]
└─$ file enc        
enc: Unicode text, UTF-8 text, with no line terminators
                                                                                 
┌──(kali㉿kali)-[~/Parcial3/Transformation]
└─$ cat enc          
灩捯䍔䙻ㄶ形楴獟楮獴㌴摟潦弸彥ㄴㅡて㝽                                                                                 
┌──(kali㉿kali)-[~/Parcial3/Transformation]
└─$ python3           
Python 3.12.6 (main, Sep  7 2024, 14:20:15) [GCC 14.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> enc=open("enc").read()
>>> print(enc)
灩捯䍔䙻ㄶ形楴獟楮獴㌴摟潦弸彥ㄴㅡて㝽
>>> print(hex(ord(enc[0])))
0x7069
>>> for c in enc:
...     print(hex(ord(c)).lstrip("0x"),end='')
... 
7069636f4354467b31365f626974735f696e73743334645f6f665f385f65313431613066377d>>> 
>>> hex_string = "7069636f4354467b31365f626974735f696e73743334645f6f665f385f65313431613066377d"
>>> bytes_data = bytes.fromhex(hex_string)
>>> decoded_text = bytes_data.decode('ascii')
>>> print(decoded_text)
picoCTF{16_bits_inst34d_of_8_e141a0f7}
>>> 
```

- Flag: picoCTF{16_bits_inst34d_of_8_e141a0f7}

## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/104
