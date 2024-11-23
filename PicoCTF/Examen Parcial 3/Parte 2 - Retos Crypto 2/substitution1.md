## Descripción 
A second message has come in the mail, and it seems almost identical to the first one. Maybe the same thing will work again.Download the message [here](https://artifacts.picoctf.net/c/182/message.txt).

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
┌──(kali㉿kali)-[~/Parcial3]
└─$ mkdir substitution1
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Parcial3]
└─$ cd substitution1
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Parcial3/substitution1]
└─$ wget https://artifacts.picoctf.net/c/182/message.txt
--2024-11-17 07:00:57--  https://artifacts.picoctf.net/c/182/message.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.249.21.66, 13.249.21.46, 13.249.21.85, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.249.21.66|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 638 [application/octet-stream]
Saving to: ‘message.txt’

message.txt                               100%[====================================================================================>]     638  --.-KB/s    in 0s      

2024-11-17 07:00:58 (12.5 MB/s) - ‘message.txt’ saved [638/638]

                                                                                                                                                                       
┌──(kali㉿kali)-[~/Parcial3/substitution1]
└─$ cat message.txt 
SYTe (eakdy tkd sjbyndr yar thjm) jdr j yobr kt skxbnyrd ersndzyo skxbryzyzkc. Skcyreyjcye jdr bdrercyrq gzya j ery kt sajhhrcmre gazsa yrey yarzd sdrjyzwzyo, yrsaczsjh (jcq mkkmhzcm) evzhhe, jcq bdklhrx-ekhwzcm jlzhzyo. Sajhhrcmre nenjhho skwrd j cnxlrd kt sjyrmkdzre, jcq garc ekhwrq, rjsa ozrhqe j eydzcm (sjhhrq j thjm) gazsa ze enlxzyyrq yk jc kchzcr eskdzcm erdwzsr. SYTe jdr j mdrjy gjo yk hrjdc j gzqr jddjo kt skxbnyrd ersndzyo evzhhe zc j ejtr, hrmjh rcwzdkcxrcy, jcq jdr akeyrq jcq bhjorq lo xjco ersndzyo mdknbe jdkncq yar gkdhq tkd tnc jcq bdjsyzsr. Tkd yaze bdklhrx, yar thjm ze: bzskSYT{TD3UN3CSO_4774SV5_4D3_S001_7JJ384LS}  
```

- Ingresamos a la pagina [Online calculator: Substitution cipher decoder](https://planetcalc.com/8047/) y pegamos el mensaje, damos clic en calcular.
- Obtenemos lo siguiente:

```bash
Decrypted text

CTFS (SHORT FOR CAPTURE THE FLAG) ARE A TYPE OF COMPUTER SECURITY COMPETITION. CONTESTANTS ARE PRESENTED WITH A SET OF CHALLENGES WHICH TEST THEIR CREATIVITY, TECHNICAL (AND GOOGLING) SKILLS, AND PROBLEM-SOLVING ABILITY. CHALLENGES USUALLY COVER A NUMBER OF CATEGORIES, AND WHEN SOLVED, EACH YIELDS A STRING (CALLED A FLAG) WHICH IS SUBMITTED TO AN ONLINE SCORING SERVICE. CTFS ARE A GREAT WAY TO LEARN A WIDE ARRAY OF COMPUTER SECURITY SKILLS IN A SAFE, LEGAL ENVIRONMENT, AND ARE HOSTED AND PLAYED BY MANY SECURITY GROUPS AROUND THE WORLD FOR FUN AND PRACTICE. FOR THIS PROBLEM, THE FLAG IS: PICOCTF{FR3JU3NCY_4774CK5_4R3_C001_7AA384BC}
```
- A la bandera le haremos una pequeña modificación, cambiaremos la `J` por la `Q` quedando de la siguiente manera:

- Flag: PICOCTF{FR3QU3NCY_4774CK5_4R3_C001_7AA384BC}

## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/308
[Online calculator: Substitution cipher decoder](https://planetcalc.com/8047/)
