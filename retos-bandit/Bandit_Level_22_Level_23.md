# Bandit Level 22 → Level 23
## Objetivo
A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

**NOTE:** Looking at shell scripts written by other people is a very useful skill. The script for this level is intentionally made easy to read. If you are having problems understanding what it does, try executing it to see the debug information it prints.
## Datos de acceso al nivel
```
ssh bandit22@bandit.labs.overthewire.org -p 2220 
	(comando para iniciar ssh)
contraseña: 
WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff
```
## Solución 
```pwd
bandit22@bandit:~$ pwd
/home/bandit22
bandit22@bandit:~$ ls
bandit22@bandit:~$ ls -la
total 20
drwxr-xr-x  2 root root 4096 Apr 23 18:04 .
drwxr-xr-x 70 root root 4096 Apr 23 18:05 ..
-rw-r--r--  1 root root  220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root root 3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root root  807 Jan  6  2022 .profile
bandit22@bandit:~$ ls etc/cron.d
ls: cannot access 'etc/cron.d': No such file or directory
bandit22@bandit:~$ ls /etc/cron.d
cronjob_bandit15_root  cronjob_bandit22  cronjob_bandit24       e2scrub_all  sysstat
cronjob_bandit17_root  cronjob_bandit23  cronjob_bandit25_root  otw-tmp-dir
bandit22@bandit:~$ cat /etc/cron.d/cronjob_bandit23
@reboot bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
* * * * * bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
bandit22@bandit:~$ whoami
bandit22
bandit22@bandit:~$ myname=bandit23
bandit22@bandit:~$ echo $(echo I am user $myname | md5aum | cut -d ' ' -f l)
cut: invalid field value ‘l’
Try 'cut --help' for more information.
Command 'md5aum' not found, did you mean:
  command 'md5sum' from deb coreutils (8.32-4.1ubuntu1)
Try: apt install <deb name>

bandit22@bandit:~$ echo $(echo I am user $myname | md5aum | cut -d ' ' -f 1)
Command 'md5aum' not found, did you mean:
  command 'md5sum' from deb coreutils (8.32-4.1ubuntu1)
Try: apt install <deb name>

bandit22@bandit:~$ echo $(echo I am user $myname | md5sum | cut -d ' ' -f 1)
8ca319486bfbbc3663ea0fbe81326349
bandit22@bandit:~$ cat /tmp/8ca319486bfbbc3663ea0fbe81326349
QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G
```
## Notas adicionales
echo $(echo I am user $myname | md5sum | cut -d ' ' -f 1)
1. Toma una variable llamada `$myname`.
2. Concatena el texto "I am user" seguido del valor de la variable `$myname`.
3. Luego, utiliza `md5sum` para calcular el valor hash MD5 de la cadena resultante. Esto crea un resumen criptográfico de la cadena.
4. Finalmente, usa `cut` para extraer el primer campo (que es el valor hash MD5) de la salida de `md5sum`.

Entonces, el comando completo toma el valor de la variable `$myname`, lo combina con la cadena "I am user", calcula el valor hash MD5 de esa cadena, y finalmente, imprime el valor hash MD5 en la salida estándar.

El propósito de este comando podría ser utilizarlo como una forma de crear una representación única y fija de la cadena "I am user" seguida del valor de `$myname` para su uso en identificación o verificación de integridad, ya que el valor hash MD5 es generalmente único para entradas diferentes y es difícil de revertir para obtener el valor original. Sin embargo, es importante mencionar que el uso de MD5 para la seguridad criptográfica se considera obsoleto y no seguro en la actualidad debido a vulnerabilidades conocidas, y se recomienda utilizar algoritmos de hash más seguros, como SHA-256 o SHA-3, en lugar de MD5.
## Referencias
