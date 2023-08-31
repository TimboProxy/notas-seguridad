## Bandit Level 1 → Level 2
## Objetivo
The password for the next level is stored in a file called **readme** located in the home directory. Use this password to log into bandit1 using SSH. Whenever you find a password for a level, use SSH (on port 2220) to log into that level and continue the game.
## Datos de acceso al nivel
```
Server : bandit1.labs.overthewire.org
User : bandit1
Password : NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL
Comando: SSH bandit1@bandit.labs.overthewire.org -p 2220
```
## Solución 
bandit1@bandit:~$ whoami
bandit1
bandit1@bandit:~$ pwd
/home/bandit1
bandit1@bandit:~$ ls
-
bandit1@bandit:~$ cat ./-
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi
bandit1@bandit:~$
## Notas adicionales
el guion funciona como indicador de parámetro, así que al intentar entrar al archivo con "cat -" se queda esperando una letra para un parámetro. Asi que si queremos acceder debemos:
1.- Poner un punto y diagonal antes del nombre del archivo
2.-acceder con la dirección completa del archivo (por ejemplo "cat /home/bandit1/-")
## Referencias