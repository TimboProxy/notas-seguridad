# # Bandit Level 5 → Level 6
## Objetivo
The password for the next level is stored in a file somewhere under the **inhere** directory and has all of the following properties:

- human-readable
- 1033 bytes in size
- not executable
## Datos de acceso al nivel
```
Server : bandit5.labs.overthewire.org
User : bandit5
Password : lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR
Comando: SSH bandit5@bandit.labs.overthewire.org -p 2220
```
## Solución 
bandit5@bandit:~$ whoami
bandit5
bandit5@bandit:~$ pwd
/home/bandit5
bandit5@bandit:~$ ls
inhere
bandit5@bandit:~$ cd inhere
bandit5@bandit:~/inhere$ ls
maybehere00  maybehere03  maybehere06  maybehere09  maybehere12  maybehere15  maybehere18
maybehere01  maybehere04  maybehere07  maybehere10  maybehere13  maybehere16  maybehere19
maybehere02  maybehere05  maybehere08  maybehere11  maybehere14  maybehere17
bandit5@bandit:~/inhere$ find -readable -type f -size 1033c
./maybehere07/.file2
bandit5@bandit:~/inhere$ cd maybehere07
bandit5@bandit:~/inhere/maybehere07$ cat .file2
P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
                                   
## Notas adicionales
El comando "find" nos permite buscar desde la ruta especificada hasta todo lo que contenga esa ruta un archivo, podemos poner parámetros para especificar que características puede tener ese archivo:
-readable: que este en formato ASCII
-type f: F es regular, un tipo de archivo regular
-size: el numero de bytes en caracteres, si son 100 bites entonces tiene 100 caracteres y sería (size 100c)
## Referencias