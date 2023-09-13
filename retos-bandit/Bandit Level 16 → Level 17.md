# Bandit Level 16 → Level 17

## Objetivo
The credentials for the next level can be retrieved by submitting the password of the current level to **a port on localhost in the range 31000 to 32000**. First find out which of these ports have a server listening on them. Then find out which of those speak SSL and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it.
## Datos de acceso al nivel
```
bandit16
JQttfApK4SeyHwDlI9SXGR50qclOAil1
```
## Solución
```bash
bandit16@bandit:~$ nmap localhost -p 31000-32000
Starting Nmap 7.80 ( https://nmap.org ) at 2023-09-13 16:24 UTC
Nmap scan report for localhost (127.0.0.1)
Host is up (0.00015s latency).
Not shown: 996 closed ports
PORT      STATE SERVICE
31046/tcp open  unknown
31518/tcp open  unknown
31691/tcp open  unknown
31790/tcp open  unknown
31960/tcp open  unknown

Nmap done: 1 IP address (1 host up) scanned in 0.06 seconds
bandit16@bandit:~$ openssl s_client -connect localhost:31790
CONNECTED(00000003)
Can´t use SSL_get_servername
depth=0 CN = localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = localhost
verify error:num=10:certificate has expired
notAfter=Sep 12 19:28:37 2023 GMT
verify return:1
depth=0 CN = localhost
notAfter=Sep 12 19:28:37 2023 GMT
verify return:1
---
Certificate chain
 0 s:CN = localhost
   i:CN = localhost
   a:PKEY: rsaEncryption, 2048 (bit); sigalg: RSA-SHA1
   v:NotBefore: Sep 12 19:27:37 2023 GMT; NotAfter: Sep 12 19:28:37 2023 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIDCzCCAfOgAwIBAgIEG0BsVDANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjMwOTEyMTkyNzM3WhcNMjMwOTEyMTkyODM3WjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQCZ
UxuYBHOC1cImS+smCpNf/KLX5cINzvBHS5Q9vhOKwtTH2+XbP4oEmVJZi/3JYiKz
pjLWLHQ1RUvyZfgWd9TTYKsdQTwLPOVnbPBYSPxQ0ldiL/ShKGfJbBgg48gXwAVN
9TkHbasY+fED+5ZdNijL1oDdawN5kyqrNFC+y8EAIoy1hxMWLWnsUWpCwUu15Yv+
tRktkAKbKzxkLzf5pZapx0voSCJJtjrKkp8Vgwrp4VJpZKe6SzwDQoZldH5eVicl
Hnii4uBJD/w0+W41lp6MVUt4aiLT1EKSuetmaOSCWgFmKYxtI3rvF06yyh3X1Aq/
HGbxxECGCN8GRHAOZvMFAgMBAAGjZTBjMBQGA1UdEQQNMAuCCWxvY2FsaG9zdDBL
BglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0ZWQgYnkgTmNhdC4g
U2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3DQEBBQUAA4IBAQBx
jVQ/R9YfVw9NpY4D636lio5z6My2qR3Vm2Ef+s/iYyNjjIJlYybp87znYWPsnsnI
H14GtLrn4Q5yAnQeZLhEP/kh+P2tHm2kPEXQiUF0St6NkMcwrCFg5FTC5WCL77kP
scevmIbhi8McjEFY4EWEh4o2kslskd8v7ILUGe5gcyntBVC1SrO1pflz+M58djZn
sfGodUvs3yNlHNqpmkbHA7uFnXU8WdDGJzr0KPjmG7tphYiRTUlv7G5AjqrsP6ts
yaqv6EdwogT3e09bc3Tt4TCZkyoUUeE6prhO1d3tP8+IpwtG+0YqOLjaZl7e2UXI
5B1Zk8452tK/oSSc52TD
-----END CERTIFICATE-----
subject=CN = localhost
issuer=CN = localhost
---
No client certificate CA names sent
Peer signing digest: SHA256
Peer signature type: RSA-PSS
Server Temp Key: X25519, 253 bits
---
SSL handshake has read 1339 bytes and written 373 bytes
Verification error: certificate has expired
---
New, TLSv1.3, Cipher is TLS_AES_256_GCM_SHA384
Server public key is 2048 bit
Secure Renegotiation IS NOT supported
Compression: NONE
Expansion: NONE
No ALPN negotiated
Early data was not sent
Verify return code: 10 (certificate has expired)
---
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: F903F9758D0ACC0E0A8477882C530C0105126625B43404EC89B935CD7F486B75
    Session-ID-ctx:
    Resumption PSK: AD8295ED51056E247D44EE144188A48BC6AF795E4CAC3AA7F79E5B301E4C6649791A5603F66F1AAFC61F67F191780E54
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 8a 53 79 53 f7 5d bc c9-dd 02 bc 88 5e 20 c6 eb   .SyS.]......^ ..
    0010 - c2 3f 3b d4 ad 17 e6 ee-c0 44 dc 12 a9 ec 86 6b   .?;......D.....k
    0020 - 9b 84 b4 1b 70 37 c3 01-0f cf bd 85 17 64 86 e0   ....p7.......d..
    0030 - c0 7b 23 f8 78 4c 41 d7-4f 20 7a 9d d1 65 b0 a6   .{#.xLA.O z..e..
    0040 - 03 bf 1c 64 97 a3 b2 b9-d5 ed b4 46 d0 00 da 28   ...d.......F...(
    0050 - 45 6f 1f d3 19 7d 13 30-26 0a 0f d5 e1 8b 1d b2   Eo...}.0&.......
    0060 - d9 01 40 41 6f a6 4b 31-b9 8d 28 14 62 33 4d 6d   ..@Ao.K1..(.b3Mm
    0070 - 11 3e 67 02 8c dc e5 6f-07 26 5e 2f 5d dd 15 b2   .>g....o.&^/]...
    0080 - b8 8f f4 5a b3 b9 4e b2-cf bd a6 31 96 87 df 19   ...Z..N....1....
    0090 - 4f 82 9a a3 f1 b4 41 c8-3f ec 9a 2b 99 ec d2 ec   O.....A.?..+....
    00a0 - 82 13 fd de 05 60 b6 c2-29 3c 31 19 f3 f3 bc 5b   .....`..)<1....[
    00b0 - 38 c4 52 96 23 92 87 27-ce 3c 70 d8 ba 0c ed e4   8.R.#..´.<p.....
    00c0 - c2 5f c9 0c f4 86 4c 0f-46 29 b0 9b 10 f5 2b da   ._....L.F)....+.

    Start Time: 1694622277
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: D2F8715016613D105EEF2B264B23229FCB98FCE46ABFE9EB05F83E389C427A41
    Session-ID-ctx:
    Resumption PSK: A9602134C3BD63FE58DE4F3B2B62E8B22D05962BCAE579B15577C6A191B66F3552B204C2350103C6CB864B87DEF7F6E9
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 8a 53 79 53 f7 5d bc c9-dd 02 bc 88 5e 20 c6 eb   .SyS.]......^ ..
    0010 - f9 e8 12 fd d7 7e 89 ac-1b 50 2b cf 49 db 61 bf   .....~...P+.I.a.
    0020 - de 8a de 20 cd c7 72 a2-5d 89 89 25 8c 98 57 a2   ... ..r.]..%..W.
    0030 - 41 6e 15 cf 25 0f 23 a0-52 38 2f 84 a0 2e ad 7e   An..%.#.R8/....~
    0040 - 28 0b 77 ff f9 9c 2c 5d-85 1d db 01 59 11 7f fe   (.w...,]....Y...
    0050 - 1b a3 cd 7b 04 2c c6 3f-73 c1 70 ab 4b a2 dc 9a   ...{.,.?s.p.K...
    0060 - 17 ad 84 96 1e 24 fa aa-cc 60 46 8c c8 f7 b1 ce   .....$...`F.....
    0070 - e6 6f 97 5a 8c 52 ae 30-24 4b 82 7f 84 6c cb 12   .o.Z.R.0$K...l..
    0080 - 3c 87 bc a2 fa 4d 3c 40-50 d8 0e e0 49 72 33 3c   <....M<@P...Ir3<
    0090 - 83 a4 cf a4 dd ce 01 3d-3b f4 2f ca 6b 43 6f 00   .......=;./.kCo.
    00a0 - 64 76 8b fe ac 3e 92 e3-05 87 e8 40 b2 6e 04 01   dv...>.....@.n..
    00b0 - d2 ac 38 19 4a 04 ee 5e-4e 64 b7 60 7e ef e1 00   ..8.J..^Nd.`~...
    00c0 - 33 2d b4 fe 12 83 be 54-4b aa 2c 51 56 09 74 6e   3-.....TK.,QV.tn

    Start Time: 1694622277
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
JQttfApK4SeyHwDlI9SXGR50qclOAil1
Correct!
-----BEGIN RSA PRIVATE KEY-----
MIIEogIBAAKCAQEAvmOkuifmMg6HL2YPIOjon6iWfbp7c3jx34YkYWqUH57SUdyJ
imZzeyGC0gtZPGujUSxiJSWI/oTqexh+cAMTSMlOJf7+BrJObArnxd9Y7YT2bRPQ
Ja6Lzb558YW3FZl87ORiO+rW4LCDCNd2lUvLE/GL2GWyuKN0K5iCd5TbtJzEkQTu
DSt2mcNn4rhAL+JFr56o4T6z8WWAW18BR6yGrMq7Q/kALHYW3OekePQAzL0VUYbW
JGTi65CxbCnzc/w4+mqQyvmzpWtMAzJTzAzQxNbkR2MBGySxDLrjg0LWN6sK7wNX
x0YVztz/zbIkPjfkU1jHS+9EbVNj+D1XFOJuaQIDAQABAoIBABagpxpM1aoLWfvD
KHcj10nqcoBc4oE11aFYQwik7xfW+24pRNuDE6SFthOar69jp5RlLwD1NhPx3iBl
J9nOM8OJ0VToum43UOS8YxF8WwhXriYGnc1sskbwpXOUDc9uX4+UESzH22P29ovd
d8WErY0gPxun8pbJLmxkAtWNhpMvfe0050vk9TL5wqbu9AlbssgTcCXkMQnPw9nC
YNN6DDP2lbcBrvgT9YCNL6C+ZKufD52yOQ9qOkwFTEQpjtF4uNtJom+asvlpmS8A
vLY9r60wYSvmZhNqBUrj7lyCtXMIu1kkd4w7F77k+DjHoAXyxcUp1DGL51sOmama
+TOWWgECgYEA8JtPxP0GRJ+IQkX262jM3dEIkza8ky5moIwUqYdsx0NxHgRRhORT
8c8hAuRBb2G82so8vUHk/fur85OEfc9TncnCY2crpoqsghifKLxrLgtT+qDpfZnx
SatLdt8GfQ85yA7hnWWJ2MxF3NaeSDm75Lsm+tBbAiyc9P2jGRNtMSkCgYEAypHd
HCctNi/FwjulhttFx/rHYKhLidZDFYeiE/v45bN4yFm8x7R/b0iE7KaszX+Exdvt
SghaTdcG0Knyw1bpJVyusavPzpaJMjdJ6tcFhVAbAjm7enCIvGCSx+X3l5SiWg0A
R57hJglezIiVjv3aGwHwvlZvtszK6zV6oXFAu0ECgYAbjo46T4hyP5tJi93V5HDi
Ttiek7xRVxUl+iU7rWkGAXFpMLFteQEsRr7PJ/lemmEY5eTDAFMLy9FL2m9oQWCg
R8VdwSk8r9FGLS+9aKcV5PI/WEKlwgXinB3OhYimtiG2Cg5JCqIZFHxD6MjEGOiu
L8ktHMPvodBwNsSBULpG0QKBgBAplTfC1HOnWiMGOU3KPwYWt0O6CdTkmJOmL8Ni
blh9elyZ9FsGxsgtRBXRsqXuz7wtsQAgLHxbdLq/ZJQ7YfzOKU4ZxEnabvXnvWkU
YOdjHdSOoKvDQNWu6ucyLRAWFuISeXw9a/9p7ftpxm0TSgyvmfLF2MIAEwyzRqaM
77pBAoGAMmjmIJdjp+Ez8duyn3ieo36yrttF5NSsJLAbxFpdlc1gvtGCWW+9Cq0b
dxviW8+TFVEBl1O4f7HVm6EpTscdDxU+bCXWkfjuRb7Dy9GOtt9JPsX8MBTakzh3
vBgsyi/sN3RqRBcGU40fOoZyfAMT8s1m/uYv52O6IgeuZ/ujbjY=
-----END RSA PRIVATE KEY-----

closed
```
## Notas adicionales
nmap es un scanner de puertos, por defecto escanea los primeros 1000 puertos (los más comunes), con la opción -p podemos añadir un rango de puertos a verificar, con la opción -sV le dices a nmap que intente averiguar el servicio que corre en el puerto.
## Referencias
[Port scanner on Wikipedia](https://en.wikipedia.org/wiki/Port_scanner)