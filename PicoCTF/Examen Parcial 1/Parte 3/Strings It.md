## Descripción 
Can you find the flag in [file](https://jupiter.challenges.picoctf.org/static/94d00153b0057d37da225ee79a846c62/strings) without running it?

## Datos de Acceso al Nivel
user: carlosof
password:

## Solución
```bash
carlosof-picoctf@webshell:/tmp/tmp.yCooFOblBe$ ls
strings
carlosof-picoctf@webshell:/tmp/tmp.yCooFOblBe$ strings strings
s4940
s4590
s8640
s8290
s619
s249
s204
s9879
s9446
s9409
s9016
s1279
s5346
s1846
s531
s181
s5033
s1533
s9559
s9109
s889
stdout@@GLIBC_2.2.5
s698
s4233
s9587
s9137
s4883
s8990
s8953
s8583
s2772
s2735
s6822
s6472
s6435
s2179
s6987
s6901
s6531
s2831
s6174
s2474
s2061
s2024
s1743
s1708
s5243
s5208
s6446
s2746
s5781
s5744
s5394
s1894
s615
s245
s200
s7687
s7601
s7231
s3731
s6792
s6757
s9276
s8143
s8108
s4443
s4408
main
s3333
s6212
s2512
s9761
s9724
s9351
s9314
s5074
s1574
s1161
s1124
s7522
s7172
s7135
s3672
s3635
s5840
s5470
s1970
s7146
s3646
s2794
s6881
s4178
s4139
s4674
s8744
s8374
.symtab
.strtab
.shstrtab
.interp
.note.ABI-tag
.note.gnu.build-id
.gnu.hash
.dynsym
.dynstr
.gnu.version
.gnu.version_r
.rela.dyn
.rela.plt
.init
.plt.got
.text
.fini
.rodata
.eh_frame_hdr
.eh_frame
.init_array
.fini_array
.dynamic
.data
.bss
.comment
carlosof-picoctf@webshell:/tmp/tmp.yCooFOblBe$ strings stings | grep picoCTF
strings: 'stings': No such file
carlosof-picoctf@webshell:/tmp/tmp.yCooFOblBe$ strings strings | grep picoCTF
picoCTF{5tRIng5_1T_d66c7bb7}
carlosof-picoctf@webshell:/tmp/tmp.yCooFOblBe$ 
```


## Notas Adicionales
- El comando `strings` extrae y muestra las secuencias de caracteres legibles (de al menos 4 caracteres de longitud por defecto) de archivos binarios. Es especialmente útil para inspeccionar archivos binarios y ver qué texto imprimible contienen.

## Referencias 
https://play.picoctf.org/practice/challenge/37
[How to Use the strings Command on Linux (howtogeek.com)](https://www.howtogeek.com/427805/how-to-use-the-strings-command-on-linux/)