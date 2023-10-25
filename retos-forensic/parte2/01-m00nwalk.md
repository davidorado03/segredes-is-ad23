# m00nwalk

## Objetivo
Decode this [message](https://jupiter.challenges.picoctf.org/static/d6fcea5e3c6433680ea4f914e24fab61/message.wav) from the moon.
## Solución
```bash
┌──(kali㉿kali)-[/opt]
└─$ sudo git clone https://github.com/colaclanth/sstv.git 
Cloning into 'sstv'...
remote: Enumerating objects: 221, done.
remote: Counting objects: 100% (59/59), done.
remote: Compressing objects: 100% (10/10), done.
remote: Total 221 (delta 51), reused 49 (delta 49), pack-reused 162
Receiving objects: 100% (221/221), 1.01 MiB | 302.00 KiB/s, done.
Resolving deltas: 100% (139/139), done.
┌──(kali㉿kali)-[/opt]
└─$ ls
microsoft  sstv
┌──(kali㉿kali)-[/opt]
└─$ cd sstv 
┌──(kali㉿kali)-[/opt/sstv]
└─$ sudo python setup.py install                         
running install
Using /usr/lib/python3/dist-packages
Finished processing dependencies for sstv==0.1
┌──(kali㉿kali)-[/opt/sstv]
└─$ sstv                        
┌──(kali㉿kali)-[/opt/sstv/sstv]
└─$ cd ..  
┌──(kali㉿kali)-[/opt/sstv]
└─$ cd ..

┌──(kali㉿kali)-[/]
└─$ sstv -d message.wav -o img.jpg
usage: sstv [-h] [-d AUDIO_FILE] [-o OUTPUT_FILE] [-s SKIP] [-V] [--list-modes] [--list-audio-formats] [--list-image-formats]
sstv: error: argument -d/--decode: can't open 'message.wav': [Errno 2] No such file or directory: 'message.wav'
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[/]
└─$ cd ..                         
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[/]
└─$ ls
bin  boot  dev  etc  home  initrd.img  initrd.img.old  lib  lib32  lib64  libx32  lost+found  media  mnt  opt  proc  root  run  sbin  srv  swapfile  sys  tmp  usr  var  vmlinuz  vmlinuz.old
┌──(kali㉿kali)-[/]
└─$ cd ~ 
┌──(kali㉿kali)-[~]
└─$ cd notas-hacking 
┌──(kali㉿kali)-[~/notas-hacking]
└─$ sstv -d message.wav -o img.jpg
[sstv] Searching for calibration header... Found!    
[sstv] Detected SSTV mode Scottie 1
[sstv] Decoding image...                                                                                                         [####################################################################################################] 100%
[sstv] Drawing image data...
[sstv] ...Done!
┌──(kali㉿kali)-[~/notas-hacking]
└─$ open img.jpg 
┌──(kali㉿kali)-[~/notas-hacking]
└─$ 

```
## Notas adicionales

## Referencias