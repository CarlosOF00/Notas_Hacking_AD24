## Descripción 
Now you DON’T see me.This [report](https://artifacts.picoctf.net/c/84/Financial_Report_for_ABC_Labs.pdf) has some critical data in it, some of which have been redacted correctly, while some were not. Can you find an important key that was not redacted properly?

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2]
└─$ mkdir redaction    
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2]
└─$ cd redaction    
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2/redaction]
└─$ wget https://artifacts.picoctf.net/c/84/Financial_Report_for_ABC_Labs.pdf                             
--2024-10-16 22:40:07--  https://artifacts.picoctf.net/c/84/Financial_Report_for_ABC_Labs.pdf
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.100, 3.161.55.64, 3.161.55.61, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.100|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 34915 (34K) [application/octet-stream]
Saving to: ‘Financial_Report_for_ABC_Labs.pdf’

Financial_Report_for_ABC_Labs.pdf         100%[===================================================================================>]  34.10K  --.-KB/s    in 0.04s   

2024-10-16 22:40:08 (941 KB/s) - ‘Financial_Report_for_ABC_Labs.pdf’ saved [34915/34915]

                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2/redaction]
└─$ ls
Financial_Report_for_ABC_Labs.pdf
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2/redaction]
└─$ open Financial_Report_for_ABC_Labs.pdf 
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2/redaction]
└─$ echo "^[[200~Financial Report for ABC Labs, Kigali, Rwanda for the year 2021."
Financial Report for ABC Labs, Kigali, Rwanda for the year 2021.
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2/redaction]
└─$ Breakdown - Just painted over in MS word.
Breakdown: command not found
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2/redaction]
└─$ Cost Benefit Analysis
Command 'Cost' not found, did you mean:
  command 'ost' from deb openstructure
  command 'host' from deb bind9-host
  command 'most' from deb most
Try: sudo apt install <deb name>
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2/redaction]
└─$ Credit Debit
Command 'Credit' not found, did you mean:
  command 'mredit' from deb mrtrix3
Try: sudo apt install <deb name>
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2/redaction]
└─$ This is not the flag, keep looking
This: command not found
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2/redaction]
└─$ Expenses from the
Expenses: command not found
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2/redaction]
└─$ picoCTF{C4n_Y0u_S33_m3_fully}
picoCTF{C4n_Y0u_S33_m3_fully}: command not found
                                                                                                                                                                      
┌──(kali㉿kali)-[~/Parcial2/redaction]
└─$ Redacted document.~

```
## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/290
