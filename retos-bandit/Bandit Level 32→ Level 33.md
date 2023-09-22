# Bandit Level 32→ Level 33

## Objetivo
After all this `git` stuff its time for another escape. Good luck!
## Datos de acceso al nivel
```
bandit32
rmCBvG56y58BXzv98yZGdO7ATVL5dW8y
```
## Solución
```bash
WELCOME TO THE UPPERCASE SHELL
>> ls
sh: 1: LS: Permission denied
>> $0
$ ls -la
total 36
drwxr-xr-x  2 root     root      4096 Apr 23 18:04 .
drwxr-xr-x 70 root     root      4096 Apr 23 18:05 ..
-rw-r--r--  1 root     root       220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root     root      3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root     root       807 Jan  6  2022 .profile
-rwsr-x---  1 bandit33 bandit32 15128 Apr 23 18:04 uppershell
$ cat /etc/bandit_pass/bandit33
odHo63fHiFqcWWJG9rLiLDtPm45KzUKy
$
```
## Notas adicionales
Al entrar a este reto nos muestran una shell donde no hay ciertos permisos, con lo cual ingresamos en $0 para poder ejecutar comandos, hacemos un ls -la, y desde esta terminal podemos ver la contraseña del siguiente nivel.
## Referencias