# Bandit Level 9 → Level 10
## Objetivo
The password for the next level is stored in the file **data.txt** in one of the few human-readable strings, preceded by several ‘=’ characters.
## Datos de acceso al nivel
```
Server : bandit9.labs.overthewire.org
User : bandit9
Password : EN632PlfYiZbn3PhVK3XOGSlNInNE00t
Comando: SSH bandit9@bandit.labs.overthewire.org -p 2220
```
## Solución 
bandit9@bandit:~$ whoami
bandit9
bandit9@bandit:~$ pwd
/home/bandit9
bandit9@bandit:~$ ls
data.txt
bandit9@bandit:~$ cat data.txt | strings -n 12
4========== the#
========== password
========== is
========== G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
bandit9@bandit:~$
## Notas adicionales
String imprime las cadenas que si se pueden imprimir (código ASCII)
-n es para mostrar las líneas que mínimo tengan 12 caracteres 
## Referencias