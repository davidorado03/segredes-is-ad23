# Mr-Worldwide

## Objetivo
A musician left us a [message](https://jupiter.challenges.picoctf.org/static/d5570d48262dbba2a31f2a940409ad9d/message.txt). What's it mean?
## Solución
```bash
┌──(kali㉿kali)-[~/retos/3exa/Mr-Worldwide]
└─$ wget https://jupiter.challenges.picoctf.org/static/d5570d48262dbba2a31f2a940409ad9d/message.txt
--2023-11-28 13:33:23--  https://jupiter.challenges.picoctf.org/static/d5570d48262dbba2a31f2a940409ad9d/message.txt
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 278 [application/octet-stream]
Saving to: ‘message.txt’

message.txt                                                100%[========================================================================================================================================>]     278  --.-KB/s    in 0s      

2023-11-28 13:33:24 (5.96 MB/s) - ‘message.txt’ saved [278/278]

┌──(kali㉿kali)-[~/retos/3exa/Mr-Worldwide]
└─$ cat message.txt 
picoCTF{(35.028309, 135.753082)(46.469391, 30.740883)(39.758949, -84.191605)(41.015137, 28.979530)(24.466667, 54.366669)(3.140853, 101.693207)_(9.005401, 38.763611)(-3.989038, -79.203560)(52.377956, 4.897070)(41.085651, -73.858467)(57.790001, -152.407227)(31.205753, 29.924526)}  
maps
picoCTF{(
35.028309, 135.753082 Kyoto, Japan
46.469391, 30.740883 Odesa, Ukraine
39.758949, -84.191605 Dayton, OH
41.015137, 28.979530 Istanbul, Turkey
24.466667, 54.366669 Abu Dhabi, United Arab Emirates
3.140853, 101.693207 Kuala Lumpur, Malaysia
9.005401, 38.763611 Addis Ababa, Ethiopia
-3.989038, -79.203560 Loja, Ecuador
52.377956, 4.897070 Amsterdam, Netherlands
41.085651, -73.858467 Sleepy Hollow, NY
57.790001, -152.407227 Kodiak, AK
31.205753, 29.924526 Alexandria, Egypt
)}  
```
## Notas adicionales

## Referencias
