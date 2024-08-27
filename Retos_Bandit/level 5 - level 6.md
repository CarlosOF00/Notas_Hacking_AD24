## Objetivo 
The password for the next level is stored in a file somewhere under the **inhere** directory and has all of the following properties:

- human-readable
- 1033 bytes in size
- not executable

## Datos de Acceso al Nivel
user: bandit5
password: 4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw

## Solución
```
└─$ ssh bandit5@bandit.labs.overthewire.org -p 2220
                         _                     _ _ _   
                        | |__   __ _ _ __   __| (_) |_ 
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_ 
                        |_.__/ \__,_|_| |_|\__,_|_|\__|
                                                       

                      This is an OverTheWire game server. 
            More information on http://www.overthewire.org/wargames

bandit5@bandit.labs.overthewire.org's password: 

      ,----..            ,----,          .---.
     /   /   \         ,/   .`|         /. ./|
    /   .     :      ,`   .'  :     .--'.  ' ;
   .   /   ;.  \   ;    ;     /    /__./ \ : |
  .   ;   /  ` ; .'___,/    ,' .--'.  '   \' .
  ;   |  ; \ ; | |    :     | /___/ \ |    ' '
  |   :  | ; | ' ;    |.';  ; ;   \  \;      :
  .   |  ' ' ' : `----'  |  |  \   ;  `      |
  '   ;  \; /  |     '   :  ;   .   \    .\  ;
   \   \  ',  /      |   |  '    \   \   ' \ |
    ;   :    /       '   :  |     :   '  |--"
     \   \ .'        ;   |.'       \   \ ;
  www. `---` ver     '---' he       '---" ire.org


Welcome to OverTheWire!

If you find any problems, please report them to the #wargames channel on
discord or IRC.

--[ Playing the games ]--

  This machine might hold several wargames.
  If you are playing "somegame", then:

    * USERNAMES are somegame0, somegame1, ...
    * Most LEVELS are stored in /somegame/.
    * PASSWORDS for each level are stored in /etc/somegame_pass/.

  Write-access to homedirectories is disabled. It is advised to create a
  working directory with a hard-to-guess name in /tmp/.  You can use the
  command "mktemp -d" in order to generate a random and hard to guess
  directory in /tmp/.  Read-access to both /tmp/ is disabled and to /proc
  restricted so that users cannot snoop on eachother. Files and directories
  with easily guessable or short names will be periodically deleted! The /tmp
  directory is regularly wiped.
  Please play nice:

    * don't leave orphan processes running
    * don't leave exploit-files laying around
    * don't annoy other players
    * don't post passwords or spoilers
    * again, DONT POST SPOILERS!
      This includes writeups of your solution on your blog or website!

--[ Tips ]--

  This machine has a 64bit processor and many security-features enabled
  by default, although ASLR has been switched off.  The following
  compiler flags might be interesting:

    -m32                    compile for 32bit
    -fno-stack-protector    disable ProPolice
    -Wl,-z,norelro          disable relro

  In addition, the execstack tool can be used to flag the stack as
  executable on ELF binaries.

  Finally, network-access is limited for most levels by a local
  firewall.

--[ Tools ]--

 For your convenience we have installed a few useful tools which you can find
 in the following locations:

    * gef (https://github.com/hugsy/gef) in /opt/gef/
    * pwndbg (https://github.com/pwndbg/pwndbg) in /opt/pwndbg/
    * peda (https://github.com/longld/peda.git) in /opt/peda/
    * gdbinit (https://github.com/gdbinit/Gdbinit) in /opt/gdbinit/
    * pwntools (https://github.com/Gallopsled/pwntools)
    * radare2 (http://www.radare.org/)

--[ More information ]--

  For more information regarding individual wargames, visit
  http://www.overthewire.org/wargames/

  For support, questions or comments, contact us on discord or IRC.

  Enjoy your stay!

bandit5@bandit:~$ ls 
inhere
bandit5@bandit:~$ cd inhere/
bandit5@bandit:~/inhere$ ls -la
total 88
drwxr-x--- 22 root bandit5 4096 Jul 17 15:57 .
drwxr-xr-x  3 root root    4096 Jul 17 15:57 ..
drwxr-x---  2 root bandit5 4096 Jul 17 15:57 maybehere00
drwxr-x---  2 root bandit5 4096 Jul 17 15:57 maybehere01
drwxr-x---  2 root bandit5 4096 Jul 17 15:57 maybehere02
drwxr-x---  2 root bandit5 4096 Jul 17 15:57 maybehere03
drwxr-x---  2 root bandit5 4096 Jul 17 15:57 maybehere04
drwxr-x---  2 root bandit5 4096 Jul 17 15:57 maybehere05
drwxr-x---  2 root bandit5 4096 Jul 17 15:57 maybehere06
drwxr-x---  2 root bandit5 4096 Jul 17 15:57 maybehere07
drwxr-x---  2 root bandit5 4096 Jul 17 15:57 maybehere08
drwxr-x---  2 root bandit5 4096 Jul 17 15:57 maybehere09
drwxr-x---  2 root bandit5 4096 Jul 17 15:57 maybehere10
drwxr-x---  2 root bandit5 4096 Jul 17 15:57 maybehere11
drwxr-x---  2 root bandit5 4096 Jul 17 15:57 maybehere12
drwxr-x---  2 root bandit5 4096 Jul 17 15:57 maybehere13
drwxr-x---  2 root bandit5 4096 Jul 17 15:57 maybehere14
drwxr-x---  2 root bandit5 4096 Jul 17 15:57 maybehere15
drwxr-x---  2 root bandit5 4096 Jul 17 15:57 maybehere16
drwxr-x---  2 root bandit5 4096 Jul 17 15:57 maybehere17
drwxr-x---  2 root bandit5 4096 Jul 17 15:57 maybehere18
drwxr-x---  2 root bandit5 4096 Jul 17 15:57 maybehere19
bandit5@bandit:~/inhere$ find . -type f -size 1033c
./maybehere07/.file2
bandit5@bandit:~/inhere$ cat maybehere07/.file2
HWasnPhtq9AVKe0dmk45nxy20cvUa6EG

```

## Notas Adicionales
## Referencias 

