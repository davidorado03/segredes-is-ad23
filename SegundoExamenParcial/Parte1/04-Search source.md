# Search source

## Objetivo
The developer of this website mistakenly left an important artifact in the website source, can you find it?The website is [here](http://saturn.picoctf.net:63978/)
## Solución
```bash
┌──(kali㉿kali)-[~/2Exa/parte1/searchSource]
└─$ wget -r http://saturn.picoctf.net:63978/
--2023-11-03 13:21:22--  http://saturn.picoctf.net:63978/
Resolving saturn.picoctf.net (saturn.picoctf.net)... 13.59.203.175
Connecting to saturn.picoctf.net (saturn.picoctf.net)|13.59.203.175|:63978... connected.
HTTP request sent, awaiting response... 200 OK
Length: 15920 (16K) [text/html]
Saving to: ‘saturn.picoctf.net:63978/index.html’

FINISHED --2023-11-03 13:21:29--
Total wall clock time: 7.3s
Downloaded: 21 files, 670K in 3.0s (221 KB/s)

┌──(kali㉿kali)-[~/2Exa/parte1/searchSource]
└─$ ls
saturn.picoctf.net:63978

┌──(kali㉿kali)-[~/2Exa/parte1/searchSource]
└─$ cat saturn.picoctf.net:63978 | grep pico
cat: 'saturn.picoctf.net:63978': Is a directory

┌──(kali㉿kali)-[~/2Exa/parte1/searchSource]
└─$ grep -R pico saturn.picoctf.net:63978                 
saturn.picoctf.net:63978/css/style.css:/** banner_main picoCTF{1nsp3ti0n_0f_w3bpag3s_ec95fa49} **/

```
## Notas adicionales

## Referencias