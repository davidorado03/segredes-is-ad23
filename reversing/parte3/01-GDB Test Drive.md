# GDB Test Drive

## Objetivo
Can you get the flag?Download this [binary](https://artifacts.picoctf.net/c/87/gdbme).Here's the test drive instructions:

- `$ chmod +x gdbme`
- `$ gdb gdbme`
- `(gdb) layout asm`
- `(gdb) break *(main+99)`
- `(gdb) run`
- `(gdb) jump *(main+104)`
## Solución
```bash
┌──(kali㉿kali)-[~/retos/reversing/parte3/GDB-Test-Drive]
└─$ wget https://artifacts.picoctf.net/c/87/gdbme         
--2023-11-22 13:30:18--  https://artifacts.picoctf.net/c/87/gdbme
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 18.154.144.104, 18.154.144.85, 18.154.144.107, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|18.154.144.104|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 17048 (17K) [application/octet-stream]
Saving to: ‘gdbme’

gdbme                                                      100%[========================================================================================================================================>]  16.65K  --.-KB/s    in 0.001s  

2023-11-22 13:30:20 (12.7 MB/s) - ‘gdbme’ saved [17048/17048]
                                                               
┌──(kali㉿kali)-[~/retos/reversing/parte3/GDB-Test-Drive]
└─$ chmod +x gdbme   
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/retos/reversing/parte3/GDB-Test-Drive]
└─$ gdb gdbme     
GNU gdb (Debian 13.2-1) 13.2
Copyright (C) 2023 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.
Type "show copying" and "show warranty" for details.
This GDB was configured as "x86_64-linux-gnu".
Type "show configuration" for configuration details.
For bug reporting instructions, please see:
<https://www.gnu.org/software/gdb/bugs/>.
Find the GDB manual and other documentation resources online at:
    <http://www.gnu.org/software/gdb/documentation/>.

For help, type "help".
Type "apropos word" to search for commands related to "word"...
Reading symbols from gdbme...
(No debugging symbols found in gdbme)
(gdb) layout asm
picoCTF{d3bugg3r_dr1v3_7776d758}
```
## Notas adicionales

## Referencias
