# MacroHard WeakEdge

## Objetivo
I've hidden a flag in this file. Can you find it? [Forensics is fun.pptm](https://mercury.picoctf.net/static/3944a59474f9f676942282c50b9c3675/Forensics%20is%20fun.pptm)
## Solución
```bash
┌──(kali㉿kali)-[~/Retos/MacroHardWeakEdge]
└─$ wget https://mercury.picoctf.net/static/d3dd8cd51524d9fafcccd1b7d55f85e7/Forensics%20is%20fun.pptm
--2023-10-30 02:25:57--  https://mercury.picoctf.net/static/d3dd8cd51524d9fafcccd1b7d55f85e7/Forensics%20is%20fun.pptm    

2023-10-30 02:25:57 (738 KB/s) - ‘Forensics is fun.pptm’ saved [100093/100093]

┌──(kali㉿kali)-[~/Retos/MacroHardWeakEdge]
└─$ file Forensics\ is\ fun.pptm 
Forensics is fun.pptm: Microsoft PowerPoint 2007+

┌──(kali㉿kali)-[~/Retos/MacroHardWeakEdge]
└─$ ls -la
total 108
drwxr-xr-x  2 kali kali   4096 Oct 23 02:17  .
drwxr-xr-x 14 kali kali   4096 Oct 23 02:17  ..
-rw-r--r--  1 kali kali 100093 Mar 23  2021 'Forensics is fun.pptm'

┌──(kali㉿kali)-[~/Retos/MacroHardWeakEdge]
└─$ unzip Forensics\ is\ fun.pptm 
Archive:  Forensics is fun.pptm
  inflating: [Content_Types].xml             
  inflating: ppt/slideMasters/hidden  
  
┌──(kali㉿kali)-[~/Retos/MacroHardWeakEdge]
└─$  ls -la
total 132
drwxr-xr-x  5 kali kali   4096 Oct 30 02:25  .
drwxr-xr-x 14 kali kali   4096 Oct 30 02:23  ..
-rw-r--r--  1 kali kali  10660 Jan  1  1980 '[Content_Types].xml'
drwxr-xr-x  2 kali kali   4096 Oct 30 02:25  docProps
-rw-r--r--  1 kali kali 100093 Mar 23  2021 'Forensics is fun.pptm'
drwxr-xr-x  7 kali kali   4096 Oct 30 02:25  ppt
drwxr-xr-x  2 kali kali   4096 Oct 30 02:25  _rels
┌──(kali㉿kali)-[~/Retos/MacroHardWeakEdge]
└─$ code .  

┌──(kali㉿kali)-[~/Retos/MacroHardWeakEdge]
└─$ echo "Z m x h Z z o g c G l j b 0 N U R n t E M W R f d V 9 r b j B 3 X 3 B w d H N f c l 9 6 M X A 1 f Q" | tr -d " " | base64 -d 
flag: picoCTF{D1d_u_kn0w_ppts_r_z1p5}base64: invalid input

```
## Notas adicionales

## Referencias