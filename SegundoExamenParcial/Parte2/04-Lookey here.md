# Lookey here

## Objetivo
Attackers have hidden information in a very large mass of data in the past, maybe they are still doing it.Download the data [here](https://artifacts.picoctf.net/c/124/anthem.flag.txt).
## Solución
```bash
┌──(kali㉿kali)-[~/2Exa/2/lookey]
└─$ wget https://artifacts.picoctf.net/c/124/anthem.flag.txt
--2023-11-03 19:10:24--  https://artifacts.picoctf.net/c/124/anthem.flag.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 18.160.124.38, 18.160.124.34, 18.160.124.108, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|18.160.124.38|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 108668 (106K) [application/octet-stream]
Saving to: ‘anthem.flag.txt’

anthem.flag.txt                                            100%[=======================================================================================================================================>] 106.12K  --.-KB/s    in 0.1s    

2023-11-03 19:10:24 (863 KB/s) - ‘anthem.flag.txt’ saved [108668/108668]

                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/2Exa/2/lookey]
└─$ strings flag.txt | grep pico
strings: 'flag.txt': No such file
                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/2Exa/2/lookey]
└─$ strings anthem.flag.txt | grep pico
      we think that the men of picoCTF{gr3p_15_@w3s0m3_4c479940}
                                                                    
```
## Notas adicionales

## Referencias