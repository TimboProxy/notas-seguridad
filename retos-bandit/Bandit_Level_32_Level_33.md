# Bandit Level 32 → Level 33
## Objetivo
After all this `git` stuff its time for another escape. Good luck!
## Datos de acceso al nivel
```
ssh bandit32@bandit.labs.overthewire.org -p 2220 
	(comando para iniciar ssh)
contraseña: 
rmCBvG56y58BXzv98yZGdO7ATVL5dW8y
```
## Solución 
```
  Enjoy your stay!

WELCOME TO THE UPPERCASE SHELL
>> ls
sh: 1: LS: Permission denied
>> sh -c "<user-input>"
sh: 1: SH: Permission denied
>> pwd
sh: 1: PWD: Permission denied
>> $shell
WELCOME TO THE UPPERCASE SHELL
>> $euid
>> $0
$ export SHELL=/biun/bash
$ echo $SHELL
/biun/bash
$ $SHELL
sh: 3: /biun/bash: not found
$ export SHELL=/bin/bash
$ echo $SHELL
/bin/bash
$ $SHELL
bandit33@bandit:~$
bandit33@bandit:~$ ls
uppershell
bandit33@bandit:~$ cat /etc/bandit_pass
cat: /etc/bandit_pass: Is a directory
bandit33@bandit:~$ cd /etc/bandit_pass
bandit33@bandit:/etc/bandit_pass$ ls
bandit0   bandit12  bandit16  bandit2   bandit23  bandit27  bandit30  bandit4  bandit8
bandit1   bandit13  bandit17  bandit20  bandit24  bandit28  bandit31  bandit5  bandit9
bandit10  bandit14  bandit18  bandit21  bandit25  bandit29  bandit32  bandit6
bandit11  bandit15  bandit19  bandit22  bandit26  bandit3   bandit33  bandit7
bandit33@bandit:/etc/bandit_pass$ cat bandit33
odHo63fHiFqcWWJG9rLiLDtPm45KzUKy
bandit33@bandit:/etc/bandit_pass$
```
## Notas adicionales
## Referencias