# Bit-O-Asm-1

## Objetivo
Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`.Download the assembly dump [here](https://artifacts.picoctf.net/c/509/disassembler-dump0_a.txt).
## Solución
```bash
┌──(kali㉿kali)-[~/retos/3exa/parte2/asm1]
└─$ wget https://artifacts.picoctf.net/c/509/disassembler-dump0_a.txt
--2023-11-29 12:52:55--  https://artifacts.picoctf.net/c/509/disassembler-dump0_a.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.61, 3.161.55.64, 3.161.55.100, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.61|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 209 [application/octet-stream]
Saving to: ‘disassembler-dump0_a.txt’

disassembler-dump0_a.txt                                   100%[========================================================================================================================================>]     209  --.-KB/s    in 0s      

2023-11-29 12:52:55 (156 MB/s) - ‘disassembler-dump0_a.txt’ saved [209/209]

                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/retos/3exa/parte2/asm1]
└─$ cat disassembler-dump0_a.txt 
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x4],edi
<+11>:    mov    QWORD PTR [rbp-0x10],rsi
<+15>:    mov    eax,0x30
<+20>:    pop    rbp
<+21>:    ret
0x30=48
picoCTF{48}
```
## Notas adicionales

## Referencias