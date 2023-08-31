# Bandit Level 7 → Level 8
## Objetivo
The password for the next level is stored in the file **data.txt** next to the word **millionth**
## Datos de acceso al nivel
```
Server : bandit7.labs.overthewire.org
User : bandit7
Password : z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S
Comando: SSH bandit7@bandit.labs.overthewire.org -p 2220
```
## Solución 
bandit7@bandit:~$ ls
data.txt
bandit7@bandit:~$ nano data.txt
Unable to create directory /home/bandit7/.local/share/nano/: No such file or directory
It is required for saving/loading search history or cursor positions.

bandit7@bandit:~$ bandit7@bandit:~$ millionth       TESKZC0XvTetK0S9xNwm25STk5iWrBvP
## Notas adicionales
Al tener mucho texto el archivo "data.txt" y como sabemos que la contraseña esta despues de la palabra "millionth" usamos el editor de nano para poder buscar y localizar esta palabra sobre todas las demas
## Referencias