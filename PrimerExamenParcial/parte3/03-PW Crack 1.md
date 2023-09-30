# PW Crack 1

## Objetivo
Can you crack the password to get the flag?Download the password checker [here](https://artifacts.picoctf.net/c/12/level1.py) and you'll need the encrypted [flag](https://artifacts.picoctf.net/c/12/level1.flag.txt.enc) in the same directory too.
## Solución
```bash
davidorado-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/12/level1.py
--2023-09-27 17:08:08--  
2023-09-27 17:08:08 (358 MB/s) - 'level1.py' saved [876/876]

davidorado-picoctf@webshell:~$ wget https://artifacts.picoctf.net/c/12/level1.flag.txt.enc
--2023-09-27 17:08:46--  
2023-09-27 17:08:46 (10.6 MB/s) - 'level1.flag.txt.enc' saved [30/30]

davidorado-picoctf@webshell:~$ nano level1.py 
davidorado-picoctf@webshell:~$ python level1.py 
Please enter correct password for flag: 8713    
Welcome back... your flag, user:
picoCTF{545h_r1ng1ng_1b2fd683}
```
## Notas adicionales

## Referencias