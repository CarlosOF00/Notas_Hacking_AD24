## Objetivo 
There is a git repository at `ssh://bandit30-git@localhost/home/bandit30-git/repo` via the port `2220`. The password for the user `bandit30-git` is the same as for the user `bandit30`.

Clone the repository and find the password for the next level.

## Datos de Acceso al Nivel
user: bandit30
password: qp30ex3VLz5MDG1n91YowTv4Q8l7CDZL

## Solución
```bash
┌──(kali㉿kali)-[~]
└─$ ssh bandit30@bandit.labs.overthewire.org -p2220 
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

bandit30@bandit.labs.overthewire.org's password: 

bandit30@bandit:~$ mktemp -d
/tmp/tmp.LLbc76xvwY
bandit30@bandit:~$ cd /tmp/tmp.LLbc76xvwY
bandit30@bandit:/tmp/tmp.LLbc76xvwY$ git clone ssh://bandit30-git@localhost:2220/home/bandit30-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit30/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit30/.ssh/known_hosts).
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

bandit30-git@localhost's password: 
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (4/4), done.
bandit30@bandit:/tmp/tmp.LLbc76xvwY$ cd repo/
bandit30@bandit:/tmp/tmp.LLbc76xvwY/repo$ ls -la
total 16
drwxrwxr-x 3 bandit30 bandit30 4096 Sep  8 01:30 .
drwx------ 3 bandit30 bandit30 4096 Sep  8 01:30 ..
drwxrwxr-x 8 bandit30 bandit30 4096 Sep  8 01:30 .git
-rw-rw-r-- 1 bandit30 bandit30   30 Sep  8 01:30 README.md
bandit30@bandit:/tmp/tmp.LLbc76xvwY/repo$ cat README.md 
just an epmty file... muahaha
bandit30@bandit:/tmp/tmp.LLbc76xvwY/repo$ git tag
secret
bandit30@bandit:/tmp/tmp.LLbc76xvwY/repo$ git show secret 
fb5S2xb7bRyFmAvQYQGEqsbhVyJqhnDy
bandit30@bandit:/tmp/tmp.LLbc76xvwY/repo$ 

```


## Notas Adicionales
- El comando `git tag` en Git se utiliza para crear, listar y eliminar etiquetas (tags) en un repositorio. Las etiquetas en Git son referencias a commits específicos y se utilizan comúnmente para marcar puntos importantes en la historia del proyecto, como versiones de software
- El comando `git show secret` en Git se utiliza para mostrar información detallada sobre una etiqueta, rama, o commit específico. La etiqueta, rama, o commit debe ser reemplazada por `secret` en este caso.

## Referencias 

[Git - git-tag Documentation (git-scm.com)](https://git-scm.com/docs/git-tag)
[Git - git-show Documentation (git-scm.com)](https://git-scm.com/docs/git-show)
