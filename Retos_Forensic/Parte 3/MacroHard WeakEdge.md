## Descripción 
I've hidden a flag in this file. Can you find it? [Forensics is fun.pptm](https://mercury.picoctf.net/static/d3dd8cd51524d9fafcccd1b7d55f85e7/Forensics%20is%20fun.pptm)

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
┌──(kali㉿kali)-[~/retosForensic]
└─$ mkdir macroHard   
                                                                                 
┌──(kali㉿kali)-[~/retosForensic]
└─$ cd macroHard    
                                                                                 
┌──(kali㉿kali)-[~/retosForensic/macroHard]
└─$ wget https://mercury.picoctf.net/static/d3dd8cd51524d9fafcccd1b7d55f85e7/Forensics%20is%20fun.pptm
--2024-10-08 20:05:52--  https://mercury.picoctf.net/static/d3dd8cd51524d9fafcccd1b7d55f85e7/Forensics%20is%20fun.pptm
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 100093 (98K) [application/octet-stream]
Saving to: ‘Forensics is fun.pptm’

Forensics is fun.ppt 100%[===================>]  97.75K  --.-KB/s    in 0.08s   

2024-10-08 20:05:53 (1.13 MB/s) - ‘Forensics is fun.pptm’ saved [100093/100093]

                                                                                 
┌──(kali㉿kali)-[~/retosForensic/macroHard]
└─$ ls -la
total 108
drwxrwxr-x  2 kali kali   4096 Oct  8 20:05  .
drwxrwxr-x 11 kali kali   4096 Oct  8 20:05  ..
-rw-rw-r--  1 kali kali 100093 Mar 23  2021 'Forensics is fun.pptm'
                                                                                 
