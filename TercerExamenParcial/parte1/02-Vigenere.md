# Vigenere

## Objetivo
Can you decrypt this message?Decrypt this [message](https://artifacts.picoctf.net/c/158/cipher.txt) using this key "CYLAB".
## Solución
```bash
┌──(kali㉿kali)-[~/retos/3exa/vigenere]
└─$ wget https://artifacts.picoctf.net/c/158/cipher.txt 
--2023-11-28 13:11:07--  https://artifacts.picoctf.net/c/158/cipher.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 18.154.144.104, 18.154.144.85, 18.154.144.107, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|18.154.144.104|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 43 [application/octet-stream]
Saving to: ‘cipher.txt’

cipher.txt                                                 100%[========================================================================================================================================>]      43  --.-KB/s    in 0s      

2023-11-28 13:11:08 (70.5 MB/s) - ‘cipher.txt’ saved [43/43]

┌──(kali㉿kali)-[~/retos/3exa/vigenere]
└─$ cat cipher.txt      
rgnoDVD{O0NU_WQ3_G1G3O3T3_A1AH3S_cc82272b}

https://www.dcode.fr/cifrado-

picoCTF{D0NT_US3_V1G3N3R3_C1PH3R_ae82272q}
```
## Notas adicionales

## Referencias
