# Level 19 → Level 20
## Objetivo
To gain access to the next level, you should use the setuid binary in the homedirectory. Execute it without arguments to find out how to use it. The password for this level can be found in the usual place (/etc/bandit_pass), after you have used the setuid binary.
## Datos de acceso al nivel
```
Server : bandit19.labs.overthewire.org
User : bandit19
Password : awhqfNnAbc1naukrpqDYcF95h7HoMTrC
Comando: SSH bandit19@bandit.labs.overthewire.org -p 2220
```
## Solución 
```
bandit19@bandit:~$ pwd
/home/bandit19
bandit19@bandit:~$ ls
bandit20-do
bandit19@bandit:~$ ls -la
total 36
drwxr-xr-x  2 root     root      4096 Apr 23 18:04 .
drwxr-xr-x 70 root     root      4096 Apr 23 18:05 ..
-rwsr-x---  1 bandit20 bandit19 14876 Apr 23 18:04 bandit20-do
-rw-r--r--  1 root     root       220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root     root      3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root     root       807 Jan  6  2022 .profile
bandit19@bandit:~$ ./bandit20-do cat /etc/bandit_pass/bandit20
VxCazJaVykI6W36BkBU0mJTCM8rR95XT
bandit19@bandit:~$
```

## Notas adicionales
- `cat /etc/bandit_pass/bandit20`: Este es el comando que se ejecuta utilizando "bandit20-do". Se utiliza el comando `cat` para leer el contenido de un archivo en el sistema. En este caso, el archivo que se está leyendo es `/etc/bandit_pass/bandit20`, que probablemente contiene la contraseña para el nivel 20 del juego "Bandit".
    
En resumen, este comando parece estar diseñado para leer y mostrar la contraseña.

La contraseña se mostrará en la salida de la terminal cuando se ejecute este comando, siempre y cuando el usuario tenga los permisos necesarios para acceder al archivo `/etc/bandit_pass/bandit20`.
## Referencias