┌──(kali㉿kali)-[~/retosForensic/macroHard]
└─$ unzip Forensics\ is\ fun.pptm 
Archive:  Forensics is fun.pptm
  inflating: [Content_Types].xml     
  inflating: _rels/.rels             
  inflating: ppt/presentation.xml    
  inflating: ppt/slides/_rels/slide46.xml.rels  
  inflating: ppt/slides/slide1.xml   
  inflating: ppt/slides/slide2.xml   
  inflating: ppt/slides/slide3.xml   
  inflating: ppt/slides/slide4.xml   
  inflating: ppt/slides/slide5.xml   
  inflating: ppt/slides/slide6.xml   
  inflating: ppt/slides/slide7.xml   
  inflating: ppt/slides/slide8.xml   
  inflating: ppt/slides/slide9.xml   
  inflating: ppt/slides/slide10.xml  
  inflating: ppt/slides/slide11.xml  
  inflating: ppt/slides/slide12.xml  
  inflating: ppt/slides/slide13.xml  
  inflating: ppt/slides/slide14.xml  
  inflating: ppt/slides/slide15.xml  
  inflating: ppt/slides/slide16.xml  
  inflating: ppt/slides/slide17.xml  
  inflating: ppt/slides/slide18.xml  
  inflating: ppt/slides/slide19.xml  
  inflating: ppt/slides/slide20.xml  
  inflating: ppt/slides/slide21.xml  
  inflating: ppt/slides/slide22.xml  
  inflating: ppt/slides/slide23.xml  
  inflating: ppt/slides/slide24.xml  
  inflating: ppt/slides/slide25.xml  
  inflating: ppt/slides/slide26.xml  
  inflating: ppt/slides/slide27.xml  
  inflating: ppt/slides/slide28.xml  
  inflating: ppt/slides/slide29.xml  
  inflating: ppt/slides/slide30.xml  
  inflating: ppt/slides/slide31.xml  
  inflating: ppt/slides/slide32.xml  
  inflating: ppt/slides/slide33.xml  
  inflating: ppt/slides/slide34.xml  
  inflating: ppt/slides/slide35.xml  
  inflating: ppt/slides/slide36.xml  
  inflating: ppt/slides/slide37.xml  
  inflating: ppt/slides/slide38.xml  
  inflating: ppt/slides/slide39.xml  
  inflating: ppt/slides/slide40.xml  
  inflating: ppt/slides/slide41.xml  
  inflating: ppt/slides/slide42.xml  
  inflating: ppt/slides/slide43.xml  
  inflating: ppt/slides/slide44.xml  
  inflating: ppt/slides/slide45.xml  
  inflating: ppt/slides/slide46.xml  
  inflating: ppt/slides/slide47.xml  
  inflating: ppt/slides/slide48.xml  
  inflating: ppt/slides/slide49.xml  
  inflating: ppt/slides/slide50.xml  
  inflating: ppt/slides/slide51.xml  
  inflating: ppt/slides/slide52.xml  
  inflating: ppt/slides/slide53.xml  
  inflating: ppt/slides/slide54.xml  
  inflating: ppt/slides/slide55.xml  
  inflating: ppt/slides/slide56.xml  
  inflating: ppt/slides/slide57.xml  
  inflating: ppt/slides/slide58.xml  
  inflating: ppt/slides/_rels/slide47.xml.rels  
  inflating: ppt/slides/_rels/slide48.xml.rels  
  inflating: ppt/slides/_rels/slide49.xml.rels  
  inflating: ppt/slides/_rels/slide50.xml.rels  
  inflating: ppt/slides/_rels/slide32.xml.rels  
  inflating: ppt/slides/_rels/slide52.xml.rels  
  inflating: ppt/slides/_rels/slide53.xml.rels  
  inflating: ppt/slides/_rels/slide54.xml.rels  
  inflating: ppt/slides/_rels/slide55.xml.rels  
  inflating: ppt/slides/_rels/slide56.xml.rels  
  inflating: ppt/slides/_rels/slide57.xml.rels  
  inflating: ppt/slides/_rels/slide58.xml.rels  
  inflating: ppt/slides/_rels/slide51.xml.rels  
  inflating: ppt/slides/_rels/slide13.xml.rels  
  inflating: ppt/_rels/presentation.xml.rels  
  inflating: ppt/slides/_rels/slide1.xml.rels  
  inflating: ppt/slides/_rels/slide2.xml.rels  
  inflating: ppt/slides/_rels/slide3.xml.rels  
  inflating: ppt/slides/_rels/slide4.xml.rels  
  inflating: ppt/slides/_rels/slide5.xml.rels  
  inflating: ppt/slides/_rels/slide6.xml.rels  
  inflating: ppt/slides/_rels/slide7.xml.rels  
  inflating: ppt/slides/_rels/slide8.xml.rels  
  inflating: ppt/slides/_rels/slide9.xml.rels  
  inflating: ppt/slides/_rels/slide10.xml.rels  
  inflating: ppt/slides/_rels/slide11.xml.rels  
  inflating: ppt/slides/_rels/slide12.xml.rels  
  inflating: ppt/slides/_rels/slide14.xml.rels  
  inflating: ppt/slides/_rels/slide15.xml.rels  
  inflating: ppt/slides/_rels/slide16.xml.rels  
  inflating: ppt/slides/_rels/slide17.xml.rels  
  inflating: ppt/slides/_rels/slide18.xml.rels  
  inflating: ppt/slides/_rels/slide19.xml.rels  
  inflating: ppt/slides/_rels/slide20.xml.rels  
  inflating: ppt/slides/_rels/slide21.xml.rels  
  inflating: ppt/slides/_rels/slide22.xml.rels  
  inflating: ppt/slides/_rels/slide23.xml.rels  
  inflating: ppt/slides/_rels/slide24.xml.rels  
  inflating: ppt/slides/_rels/slide25.xml.rels  
  inflating: ppt/slides/_rels/slide26.xml.rels  
  inflating: ppt/slides/_rels/slide27.xml.rels  
  inflating: ppt/slides/_rels/slide28.xml.rels  
  inflating: ppt/slides/_rels/slide29.xml.rels  
  inflating: ppt/slides/_rels/slide30.xml.rels  
  inflating: ppt/slides/_rels/slide31.xml.rels  
  inflating: ppt/slides/_rels/slide33.xml.rels  
  inflating: ppt/slides/_rels/slide34.xml.rels  
  inflating: ppt/slides/_rels/slide35.xml.rels  
  inflating: ppt/slides/_rels/slide36.xml.rels  
  inflating: ppt/slides/_rels/slide37.xml.rels  
  inflating: ppt/slides/_rels/slide38.xml.rels  
  inflating: ppt/slides/_rels/slide39.xml.rels  
  inflating: ppt/slides/_rels/slide40.xml.rels  
  inflating: ppt/slides/_rels/slide41.xml.rels  
  inflating: ppt/slides/_rels/slide42.xml.rels  
  inflating: ppt/slides/_rels/slide43.xml.rels  
  inflating: ppt/slides/_rels/slide44.xml.rels  
  inflating: ppt/slides/_rels/slide45.xml.rels  
  inflating: ppt/slideMasters/slideMaster1.xml  
  inflating: ppt/slideLayouts/slideLayout1.xml  
  inflating: ppt/slideLayouts/slideLayout2.xml  
  inflating: ppt/slideLayouts/slideLayout3.xml  
  inflating: ppt/slideLayouts/slideLayout4.xml  
  inflating: ppt/slideLayouts/slideLayout5.xml  
  inflating: ppt/slideLayouts/slideLayout6.xml  
  inflating: ppt/slideLayouts/slideLayout7.xml  
  inflating: ppt/slideLayouts/slideLayout8.xml  
  inflating: ppt/slideLayouts/slideLayout9.xml  
  inflating: ppt/slideLayouts/slideLayout10.xml  
  inflating: ppt/slideLayouts/slideLayout11.xml  
  inflating: ppt/slideMasters/_rels/slideMaster1.xml.rels  
  inflating: ppt/slideLayouts/_rels/slideLayout1.xml.rels  
  inflating: ppt/slideLayouts/_rels/slideLayout2.xml.rels  
  inflating: ppt/slideLayouts/_rels/slideLayout3.xml.rels  
  inflating: ppt/slideLayouts/_rels/slideLayout4.xml.rels  
  inflating: ppt/slideLayouts/_rels/slideLayout5.xml.rels  
  inflating: ppt/slideLayouts/_rels/slideLayout6.xml.rels  
  inflating: ppt/slideLayouts/_rels/slideLayout7.xml.rels  
  inflating: ppt/slideLayouts/_rels/slideLayout8.xml.rels  
  inflating: ppt/slideLayouts/_rels/slideLayout9.xml.rels  
  inflating: ppt/slideLayouts/_rels/slideLayout10.xml.rels  
  inflating: ppt/slideLayouts/_rels/slideLayout11.xml.rels  
  inflating: ppt/theme/theme1.xml    
 extracting: docProps/thumbnail.jpeg  
  inflating: ppt/vbaProject.bin      
  inflating: ppt/presProps.xml       
  inflating: ppt/viewProps.xml       
  inflating: ppt/tableStyles.xml     
  inflating: docProps/core.xml       
  inflating: docProps/app.xml        
  inflating: ppt/slideMasters/hidden  
                                                                                 
