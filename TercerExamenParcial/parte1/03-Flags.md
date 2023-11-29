# Flags

## Objetivo
What do the [flags](https://jupiter.challenges.picoctf.org/static/fbeb5f9040d62b18878d199cdda2d253/flag.png) mean?
## Solución
```bash
┌──(kali㉿kali)-[~/retos/3exa/Flags]
└─$ wget https://jupiter.challenges.picoctf.org/static/fbeb5f9040d62b18878d199cdda2d253/flag.png
--2023-11-28 13:17:06--  https://jupiter.challenges.picoctf.org/static/fbeb5f9040d62b18878d199cdda2d253/flag.png
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 43257 (42K) [application/octet-stream]
Saving to: ‘flag.png’

flag.png                                                   100%[========================================================================================================================================>]  42.24K   155KB/s    in 0.3s    

2023-11-28 13:17:07 (155 KB/s) - ‘flag.png’ saved [43257/43257]

┌──(kali㉿kali)-[~/retos/3exa/Flags]
└─$ open flag.png 
flag cipher 
https://www.dcode.fr/maritime-signals-code
PICOCTF{F1AG5AND5TUFF}
```
## Notas adicionales

## Referencias
