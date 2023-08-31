# Bandit Level 0 → Level 1 
## Objetivo
The password for the next level is stored in a file called **readme** located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.
## Datos de acceso al nivel
```
Server : bandit.labs.overthewire.org
User : bandit0
Password : bandit0
Comando: SSH bandit0@bandit.labs.overthewire.org -p 2220
```
## Solución 
```
bandit0@bandit:~$ whoami
bandit0
bandit0@bandit:~$ pwd
/home/bandit0
bandit0@bandit:~$ ls
readme
bandit0@bandit:~$ cat readme
NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL
bandit0@bandit:~$
```
## Notas adicionales
El comando "whoami" nos dice con que usuario estamos logeados
El comando "pwd" nos dice en que directorio nos encontramos
El comando "ls" nos lista los archivos del directorio especificado, si no hay nada entonces especifica en el directorio en el que nos encontramos
El comando "cat" permite leer archivos de texto
## Referencias