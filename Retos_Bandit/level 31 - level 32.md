## Objetivo 
There is a git repository at `ssh://bandit31-git@localhost/home/bandit31-git/repo` via the port `2220`. The password for the user `bandit31-git` is the same as for the user `bandit31`.

Clone the repository and find the password for the next level.

## Datos de Acceso al Nivel
user: bandit31
password: fb5S2xb7bRyFmAvQYQGEqsbhVyJqhnDy

## Solución
```bash
┌──(kali㉿kali)-[~]
└─$ ssh bandit31@bandit.labs.overthewire.org -p2220 
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

bandit31@bandit.labs.overthewire.org's password: 

bandit31@bandit:~$ mktemp -d
/tmp/tmp.gwgDtUruaw
bandit31@bandit:~$ cd /tmp/tmp.gwgDtUruaw
bandit31@bandit:/tmp/tmp.gwgDtUruaw$ git clone ssh://bandit31-git@localhost:2220/home/bandit31-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit31/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit31/.ssh/known_hosts).
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

bandit31-git@localhost's password: 
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Compressing objects: 100% (3/3), done.
Receiving objects: 100% (4/4), 382 bytes | 382.00 KiB/s, done.
remote: Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
bandit31@bandit:/tmp/tmp.gwgDtUruaw$ cd repo/
bandit31@bandit:/tmp/tmp.gwgDtUruaw/repo$ ls -la
total 20
drwxrwxr-x 3 bandit31 bandit31 4096 Sep  8 01:36 .
drwx------ 3 bandit31 bandit31 4096 Sep  8 01:36 ..
drwxrwxr-x 8 bandit31 bandit31 4096 Sep  8 01:36 .git
-rw-rw-r-- 1 bandit31 bandit31    6 Sep  8 01:36 .gitignore
-rw-rw-r-- 1 bandit31 bandit31  147 Sep  8 01:36 README.md
bandit31@bandit:/tmp/tmp.gwgDtUruaw/repo$ cat README.md 
This time your task is to push a file to the remote repository.

Details:
    File name: key.txt
    Content: 'May I come in?'
    Branch: master

bandit31@bandit:/tmp/tmp.gwgDtUruaw/repo$ echo 'May I come in?' > key.txt
bandit31@bandit:/tmp/tmp.gwgDtUruaw/repo$ ls -la
total 24
drwxrwxr-x 3 bandit31 bandit31 4096 Sep  8 01:37 .
drwx------ 3 bandit31 bandit31 4096 Sep  8 01:36 ..
drwxrwxr-x 8 bandit31 bandit31 4096 Sep  8 01:36 .git
-rw-rw-r-- 1 bandit31 bandit31    6 Sep  8 01:36 .gitignore
-rw-rw-r-- 1 bandit31 bandit31   15 Sep  8 01:37 key.txt
-rw-rw-r-- 1 bandit31 bandit31  147 Sep  8 01:36 README.md
bandit31@bandit:/tmp/tmp.gwgDtUruaw/repo$ cat key.txt 
May I come in?
bandit31@bandit:/tmp/tmp.gwgDtUruaw/repo$ cat .gitignore 
*.txt
bandit31@bandit:/tmp/tmp.gwgDtUruaw/repo$ git add -f key.txt
bandit31@bandit:/tmp/tmp.gwgDtUruaw/repo$ git commit -m "key"
[master 993b8c7] key
 1 file changed, 1 insertion(+)
 create mode 100644 key.txt
bandit31@bandit:/tmp/tmp.gwgDtUruaw/repo$ git push -u origin master
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit31/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit31/.ssh/known_hosts).
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

bandit31-git@localhost's password: 
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 2 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 318 bytes | 318.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
remote: ### Attempting to validate files... ####
remote: 
remote: .oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.
remote: 
remote: Well done! Here is the password for the next level:
remote: 3O9RfhqyAlVBEZpVb6LYStshZoqoSx5K 
remote: 
remote: .oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.
remote: 
To ssh://localhost:2220/home/bandit31-git/repo
 ! [remote rejected] master -> master (pre-receive hook declined)
error: failed to push some refs to 'ssh://localhost:2220/home/bandit31-git/repo'
bandit31@bandit:/tmp/tmp.gwgDtUruaw/repo$   
```


## Notas Adicionales
- Al ejecutar `cat .gitignore`, puedes revisar qué archivos están excluidos del repositorio. Esto te puede ayudar a identificar archivos que podrían estar ocultos y que podrían contener pistas o soluciones.
- Normalmente, si un archivo está listado en `.gitignore`, Git lo ignorará y no lo incluirá en el área de preparación para el commit. Sin embargo, usando `-f`, puedes forzar la inclusión de ese archivo.
## Referencias 

[Walkthrough - MayADevBe Blog](https://mayadevbe.me/posts/overthewire/bandit/level32/)