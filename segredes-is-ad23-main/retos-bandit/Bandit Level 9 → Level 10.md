# Bandit Level 9 → Level 10

## Objetivo
The password for the next level is stored in the file **data.txt** in one of the few human-readable strings, preceded by several ‘=’ characters.
## Datos de acceso al nivel
```
bandit9
EN632PlfYiZbn3PhVK3XOGSlNInNE00t
```
## Solución
```bash
bandit9@bandit:~$ cat data.txt | strings -n 12
4========== the#
========== password
========== is
========== G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
```
## Notas adicionales
Strings es un comando que muestra la salida con strings, y con -n limitamos el numero de caracteres a un minimo, en este caso 12, entonces mostramos data.txt y filtramos a salida que solo muestre strings.
## Referencias
```bash
strings --help
```