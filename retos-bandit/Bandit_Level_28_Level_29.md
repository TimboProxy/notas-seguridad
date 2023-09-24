# Bandit Level 28 → Level 29
## Objetivo
There is a git repository at `ssh://bandit28-git@localhost/home/bandit28-git/repo` via the port `2220`. The password for the user `bandit28-git` is the same as for the user `bandit28`.

Clone the repository and find the password for the next level.
## Datos de acceso al nivel
```
ssh bandit28@bandit.labs.overthewire.org -p 2220 
	(comando para iniciar ssh)
contraseña: 
AVanL161y9rsbcJIsFHuw35rjaOM19nR
```
## Solución 
```pwd
bandit28@bandit:~$
bandit28@bandit:~$ mktemp -d
/tmp/tmp.yk1piEyyud
bandit28@bandit:~$ cd /tmp/tmp.duyyEip1ky 
bandit28@bandit:/tmp/tmp.duyyEip1ky$ git clone ssh://bandit28-git@localhost:2220/home/bandit28-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit28/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit28/.ssh/known_hosts).
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit28-git@localhost's password:
remote: Enumerating objects: 9, done.
remote: Counting objects: 100% (9/9), done.
remote: Compressing objects: 100% (6/6), done.
remote: Total 9 (delta 2), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (9/9), done.
Resolving deltas: 100% (2/2), done.
bandit28@bandit:/tmp/tmp.duyyEip1ky$ ls -la
total 10564
drwx------    3 bandit28 bandit28     4096 Sep 23 03:48 .
drwxrwx-wt 4737 root     root     10801152 Sep 23 03:48 ..
drwxrwxr-x    3 bandit28 bandit28     4096 Sep 23 03:48 repo
bandit28@bandit:/tmp/tmp.duyyEip1ky$ cd repo
bandit28@bandit:/tmp/tmp.duyyEip1ky/repo$ ls
README.md
bandit28@bandit:/tmp/tmp.duyyEip1ky/repo$ cat README.md
# Bandit Notes
Some notes for level29 of bandit.

## credentials

- username: bandit29
- password: xxxxxxxxxx

bandit28@bandit:/tmp/tmp.duyyEip1ky/repo$ git log
commit 899ba88df296331cc01f30d022c006775d467f28 (HEAD -> master, origin/master, origin/HEAD)
Author: Morla Porla <morla@overthewire.org>
Date:   Sun Apr 23 18:04:39 2023 +0000

    fix info leak

commit abcff758fa6343a0d002a1c0add1ad8c71b88534
Author: Morla Porla <morla@overthewire.org>
Date:   Sun Apr 23 18:04:39 2023 +0000

    add missing data

commit c0a8c3cf093fba65f4ee0e1fe2a530b799508c78
Author: Ben Dover <noone@overthewire.org>
Date:   Sun Apr 23 18:04:39 2023 +0000

    initial commit of README.md
bandit28@bandit:/tmp/tmp.duyyEip1ky/repo$ git checkout 899ba88df296331cc01f30d022c006775d467f28
Note: switching to '899ba88df296331cc01f30d022c006775d467f28'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at 899ba88 fix info leak
bandit28@bandit:/tmp/tmp.duyyEip1ky/repo$ cat README.md
# Bandit Notes
Some notes for level29 of bandit.

## credentials

- username: bandit29
- password: xxxxxxxxxx

bandit28@bandit:/tmp/tmp.duyyEip1ky/repo$ git checkout c0a8c3cf093fba65f4ee0e1fe2a530b799508c78
Previous HEAD position was 899ba88 fix info leak
HEAD is now at c0a8c3c initial commit of README.md
bandit28@bandit:/tmp/tmp.duyyEip1ky/repo$ cat README.md
# Bandit Notes
Some notes for level29 of bandit.

## credentials

- username: bandit29
- password: <TBD>

bandit28@bandit:/tmp/tmp.duyyEip1ky/repo$ git checkout abcff758fa6343a0d002a1c0add1ad8c71b88534
Previous HEAD position was c0a8c3c initial commit of README.md
HEAD is now at abcff75 add missing data
bandit28@bandit:/tmp/tmp.duyyEip1ky/repo$ cat readme.md
cat: readme.md: No such file or directory
bandit28@bandit:/tmp/tmp.duyyEip1ky/repo$ cat README.md
# Bandit Notes
Some notes for level29 of bandit.

## credentials

- username: bandit29
- password: tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S

bandit28@bandit:/tmp/tmp.duyyEip1ky/repo$
```
## Notas adicionales
`git log` es un comando utilizado en Git para ver el historial de confirmaciones (commits) en un repositorio. Proporciona una lista detallada de todas las confirmaciones que han ocurrido en la rama actual, en orden cronológico inverso, es decir, muestra las confirmaciones más recientes primero.

El comando `git log` muestra información importante sobre cada confirmación, como:

1. **Hash del Commit**: Un número único que identifica cada confirmación de forma única.
2. **Autor**: El nombre y la dirección de correo electrónico del autor de la confirmación.
3. **Fecha**: La fecha y la hora en que se realizó la confirmación.
4. **Mensaje de Confirmación**: El mensaje descriptivo proporcionado por el autor al realizar la confirmación

## Referencias
