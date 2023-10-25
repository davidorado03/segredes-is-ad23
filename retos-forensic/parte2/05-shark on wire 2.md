# shark on wire 2

## Objetivo

## Solución
```bash
┌──(kali㉿kali)-[~/notas-hacking/forensic/whireOnShark2]
└─$ python3 -m pip install scapy
Defaulting to user installation because normal site-packages is not writeable
Requirement already satisfied: scapy in /usr/lib/python3/dist-packages (2.5.0)

from scapy.all import *

packets = rdpcap('capture.pcap')

flag = ''

for p in packets:
        if UDP in p and p[UDP].dport == 22:
                if p[UDP].sport > 5000:
                        flag += chr(p[UDP].sport - 5000)

print(flag)

┌──(kali㉿kali)-[~/notas-hacking/forensic/whireOnShark2]
└─$ python3 ex.py
picoCTF{p1LLf3r3d_data_v1a_st3g0}

```
## Notas adicionales

## Referencias
