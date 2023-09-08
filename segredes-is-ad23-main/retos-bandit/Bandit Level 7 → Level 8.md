# Bandit Level 7 → Level 8

## Objetivo
The password for the next level is stored in the file **data.txt** next to the word **millionth**
## Datos de acceso al nivel
```
bandit7
z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S
```
## Solución
```bash
bandit7@bandit:~$ grep millionth data.txt
millionth       TESKZC0XvTetK0S9xNwm25STk5iWrBvP
```
## Notas adicionales
El comando grep nos ayuda a buscar por patrones, en este caso buscamos el patron millionth en el archivo data.txt
## Referencias
```bash
grp --help
```