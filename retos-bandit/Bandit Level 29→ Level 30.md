# Bandit Level 29→ Level 30

## Objetivo
There is a git repository at `ssh://bandit29-git@localhost/home/bandit29-git/repo` via the port `2220`. The password for the user `bandit29-git` is the same as for the user `bandit29`.

Clone the repository and find the password for the next level.
## Datos de acceso al nivel
```
bandit29
tQKvmcwNYcFS6vmPHIUSI3ShmsrQZK8S
```
## Solución
```bash
bandit29@bandit:~$ mkdir /tmp/David2003
bandit29@bandit:~$ cd /tmp/David2003
bandit29@bandit:/tmp/David2003$ git clone ssh://bandit29-git@localhost:2220/home/bandit29-git/repo
Cloning into 'repo'...
Resolving deltas: 100% (2/2), done.
bandit29@bandit:/tmp/David2003$ ls repo
bandit29@bandit:/tmp/David2003$ cd repo
bandit29@bandit:/tmp/David2003/repo$ cat README.md
# Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit30
- password: <no passwords in production!>

bandit29@bandit:/tmp/David2003/repo$ git branch -r
  origin/HEAD -> origin/master
  origin/dev
  origin/master
  origin/sploits-dev
bandit29@bandit:/tmp/David2003/repo$ git checkout dev
Branch 'dev' set up to track remote branch 'dev' from 'origin'.
Switched to a new branch 'dev'
bandit29@bandit:/tmp/David2003/repo$ cat README.md
# Bandit Notes
Some notes for bandit30 of bandit.

## credentials

- username: bandit30
- password: xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS
```
## Notas adicionales
En este reto clonamos repositorio, en README deberíamos tener la contraseña pero no es así, nos dice que no hay nada en producción, por ello podemos explorar otras ramas, si hacemos git checkout a dev (una rama), ya tenemos la contraseña para el siguiente nivel.
## Referencias