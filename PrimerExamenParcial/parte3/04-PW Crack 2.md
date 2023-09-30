# PW Crack 2
## Objetivo
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/14/level2.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/14/level2.flag.txt.enc) in the same directory too.
## Solución
```bash
davidorado-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/14/level2.py
--2023-09-27 17:13:15--
2023-09-27 17:13:15 (229 MB/s) - 'level2.py' saved [914/914]

davidorado-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/14/level2.flag.txt.enc
--2023-09-27 17:13:30--
2023-09-27 17:13:30 (10.6 MB/s) - 'level2.flag.txt.enc' saved [31/31]

davidorado-picoctf@webshell:~$ nano level2.py
davidorado-picoctf@webshell:~$ python 
.local/    .ssh/      level2.py  
davidorado-picoctf@webshell:~$ python level2.py 
Please enter correct password for flag: 4ec9
Welcome back... your flag, user:
picoCTF{tr45h_51ng1ng_9701e681}
```
## Notas adicionales
La contraseña estaba encriptada se desencripta y es 4ec9
## Referencias