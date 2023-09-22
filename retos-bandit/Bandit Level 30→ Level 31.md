# Bandit Level 30→ Level 31

## Objetivo
There is a git repository at `ssh://bandit30-git@localhost/home/bandit30-git/repo` via the port `2220`. The password for the user `bandit30-git` is the same as for the user `bandit30`.

Clone the repository and find the password for the next level.
## Datos de acceso al nivel
```
bandit30
xbhV3HpNGlTIdnjUrdAlPzc2L6y9EOnS
```
## Solución
```bash
bandit30@bandit:~$ mkdir /tmp/david2003
bandit30@bandit:~$ cd /tmp/david2003
bandit30@bandit:/tmp/david2003$ git clone ssh://bandit30-git@localhost:2220/
home/bandit30-git/repo
Cloning into 'repo'...
Receiving objects: 100% (4/4), done.
bandit30@bandit:/tmp/david2003$ cd repo/
bandit30@bandit:/tmp/david2003/repo$ cat README.md
just an epmty file... muahaha
bandit30@bandit:/tmp/david2003/repo$ git tag
secret
bandit30@bandit:/tmp/david2003/repo$ git show secret
OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt
bandit30@bandit:/tmp/david2003/repo$
```
## Notas adicionales
El comando git tag lista todas las etiquetas en el repositorio, y con git show podemos ver dichas etiquetas.
## Referencias