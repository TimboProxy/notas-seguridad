# Bandit Level 14 → Level 15
## Objetivo
The password for the next level can be retrieved by submitting the password of the current level to **port 30000 on localhost**.
## Datos de acceso al nivel
```
Server : bandit14.labs.overthewire.org
User : bandit14
Password : fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
Comando: SSH bandit14@bandit.labs.overthewire.org -p 2220
```
## Solución
bandit14@bandit:~$ ls -la
total 24
drwxr-xr-x  3 root root 4096 Apr 23 18:04 .
drwxr-xr-x 70 root root 4096 Apr 23 18:05 ..
-rw-r--r--  1 root root  220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root root 3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root root  807 Jan  6  2022 .profile
drwxr-xr-x  2 root root 4096 Apr 23 18:04 .ssh
bandit14@bandit:~$ nc -v localhost 30000
Connection to localhost (127.0.0.1) 30000 port [tcp/*] succeeded!
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq
Correct!
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

## Notas adicionales
--who is "ip" te dice información de esa ip, importante
tenemos una ip publica y privada

--host www.uaz.edu.mx da la ip del servidor de la uaz
la ip puede transformarse en la direccion y viceversa con algunos programas/paginas

puerto 80 o 443 son normalmente donde estan las paginas web

para conectarse por linux sería:

nc -v ip 80 (el puerto va a l final) 
la -v es para ver el estatus

ls -la
nc -v localhost 30000
fGrHPx402xGC7U7rXKDaxiWFTOiF0ENq

Netcat es la navaja suiza de los hackers

nc -lnvp 6666

nc -v ww.uaz.edu.mx 443 (se usa el protocolo http para poder pedir informacion)

head http/1.0

## Referencias