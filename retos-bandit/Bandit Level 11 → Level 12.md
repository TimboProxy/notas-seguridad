# Bandit Level 11 → Level 12
## Objetivo
The password for the next level is stored in the file **data.txt**, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions
## Datos de acceso al nivel
```
Server : bandit11.labs.overthewire.org
User : bandit11
Password : 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM
Comando: SSH bandit11@bandit.labs.overthewire.org -p 2220
```
## Solución 
bandit11@bandit:~$ whoami
bandit11
bandit11@bandit:~$ pwd
/home/bandit11
bandit11@bandit:~$ ls
data.txt
bandit11@bandit:~$ cat data.txt
Gur cnffjbeq vf WIAOOSFzMjXXBC0KoSKBbJ8puQm5lIEi
bandit11@bandit:~$ cat data.txt | tr [a-zA-Z] [n-za-mN-ZA-W]
The password is JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv
bandit11@bandit:~$
## Notas adicionales
-"Algoritmo de cesar" 
-ROT13: rota una letra 13 posiciones adelante, una A se convierte en una N, una B se convierte en una O y así sucesivamente.
-Lo mas sencillo es que si sabemos la "codificacion" que se esta usando vayamos a una pagina para revertir eso en especifico.
-Comando "tr" rota los caracteres en el texto, cambiando unas letras por otras, se desplazan las letras 13 lugares
-cat data.txt | tr [a-zA-Z] [n-za-mN-ZA-W]
## Referencias