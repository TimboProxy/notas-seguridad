# Bandit Level 3 → Level 4
## Objetivo
The password for the next level is stored in a hidden file in the **inhere** directory.
## Datos de acceso al nivel
```
Server : bandit3.labs.overthewire.org
User : bandit3
Password : aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG
Comando: SSH bandit3@bandit.labs.overthewire.org -p 2220
```
## Solución 
bandit3@bandit:~$ whoami
bandit3
bandit3@bandit:~$ pwd
/home/bandit3
bandit3@bandit:~$ ls
inhere
bandit3@bandit:~$ cd inhere
bandit3@bandit:~/inhere$ ls
bandit3@bandit:~/inhere$ ls -a
.  ..  .hidden
bandit3@bandit:~/inhere$ cat .hidden
2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe
bandit3@bandit:~/inhere$
## Notas adicionales
la carpeta escodida tiene un punto antes de su nombre y el comando "ls" no muestra las carpetas que empiecen con un punto porque hay dos carpetas "." y ".." que sirven para unir directorios. el parametro -a muestra las carpetas que tengan un punto al inicio
## Referencias