┌──(kali㉿kali)-[~/retosForensic/macroHard]
└─$ ls    
'Forensics is fun.pptm'  '[Content_Types].xml'   _rels   docProps   ppt
                                                                                 
┌──(kali㉿kali)-[~/retosForensic/macroHard]
└─$ tree
.
├── Forensics is fun.pptm
├── [Content_Types].xml
├── _rels
├── docProps
│   ├── app.xml
│   ├── core.xml
│   └── thumbnail.jpeg
└── ppt
    ├── _rels
    │   └── presentation.xml.rels
    ├── presProps.xml
    ├── presentation.xml
    ├── slideLayouts
    │   ├── _rels
    │   │   ├── slideLayout1.xml.rels
    │   │   ├── slideLayout10.xml.rels
    │   │   ├── slideLayout11.xml.rels
    │   │   ├── slideLayout2.xml.rels
    │   │   ├── slideLayout3.xml.rels
    │   │   ├── slideLayout4.xml.rels
    │   │   ├── slideLayout5.xml.rels
    │   │   ├── slideLayout6.xml.rels
    │   │   ├── slideLayout7.xml.rels
    │   │   ├── slideLayout8.xml.rels
    │   │   └── slideLayout9.xml.rels
    │   ├── slideLayout1.xml
    │   ├── slideLayout10.xml
    │   ├── slideLayout11.xml
    │   ├── slideLayout2.xml
    │   ├── slideLayout3.xml
    │   ├── slideLayout4.xml
    │   ├── slideLayout5.xml
    │   ├── slideLayout6.xml
    │   ├── slideLayout7.xml
    │   ├── slideLayout8.xml
    │   └── slideLayout9.xml
    ├── slideMasters
    │   ├── _rels
    │   │   └── slideMaster1.xml.rels
    │   ├── hidden
    │   └── slideMaster1.xml
    ├── slides
    │   ├── _rels
    │   │   ├── slide1.xml.rels
    │   │   ├── slide10.xml.rels
    │   │   ├── slide11.xml.rels
    │   │   ├── slide12.xml.rels
    │   │   ├── slide13.xml.rels
    │   │   ├── slide14.xml.rels
    │   │   ├── slide15.xml.rels
    │   │   ├── slide16.xml.rels
    │   │   ├── slide17.xml.rels
    │   │   ├── slide18.xml.rels
    │   │   ├── slide19.xml.rels
    │   │   ├── slide2.xml.rels
    │   │   ├── slide20.xml.rels
    │   │   ├── slide21.xml.rels
    │   │   ├── slide22.xml.rels
    │   │   ├── slide23.xml.rels
    │   │   ├── slide24.xml.rels
    │   │   ├── slide25.xml.rels
    │   │   ├── slide26.xml.rels
    │   │   ├── slide27.xml.rels
    │   │   ├── slide28.xml.rels
    │   │   ├── slide29.xml.rels
    │   │   ├── slide3.xml.rels
    │   │   ├── slide30.xml.rels
    │   │   ├── slide31.xml.rels
    │   │   ├── slide32.xml.rels
    │   │   ├── slide33.xml.rels
    │   │   ├── slide34.xml.rels
    │   │   ├── slide35.xml.rels
    │   │   ├── slide36.xml.rels
    │   │   ├── slide37.xml.rels
    │   │   ├── slide38.xml.rels
    │   │   ├── slide39.xml.rels
    │   │   ├── slide4.xml.rels
    │   │   ├── slide40.xml.rels
    │   │   ├── slide41.xml.rels
    │   │   ├── slide42.xml.rels
    │   │   ├── slide43.xml.rels
    │   │   ├── slide44.xml.rels
    │   │   ├── slide45.xml.rels
    │   │   ├── slide46.xml.rels
    │   │   ├── slide47.xml.rels
    │   │   ├── slide48.xml.rels
    │   │   ├── slide49.xml.rels
    │   │   ├── slide5.xml.rels
    │   │   ├── slide50.xml.rels
    │   │   ├── slide51.xml.rels
    │   │   ├── slide52.xml.rels
    │   │   ├── slide53.xml.rels
    │   │   ├── slide54.xml.rels
    │   │   ├── slide55.xml.rels
    │   │   ├── slide56.xml.rels
    │   │   ├── slide57.xml.rels
    │   │   ├── slide58.xml.rels
    │   │   ├── slide6.xml.rels
    │   │   ├── slide7.xml.rels
    │   │   ├── slide8.xml.rels
    │   │   └── slide9.xml.rels
    │   ├── slide1.xml
    │   ├── slide10.xml
    │   ├── slide11.xml
    │   ├── slide12.xml
    │   ├── slide13.xml
    │   ├── slide14.xml
    │   ├── slide15.xml
    │   ├── slide16.xml
    │   ├── slide17.xml
    │   ├── slide18.xml
    │   ├── slide19.xml
    │   ├── slide2.xml
    │   ├── slide20.xml
    │   ├── slide21.xml
    │   ├── slide22.xml
    │   ├── slide23.xml
    │   ├── slide24.xml
    │   ├── slide25.xml
    │   ├── slide26.xml
    │   ├── slide27.xml
    │   ├── slide28.xml
    │   ├── slide29.xml
    │   ├── slide3.xml
    │   ├── slide30.xml
    │   ├── slide31.xml
    │   ├── slide32.xml
    │   ├── slide33.xml
    │   ├── slide34.xml
    │   ├── slide35.xml
    │   ├── slide36.xml
    │   ├── slide37.xml
    │   ├── slide38.xml
    │   ├── slide39.xml
    │   ├── slide4.xml
    │   ├── slide40.xml
    │   ├── slide41.xml
    │   ├── slide42.xml
    │   ├── slide43.xml
    │   ├── slide44.xml
    │   ├── slide45.xml
    │   ├── slide46.xml
    │   ├── slide47.xml
    │   ├── slide48.xml
    │   ├── slide49.xml
    │   ├── slide5.xml
    │   ├── slide50.xml
    │   ├── slide51.xml
    │   ├── slide52.xml
    │   ├── slide53.xml
    │   ├── slide54.xml
    │   ├── slide55.xml
    │   ├── slide56.xml
    │   ├── slide57.xml
    │   ├── slide58.xml
    │   ├── slide6.xml
    │   ├── slide7.xml
    │   ├── slide8.xml
    │   └── slide9.xml
    ├── tableStyles.xml
    ├── theme
    │   └── theme1.xml
    ├── vbaProject.bin
    └── viewProps.xml

