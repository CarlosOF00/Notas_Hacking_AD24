## Descripción 
My team has been working very hard on new features for our flag printing program! I wonder how they'll work together?You can download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/179/challenge.zip)
## Datos de Acceso al Nivel
user: carlosof
password:

## Solución
```bash
carlosof-picoctf@webshell:~$ mktemp -d
/tmp/tmp.bbWbFKG5Ov
carlosof-picoctf@webshell:~$ cd /tmp/tmp.bbWbFKG5Ov/
carlosof-picoctf@webshell:/tmp/tmp.bbWbFKG5Ov$ wget https://artifacts.picoctf.net/c_titan/179/challenge.zip
--2024-09-13 15:25:19--  https://artifacts.picoctf.net/c_titan/179/challenge.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.160.5.42, 3.160.5.93, 3.160.5.71, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.160.5.42|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 24648 (24K) [application/octet-stream]
Saving to: 'challenge.zip'

challenge.zip                                   100%[======================================================================================================>]  24.07K  --.-KB/s    in 0s      

2024-09-13 15:25:19 (66.9 MB/s) - 'challenge.zip' saved [24648/24648]

carlosof-picoctf@webshell:/tmp/tmp.bbWbFKG5Ov$ unzip challenge.zip 
Archive:  challenge.zip
   creating: drop-in/
   creating: drop-in/.git/
   creating: drop-in/.git/branches/
  inflating: drop-in/.git/description  
   creating: drop-in/.git/hooks/
  inflating: drop-in/.git/hooks/applypatch-msg.sample  
  inflating: drop-in/.git/hooks/commit-msg.sample  
  inflating: drop-in/.git/hooks/fsmonitor-watchman.sample  
  inflating: drop-in/.git/hooks/post-update.sample  
  inflating: drop-in/.git/hooks/pre-applypatch.sample  
  inflating: drop-in/.git/hooks/pre-commit.sample  
  inflating: drop-in/.git/hooks/pre-merge-commit.sample  
  inflating: drop-in/.git/hooks/pre-push.sample  
  inflating: drop-in/.git/hooks/pre-rebase.sample  
  inflating: drop-in/.git/hooks/pre-receive.sample  
  inflating: drop-in/.git/hooks/prepare-commit-msg.sample  
  inflating: drop-in/.git/hooks/update.sample  
   creating: drop-in/.git/info/
  inflating: drop-in/.git/info/exclude  
   creating: drop-in/.git/refs/
   creating: drop-in/.git/refs/heads/
  inflating: drop-in/.git/refs/heads/main  
   creating: drop-in/.git/refs/heads/feature/
 extracting: drop-in/.git/refs/heads/feature/part-1  
 extracting: drop-in/.git/refs/heads/feature/part-2  
 extracting: drop-in/.git/refs/heads/feature/part-3  
   creating: drop-in/.git/refs/tags/
 extracting: drop-in/.git/HEAD       
  inflating: drop-in/.git/config     
   creating: drop-in/.git/objects/
   creating: drop-in/.git/objects/pack/
   creating: drop-in/.git/objects/info/
   creating: drop-in/.git/objects/77/
 extracting: drop-in/.git/objects/77/d6ceca6fe23b57d88cf16f20003e10d6715690  
   creating: drop-in/.git/objects/b9/
 extracting: drop-in/.git/objects/b9/32e8c048154a46d224cd7691c99dc8cb88164a  
   creating: drop-in/.git/objects/5e/
 extracting: drop-in/.git/objects/5e/4b2dae1868abb644627483c78a683286dfe67c  
   creating: drop-in/.git/objects/6e/
 extracting: drop-in/.git/objects/6e/17fb3a35364b4f9bb8bef8b5e6a5af2d3e7dfa  
   creating: drop-in/.git/objects/43/
 extracting: drop-in/.git/objects/43/e44dd37ba0c0adc3d78d0b85d699859ec8d75c  
   creating: drop-in/.git/objects/30/
 extracting: drop-in/.git/objects/30/0cff1bf1f64637dd9ff603d90176e8e8bdeb01  
   creating: drop-in/.git/objects/7a/
 extracting: drop-in/.git/objects/7a/b4e25c0cd108374b2275fdb1fcdf635e591833  
   creating: drop-in/.git/objects/d1/
 extracting: drop-in/.git/objects/d1/f3407cee4479c075997b497fa290ca636fe258  
   creating: drop-in/.git/objects/74/
 extracting: drop-in/.git/objects/74/989a4f650d024929388b6788d2b4c214a07e49  
   creating: drop-in/.git/objects/c3/
 extracting: drop-in/.git/objects/c3/1215218d31567374eeed51505972af2ed46a37  
   creating: drop-in/.git/objects/04/
 extracting: drop-in/.git/objects/04/ebe96db2885e1a7af6d1e4ca7ce9b89e5ba743  
   creating: drop-in/.git/objects/12/
 extracting: drop-in/.git/objects/12/c2ae89d8035b7a5aa7cd169dc9e93cc68201be  
  inflating: drop-in/.git/index      
 extracting: drop-in/.git/COMMIT_EDITMSG  
   creating: drop-in/.git/logs/
  inflating: drop-in/.git/logs/HEAD  
   creating: drop-in/.git/logs/refs/
   creating: drop-in/.git/logs/refs/heads/
  inflating: drop-in/.git/logs/refs/heads/main  
   creating: drop-in/.git/logs/refs/heads/feature/
  inflating: drop-in/.git/logs/refs/heads/feature/part-1  
  inflating: drop-in/.git/logs/refs/heads/feature/part-2  
  inflating: drop-in/.git/logs/refs/heads/feature/part-3  
  inflating: drop-in/flag.py         
carlosof-picoctf@webshell:/tmp/tmp.bbWbFKG5Ov$ cd drop-in/
carlosof-picoctf@webshell:/tmp/tmp.bbWbFKG5Ov/drop-in$ git branch
carlosof-picoctf@webshell:/tmp/tmp.bbWbFKG5Ov/drop-in$ git merge   
merge       mergetool   
carlosof-picoctf@webshell:/tmp/tmp.bbWbFKG5Ov/drop-in$ git merge 
HEAD             feature/part-1   feature/part-2   feature/part-3   main             
carlosof-picoctf@webshell:/tmp/tmp.bbWbFKG5Ov/drop-in$ git merge feature/part-1
Updating 5e4b2da..300cff1
Fast-forward
 flag.py | 1 +
 1 file changed, 1 insertion(+)
carlosof-picoctf@webshell:/tmp/tmp.bbWbFKG5Ov/drop-in$ git merge feature/part-2
Auto-merging flag.py
CONFLICT (content): Merge conflict in flag.py
Automatic merge failed; fix conflicts and then commit the result.
carlosof-picoctf@webshell:/tmp/tmp.bbWbFKG5Ov/drop-in$ cat flag.py 
print("Printing the flag...")
<<<<<<< HEAD
print("picoCTF{t3@mw0rk_", end='')
=======

print("m@k3s_th3_dr3@m_", end='')
>>>>>>> feature/part-2
carlosof-picoctf@webshell:/tmp/tmp.bbWbFKG5Ov/drop-in$ git add flag.py 
carlosof-picoctf@webshell:/tmp/tmp.bbWbFKG5Ov/drop-in$ git commit -m "Agregacion de la flag"
[main 62ba657] Agregacion de la flag
carlosof-picoctf@webshell:/tmp/tmp.bbWbFKG5Ov/drop-in$ git merge feature/part-3
Auto-merging flag.py
CONFLICT (content): Merge conflict in flag.py
Automatic merge failed; fix conflicts and then commit the result.
carlosof-picoctf@webshell:/tmp/tmp.bbWbFKG5Ov/drop-in$ git add flag.py 
carlosof-picoctf@webshell:/tmp/tmp.bbWbFKG5Ov/drop-in$ git commit -m "part3"
[main aa4d63d] part3
carlosof-picoctf@webshell:/tmp/tmp.bbWbFKG5Ov/drop-in$ cat flag.py 
print("Printing the flag...")
<<<<<<< HEAD
<<<<<<< HEAD
print("picoCTF{t3@mw0rk_", end='')
=======

print("m@k3s_th3_dr3@m_", end='')
>>>>>>> feature/part-2
=======

print("w0rk_798f9981}")
>>>>>>> feature/part-3
carlosof-picoctf@webshell:/tmp/tmp.bbWbFKG5Ov/drop-in$ 
```


## Notas Adicionales
`git branch`: Muestra una lista de las ramas disponibles en el repositorio local.
`git merge` : Combina los cambios de una rama con la rama actual en la que te encuentras.

## Referencias 
https://play.picoctf.org/practice/challenge/
[Git - git-merge Documentation (git-scm.com)](https://git-scm.com/docs/git-merge)
