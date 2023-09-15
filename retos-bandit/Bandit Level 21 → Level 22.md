# Level 21 → Level 22
## Objetivo
A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.
## Datos de acceso al nivel
```
Server : bandit21.labs.overthewire.org
User : bandit21
Password : NvEJF7oVjkddltPSrdKEFOllh9V1IBcq
Comando: SSH bandit21@bandit.labs.overthewire.org -p 2220
```
## Solución 
```
bandit21@bandit:~$
bandit21@bandit:~$ pwd
/home/bandit21
bandit21@bandit:~$ ls
bandit21@bandit:~$ ls -la
total 24
drwxr-xr-x  2 root     root     4096 Apr 23 18:04 .
drwxr-xr-x 70 root     root     4096 Apr 23 18:05 ..
-rw-r--r--  1 root     root      220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root     root     3771 Jan  6  2022 .bashrc
-r--------  1 bandit21 bandit21   33 Apr 23 18:04 .prevpass
-rw-r--r--  1 root     root      807 Jan  6  2022 .profile
bandit21@bandit:~$ man cron
bandit21@bandit:~$ bandit21@bandit:~$ man crontab
bandit21@bandit:~$ man 5 crontab
bandit21@bandit:~$ bandit21@bandit:~$ cat /etc/crontab
# /etc/crontab: system-wide crontab
# Unlike any other crontab you don't have to run the `crontab'
# command to install the new version when you edit this file
# and files in /etc/cron.d. These files also have username fields,
# that none of the other crontabs do.

SHELL=/bin/sh
# You can also override PATH, but by default, newer versions inherit it from the environment
#PATH=/usr/local/sbin:/usr/local/bin:/sbin:/bin:/usr/sbin:/usr/bin

# Example of job definition:
# .---------------- minute (0 - 59)
# |  .------------- hour (0 - 23)
# |  |  .---------- day of month (1 - 31)
# |  |  |  .------- month (1 - 12) OR jan,feb,mar,apr ...
# |  |  |  |  .---- day of week (0 - 6) (Sunday=0 or 7) OR sun,mon,tue,wed,thu,fri,sat
# |  |  |  |  |
# *  *  *  *  * user-name command to be executed
17 *    * * *   root    cd / && run-parts --report /etc/cron.hourly
25 6    * * *   root    test -x /usr/sbin/anacron || ( cd / && run-parts --report /etc/cron.daily )
47 6    * * 7   root    test -x /usr/sbin/anacron || ( cd / && run-parts --report /etc/cron.weekly )
52 6    1 * *   root    test -x /usr/sbin/anacron || ( cd / && run-parts --report /etc/cron.monthly )
#
bandit21@bandit:~$ ls -la /etc/cron.d
total 56
drwxr-xr-x   2 root root  4096 Apr 23 18:05 .
drwxr-xr-x 108 root root 12288 Aug 12 08:42 ..
-rw-r--r--   1 root root    62 Apr 23 18:04 cronjob_bandit15_root
-rw-r--r--   1 root root    62 Apr 23 18:04 cronjob_bandit17_root
-rw-r--r--   1 root root   120 Apr 23 18:04 cronjob_bandit22
-rw-r--r--   1 root root   122 Apr 23 18:04 cronjob_bandit23
-rw-r--r--   1 root root   120 Apr 23 18:04 cronjob_bandit24
-rw-r--r--   1 root root    62 Apr 23 18:04 cronjob_bandit25_root
-rw-r--r--   1 root root   201 Jan  8  2022 e2scrub_all
-rwx------   1 root root    52 Apr 23 18:05 otw-tmp-dir
-rw-r--r--   1 root root   102 Mar 23  2022 .placeholder
-rw-r--r--   1 root root   396 Feb  2  2021 sysstat
bandit21@bandit:~$ ls /etc/cron.d
cronjob_bandit15_root  cronjob_bandit17_root  cronjob_bandit22  cronjob_bandit23  cronjob_bandit24  cronjob_bandit25_root  e2scrub_all  otw-tmp-dir  sysstat
bandit21@bandit:~$ cat /etc/cron.d/creonjob_bandit22.sh
cat: /etc/cron.d/creonjob_bandit22.sh: No such file or directory
bandit21@bandit:~$ cat /etc/cron.d/creonjob_bandit22
cat: /etc/cron.d/creonjob_bandit22: No such file or directory
bandit21@bandit:~$ cat /etc/creon.d/cronjob_bandit22
cat: /etc/creon.d/cronjob_bandit22: No such file or directory
bandit21@bandit:~$ cat /etc/cron.d/cronjob_bandit22
@reboot bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
* * * * * bandit22 /usr/bin/cronjob_bandit22.sh &> /dev/null
bandit21@bandit:~$ cat /usr/bin/cronjob_bandit22.sh
#!/bin/bash
chmod 644 /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
cat /etc/bandit_pass/bandit22 > /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
bandit21@bandit:~$ cat /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv
WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff
bandit21@bandit:~$
```
## Notas adicionales
`cron`, `crontab`, y `crontab(5)` son componentes relacionados con la programación de tareas automatizadas en sistemas Unix y Unix-like (como Linux). Aquí está una breve explicación de cada uno:

1. **cron**: `cron` es un programa de planificación de tareas en sistemas Unix. Su función principal es ejecutar comandos de manera programada y automática en momentos específicos, ya sea diariamente, semanalmente, mensualmente o según otros criterios de tiempo. `cron` se ejecuta en segundo plano y verifica regularmente su tabla de tareas para ver si hay comandos que deben ejecutarse en ese momento.
    
2. **crontab**: `crontab` es una abreviatura de "tabla de cron". Es un archivo de configuración que permite a los usuarios programar tareas para `cron`. Cada usuario puede tener su propia `crontab` para programar tareas específicas para sus necesidades. Con el comando `crontab`, los usuarios pueden crear, modificar, eliminar y listar las tareas que `cron` debe ejecutar para ese usuario.
    
3. **crontab(5)**: `crontab(5)` es la página de manual (manpage) que describe la estructura y el formato de las `crontabs`. Puedes acceder a esta página de manual utilizando el comando `man crontab`. Proporciona información detallada sobre cómo escribir y configurar las entradas en una `crontab`, incluyendo la sintaxis, los campos de tiempo y las opciones disponibles.
    

En resumen, `cron` es el servicio que ejecuta tareas programadas, `crontab` es el comando que permite a los usuarios crear y gestionar sus propias tablas de tareas programadas, y `crontab(5)` es la página de manual que detalla cómo configurar y utilizar las `crontabs`.
## Referencias