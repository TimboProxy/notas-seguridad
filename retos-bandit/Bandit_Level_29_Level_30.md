# Bandit Level 29 → Level 30
## Objetivo
There is a git repository at `ssh://bandit29-git@localhost/home/bandit29-git/repo` via the port `2220`. The password for the user `bandit29-git` is the same as for the user `bandit29`.

Clone the repository and find the password for the next level.
## Datos de acceso al nivel
```
ssh bandit29@bandit.labs.overthewire.org -p 2220 
	(comando para iniciar ssh)
contraseña: 
tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S
```
## Solución 
```pwd
bandit29@bandit:~$
bandit29@bandit:~$ cd /tmp/
bandit29@bandit:/tmp$ mkdir tb15 
bandit29@bandit:/tmp$ cd tb15
bandit29@bandit:/tmp/tb15$ git clone ssh://bandit29-git@localhost:2220/home/bandit29-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit29/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit29/.ssh/known_hosts).
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit29-git@localhost's password:
remote: Enumerating objects: 16, done.
remote: Counting objects: 100% (16/16), done.
remote: Compressing objects: 100% (11/11), done.
remote: Total 16 (delta 2), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (16/16), done.
Resolving deltas: 100% (2/2), done.
bandit29@bandit:/tmp/tb15$ ls -la
total 10564
drwxrwxr-x    3 bandit29 bandit29     4096 Sep 23 04:00 .
drwxrwx-wt 4743 root     root     10801152 Sep 23 04:00 ..
drwxrwxr-x    3 bandit29 bandit29     4096 Sep 23 04:00 repo
bandit29@bandit:/tmp/tb15$ cd repo
bandit29@bandit:/tmp/tb15/repo$ ls
README.md
bandit29@bandit:/tmp/tb15/repo$ cat README.md
# Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit30
- password: <no passwords in production!>

bandit29@bandit:/tmp/tb15/repo$ git branch -a
* master
  remotes/origin/HEAD -> origin/master
  remotes/origin/dev
  remotes/origin/master
  remotes/origin/sploits-dev
bandit29@bandit:/tmp/tb15/repo$ git checkout remotes/origin/dev
Note: switching to 'remotes/origin/dev'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at 13e7356 add data needed for development
bandit29@bandit:/tmp/tb15/repo$ ls -la
total 20
drwxrwxr-x 4 bandit29 bandit29 4096 Sep 23 04:01 .
drwxrwxr-x 3 bandit29 bandit29 4096 Sep 23 04:00 ..
drwxrwxr-x 2 bandit29 bandit29 4096 Sep 23 04:01 code
drwxrwxr-x 8 bandit29 bandit29 4096 Sep 23 04:01 .git
-rw-rw-r-- 1 bandit29 bandit29  134 Sep 23 04:01 README.md
bandit29@bandit:/tmp/tb15/repo$ cat README.md
# Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit30
- password: xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS

bandit29@bandit:/tmp/tb15/repo$
```

## Notas adicionales
`git checkout remotes/origin/dev` se utiliza para cambiar a una rama remota llamada "dev" que está almacenada en el repositorio remoto denominado "origin". Sin embargo, es importante tener en cuenta que no puedes cambiar directamente a una rama remota con `git checkout` en la mayoría de los casos, ya que las ramas remotas son solo referencias a estados remotos del repositorio y no son directamente editables.
## Referencias