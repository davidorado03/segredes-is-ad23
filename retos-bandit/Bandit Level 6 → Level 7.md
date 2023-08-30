# Bandit Level 6 → Level 7

## Objetivo
The password for the next level is stored **somewhere on the server** and has all of the following properties:

- owned by user bandit7
- owned by group bandit6
- 33 bytes in size
## Datos de acceso al nivel
```
bandit6
P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
```
## Solución
```bash
bandit6@bandit:~$ find / -size 33c -user bandit7 -group bandit6
2>/dev/null
/var/lib/dpkg/info/bandit7.password
bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S
```

## Notas adicionales
El comando -user especifica el usaurio al que pertenece el archivo, - group especifica el grupo al que pertenece el archivo, y 2>/dev/null elimina los mensajes de error en cualquier comando.
## Referencias
```bash
man find
```