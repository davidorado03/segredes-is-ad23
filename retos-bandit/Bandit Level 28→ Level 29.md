# Bandit Level 28→ Level 29

## Objetivo
There is a git repository at `ssh://bandit28-git@localhost/home/bandit28-git/repo` via the port `2220`. The password for the user `bandit28-git` is the same as for the user `bandit28`.

Clone the repository and find the password for the next level.
## Datos de acceso al nivel
```
bandit28
AVanL161y9rsbcJIsFHuw35rjaOM19nR
```
## Solución
```bash
bandit28@bandit:~$ mkdir /tmp/repoDavid2003
bandit28@bandit:~$ cd /tmp/repoDavid2003
bandit28@bandit:/tmp/repoDavid2003$ git clone ssh://bandit28-git@localhost:2220/home/bandit28-git/repo
Cloning into 'repo'...
Resolving deltas: 100% (2/2), done.
bandit28@bandit:/tmp/repoDavid2003$ cd repo/
bandit28@bandit:/tmp/repoDavid2003/repo$ ls
README.md
bandit28@bandit:/tmp/repoDavid2003/repo$ cat README.md
# Bandit Notes
Some notes for level29 of bandit.

## credentials

- username: bandit29
- password: xxxxxxxxxx

bandit28@bandit:/tmp/repoDavid2003/repo$ git log
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
bandit28@bandit:/tmp/repoDavid2003/repo$ git checkout abcff758fa6343a0d002a1c0add1ad8c71b88534
Note: switching to 'abcff758fa6343a0d002a1c0add1ad8c71b88534'.

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

Turn off this advice by setting config variable advice.detachedHead to false

HEAD is now at abcff75 add missing data
bandit28@bandit:/tmp/repoDavid2003/repo$ cat README.md
# Bandit Notes
Some notes for level29 of bandit.

## credentials

- username: bandit29
- password: tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S
```
## Notas adicionales
En este reto tenemos que clonar un repositorio, dentro de este tenemos un README el cual debería contener la contraseña, pero hay datos faltantes, por lo cual tenemos que hacer un git log, este comandos nos dice todos los commits realizados, en uno de ellos dice que se agrega la información faltante, por ello hacemos un git checkout a ese commit, obteniendo la contraseña en README.
## Referencias