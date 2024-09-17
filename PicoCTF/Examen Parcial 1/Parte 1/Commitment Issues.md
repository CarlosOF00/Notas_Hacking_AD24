## Descripción 
I accidentally wrote the flag down. Good thing I deleted it!You download the challenge files here:

- [challenge.zip](https://artifacts.picoctf.net/c_titan/138/challenge.zip)

## Datos de Acceso al Nivel
user: bandit
password:

## Solución
```bash
carlosof-picoctf@webshell:~$ mktemp -d
/tmp/tmp.OMZQXHXBxz
carlosof-picoctf@webshell:~$ cd /tmp/tmp.OMZQXHXBxz/
carlosof-picoctf@webshell:/tmp/tmp.OMZQXHXBxz$ wget https://artifacts.picoctf.net/c_titan/138/challenge.zip
--2024-09-13 15:54:24--  https://artifacts.picoctf.net/c_titan/138/challenge.zip
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.167.183.74, 3.167.183.66, 3.167.183.29, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.167.183.74|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 19199 (19K) [application/octet-stream]
Saving to: 'challenge.zip'

challenge.zip                                   100%[======================================================================================================>]  18.75K  --.-KB/s    in 0s      

2024-09-13 15:54:24 (39.3 MB/s) - 'challenge.zip' saved [19199/19199]

carlosof-picoctf@webshell:/tmp/tmp.OMZQXHXBxz$ unzip challenge.zip 
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
 extracting: drop-in/.git/refs/heads/master  
   creating: drop-in/.git/refs/tags/
 extracting: drop-in/.git/HEAD       
  inflating: drop-in/.git/config     
   creating: drop-in/.git/objects/
   creating: drop-in/.git/objects/pack/
   creating: drop-in/.git/objects/info/
   creating: drop-in/.git/objects/0e/
 extracting: drop-in/.git/objects/0e/0fefcdc9c9722914a7a9ecab1e88784f005eeb  
   creating: drop-in/.git/objects/5b/
 extracting: drop-in/.git/objects/5b/222fb49097fe9874695e8cc7cd9a6c80886017  
   creating: drop-in/.git/objects/b5/
 extracting: drop-in/.git/objects/b5/62f0b425907789d11d2fe2793e67592dc6be93  
   creating: drop-in/.git/objects/d5/
 extracting: drop-in/.git/objects/d5/52d1ecd2d83fa2e65b6724d1ff73b45a7d59b7  
   creating: drop-in/.git/objects/0c/
 extracting: drop-in/.git/objects/0c/1ab266b7a3a1cd099bb509f82b7a2d03aecd03  
   creating: drop-in/.git/objects/42/
 extracting: drop-in/.git/objects/42/942c9c605b30100f5d859ef6e172027447c0db  
  inflating: drop-in/.git/index      
 extracting: drop-in/.git/COMMIT_EDITMSG  
   creating: drop-in/.git/logs/
  inflating: drop-in/.git/logs/HEAD  
   creating: drop-in/.git/logs/refs/
   creating: drop-in/.git/logs/refs/heads/
  inflating: drop-in/.git/logs/refs/heads/master  
 extracting: drop-in/message.txt     
carlosof-picoctf@webshell:/tmp/tmp.OMZQXHXBxz$ cd drop-in/
carlosof-picoctf@webshell:/tmp/tmp.OMZQXHXBxz/drop-in$ git branch
carlosof-picoctf@webshell:/tmp/tmp.OMZQXHXBxz/drop-in$ git checkout
carlosof-picoctf@webshell:/tmp/tmp.OMZQXHXBxz/drop-in$ ls
message.txt
carlosof-picoctf@webshell:/tmp/tmp.OMZQXHXBxz/drop-in$ cat message.txt 
TOP SECRET
carlosof-picoctf@webshell:/tmp/tmp.OMZQXHXBxz/drop-in$ git reflog 
carlosof-picoctf@webshell:/tmp/tmp.OMZQXHXBxz/drop-in$ git checkout b562f0b
Note: switching to 'b562f0b'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at b562f0b create flag
carlosof-picoctf@webshell:/tmp/tmp.OMZQXHXBxz/drop-in$ cat message.txt 
picoCTF{s@n1t1z3_c785c319}
carlosof-picoctf@webshell:/tmp/tmp.OMZQXHXBxz/drop-in$ 
```


## Notas Adicionales
- El comando `git checkout` en Git se utiliza para varias tareas importantes relacionadas con el manejo de ramas y el contenido de archivos. Seguido del nombre de una rama, cambias a esa rama en tu repositorio local. Esto actualiza el estado del directorio de trabajo para que coincida con el estado de esa rama.
- El comando `git reflog` en Git es una herramienta poderosa para visualizar el historial de los movimientos de los punteros en tu repositorio, principalmente `HEAD` y las referencias de las ramas. Es útil para recuperar commits que no están en el historial de la rama actual o para entender mejor qué ha pasado en el repositorio.
## Referencias 
https://play.picoctf.org/practice/challenge/411
[Git - git-reflog Documentation (git-scm.com)](https://git-scm.com/docs/git-reflog)
