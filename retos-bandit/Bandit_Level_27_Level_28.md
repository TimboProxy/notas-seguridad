# Bandit Level 27 → Level 28
## Objetivo
There is a git repository at `ssh://bandit27-git@localhost/home/bandit27-git/repo` via the port `2220`. The password for the user `bandit27-git` is the same as for the user `bandit27`.

Clone the repository and find the password for the next level.
## Datos de acceso al nivel
```
ssh bandit27@bandit.labs.overthewire.org -p 2220 
	(comando para iniciar ssh)
contraseña: 
YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS
```
## Solución 
```pwd
bandit27@bandit:~$ ls -la
total 20
drwxr-xr-x  2 root root 4096 Apr 23 18:04 .
drwxr-xr-x 70 root root 4096 Apr 23 18:05 ..
-rw-r--r--  1 root root  220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root root 3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root root  807 Jan  6  2022 .profile
bandit27@bandit:~$ pwd
/home/bandit27
bandit27@bandit:~$ mktemp -d
/tmp/tmp.mMwjiAsPQ4 
bandit27@bandit:~$ cd /tmp/tmp
bandit27@bandit:/tmp/tmp$ cd ..
bandit27@bandit:/tmp$ cd ..
bandit27@bandit:/$ cd /tmp/tmp.mMwjiAsPQ4
bandit27@bandit:/tmp/tmp.mMwjiAsPQ4$ git clone ssh://bandit27-
Cloning into 'bandit27-'...
fatal: no path specified; see 'git help pull' for valid url syntax
bandit27@bandit:/tmp/tmp.mMwjiAsPQ4$ git clone ssh://bandit27-git@localhost:2220/home/bandit27-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit27/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit27/.ssh/known_hosts).
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit27-git@localhost's password:
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (3/3), done.
bandit27@bandit:/tmp/tmp.mMwjiAsPQ4$ ls -la
total 10564
drwx------    3 bandit27 bandit27     4096 Sep 22 03:00 .
drwxrwx-wt 3747 root     root     10801152 Sep 22 03:01 ..
drwxrwxr-x    3 bandit27 bandit27     4096 Sep 22 03:00 repo
bandit27@bandit:/tmp/tmp.mMwjiAsPQ4$ ls
repo
bandit27@bandit:/tmp/tmp.mMwjiAsPQ4$ cat repo
cat: repo: Is a directory
bandit27@bandit:/tmp/tmp.mMwjiAsPQ4$ cat README
cat: README: No such file or directory
bandit27@bandit:/tmp/tmp.mMwjiAsPQ4$ cd repo
bandit27@bandit:/tmp/tmp.mMwjiAsPQ4/repo$ ls
README
bandit27@bandit:/tmp/tmp.mMwjiAsPQ4/repo$ cat README
The password to the next level is: AVanL161y9rsbcJIsFHuw35rjaOM19nR
bandit27@bandit:/tmp/tmp.mMwjiAsPQ4/repo$
```
## Notas adicionales
- `git clone` es el comando para clonar un repositorio.
- `ssh://` indica que la conexión se realizará a través del protocolo SSH.
- `bandit27-git@localhost:2220` es la dirección y el puerto para conectarse al servidor SSH en localhost con el usuario "bandit27-git".
- `/home/bandit27-git/repo` es la ruta al repositorio Git que deseas clonar.
## Referencias
