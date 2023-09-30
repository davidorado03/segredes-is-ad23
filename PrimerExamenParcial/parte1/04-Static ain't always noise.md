# Static ain't always noise

## Objetivo
Can you look at the data in this binary: [static](https://mercury.picoctf.net/static/ec4dbd8898ade34e1d60d5b70c1b8c8c/static)? This [BASH script](https://mercury.picoctf.net/static/ec4dbd8898ade34e1d60d5b70c1b8c8c/ltdis.sh) might help!
## Solución
```bash
davidorado-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/ec4dbd8898ade34e1d60d5b70c1b8c8c/static  
2023-09-25 17:07:35 (207 MB/s) - 'static' saved [8376/8376]
davidorado-picoctf@webshell:~$ wget https://mercury.picoctf.net/static/ec4dbd8898ade34e1d60d5b70c1b8c8c/ltdis.sh
--2023-09-25 17:08:19--  https://mercury.picoctf.net/static/ec4dbd8898ade34e1d60d5b70c1b8c8c/ltdis.sh    
2023-09-25 17:08:19 (301 MB/s) - 'ltdis.sh' saved [785/785]
davidorado-picoctf@webshell:~$ file static
static: ELF 64-bit LSB pie executable, x86-64, version 1 (SYSV), dynamically linked, interpreter /lib64/ld-linux-x86-64.so.2, for GNU/Linux 3.2.0, BuildID[sha1]=639391a8b15c579d69659462d3c935fa61693f17, not stripped
davidorado-picoctf@webshell:~$ chmod +x static
davidorado-picoctf@webshell:~$ ./stt
-bash: ./stt: No such file or directory
davidorado-picoctf@webshell:~$ ./static
Oh hai! Wait what? A flag? Yes, it's around here somewhere!
davidorado-picoctf@webshell:~$ strings static | grep pico
picoCTF{d15a5m_t34s3r_98d35619}
```
## Notas adicionales

## Referencias