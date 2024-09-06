## Objetivo 


## Datos de Acceso al Nivel
user: bandit26
password: s0773xxkk0MXfdqOfPRVr9L3jJBUOgCZ

## Solución
```bash
bandit26@bandit:~$ whoami
bandit26
bandit26@bandit:~$ ls -la
total 44
drwxr-xr-x  3 root     root      4096 Jul 17 15:57 .
drwxr-xr-x 70 root     root      4096 Jul 17 15:58 ..
-rwsr-x---  1 bandit27 bandit26 14880 Jul 17 15:57 bandit27-do
-rw-r--r--  1 root     root       220 Mar 31 08:41 .bash_logout
-rw-r--r--  1 root     root      3771 Mar 31 08:41 .bashrc
-rw-r--r--  1 root     root       807 Mar 31 08:41 .profile
drwxr-xr-x  2 root     root      4096 Jul 17 15:57 .ssh
-rw-r-----  1 bandit26 bandit26   258 Jul 17 15:57 text.txt
bandit26@bandit:~$ ./bandit27-do cat /etc/bandit_pass/bandit27
upsNCc7vzaRDx6oZC6GiR6ERwe1MowGB
bandit26@bandit:~$
```

## Notas Adicionales

1. Conéctate al sistema remoto con SSH usando una llave.
2.  Reduce el tamaño de la ventana del terminal para que `more` no termine de ejecutarse completamente.
3. Presiona `v` en `more` para abrir el archivo en `vi`.
4. entro de `vi`, presiona `ESC`, luego escribe `:set shell=/bin/bash` y presiona `Enter` para configurar el shell.
## Referencias 
[ Walkthrough - MayADevBe Blog](https://mayadevbe.me/posts/overthewire/bandit/level27/)