# Packets Primer

## Objetivo
Download the packet capture file and use packet analysis software to find the flag.

- [Download packet capture](https://artifacts.picoctf.net/c/194/network-dump.flag.pcap)
## Solución
```bash
┌──(kali㉿kali)-[~/2Exa/2]
└─$ wget https://artifacts.picoctf.net/c/194/network-dump.flag.pcap
--2023-11-03 19:15:42--  https://artifacts.picoctf.net/c/194/network-dump.flag.pcap
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 18.160.124.38, 18.160.124.34, 18.160.124.108, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|18.160.124.38|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 778 [application/octet-stream]
Saving to: ‘network-dump.flag.pcap’

network-dump.flag.pcap                                     100%[=======================================================================================================================================>]     778  --.-KB/s    in 0s      

2023-11-03 19:15:48 (22.7 MB/s) - ‘network-dump.flag.pcap’ saved [778/778]

                                                                                                                                                                                                                                           
┌──(kali㉿kali)-[~/2Exa/2]
└─$ wireshark network-dump.flag.pcap 

p i c o C T F { p 4 c k 3 7 _ 5 h 4 r k _ c e c c a a 7 f }
picoCTF{p4ck37_5h4rk_ceccaa7f}
```
## Notas adicionales

## Referencias