# Webnet1

## Objetivo
We found this [packet capture](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap) and [key](https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key). Recover the flag.
## Solución
```bash
┌──(kali㉿kali)-[~/WebNet1]
└─$ wget https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap
--2023-10-23 01:36:42--  https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap
3-10-23 01:36:43 (1.29 MB/s) - ‘capture.pcap’ saved [92525/92525]

┌──(kali㉿kali)-[~/WebNet1]
└─$ wget https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key
picopico.key             100%[=================================>]   1.66K  --.-KB/s    in 0s      

2023-10-30 01:36:59 (30.7 MB/s) - ‘picopico.key’ saved [1704/1704]

┌──(kali㉿kali)-[~/WebNet1]
└─$ wireshark capture.pcap 
 ** (wireshark:7699) 01:39:52.824106 [GUI WARNING] -- FIX Add drag reordering to UAT dialog

┌──(kali㉿kali)-[~/WebNet1]
└─$ strings vulture.jpg -n15
picoCTF{honey.roasted.peanuts}
 )/'%'/9339GDG]]}
 )/'%'/9339GDG]]}
%&'()*456789:CDEFGHIJSTUVWXYZcdefghijstuvwxyz
&'()*56789:CDEFGHIJSTUVWXYZcdefghijstuvwxyz
         
```
## Notas adicionales

## Referencias