# Bandit Level 20 → Level 21

## Objetivo
There is a setuid binary in the homedirectory that does the following: it makes a connection to localhost on the port you specify as a commandline argument. It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). If the password is correct, it will transmit the password for the next level (bandit21).

**NOTE:** Try connecting to your own network daemon to see if it works as you think
## Datos de acceso al nivel
```
bandit20
VxCazJaVykI6W36BkBU0mJTCM8rR95XT
```
## Solución
```bash
# Terminal 1
bandit20@bandit:~$ nc -lp 31337 < /etc/bandit_pass/bandit20
gE269g2h3mw3pwgrj0Ha9Uoqen1c9DGr

# Terminal 2
bandit20@bandit:~$ ./suconnect 31337
Read: GbKksEFF4yrVs6il55v6gwY5aVje5f0j
Password matches, sending next password

```
## Notas adicionales
En este caso tenemos que la solución se otorga mediante un setuid siendo que establecemos un oyente (mediante netcad) y alguien que se conecta, cuando el segundo ingresa la contraseña del anterior nivel en el oyente aparece la del siguiente nivel.
## Referencias