# Level X

## Objetivo
Can you invoke help flags for a tool or binary? [This program](https://mercury.picoctf.net/static/b28b6021d6040b086c2226ebeb913bc2/warm) has extraordinarily helpful information...
## Solución
```bash
davidorado-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/b28b6021d6040b086c2226ebeb913bc2/warm
--2023-09-25 16:39:49--  https://mercury.picoctf.net/static/b28b6021d6040b086c2226ebeb913bc2/warm
2023-09-25 16:39:49 (74.5 MB/s) - 'warm' saved [10936/10936]

davidorado-picoctf@webshell:~$ ls -la
total 40
drwxr-xr-x 2 davidorado-picoctf davidorado-picoctf   117 Sep 25 16:39 .
drwxr-xr-x 3 root               root                  32 Sep 25 16:26 ..
-rw-r--r-- 1 davidorado-picoctf davidorado-picoctf   220 Sep 25 16:26 .bash_logout
-rw-r--r-- 1 davidorado-picoctf davidorado-picoctf  3771 Sep 25 16:26 .bashrc
-rw-r--r-- 1 davidorado-picoctf davidorado-picoctf   807 Sep 25 16:26 .profile
-rw-rw-r-- 1 davidorado-picoctf davidorado-picoctf   167 Sep 25 16:34 .wget-hsts
-rw-r--r-- 1 root               root                4443 Sep 25 16:26 README.txt
-rw-rw-r-- 1 davidorado-picoctf davidorado-picoctf    34 Mar 16  2021 flag
-rw-rw-r-- 1 davidorado-picoctf davidorado-picoctf 10936 Mar 16  2021 warm
davidorado-picoctf@webshell:~$ ./warm
-bash: ./warm: Permission denied
davidorado-picoctf@webshell:~$ chmod +x warm
davidorado-picoctf@webshell:~$ ./warm
Hello user! Pass me a -h to learn what I can do!
davidorado-picoctf@webshell:~$ ./warm -h
Oh, help? I actually don't do much, but I do have this flag here: picoCTF{b1scu1ts_4nd_gr4vy_d6969390}
```
## Notas adicionales

## Referencias
