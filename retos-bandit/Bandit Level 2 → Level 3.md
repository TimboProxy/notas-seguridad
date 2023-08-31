# Bandit Level 2 → Level 3
## Objetivo
The password for the next level is stored in a file called **spaces in this filename** located in the home directory
## Datos de acceso al nivel
```
Server : bandit2.labs.overthewire.org
User : bandit2
Password : rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
Comando: SSH bandit2@bandit.labs.overthewire.org -p 2220
```
## Solución 
bandit2@bandit:~$ whoami
bandit2
bandit2@bandit:~$ pwd
/home/bandit2
bandit2@bandit:~$ ls
spaces in this filename
bandit2@bandit:~$ cat "spaces in this filename"
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
bandit2@bandit:~$
## Notas adicionales
Si ponemos "cat spaces in this filename" el comando cat toma cada palabra como un archivo y los intenta abrir, asi que tenemos que poner el nombre del archivo entre comillas para que lo tome como un solo archivo
## Referencias
