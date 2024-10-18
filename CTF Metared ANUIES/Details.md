## Objetivo 

## Datos de Acceso al Nivel
user: carlosof
password:

## Solución
- Descargamos el archivo.
```bash
┌──(kali㉿kali)-[~/Concurso_Metared]
└─$ mkdir Details      
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Concurso_Metared]
└─$ cd Details         
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Concurso_Metared/Details]
└─$ ls    
'Ciberseguridad.pptx?token=eyJ1c2VyX2lkIjoyMTIsInRlYW1faWQiOjc2LCJmaWxlX2lkIjoxN30.Zw8Uxg.TJid82ik91BH2k8rCmBkerIeibs'
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Concurso_Metared/Details]
└─$ ls -la             
total 5532
drwxrwxr-x 2 kali kali    4096 Oct 17 21:42  .
drwxrwxr-x 3 kali kali    4096 Oct 17 21:42  ..
-rw-rw-r-- 1 kali kali 5653594 Sep 30 20:48 'Ciberseguridad.pptx?token=eyJ1c2VyX2lkIjoyMTIsInRlYW1faWQiOjc2LCJmaWxlX2lkIjoxN30.Zw8Uxg.TJid82ik91BH2k8rCmBkerIeibs'

┌──(kali㉿kali)-[~/Concurso_Metared/Details]
└─$ unzip Ciberseguridad.pptx\?token=eyJ1c2VyX2lkIjoyMTIsInRlYW1faWQiOjc2LCJmaWxlX2lkIjoxN30.Zw8Uxg.TJid82ik91BH2k8rCmBkerIeibs   
Archive:  Ciberseguridad.pptx?token=eyJ1c2VyX2lkIjoyMTIsInRlYW1faWQiOjc2LCJmaWxlX2lkIjoxN30.Zw8Uxg.TJid82ik91BH2k8rCmBkerIeibs
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Concurso_Metared/Details]
└─$ ls
'Ciberseguridad.pptx?token=eyJ1c2VyX2lkIjoyMTIsInRlYW1faWQiOjc2LCJmaWxlX2lkIjoxN30.Zw8Uxg.TJid82ik91BH2k8rCmBkerIeibs'   _rels      ppt
'[Content_Types].xml'                                                                                                    docProps
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Concurso_Metared/Details]
└─$ tree                                                                                                                            
.
├── Ciberseguridad.pptx?token=eyJ1c2VyX2lkIjoyMTIsInRlYW1faWQiOjc2LCJmaWxlX2lkIjoxN30.Zw8Uxg.TJid82ik91BH2k8rCmBkerIeibs
├── [Content_Types].xml
├── _rels
├── docProps
│   ├── app.xml
│   ├── core.xml
│   └── custom.xml
└── ppt
    ├── _rels
    │   └── presentation.xml.rels
    ├── media
    │   ├── file.png
    │   ├── image1.png
    │   ├── image10.jpeg
    │   ├── image11.png
    │   ├── image12.png
    │   ├── image2.png
    │   ├── image3.jpeg
    │   ├── image4.jpeg
    │   ├── image5.jpeg
    │   ├── image6.png
    │   ├── image7.jpeg
    │   ├── image8.png
    │   └── image9.png
    ├── presProps.xml
    ├── presentation.xml
    ├── slideLayouts
    │   ├── _rels
    │   │   ├── slideLayout1.xml.rels
    │   │   ├── slideLayout10.xml.rels
    │   │   ├── slideLayout11.xml.rels
    │   │   ├── slideLayout12.xml.rels
    │   │   ├── slideLayout13.xml.rels
    │   │   ├── slideLayout14.xml.rels
    │   │   ├── slideLayout15.xml.rels
    │   │   ├── slideLayout16.xml.rels
    │   │   ├── slideLayout17.xml.rels
    │   │   ├── slideLayout18.xml.rels
    │   │   ├── slideLayout19.xml.rels
    │   │   ├── slideLayout2.xml.rels
    │   │   ├── slideLayout20.xml.rels
    │   │   ├── slideLayout21.xml.rels
    │   │   ├── slideLayout22.xml.rels
    │   │   ├── slideLayout23.xml.rels
    │   │   ├── slideLayout24.xml.rels
    │   │   ├── slideLayout25.xml.rels
    │   │   ├── slideLayout26.xml.rels
    │   │   ├── slideLayout27.xml.rels
    │   │   ├── slideLayout28.xml.rels
    │   │   ├── slideLayout29.xml.rels
    │   │   ├── slideLayout3.xml.rels
    │   │   ├── slideLayout30.xml.rels
    │   │   ├── slideLayout31.xml.rels
    │   │   ├── slideLayout32.xml.rels
    │   │   ├── slideLayout33.xml.rels
    │   │   ├── slideLayout34.xml.rels
    │   │   ├── slideLayout35.xml.rels
    │   │   ├── slideLayout36.xml.rels
    │   │   ├── slideLayout4.xml.rels
    │   │   ├── slideLayout5.xml.rels
    │   │   ├── slideLayout6.xml.rels
    │   │   ├── slideLayout7.xml.rels
    │   │   ├── slideLayout8.xml.rels
    │   │   └── slideLayout9.xml.rels
    │   ├── slideLayout1.xml
    │   ├── slideLayout10.xml
    │   ├── slideLayout11.xml
    │   ├── slideLayout12.xml
    │   ├── slideLayout13.xml
    │   ├── slideLayout14.xml
    │   ├── slideLayout15.xml
    │   ├── slideLayout16.xml
    │   ├── slideLayout17.xml
    │   ├── slideLayout18.xml
    │   ├── slideLayout19.xml
    │   ├── slideLayout2.xml
    │   ├── slideLayout20.xml
    │   ├── slideLayout21.xml
    │   ├── slideLayout22.xml
    │   ├── slideLayout23.xml
    │   ├── slideLayout24.xml
    │   ├── slideLayout25.xml
    │   ├── slideLayout26.xml
    │   ├── slideLayout27.xml
    │   ├── slideLayout28.xml
    │   ├── slideLayout29.xml
    │   ├── slideLayout3.xml
    │   ├── slideLayout30.xml
    │   ├── slideLayout31.xml
    │   ├── slideLayout32.xml
    │   ├── slideLayout33.xml
    │   ├── slideLayout34.xml
    │   ├── slideLayout35.xml
    │   ├── slideLayout36.xml
    │   ├── slideLayout4.xml
    │   ├── slideLayout5.xml
    │   ├── slideLayout6.xml
    │   ├── slideLayout7.xml
    │   ├── slideLayout8.xml
    │   └── slideLayout9.xml
    ├── slideMasters
    │   ├── _rels
    │   │   ├── slideMaster1.xml.rels
    │   │   ├── slideMaster2.xml.rels
    │   │   └── slideMaster3.xml.rels
    │   ├── slideMaster1.xml
    │   ├── slideMaster2.xml
    │   └── slideMaster3.xml
    ├── slides
    │   ├── _rels
    │   │   ├── slide1.xml.rels
    │   │   ├── slide10.xml.rels
    │   │   ├── slide2.xml.rels
    │   │   ├── slide3.xml.rels
    │   │   ├── slide4.xml.rels
    │   │   ├── slide5.xml.rels
    │   │   ├── slide6.xml.rels
    │   │   ├── slide7.xml.rels
    │   │   ├── slide8.xml.rels
    │   │   └── slide9.xml.rels
    │   ├── slide1.xml
    │   ├── slide10.xml
    │   ├── slide2.xml
    │   ├── slide3.xml
    │   ├── slide4.xml
    │   ├── slide5.xml
    │   ├── slide6.xml
    │   ├── slide7.xml
    │   ├── slide8.xml
    │   └── slide9.xml
    └── theme
        ├── theme1.xml
        ├── theme2.xml
        └── theme3.xml

13 directories, 122 files

┌──(kali㉿kali)-[~/Concurso_Metared/Details]
└─$ cd ppt/media 
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Concurso_Metared/Details/ppt/media]
└─$ ls
file.png  image1.png  image10.jpeg  image11.png  image12.png  image2.png  image3.jpeg  image4.jpeg  image5.jpeg  image6.png  image7.jpeg  image8.png  image9.png
┌──(kali㉿kali)-[~/Concurso_Metared/Details/ppt/media]
└─$ cat file.png           
iVBORw0KGgoAAAANSUhEUgAABDoAAALQCAYAAABxIhBnAAAAyXpUWHRSYXcgcHJvZmlsZSB0eXBlIGV4aWYAAHjabVDbDcMgDPxnio7gBw8zjtMkUjfo+LUxSEnUkzj84rCdju/nTC8HYU65NKm9VjDknjupGQIBHYyQBw+wDs/9WzztADQsshB7ZSSkxo0rPh+sG9WschGS90xs90SPf4HkITQ/Yu/IW9inUJ9CTJHAKaAxFtQu7TrCdsAdEic5cYvxlsjTz822txcLMtHByGDMLNEA+8mJ1QwxJi5WiFagxmXE++zEFvJvTwvpB3p5WYlxrLQDAAABhGlDQ1BJQ0MgcHJvZmlsZQAAeJx9kT1Iw0AcxV9TpUWqDu2g4pChOlkQFXHUKhShQqkVWnUwufQLmjQkKS6OgmvBwY/FqoOLs64OroIg+AHi7OCk6CIl/i8ptIjx4Lgf7+497t4BQqPCVLNrHFA1y0gn4mI2tyoGXhHEIMLoQ0xipj6XSiXhOb7u4ePrXYxneZ/7c/QqeZMBPpF4lumGRbxBPL1p6Zz3iSOsJCnE58RjBl2Q+JHrsstvnIsOCzwzYmTS88QRYrHYwXIHs5KhEk8RRxVVo3wh67LCeYuzWqmx1j35C0N5bWWZ6zSHkcAilpCCCBk1lFGBhRitGikm0rQf9/APOf4UuWRylcHIsYAqVEiOH/wPfndrFiYn3KRQHOh+se2PESCwCzTrtv19bNvNE8D/DFxpbX+1Acx8kl5va9EjoH8buLhua/IecLkDDDzpkiE5kp+mUCgA72f0TTkgfAv0rLm9tfZx+gBkqKvkDXBwCIwWKXvd493Bzt7+PdPq7weJrHKwyVQzUgAADz5pVFh0WE1MOmNvbS5hZG9iZS54bXAAAAAAADw/eHBhY2tldCBiZWdpbj0i77u/IiBpZD0iVzVNME1wQ2VoaUh6cmVTek5UY3prYzlkIj8+Cjx4OnhtcG1ldGEgeG1sbnM6eD0iYWRvYmU6bnM6bWV0YS8iIHg6eG1wdGs9IlhNUCBDb3JlIDQuNC4wLUV4aXYyIj4KIDxyZGY6UkRGIHhtbG5zOnJkZj0iaHR0cDovL3d3dy53My5vcmcvMTk5OS8wMi8yMi1yZGYtc3ludGF4LW5zIyI+CiAgPHJkZjpEZXNjcmlwdGlvbiByZGY6YWJvdXQ9IiIKICAgIHhtbG5zOnhtcE1NPSJodHRwOi8vbnMuYWRvYmUuY29tL3hhcC8xLjAvbW0vIgogICAgeG1sbnM6c3RFdnQ9Imh0dHA6Ly9ucy5hZG9iZS5jb20veGFwLzEuMC9zVHlwZS9SZXNvdXJjZUV2ZW50IyIKICAgIHhtbG5zOmRjPSJodHRwOi8vcHVybC5vcmcvZGMvZWxlbWVudHMvMS4xLyIKICAgIHhtbG5zOkdJTVA9Imh0dHA6Ly93d3cuZ2ltcC5vcmcveG1wLyIKICAgIHhtbG5zOnRpZmY9Im

┌──(kali㉿kali)-[~/Concurso_Metared/Details/ppt/media]
└─$ cp file.png file.txt  
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Concurso_Metared/Details/ppt/media]
└─$ ls
file.png  image1.png    image11.png  image2.png   image4.jpeg  image6.png   image8.png
file.txt  image10.jpeg  image12.png  image3.jpeg  image5.jpeg  image7.jpeg  image9.png
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Concurso_Metared/Details/ppt/media]
└─$ base64 -d file.txt > imagen.png 

┌──(kali㉿kali)-[~/Concurso_Metared/Details/ppt/media]
└─$ open imagen.png  
                                                                                 
┌──(kali㉿kali)-[~/Concurso_Metared/Details/ppt/media]
└─$ echo 'flagmx{the_details_are_important}'                                    
flagmx{the_details_are_important}
                                                                                 
┌──(kali㉿kali)-[~/Concurso_Metared/Details/ppt/media]
└─$ 
```
## Notas Adicionales

## Referencias 
https://ctfd.anuies.mx/challenges#Details-20
