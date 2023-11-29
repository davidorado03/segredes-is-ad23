# Bit-O-Asm-2

## Objetivo
Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`.Download the assembly dump [here](https://artifacts.picoctf.net/c/510/disassembler-dump0_b.txt).
## Solución
```bash
┌──(kali㉿kali)-[~/retos/3exa/parte2]
└─$ cd asm2                                                          

┌──(kali㉿kali)-[~/retos/3exa/parte2/asm2]
└─$ wget https://artifacts.picoctf.net/c/510/disassembler-dump0_b.txt
--2023-11-29 13:23:36--  https://artifacts.picoctf.net/c/510/disassembler-dump0_b.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.61, 3.161.55.64, 3.161.55.100, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.61|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 270 [application/octet-stream]
Saving to: ‘disassembler-dump0_b.txt’

disassembler-dump0_b.txt                                   100%[========================================================================================================================================>]     270  --.-KB/s    in 0s      

2023-11-29 13:23:36 (494 MB/s) - ‘disassembler-dump0_b.txt’ saved [270/270]

┌──(kali㉿kali)-[~/retos/3exa/parte2/asm2]
└─$ cat disassembler-dump0_a.txt
cat: disassembler-dump0_a.txt: No such file or directory

┌──(kali㉿kali)-[~/retos/3exa/parte2/asm2]
└─$ cat disassembler-dump0_b.txt
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x14],edi
<+11>:    mov    QWORD PTR [rbp-0x20],rsi
<+15>:    mov    DWORD PTR [rbp-0x4],0x9fe1a
<+22>:    mov    eax,DWORD PTR [rbp-0x4]
<+25>:    pop    rbp
<+26>:    ret
0x9fe1a = 654874
picoCTF{654874}
```
## Notas adicionales

## Referencias