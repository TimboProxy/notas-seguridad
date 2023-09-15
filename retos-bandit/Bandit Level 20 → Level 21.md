# Level 20 → Level 21
## Objetivo
There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).

**NOTE:** Try connecting to your own network daemon to see if it works as you think
## Datos de acceso al nivel
```
Server : bandit20.labs.overthewire.org
User : bandit20
Password : VxCazJaVykI6W36BkBU0mJTCM8rR95XT
Comando: SSH bandit20@bandit.labs.overthewire.org -p 2220
```
## Solución 
```
bandit20@bandit:~$ pwd
/home/bandit20
bandit20@bandit:~$ ls
suconnect
bandit20@bandit:~$ ls -la
total 36
drwxr-xr-x  2 root     root      4096 Apr 23 18:04 .
drwxr-xr-x 70 root     root      4096 Apr 23 18:05 ..
-rw-r--r--  1 root     root       220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root     root      3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root     root       807 Jan  6  2022 .profile
-rwsr-x---  1 bandit21 bandit20 15600 Apr 23 18:04 suconnect
bandit20@bandit:~$ nc -lnvp 2020 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT &
[1] 3505824
bandit20@bandit:~$ [1] 3444802Listening on 0.0.0.0 2020
bandit20@bandit:~$ ./suconnect 2020
Connection received on 127.0.0.1 48964
Read: VxCazJaVykI6W36BkBU0mJTCM8rR95XT
Password matches, sending next password
NvEJF7oVjkddltPSrdKEFOllh9V1IBcq
[1]+ Done nc -lnvp 2020 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT
bandit20@bandit:~$ exit
```
## Notas adicionales
`nc -lnvp 2020 <<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT &` ejecuta el programa `nc` (netcat) en modo servidor en el puerto 2020 y redirige la entrada estándar (`<<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT`) con una contraseña o datos en forma de cadena (`VxCazJaVykI6W36BkBU0mJTCM8rR95XT`). El `&` al final del comando significa que se ejecutará en segundo plano.

Aquí hay una explicación de cada parte del comando:

- `nc`: Esto inicia el programa `nc`, también conocido como netcat, que es una herramienta de red que se utiliza para crear conexiones de red y transferir datos a través de ellas.
    
- `-lnvp 2020`: Estos son argumentos que configuran la forma en que se ejecutará `nc`:
    
    - `-l`: Indica que `nc` debe funcionar en modo servidor, esperando conexiones entrantes.
    - `-n`: Evita la resolución de nombres de host y números de puerto para que `nc` utilice direcciones IP y números de puerto en lugar de nombres de host y números de servicio.
    - `-v`: Habilita el modo detallado o "verbose", lo que significa que mostrará información detallada sobre las conexiones entrantes.
    - `-p 2020`: Especifica el puerto en el que `nc` escuchará conexiones entrantes, en este caso, el puerto 2020.
- `<<< VxCazJaVykI6W36BkBU0mJTCM8rR95XT`: Esto redirige la cadena `VxCazJaVykI6W36BkBU0mJTCM8rR95XT` como entrada estándar al comando `nc`. Esto significa que esta cadena se enviará a través de la conexión cuando alguien se conecte al puerto 2020.
    
- `&`: Esto indica que el comando se ejecutará en segundo plano, lo que significa que seguirá funcionando mientras puedes continuar usando la terminal para otros comandos.
    

En resumen, este comando inicia un servidor `nc` en el puerto 2020 que envía la cadena `VxCazJaVykI6W36BkBU0mJTCM8rR95XT` como respuesta cuando alguien se conecta a ese puerto. El proceso se ejecuta en segundo plano, lo que permite que la terminal siga siendo utilizada para otros comandos.
## Referencias
## Referencias