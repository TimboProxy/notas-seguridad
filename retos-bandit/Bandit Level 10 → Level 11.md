# Bandit Level 10 → Level 11
## Objetivo
The password for the next level is stored in the file **data.txt**, which contains base64 encoded data
## Datos de acceso al nivel
```
Server : bandit10.labs.overthewire.org
User : bandit10
Password : G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
Comando: SSH bandit10@bandit.labs.overthewire.org -p 2220
```
## Solución 
bandit10@bandit:~$ whoami
bandit10
bandit10@bandit:~$ pwd
/home/bandit10
bandit10@bandit:~$ ls
data.txt
bandit10@bandit:~$ cat data.txt | base64 -d
The password is 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM
bandit10@bandit:~$ cat data.txt
VGhlIHBhc3N3b3JkIGlzIDZ6UGV6aUxkUjJSS05kTllGTmI2blZDS3pwaGxYSEJNCg==
bandit10@bandit:~$
## Notas adicionales
-Se codifican los archivos para que si alguien lo   intercepta no pueda ver el mensaje original.
-Base64 es un esquema de codificación de binario a texto.
-Para codificar un mensaje en base64:
echo "hola profe hoy no venimos" | base64
-Para revertir hay que tomar la cadena modificada y:
echo "linea modificada" | base64 -d
## Referencias