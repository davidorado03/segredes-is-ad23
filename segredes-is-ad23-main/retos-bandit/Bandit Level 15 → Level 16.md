# Bandit Level 15 → Level 16

## Objetivo
The password for the next level can be retrieved by submitting the password of the current level to **port 30001 on localhost** using SSL encryption.

**Helpful note: Getting “HEARTBEATING” and “Read R BLOCK”? Use -ign_eof and read the “CONNECTED COMMANDS” section in the manpage. Next to ‘R’ and ‘Q’, the ‘B’ command also works in this version of that command…**
## Datos de acceso al nivel
```
bandit15
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
```
## Solución
```bash
bandit15@bandit:~$ openssl s_client -connect localhost:30001
CONNECTED(00000003)
Can´t use SSL_get_servername
depth=0 CN = localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = localhost
verify error:num=10:certificate has expired
notAfter=Sep  8 06:30:39 2023 GMT
verify return:1
depth=0 CN = localhost
notAfter=Sep  8 06:30:39 2023 GMT
verify return:1
---
Certificate chain
 0 s:CN = localhost
   i:CN = localhost
   a:PKEY: rsaEncryption, 2048 (bit); sigalg: RSA-SHA1
   v:NotBefore: Sep  8 06:29:39 2023 GMT; NotAfter: Sep  8 06:30:39 2023 GMT
---
read R BLOCK
---
Post-Handshake New Session Ticket arrived:
SSL-Session:
    Protocol  : TLSv1.3
    Cipher    : TLS_AES_256_GCM_SHA384
    Session-ID: 8DA926CEEC7C51E01A50BB917EB65FCC85CDD552831E3F89A014756298B4E4ED
    Session-ID-ctx:
    Resumption PSK: 2E16AA7AA736BF7FCB6178FF50A790DAFB1FD8AD6A9B452A6D22444DD9630359A11B116EC53D0ADDB04EA878C8E5D728
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    00c0 - 50 46 95 5d 99 10 b8 cd-8e 33 7f 62 f4 1e 25 36   PF.].....3.b..%6

    Start Time: 1694204980
    Timeout   : 7200 (sec)
    Verify return code: 10 (certificate has expired)
    Extended master secret: no
    Max Early Data: 0
---
read R BLOCK
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
Correct!
JQttfApK4SeyHwDlI9SXGR50qclOAil1

closed
```
## Notas adicionales
El comando openssl permite conectarse a un servidor con protocolo ssl, introdujendo openssl s_client -connect localhost:30001 para conectarse al localhost en el puerto 30001, para lugo introducir la contraseña anterior y así nos devuelve la del sigueinte.
## Referencias
- [Secure Socket Layer/Transport Layer Security on Wikipedia](https://en.wikipedia.org/wiki/Secure_Socket_Layer)
- [OpenSSL Cookbook - Testing with OpenSSL](https://www.feistyduck.com/library/openssl-cookbook/online/ch-testing-with-openssl.html)