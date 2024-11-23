## Descripción 
A message has come in but it seems to be all scrambled. Luckily it seems to have the key at the beginning. Can you crack this substitution cipher?Download the message [here](https://artifacts.picoctf.net/c/153/message.txt).

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
┌──(kali㉿kali)-[~/Parcial3]
└─$ mkdir substitution0
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Parcial3]
└─$ cd substitution0 
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Parcial3/substitution0]
└─$ wget https://artifacts.picoctf.net/c/153/message.txt  
--2024-11-17 06:55:07--  https://artifacts.picoctf.net/c/153/message.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 13.249.21.32, 13.249.21.46, 13.249.21.85, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|13.249.21.32|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 670 [application/octet-stream]
Saving to: ‘message.txt’

message.txt                               100%[====================================================================================>]     670  --.-KB/s    in 0s      

2024-11-17 06:55:07 (16.4 MB/s) - ‘message.txt’ saved [670/670]

                                                                                                                                                                       
┌──(kali㉿kali)-[~/Parcial3/substitution0]
└─$ ls
message.txt
                                                                                                                                                                       
┌──(kali㉿kali)-[~/Parcial3/substitution0]
└─$ cat message.txt  
OHNFUMWSVZLXEGCPTAJDYIRKQB 

Suauypcg Xuwaogf oacju, rvds o waoiu ogf jdoduxq ova, ogf hacywsd eu dsu huudxu
mace o wxojj noju vg rsvns vd roj ugnxcjuf. Vd roj o huoydvmyx jnoaohouyj, ogf, od
dsod dveu, yglgcrg dc godyaoxvjdj—cm ncyaju o wauod pavbu vg o jnvugdvmvn pcvgd
cm ivur. Dsuau ruau drc acygf hxonl jpcdj guoa cgu ukdauevdq cm dsu honl, ogf o
xcgw cgu guoa dsu cdsua. Dsu jnoxuj ruau uknuufvgwxq soaf ogf wxcjjq, rvds oxx dsu
oppuoaognu cm hyagvjsuf wcxf. Dsu ruvwsd cm dsu vgjund roj iuaq aueoalohxu, ogf,
dolvgw oxx dsvgwj vgdc ncgjvfuaodvcg, V ncyxf soafxq hxoeu Zypvdua mca svj cpvgvcg
aujpundvgw vd.

Dsu mxow vj: pvncNDM{5YH5717Y710G_3I0XY710G_03055505}              
```
- Ingresamos a la pagina [Online calculator: Substitution cipher decoder](https://planetcalc.com/8047/) y pegamos el mensaje, damos clic en calcular y obtenemos la bandera.

```bash
Decrypted text

ABCDEFGHIJKLMNOPQRSTUVWXYZ HEREUPON LEGRAND AROSE, WITH A GRAVE AND STATELY AIR, AND BROUGHT ME THE BEETLE FROM A GLASS CASE IN WHICH IT WAS ENCLOSED. IT WAS A BEAUTIFUL SCARABAEUS, AND, AT THAT TIME, UNKNOWN TO NATURALISTS—OF COURSE A GREAT PRIZE IN A SCIENTIFIC POINT OF VIEW. THERE WERE TWO ROUND BLACK SPOTS NEAR ONE EXTREMITY OF THE BACK, AND A LONG ONE NEAR THE OTHER. THE SCALES WERE EXCEEDINGLY HARD AND GLOSSY, WITH ALL THE APPEARANCE OF BURNISHED GOLD. THE WEIGHT OF THE INSECT WAS VERY REMARKABLE, AND, TAKING ALL THINGS INTO CONSIDERATION, I COULD HARDLY BLAME JUPITER FOR HIS OPINION RESPECTING IT. THE FLAG IS: PICOCTF{5UB5717U710N_3V0LU710N_03055505}
```

- Flag: PICOCTF{5UB5717U710N_3V0LU710N_03055505}

## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/307
[Online calculator: Substitution cipher decoder](https://planetcalc.com/8047/)
