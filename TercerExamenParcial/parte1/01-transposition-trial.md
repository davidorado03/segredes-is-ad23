# transposition-trial

## Objetivo
Our data got corrupted on the way here. Luckily, nothing got replaced, but every block of 3 got scrambled around! The first word seems to be three letters long, maybe you can use that to recover the rest of the message.Download the corrupted message [here](https://artifacts.picoctf.net/c/193/message.txt).
## Solución
```bash
┌──(kali㉿kali)-[~/retos/3exa]
└─$ mkdir transposition-trial
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/retos/3exa]
└─$ cd transposition-trial 
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/retos/3exa/transposition-trial]
└─$ wget https://artifacts.picoctf.net/c/193/message.txt  
--2023-11-28 12:55:06--  https://artifacts.picoctf.net/c/193/message.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 18.154.144.104, 18.154.144.85, 18.154.144.107, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|18.154.144.104|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 54 [application/octet-stream]
Saving to: ‘message.txt’

message.txt                                                100%[========================================================================================================================================>]      54  --.-KB/s    in 0s      

2023-11-28 12:55:07 (87.0 MB/s) - ‘message.txt’ saved [54/54]

┌──(kali㉿kali)-[~/retos/3exa/transposition-trial]
└─$ cat message.txt                                     
heTfl g as iicpCTo{7F4NRP051N5_16_35P3X51N3_V9AAB1F8}7                                                                    
┌──(kali㉿kali)-[~/retos/3exa/transposition-trial]
└─$ touch transposition.py
┌──(kali㉿kali)-[~/retos/3exa/transposition-trial]
└─$ sudo nano transposition.py 

┌──(kali㉿kali)-[~/retos/3exa/transposition-trial]
└─$ cat transposition.py 
MESSAGE = "heTfl g as iicpCTo{7F4NRP051N5_16_35P3X51N3_V9AAB1F8}7"

FLAG = ""

for i in range(0, len(MESSAGE), 3):
        FLAG += MESSAGE[i + 2] + MESSAGE[i:i + 2]
print(FLAG)

[sudo] password for kali: 
┌──(kali㉿kali)-[~/retos/3exa/transposition-trial]
└─$ python3 transposition.py         
The flag is picoCTF{7R4N5P051N6_15_3XP3N51V3_A9AFB178}

```
## Notas adicionales

## Referencias