12 directories, 153 files
                                                                                 
┌──(kali㉿kali)-[~/retosForensic/macroHard]
└─$ cd ppt/slideMasters/      
                                                                                 
┌──(kali㉿kali)-[~/retosForensic/macroHard/ppt/slideMasters]
└─$ file hidden                                                
hidden: ASCII text, with no line terminators
                                                                                 
┌──(kali㉿kali)-[~/retosForensic/macroHard/ppt/slideMasters]
└─$ cat hidden  
Z m x h Z z o g c G l j b 0 N U R n t E M W R f d V 9 r b j B 3 X 3 B w d H N f c l 9 6 M X A 1 f Q                                                                                 
┌──(kali㉿kali)-[~/retosForensic/macroHard/ppt/slideMasters]
└─$ cat hidden | tr -d ' ' | base64 -d        
flag: picoCTF{D1d_u_kn0w_ppts_r_z1p5}base64: invalid input

```
## Notas Adicionales
`cat hidden | tr -d ' ' | base64 -d  `

- **`cat hidden`**: Este comando lee el contenido del archivo llamado `hidden` y lo muestra en la salida estándar (generalmente la pantalla).
    
- **`tr -d ' '`**: El comando `tr` se utiliza para traducir o eliminar caracteres. En este caso, la opción `-d ' '` elimina todos los espacios en blanco (caracteres de espacio) del texto que le pasa el comando anterior.
    
- **`base64 -d`**: El comando `base64` se usa para codificar y decodificar datos en formato Base64. La opción `-d` indica que debe decodificar el texto en lugar de codificarlo. Así que toma el texto sin espacios y lo decodifica de Base64.

## Referencias 
https://play.picoctf.org/practice/challenge/130
https://askubuntu.com/questions/178521/how-can-i-decode-a-base64-string-from-the-command-line
