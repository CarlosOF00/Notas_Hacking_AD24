## Objetivo 
There is a git repository at `ssh://bandit28-git@localhost/home/bandit28-git/repo` via the port `2220`. The password for the user `bandit28-git` is the same as for the user `bandit28`.

Clone the repository and find the password for the next level.

## Datos de Acceso al Nivel
user: bandit28
password: Yz9IpL0sBcCeuG7m9uQFt8ZNpS4HZRcN

## Solución
```bash
┌──(kali㉿kali)-[~]
└─$ ssh bandit28@bandit.labs.overthewire.org -p2220 
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

bandit28@bandit.labs.overthewire.org's password: 

bandit28@bandit:~$ mktemp -d
/tmp/tmp.8S2k2TIKRd
bandit28@bandit:~$ cd /tmp/tmp.8S2k2TIKRd
bandit28@bandit:/tmp/tmp.8S2k2TIKRd$ git clone ssh://bandit28-git@localhost:2220/home/bandit28-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names.
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit28/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit28/.ssh/known_hosts).
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

bandit28-git@localhost's password: 
remote: Enumerating objects: 9, done.
remote: Counting objects: 100% (9/9), done.
remote: Compressing objects: 100% (6/6), done.
remote: Total 9 (delta 2), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (9/9), done.
Resolving deltas: 100% (2/2), done.
bandit28@bandit:/tmp/tmp.8S2k2TIKRd$ ls
repo
bandit28@bandit:/tmp/tmp.8S2k2TIKRd$ cd repo/
bandit28@bandit:/tmp/tmp.8S2k2TIKRd/repo$ ls 
README.md
bandit28@bandit:/tmp/tmp.8S2k2TIKRd/repo$ cat README.md 
# Bandit Notes
Some notes for level29 of bandit.

## credentials

- username: bandit29
- password: xxxxxxxxxx

bandit28@bandit:/tmp/tmp.8S2k2TIKRd/repo$ git log
commit 8cbd1e08d1879415541ba19ddee3579e80e3f61a (HEAD -> master, origin/master, origin/HEAD)
Author: Morla Porla <morla@overthewire.org>
Date:   Wed Jul 17 15:57:30 2024 +0000

    fix info leak

commit 73f5d0435070c8922da12177dc93f40b2285e22a
Author: Morla Porla <morla@overthewire.org>
Date:   Wed Jul 17 15:57:30 2024 +0000

    add missing data

commit 5f7265568c7b503b276ec20f677b68c92b43b712
Author: Ben Dover <noone@overthewire.org>
Date:   Wed Jul 17 15:57:30 2024 +0000

    initial commit of README.md
bandit28@bandit:/tmp/tmp.8S2k2TIKRd/repo$ git show 8cbd1e08d1879415541ba19ddee3579e80e3f61a
commit 8cbd1e08d1879415541ba19ddee3579e80e3f61a (HEAD -> master, origin/master, origin/HEAD)
Author: Morla Porla <morla@overthewire.org>
Date:   Wed Jul 17 15:57:30 2024 +0000

    fix info leak

diff --git a/README.md b/README.md
index d4e3b74..5c6457b 100644
--- a/README.md
+++ b/README.md
@@ -4,5 +4,5 @@ Some notes for level29 of bandit.
 ## credentials
 
 - username: bandit29
-- password: 4pT1t5DENaYuqnqvadYs1oE4QLCdjmJ7
+- password: xxxxxxxxxx
 
bandit28@bandit:/tmp/tmp.8S2k2TIKRd/repo$ 

```

## Notas Adicionales
**`git log`** es un comando que muestra el historial de commits en un repositorio Git. Cuando ejecutas `git log`, Git te muestra una lista de commits ordenados por fecha (de más reciente a más antiguo). Cada commit incluye información como el hash del commit, el autor, la fecha y el mensaje del commit.

**`git show`** es un comando que muestra información detallada sobre un commit específico. Puedes usarlo para ver el contenido y los detalles de un commit particular, incluyendo el mensaje del commit, la diferencia introducida (diff), y los archivos modificados.

## Referencias 
[Explicación del comando Git Log (freecodecamp.org)](https://www.freecodecamp.org/espanol/news/explicacion-del-comando-git-log/)
