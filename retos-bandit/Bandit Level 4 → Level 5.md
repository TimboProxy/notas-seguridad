# Bandit Level 4 → Level 5
## Objetivo
The password for the next level is stored in the only human-readable file in the **inhere** directory. Tip: if your terminal is messed up, try the “reset” command.
## Datos de acceso al nivel
```
Server : bandit4.labs.overthewire.org
User : bandit4
Password : 2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe
Comando: SSH bandit4@bandit.labs.overthewire.org -p 2220
```
## Solución 
bandit4@bandit:~$ whoami
bandit4
bandit4@bandit:~$ pwd
/home/bandit4
bandit4@bandit:~$ ls
inhere
bandit4@bandit:~$ cd inhere
bandit4@bandit:~/inhere$ ls
-file00  -file01  -file02  -file03  -file04  -file05  -file06  -file07  -file08  -file09
bandit4@bandit:~/inhere$ file ./*
./-file00: data
./-file01: data
./-file02: data
./-file03: data
./-file04: data
./-file05: data
./-file06: data
./-file07: ASCII text
./-file08: data
./-file09: Non-ISO extended-ASCII text, with no line terminators
bandit4@bandit:~/inhere$ cat /home/bandit4/inhere/-file07
lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR
bandit4@bandit:~/inhere$
## Notas adicionales
El comando "file" determina el tipo del archivo que especifiquemos.
El asterisco es un comodín que efectúa el comando en todos los archivos de la dirección actual (si no esta ninguna especificada)
## Referencias