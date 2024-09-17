## Descripción 
Someone's commits seems to be preventing the program from working. Who is it?You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/156/challenge.zip)

## Datos de Acceso al Nivel
user: carlosof
password:

## Solución
```bash
carlosof-picoctf@webshell:~$ mktemp -d 
/tmp/tmp.B5flAvJ0wo
carlosof-picoctf@webshell:~$ cd /tmp/tmp.B5flAvJ0wo/
carlosof-picoctf@webshell:/tmp/tmp.B5flAvJ0wo$ wget https://artifacts.picoctf.net/c_titan/156/challenge.zip
--2024-09-11 21:46:34--  https://artifacts.picoctf.net/c_titan/156/challenge.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.22.128, 3.160.22.16, 3.160.22.92, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.22.128|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 293739 (287K) [application/octet-stream]
Saving to: 'challenge.zip'

challenge.zip           100%[============================>] 286.85K  --.-KB/s    in 0.005s  

2024-09-11 21:46:34 (56.6 MB/s) - 'challenge.zip' saved [293739/293739]

carlosof-picoctf@webshell:/tmp/tmp.B5flAvJ0wo$ ls -la
total 288
drwx------ 2 carlosof-picoctf carlosof-picoctf     27 Sep 11 21:46 .
drwxrwxrwt 1 root             root                 50 Sep 11 21:46 ..
-rw-rw-r-- 1 carlosof-picoctf carlosof-picoctf 293739 Mar 12  2024 challenge.zip
carlosof-picoctf@webshell:/tmp/tmp.B5flAvJ0wo$ unzip challenge.zip 
Archive:  challenge.zip
   creating: drop-in/
 extracting: drop-in/message.py      
   creating: drop-in/.git/
   creating: drop-in/.git/branches/
  inflating: drop-in/.git/description  
   creating: drop-in/.git/hooks/
carlosof-picoctf@webshell:/tmp/tmp.B5flAvJ0wo$ cd drop-in/
carlosof-picoctf@webshell:/tmp/tmp.B5flAvJ0wo/drop-in$ ls -la   
total 4
drwxr-xr-x 3 carlosof-picoctf carlosof-picoctf  36 Mar 12  2024 .
drwx------ 3 carlosof-picoctf carlosof-picoctf  42 Sep 11 21:46 ..
drwxr-xr-x 8 carlosof-picoctf carlosof-picoctf 166 Mar 12  2024 .git
-rw-r--r-- 1 carlosof-picoctf carlosof-picoctf  22 Mar 12  2024 message.py
carlosof-picoctf@webshell:/tmp/tmp.B5flAvJ0wo/drop-in$ cat message.py 
print("Hello, World!"
carlosof-picoctf@webshell:/tmp/tmp.B5flAvJ0wo/drop-in$ git log -p 
HEAD     master   
carlosof-picoctf@webshell:/tmp/tmp.B5flAvJ0wo/drop-in$ git log -p 
HEAD     master   
carlosof-picoctf@webshell:/tmp/tmp.B5flAvJ0wo/drop-in$ git log -p master 

commit 0351e0474493168ca76441c24630c17554fd09ca
Author: picoCTF{@sk_th3_1nt3rn_d2d29f22} <ops@picoctf.com>
Date:   Tue Mar 12 00:07:01 2024 +0000

    optimize file size of prod code

diff --git a/message.py b/message.py
index 7df869a..326544a 100644
--- a/message.py
+++ b/message.py
@@ -1 +1 @@
-print("Hello, World!")
+print("Hello, World!"

commit c9e851509190f5887e91339ee18087e3e77ebfda
Author: picoCTF <ops@picoctf.com>
Date:   Tue Mar 12 00:07:01 2024 +0000

    create top secret project

diff --git a/message.py b/message.py
new file mode 100644
index 0000000..7df869a
--- /dev/null
+++ b/message.py
@@ -0,0 +1 @@
+print("Hello, World!")
carlosof-picoctf@webshell:/tmp/tmp.B5flAvJ0wo/drop-in$ 

```

## Notas Adicionales
`git log -p` es una herramienta poderosa para examinar en detalle qué cambios se han realizado en cada commit en tu repositorio. Es muy útil para depurar problemas, revisar cambios y entender cómo ha evolucionado tu código.

## Referencias 
https://play.picoctf.org/practice/challenge/405
[Git - git-log Documentation (git-scm.com)](https://git-scm.com/docs/git-log)
