# Bandit Level 8 → Level 9

## Objetivo
The password for the next level is stored in the file **data.txt** and is the only line of text that occurs only once
## Datos de acceso al nivel
```
bandit8
TESKZC0XvTetK0S9xNwm25STk5iWrBvP
```
## Solución
```bash
bandit8@bandit:~$ cat data.txt | sort | uniq -u
EN632PlfYiZbn3PhVK3XOGSlNInNE00t
```
## Notas adicionales
El comando sort ordena la salida (los repetidos).
Uniq cuenta las veces que se repite una salida, tiene varias opciones con -c nos dice cuantas veces se repite cada una, -d nos dice las que se repite, y -u las que no se repite, pero necesita de una salida ordenada, por ello usamos sort.
## Referencias
[Piping and Redirection](https://ryanstutorials.net/linuxtutorial/piping.php)
```bash
sort --help
uniq --help
```