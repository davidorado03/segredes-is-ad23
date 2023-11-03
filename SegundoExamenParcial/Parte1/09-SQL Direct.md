# SQL Direct

## Objetivo
Connect to this PostgreSQL server and find the flag!

Additional details will be available after launching your challenge instance.
## Solución
```bash
┌──(kali㉿kali)-[~]
└─$ psql -h saturn.picoctf.net -p 52936 -U postgres pico
Password for user postgres: 
psql (15.3 (Debian 15.3-0+deb12u1), server 15.2 (Debian 15.2-1.pgdg110+1))
Type "help" for help.

pico=# help
You are using psql, the command-line interface to PostgreSQL.
Type:  \copyright for distribution terms
       \h for help with SQL commands
       \? for help with psql commands
       \g or terminate with semicolon to execute query
       \q to quit
pico=# \l
                                                List of databases
   Name    |  Owner   | Encoding |  Collate   |   Ctype    | ICU Locale | Locale Provider |   Access privileges   
-----------+----------+----------+------------+------------+------------+-----------------+-----------------------
 pico      | postgres | UTF8     | en_US.utf8 | en_US.utf8 |            | libc            | 
 postgres  | postgres | UTF8     | en_US.utf8 | en_US.utf8 |            | libc            | 
 template0 | postgres | UTF8     | en_US.utf8 | en_US.utf8 |            | libc            | =c/postgres          +
           |          |          |            |            |            |                 | postgres=CTc/postgres
 template1 | postgres | UTF8     | en_US.utf8 | en_US.utf8 |            | libc            | =c/postgres          +
           |          |          |            |            |            |                 | postgres=CTc/postgres
(4 rows)

pico=# select * from pico;
ERROR:  relation "pico" does not exist
LINE 1: select * from pico;
                      ^
pico=# \c pico
psql (15.3 (Debian 15.3-0+deb12u1), server 15.2 (Debian 15.2-1.pgdg110+1))
You are now connected to database "pico" as user "postgres".
pico=# select * from pico;
ERROR:  relation "pico" does not exist
LINE 1: select * from pico;
                      ^
pico=# \dt
         List of relations
 Schema | Name  | Type  |  Owner   
--------+-------+-------+----------
 public | flags | table | postgres
(1 row)

pico=# select * from flags;
 id | firstname | lastname  |                address                 
----+-----------+-----------+----------------------------------------
  1 | Luke      | Skywalker | picoCTF{L3arN_S0m3_5qL_t0d4Y_21c94904}
  2 | Leia      | Organa    | Alderaan
  3 | Han       | Solo      | Corellia
(3 rows)

```
## Notas adicionales

## Referencias