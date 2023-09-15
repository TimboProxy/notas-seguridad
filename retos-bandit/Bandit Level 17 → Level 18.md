# Level 17 → Level 18
## Objetivo
There are 2 files in the homedirectory: **passwords.old and passwords.new**. The password for the next level is in **passwords.new** and is the only line that has been changed between **passwords.old and passwords.new**

**NOTE: if you have solved this level and see ‘Byebye!’ when trying to log into bandit18, this is related to the next level, bandit19**
## Datos de acceso al nivel
```
Server : bandit17.labs.overthewire.org
User : bandit17
Password : VwOSWtCA7lRKkTfbr2IDh6awj9RNZM5e
Comando: SSH bandit17@bandit.labs.overthewire.org -p 2220
```
## Solución 
```
bandit17@bandit:~$ ls -la
total 36
drwxr-xr-x 3 root root 4096 Sep 1 06:30 .
drwxr-xr-x 49 root root 4096 Sep 1 06:30 ..
-rw-r----- 1 bandit17 bandit17 33 Sep 1 06:30 .bandit16.password
-rw-r--r-- 1 root root 220 Jan 6 2022 .bash_logout
-rw-r--r-- 1 root root 3771 Jan 6 2022 .bashrc
-rw-r----- 1 bandit18 bandit17 3300 Sep 1 06:30 passwords.new
-rw-r----- 1 bandit18 bandit17 3300 Sep 1 06:30 passwords.old
-rw-r--r-- 1 root root 807 Jan 6 2022 .profile
drwxr-xr-x 2 root root 4096 Sep 1 06:30 .ssh
bandit17@bandit:~$ diff passwords.old passwords.new --color
42c42
< 09wUIyMU4YhOzl1Lzxoz0voIBzZ2TUAf
---
> hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg
bandit17@bandit:~$ exit
```
## Notas adicionales
`diff passwords.old passwords.new --color`, se utiliza para comparar dos archivos de texto, "passwords.old" y "passwords.new", línea por línea, y mostrar las diferencias entre ellos resaltadas en color en la salida.

Aquí está la explicación de cada parte del comando:

- `diff`: Este es el comando principal que se utiliza para comparar archivos y mostrar las diferencias entre ellos. En este caso, estás utilizando `diff` para comparar los archivos "passwords.old" y "passwords.new".
    
- `passwords.old` y `passwords.new`: Estos son los nombres de los archivos que deseas comparar. "passwords.old" es el archivo de referencia o antiguo, mientras que "passwords.new" es el archivo nuevo o actualizado.
    
- `--color`: Esta opción se utiliza para resaltar las diferencias encontradas en color en la salida del comando `diff`. La salida se mostrará de una manera más legible, con las adiciones en una línea resaltadas en un color y las eliminaciones en otra línea resaltadas en un color diferente, lo que facilita la identificación de las diferencias.
    

Entonces, cuando ejecutas este comando, verás una salida que muestra las diferencias entre los dos archivos "passwords.old" y "passwords.new", y estas diferencias se resaltarán en color para que sean fácilmente visibles y distinguibles. Esto es útil para verificar qué cambios se han realizado entre las contraseñas antiguas y las nuevas, por ejemplo, en un archivo de contraseñas.
## Referencias