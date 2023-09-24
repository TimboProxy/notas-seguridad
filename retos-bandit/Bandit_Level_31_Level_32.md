# Bandit Level 31 → Level 32
## Objetivo
There is a git repository at `ssh://bandit31-git@localhost/home/bandit31-git/repo` via the port `2220`. The password for the user `bandit31-git` is the same as for the user `bandit31`.

Clone the repository and find the password for the next level.
## Datos de acceso al nivel
```
ssh bandit31@bandit.labs.overthewire.org -p 2220 
	(comando para iniciar ssh)
contraseña: 
OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt
```
## Solución 
```pwd
bandit31@bandit:~$
bandit31@bandit:~$ cd /tmp/
bandit31@bandit:/tmp$ mkdir proxonitron
bandit31@bandit:/tmp$ cd proxonitron
bandit31@bandit:/tmp/proxonitron$ git clone ssh://bandit31-git@localhost:2220/home/bandit31-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit31/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit31/.ssh/known_hosts).
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit31-git@localhost's password:
remote: Enumerating objects: 4, done.
remote: Counting objects: 100% (4/4), done.
remote: Compressing objects: 100% (3/3), done.
remote: Total 4 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (4/4), done.
bandit31@bandit:/tmp/proxonitron$ ls -la
total 10564
drwxrwxr-x    3 bandit31 bandit31     4096 Sep 23 04:27 .
drwxrwx-wt 4760 root     root     10801152 Sep 23 04:27 ..
drwxrwxr-x    3 bandit31 bandit31     4096 Sep 23 04:27 repo
bandit31@bandit:/tmp/proxonitron$ cd repo
bandit31@bandit:/tmp/proxonitron/repo$ ls -la
total 20
drwxrwxr-x 3 bandit31 bandit31 4096 Sep 23 04:27 .
drwxrwxr-x 3 bandit31 bandit31 4096 Sep 23 04:27 ..
drwxrwxr-x 8 bandit31 bandit31 4096 Sep 23 04:27 .git
-rw-rw-r-- 1 bandit31 bandit31    6 Sep 23 04:27 .gitignore
-rw-rw-r-- 1 bandit31 bandit31  147 Sep 23 04:27 README.md
bandit31@bandit:/tmp/proxonitron/repo$ cat README.md
This time your task is to push a file to the remote repository.

Details:
    File name: key.txt
    Content: 'May I come in?'
    Branch: master

bandit31@bandit:/tmp/proxonitron/repo$ echo "May I come in?" > key.txt
bandit31@bandit:/tmp/proxonitron/repo$ ls -la
total 24
drwxrwxr-x 3 bandit31 bandit31 4096 Sep 23 04:28 .
drwxrwxr-x 3 bandit31 bandit31 4096 Sep 23 04:27 ..
drwxrwxr-x 8 bandit31 bandit31 4096 Sep 23 04:27 .git
-rw-rw-r-- 1 bandit31 bandit31    6 Sep 23 04:27 .gitignore
-rw-rw-r-- 1 bandit31 bandit31   15 Sep 23 04:28 key.txt
-rw-rw-r-- 1 bandit31 bandit31  147 Sep 23 04:27 README.md
bandit31@bandit:/tmp/proxonitron/repo$ cat .gitignore *.txt
*.txt
May I come in?
bandit31@bandit:/tmp/proxonitron/repo$ cat .gitignore
*.txt
bandit31@bandit:/tmp/proxonitron/repo$ rm .gitignore
bandit31@bandit:/tmp/proxonitron/repo$ ls -la
total 20
drwxrwxr-x 3 bandit31 bandit31 4096 Sep 23 04:29 .
drwxrwxr-x 3 bandit31 bandit31 4096 Sep 23 04:27 ..
drwxrwxr-x 8 bandit31 bandit31 4096 Sep 23 04:27 .git
-rw-rw-r-- 1 bandit31 bandit31   15 Sep 23 04:28 key.txt
-rw-rw-r-- 1 bandit31 bandit31  147 Sep 23 04:27 README.md
bandit31@bandit:/tmp/proxonitron/repo$ git add .
bandit31@bandit:/tmp/proxonitron/repo$ git commit -m "Added key.txt"
[master 47ea123] Added key.txt
 2 files changed, 1 insertion(+), 1 deletion(-)
 delete mode 100644 .gitignore
 create mode 100644 key.txt
bandit31@bandit:/tmp/proxonitron/repo$ git push origin master
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit31/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit31/.ssh/known_hosts).
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit31-git@localhost's password:
Permission denied, please try again.
bandit31-git@localhost's password:
Enumerating objects: 4, done.
Counting objects: 100% (4/4), done.
Delta compression using up to 2 threads
Compressing objects: 100% (2/2), done.
Writing objects: 100% (3/3), 288 bytes | 288.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
remote: ### Attempting to validate files... ####
remote:
remote: .oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.
remote:
remote: Well done! Here is the password for the next level:
remote: rmCBvG56y58BXzv98yZGdO7ATVL5dW8y
remote:
remote: .oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.oOo.
remote:
To ssh://localhost:2220/home/bandit31-git/repo
 ! [remote rejected] master -> master (pre-receive hook declined)
error: failed to push some refs to 'ssh://localhost:2220/home/bandit31-git/repo'
bandit31@bandit:/tmp/proxonitron/repo$
```
## Notas adicionales
1. `echo "May I come in?"`: Esto imprime el texto "May I come in?" en la pantalla o en la salida estándar.
    
2. `> key.txt`: Esto redirige la salida del comando anterior hacia un archivo llamado "key.txt". En otras palabras, toma la cadena de texto "May I come in?" generada por el comando `echo` y la guarda en un archivo llamado "key.txt". Si el archivo "key.txt" ya existía, este comando sobrescribirá su contenido con la nueva cadena de texto. Si el archivo no existía, se creará.
3. El comando `cat .gitignore` se utiliza para mostrar el contenido del archivo `.gitignore` en la consola o en la salida estándar. El archivo `.gitignore` es un archivo de configuración comúnmente utilizado en repositorios Git para especificar patrones de archivos y directorios que deben ser ignorados por Git. Estos archivos y directorios ignorados no se incluirán en las confirmaciones (commits) y no se rastrearán en el control de versiones.

Al ejecutar `cat .gitignore`, verás en la pantalla o en la salida estándar los patrones y nombres de archivos y directorios que se han especificado en ese archivo `.gitignore`. Esto es útil para verificar qué archivos y directorios están configurados para ser ignorados en tu repositorio Git y asegurarte de que se estén excluyendo correctamente de las confirmaciones.
El comando `rm .gitignore` se utiliza para eliminar el archivo llamado ".gitignore" en el directorio actual.


## Referencias