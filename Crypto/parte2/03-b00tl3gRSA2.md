# b00tl3gRSA2

## Objetivo
In RSA d is a lot bigger than e, why don't we use d to encrypt instead of e? Connect with `nc jupiter.challenges.picoctf.org 19566`.
## Solución
```bash
┌──(kali㉿kali)-[~/retos/crypto]
└─$  nc jupiter.challenges.picoctf.org 19566.
c: 90406952505953627054013337724636105092119112113193885754768850956682291721053763578176536632028950273529123219999627723080697553729027592570086008128712178592868308837720468654976114808381838876225469136677499917973993527022987195247548885310283289407164275589402633590420859957829917877519438341285407035529
n: 128068431387121848856693375538776344625765744809182476404298427757928696429160538675207681659865097294587529060484131365073319046817040750851735755369390827109417456741845026656672855419269569351615340249543626151515198690363261693743973391007464110735504616157015910668326213387953360505571527889988168491243
e: 110651187250932871044774794337666840686777843570428132870241148868043311512653712283823790626794044115670907205408447967040169945328106496730529096724543157252779256915567464326021985149783514054100156383686011587093673921460372728970708636313958959249918718038527235366407029864320109783970618280763329420673

┌──(kali㉿kali)-[~/retos/crypto]
└─$ nano exp3.py

from Crypto.Util.number import inverse

c = 90406952505953627054013337724636105092119112113193885754768850956682291721053763578176536632028950273529123219999627723080697553729027592570086008128712178592868308837720468654976114808381838876225469136677499917973993527022987195247548885310283289407164275589402633590420859957829917877519438341285407035529
n = 128068431387121848856693375538776344625765744809182476404298427757928696429160538675207681659865097294587529060484131365073319046817040750851735755369390827109417456741845026656672855419269569351615340249543626151515198690363261693743973391007464110735504616157015910668326213387953360505571527889988168491243
d = 65537
e = 110651187250932871044774794337666840686777843570428132870241148868043311512653712283823790626794044115670907205408447967040169945328106496730529096724543157252779256915567464326021985149783514054100156383686011587093673921460372728970708636313958959249918718038527235366407029864320109783970618280763329420673

def get_RSA_flag(c,n,d):
	m = pow(c,d,n)
	return bytes.fromhex(format(m,'x'))

print(get_RSA_flag(c,n,d))
┌──(kali㉿kali)-[~/retos/crypto]
└─$ python exp3.py           
b'picoCTF{bad_1d3a5_2438125}'
```
## Notas adicionales

## Referencias