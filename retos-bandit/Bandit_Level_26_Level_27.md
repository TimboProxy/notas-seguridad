# Bandit Level 26 → Level 27
## Objetivo
Good job getting a shell! Now hurry and grab the password for bandit27!
## Datos de acceso al nivel
```
ssh bandit26@bandit.labs.overthewire.org -p 2220 
	(comando para iniciar ssh)
contraseña: 
c7GvcKlw9mC7aUQaPx7nwFstuAIBw1o1
```
## Solución 
```pwd
 _                     _ _ _   ___   __
 | |                   | (_) | |__ \ / /
 | |__   __ _ _ __   __| |_| |_   ) / /_
 | '_ \ / _` | '_ \ / _` | | __| / / '_ \
 | |_) | (_| | | | | (_| | | |_ / /| (_) |
:set shell=/bin/bash

 | |_) | (_| | | | | (_| | | |_ / /| (_) |
:shell
bandit26@bandit:~$ ls
bandit27-do  text.txt
bandit26@bandit:~$ ./bandit27-do id
uid=11026(bandit26) gid=11026(bandit26) euid=11027(bandit27) groups=11026(bandit26)
bandit26@bandit:~$ ./bandit27-do cat /etc/bandit_pass/bandit27
YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS
bandit26@bandit:~$
```
## Notas adicionales
`./bandit27-do cat /etc/bandit_pass/bandit27` es una operación de línea de comandos que se ejecuta en un sistema Unix o Linux. Explicaré su funcionalidad.
1. `./bandit27-do`: Un script o un programa ejecutable llamado "bandit27-do" ubicado en el directorio actual (indicado por el "./"). Este programa probablemente esté relacionado con el desafío de "bandit" en el juego "OverTheWire", donde los jugadores resuelven desafíos de seguridad de sistemas Unix.
    
2. `cat`: Es un comando que se utiliza para mostrar el contenido de archivos en la terminal.
    
3. `/etc/bandit_pass/bandit27`: Es la ruta de un archivo en el sistema de archivos. En este caso, parece ser la ubicación de un archivo que contiene la contraseña (contrasinal) del nivel 27 del desafío "bandit" en el juego.
## Referencias