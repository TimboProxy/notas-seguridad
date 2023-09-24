# Bandit Level 30 → Level 31
## Objetivo
There is a git repository at `ssh://bandit30-git@localhost/home/bandit30-git/repo` via the port `2220`. The password for the user `bandit30-git` is the same as for the user `bandit30`.

Clone the repository and find the password for the next level.
## Datos de acceso al nivel
```
ssh bandit30@bandit.labs.overthewire.org -p 2220 
	(comando para iniciar ssh)
contraseña: 
xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS
```
## Solución 
```pwd
bandit30@bandit:~$ cd /tmp/
bandit30@bandit:/tmp$ mk dir timbu12 
mk: command not found
bandit30@bandit:/tmp$ mkdir timbu12
bandit30@bandit:/tmp$ cd timbu12
bandit30@bandit:/tmp/timbu12$ git clone ssh://bandit30-git@localhost:2220/home/bandit30-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit30/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit30/.ssh/known_hosts).
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit30-git@localhost's password:
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (4/4), done.
bandit30@bandit:/tmp/timbu12$ ls -la
total 10564
drwxrwxr-x    3 bandit30 bandit30     4096 Sep 23 04:13 .
drwxrwx-wt 4748 root     root     10801152 Sep 23 04:13 ..
drwxrwxr-x    3 bandit30 bandit30     4096 Sep 23 04:13 repo
bandit30@bandit:/tmp/timbu12$ cd repo
bandit30@bandit:/tmp/timbu12/repo$ ls -la
total 16
drwxrwxr-x 3 bandit30 bandit30 4096 Sep 23 04:13 .
drwxrwxr-x 3 bandit30 bandit30 4096 Sep 23 04:13 ..
drwxrwxr-x 8 bandit30 bandit30 4096 Sep 23 04:13 .git
-rw-rw-r-- 1 bandit30 bandit30   30 Sep 23 04:13 README.md
bandit30@bandit:/tmp/timbu12/repo$ cat README.md
just an epmty file... muahaha
bandit30@bandit:/tmp/timbu12/repo$ git branch -a
* master
  remotes/origin/HEAD -> origin/master
  remotes/origin/master
bandit30@bandit:/tmp/timbu12/repo$ git tag
secret
bandit30@bandit:/tmp/timbu12/repo$ git show secret
OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt
bandit30@bandit:/tmp/timbu12/repo$
```
## Notas adicionales
## Referencias
