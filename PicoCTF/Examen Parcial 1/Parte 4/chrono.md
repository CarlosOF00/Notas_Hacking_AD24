## Descripción 
How to automate tasks to run at intervals on linux servers?

Additional details will be available after launching your challenge instance.

## Datos de Acceso al Nivel
user: carlosof
password:

## Solución
```bash
\carlosof-picoctf@webshell:~$ ssh picoplayer@saturn.picoctf.net -p 52463
The authenticity of host '[saturn.picoctf.net]:52463 ([13.59.203.175]:52463)' can't be established.
ED25519 key fingerprint is SHA256:dMTscRrUiURy7uMu5eGWwEKdd2FzqLzx6LfWhssWnNQ.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Warning: Permanently added '[saturn.picoctf.net]:52463' (ED25519) to the list of known hosts.
picoplayer@saturn.picoctf.net's password: 
Welcome to Ubuntu 20.04.5 LTS (GNU/Linux 6.5.0-1023-aws x86_64)

 * Documentation:  https://help.ubuntu.com
 * Management:     https://landscape.canonical.com
 * Support:        https://ubuntu.com/advantage

This system has been minimized by removing packages and content that are
not required on a system that users do not log into.

To restore this content, you can run the 'unminimize' command.

The programs included with the Ubuntu system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Ubuntu comes with ABSOLUTELY NO WARRANTY, to the extent permitted by
applicable law.

picoplayer@challenge:~$ pwd
/home/picoplayer
picoplayer@challenge:~$ ls -la
total 12
drwxr-xr-x 1 picoplayer picoplayer   20 Sep 16 16:42 .
drwxr-xr-x 1 root       root         24 Aug  4  2023 ..
-rw-r--r-- 1 picoplayer picoplayer  220 Feb 25  2020 .bash_logout
-rw-r--r-- 1 picoplayer picoplayer 3771 Feb 25  2020 .bashrc
drwx------ 2 picoplayer picoplayer   34 Sep 16 16:42 .cache
-rw-r--r-- 1 picoplayer picoplayer  807 Feb 25  2020 .profile
picoplayer@challenge:~$ cd /etc/
picoplayer@challenge:/etc$ ls
adduser.conf            e2scrub.conf  legal                passwd       ssh
alternatives            environment   libaudit.conf        passwd-      ssl
apt                     fstab         localtime            profile      subgid
bash.bashrc             gai.conf      login.defs           profile.d    subgid-
bindresvport.blacklist  group         logrotate.d          python3      subuid
binfmt.d                group-        lsb-release          python3.8    subuid-
ca-certificates         gshadow       machine-id           rc0.d        sudoers
ca-certificates.conf    gshadow-      magic                rc1.d        sudoers.d
cloud                   gss           magic.mime           rc2.d        sysctl.conf
cron.d                  host.conf     mailcap              rc3.d        sysctl.d
cron.daily              hostname      mailcap.order        rc4.d        systemd
cron.hourly             hosts         mime.types           rc5.d        terminfo
cron.monthly            hosts.allow   mke2fs.conf          rc6.d        timezone
cron.weekly             hosts.deny    modules-load.d       rcS.d        tmpfiles.d
crontab                 init.d        mtab                 resolv.conf  ucf.conf
dbus-1                  inputrc       networkd-dispatcher  rmt          ufw
debconf.conf            issue         networks             security     update-motd.d
debian_version          issue.net     nsswitch.conf        selinux      wgetrc
default                 kernel        opt                  shadow       xattr.conf
deluser.conf            ld.so.cache   os-release           shadow-      xdg
dhcp                    ld.so.conf    pam.conf             shells
dpkg                    ld.so.conf.d  pam.d                skel
picoplayer@challenge:/etc$ cat cron
cron.d/       cron.daily/   cron.hourly/  cron.monthly/ cron.weekly/  crontab
picoplayer@challenge:/etc$ cat crontab 
# picoCTF{Sch3DUL7NG_T45K3_L1NUX_0bb95b71}
picoplayer@challenge:/etc$ 
```

## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/347
