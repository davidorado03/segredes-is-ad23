# Bandit Level 10 → Level 11

## Objetivo
The password for the next level is stored in the file **data.txt**, which contains base64 encoded data
## Datos de acceso al nivel
```
bandit10
G7w8LIi6J3kTb8A7j9LgrywtEUlyyp6s
```
## Solución
```bash
Forma 1
bandit10@bandit:~$ ls
data.txt
bandit10@bandit:~$ cat data.txt
VGhlIHBhc3N3b3JkIGlzIElGdWt3S0dzRlc4TU9xM0lSRnFyeEUxaHhUTkViVVBSCg==
bandit10@bandit:~$
bandit10@bandit:~$ echo "hola mundo"
hola mundo
bandit10@bandit:~$ echo "hola mundo" | base64
aG9sYSBtdW5kbwo=
bandit10@bandit:~$ echo -n aG9sYSBtdW5kbwo= | base64 -d
hola mundo
bandit10@bandit:~$ base64 -d data.txt
The password is IFukwKGsFW8MOq3IRFqrxE1hxTNEbUPR
bandit10@bandit:~$
bandit10@bandit:~$ cat data.txt
VGhlIHBhc3N3b3JkIGlzIDZ6UGV6aUxkUjJSS05kTllGTmI2blZDS3pwaGxYSEJNCg==
bandit10@bandit:~$ cat data.txt | base64 -d
The password is 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM

Forma 2 
bandit10@bandit:~$ python3
Python 3.10.6 (main, Mar 10 2023, 10:55:28) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> datos = open("data.txt").read()
>>> import base64
>>> base64.b64decode(datos)
b'The password is 6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM\n'
```
## Notas adicionales
Base64 es un comando que permite convertir cadenas de texto a código ASCII, además de hacerlo al inverso, de ASCII a cadenas de texto (con la opción -d), siendo que cuando tenemos "=" es que hizo padding con el fin de completar los 8 bits, en adición también opera sobre archivos.
Para mostrar un mensaje de forma codificada podemos usar echo o cat (si es un archivo) y luego Base64.
Lo anterior se puede hacer con python, con la librería base64, primero accedemos a python3, leemos el archivo data.txt y lo almacenamos en datos, se importa base64 y decodificamos datos, dándonos la respuesta, esto es útil ya que un mismo mensaje se puede codificar varias veces, si creamos un script que decodifique la misma cantidad podemos tener la respuesta antes.
## Referencias
[Base64 on Wikipedia](https://en.wikipedia.org/wiki/Base64)