# Bandit Level 11 → Level 12

## Objetivo
The password for the next level is stored in the file **data.txt**, where all lowercase (a-z) and uppercase (A-Z) letters have been rotated by 13 positions
## Datos de acceso al nivel
```
bandit11
6zPeziLdR2RKNdNYFNb6nVCKzphlXHBM
```
## Solución
```bash
bandit11@bandit:~$ ls
data.txt
bandit11@bandit:~$ cat data.txt
Gur cnffjbeq vf WIAOOSFzMjXXBC0KoSKBbJ8puQm5lIEi
bandit11@bandit:~$ cat data.txt | tr [a-zA-Z] [n-za-mN-ZA-M]
The password is JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv

Con python
bandit11@bandit:~$ python3
Python 3.10.6 (main, Nov 14 2022, 16:10:14) [GCC 11.3.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> import codecs
>>> codecs.decode('Gur cnffjbeq vf WIAOOSFzMjXXBC0KoSKBbJ8puQm5lIEi','rot13')
'The password is JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv'
```
## Notas adicionales
Rot13 es un algoritmo de codificación en el que las letras se mueven 13 veces de posición conforme al abecedario, es decir una letra a se convierte en n, si fuera una z se convierte en m, con lo cual no es muy seguro, pues fácilmente es reversible.
https://gchq.github.io/CyberChef/
° En está página podemos introducir cadenas de texto codificadas con el fin de descodificarlas, siendo otra forma de resolver el reto.
° El comando tr nos permite transformar cadenas, en este caso la n se transforma en z, la a en m, recorriendo así 13 veces las posiciones de las letras, especificando que también lo hace con las mayúsculas.
° También se puede hacer con python, se importe codecs, se dice que es lo que queremos descodificar y con que algoritmo lo queremos hacer, en este caso rot13
## Referencias
[Rot13 on Wikipedia](https://en.wikipedia.org/wiki/Rot13)