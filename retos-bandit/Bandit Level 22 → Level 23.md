# Bandit Level 22 → Level 23

## Objetivo
A program is running automatically at regular intervals from **cron**, the time-based job scheduler. Look in **/etc/cron.d/** for the configuration and see what command is being executed.

**NOTE:** Looking at shell scripts written by other people is a very useful skill. The script for this level is intentionally made easy to read. If you are having problems understanding what it does, try executing it to see the debug information it prints.
## Datos de acceso al nivel
```
bandit22
WdDozAdTM2z9DiFEQ2mGlwngMfj4EZff
```
## Solución
```bash
bandit22@bandit:~$ ls /etc/cron.d
cronjob_bandit15_root  cronjob_bandit23       e2scrub_all
cronjob_bandit17_root  cronjob_bandit24       otw-tmp-dir
cronjob_bandit22       cronjob_bandit25_root  sysstat
bandit22@bandit:~$ cat /etc/cron.d/cronjob_bandit23
@reboot bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
* * * * * bandit23 /usr/bin/cronjob_bandit23.sh  &> /dev/null
bandit22@bandit:~$ cat /usr/bin/cronjob_bandit23.sh
#!/bin/bash

myname=$(whoami)
mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)

echo "Copying passwordfile /etc/bandit_pass/$myname to /tmp/$mytarget"

cat /etc/bandit_pass/$myname > /tmp/$mytarget
bandit22@bandit:~$ myname=bandit23
bandit22@bandit:~$ echo $bandit23

bandit22@bandit:~$ echo $myname
bandit23
bandit22@bandit:~$ mytarget=$(echo I am user $myname | md5sum | cut -d ' ' -f 1)
bandit22@bandit:~$ echo $mytarget
8ca319486bfbbc3663ea0fbe81326349
bandit22@bandit:~$ cat /tmp/8ca319486bfbbc3663ea0fbe81326349
QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G
bandit22@bandit:~$ cat /tmp/$mytarget
QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G
```
## Notas adicionales
En este reto tenemos un programa que se ejecuta en cron, siempre cada minuto, con lo cual analizamos este programa siendo un script, el cual debería ejecutar bandit23, pero podemos emularlo siendo el 22, modificamos la variable myname a bandit23, luego en mytarget guardamos el texto I am a user con la variable myname y usamos md5sum que es un hash, con lo cual nos da la localización de nuestra contraseña.
## Referencias
