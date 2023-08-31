# Bandit Level 6 → Level 7
## Objetivo
The password for the next level is stored **somewhere on the server** and has all of the following properties:

- owned by user bandit7
- owned by group bandit6
- 33 bytes in size
## Datos de acceso al nivel
```
Server : bandit6.labs.overthewire.org
User : bandit6
Password : P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
Comando: SSH bandit6@bandit.labs.overthewire.org -p 2220
```
## Solución 
bandit6@bandit:~$ whoami
bandit6
bandit6@bandit:~$ pwd
/home/bandit6
bandit6@bandit:~$ cd ..
bandit6@bandit:/home$ ls
bandit0   bandit17  bandit25      bandit30      bandit7    drifter15  formulaone0  krypton4
bandit1   bandit18  bandit26      bandit30-git  bandit8    drifter2   formulaone1  krypton5
bandit10  bandit19  bandit27      bandit31      bandit9    drifter3   formulaone2  krypton6
bandit11  bandit2   bandit27-git  bandit31-git  drifter0   drifter4   formulaone3  krypton7
bandit12  bandit20  bandit28      bandit32      drifter1   drifter5   formulaone5  ubuntu
bandit13  bandit21  bandit28-git  bandit33      drifter10  drifter6   formulaone6
bandit14  bandit22  bandit29      bandit4       drifter12  drifter7   krypton1
bandit15  bandit23  bandit29-git  bandit5       drifter13  drifter8   krypton2
bandit16  bandit24  bandit3       bandit6       drifter14  drifter9   krypton3
bandit6@bandit:/home$ find / -size 33c -user bandit7 -group bandit6 2>/dev/null
/var/lib/dpkg/info/bandit7.password
bandit6@bandit:/home$ cat /var/lib/dpkg/info/bandit7.password
z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S
bandit6@bandit:/home$
## Notas adicionales
Aquí se usa el comando "find" de nuevo, esta vez desde la carpeta de todos los usuarios.

Para que no salgan "errores" que son resultados con permisos denegados al usar "find" y no poder acceder a esas carpetas por la falta de permisos utilizamos el siguiente parámetro:
"2>/dev/null" lo que hace es mandar todos los resultados de "error" a un dispositivo nulo y se quedan los demás resultados.
1.- input
2.- output
3.- error

## Referencias