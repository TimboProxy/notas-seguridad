# Bandit Level 15 → Level 16
## Objetivo
The password for the next level can be retrieved by submitting the password of the current level to **port 30001 on localhost** using SSL encryption
## Datos de acceso al nivel
```
Server : bandit15.labs.overthewire.org
User : bandit15
Password : jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
Comando: SSH bandit15@bandit.labs.overthewire.org -p 2220
```
## Solución 

bandit15@bandit:~$
bandit15@bandit:~$ ls -la
total 24
drwxr-xr-x  2 root     root     4096 Apr 23 18:04 .
drwxr-xr-x 70 root     root     4096 Apr 23 18:05 ..
-rw-r-----  1 bandit15 bandit15   33 Apr 23 18:04 .bandit14.password
-rw-r--r--  1 root     root      220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root     root     3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root     root      807 Jan  6  2022 .profile
bandit15@bandit:~$ nc -v localhost 30001
Connection to localhost (127.0.0.1) 30001 port [tcp/*] succeeded!
jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
bandit15@bandit:~$ openssl s_client -connect localhost:30001
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = localhost
verify error:num=10:certificate has expired
notAfter=Sep  5 14:21:56 2023 GMT
verify return:1
depth=0 CN = localhost
notAfter=Sep  5 14:21:56 2023 GMT
verify return:1
---
Certificate chain
 0 s:CN = localhost
   i:CN = localhost
   a:PKEY: rsaEncryption, 2048 (bit); sigalg: RSA-SHA1
   v:NotBefore: Sep  5 14:20:56 2023 GMT; NotAfter: Sep  5 14:21:56 2023 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIDCzCCAfOgAwIBAgIERT5t9zANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjMwOTA1MTQyMDU2WhcNMjMwOTA1MTQyMTU2WjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQCm
wBiPjdh1RI2h6uD0NBu9weZgCFgUwOM5PTlJzrrbDIG6MojStI6UWFDOGJAGYk/O
3vOKI4XC1r51gsOG+JSQye+9XqlNKVidFm8muvoOQhtCb3vquFm1kn4B5ZlVFPE+
kwN9TB+Vv9vfwXI3HG7o5KBRBZRPKV1KNOU+x3jhjphuXbLOi0PeNHWAyEBHfNEX
Zrz+Zvun+kgq8CmGGp9oMYRfwjmvPaZYQtTH/JUmt7vbsXalAb6oaCHx36GeuEJH
lAoPkI++eVSLJQO7tdtMeNpYKttX1jIjVvMqAKf7Nhx91m7A1mBGjUw8FDjZjhjn
ynORJxJii0nCah3xomyHAgMBAAGjZTBjMBQGA1UdEQQNMAuCCWxvY2FsaG9zdDBL
BglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0ZWQgYnkgTmNhdC4g
U2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3DQEBBQUAA4IBAQAx
ECelAuW6irw6S0/rR2vxrL9Oeej7SWiQ1CizTLew+HZRzRQmTwGqmYnSQnMUhCRT
u5vFwP6tnDrUXlSrazBnDve87BMzdECWhauErj9Pt40gLDuSgvLkZWl6P+f8Frb8
FkDUXuqxiq1vZxOcY0gSQpwvLeS06RMi546KNmDt4+Qfvqt4oXRL+882bqgoOqHQ
P/VsqO52CXoAe5rLuhyC/YVnWxIQnjE5EUYkXCd0Zdm7JOzuKbid7FGinAnpzfUz
vaG4FaUl1ITlxUE9xAWiDIDBYZuXUbj8CyipZm+v0ksNPqXYkh/PvK24fyaAeAUL
Yrmp3Qa25oeRjlPTmVTD
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
    Session-ID: B6BE3951C3C4837D5AB17CBA3D2A0908E1C1A2CB259E06F95A0BF48BB90BA4F0
    Session-ID-ctx:
    Resumption PSK: D2F6DA457D7E6C9B88FBD2388E141D3280332AF0C0BE39AEE972C548A19A209CF5EF933CBCED6715F67ACA18028D027D
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 0a 48 a5 32 54 0e cb 4c-36 de e2 24 47 c1 4f 66   .H.2T..L6..$G.Of
    0010 - 92 2d 97 af 54 12 82 9b-7d f2 98 8d 0c 55 e2 be   .-..T...}....U..
    0020 - 9c 0e dc dd ab 61 48 d2-5d fb c9 02 57 4a 82 9e   .....aH.]...WJ..
    0030 - ba 6a a3 db 7f 18 e4 d9-61 56 97 7e 6e 80 e4 8b   .j......aV.~n...
    0040 - 60 c1 7a a9 0e 6f f3 6d-11 be 76 2b 6f 9f 11 00   `.z..o.m..v+o...
    0050 - 51 e0 78 e1 84 05 68 b0-f4 b7 d6 79 e5 e8 b7 ec   Q.x...h....y....
    0060 - 07 04 b5 66 7a 3f 10 84-4f 88 09 14 e4 9e 1a 34   ...fz?..O......4
    0070 - a9 ee 99 28 da e3 6c 05-1b ed ae fe fe 88 1a 9b   ...(..l.........
    0080 - 18 1b ad c1 48 b7 54 a2-fc ef 36 32 24 59 fe 1e   ....H.T...62$Y..
    0090 - 83 bf d2 de b7 b8 3f af-98 e1 a0 39 b9 86 b7 d6   ......?....9....
    00a0 - 08 cc 52 1d 2e d1 17 b4-2a 4d a9 dd 5d f3 56 4a   ..R.....*M..].VJ
    00b0 - e2 29 ad e8 1a 52 2f ae-62 ab 22 14 0e 59 3c 2d   .)...R/.b."..Y<-
    00c0 - c1 aa 7a bf 08 f2 b5 9f-4c 40 6c 5a af 30 fc 9f   ..z.....L@lZ.0..

    Start Time: 1694046565
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
    Session-ID: 86CA8F9606396A4960BAF386345E3195DA806BD74719846AC5CCF8F8C2F67449
    Session-ID-ctx:
    Resumption PSK: 65595549C4B9B6531062384DA9DD62BBF20E078F7DEAA3F568EBCD11CF40E3A2CD002EFBAD362B608CAF0A3D70DCB41E
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 0a 48 a5 32 54 0e cb 4c-36 de e2 24 47 c1 4f 66   .H.2T..L6..$G.Of
    0010 - 6a 21 d3 e9 51 9c 01 ef-73 5e c5 68 c2 05 2f 6d   j!..Q...s^.h../m
    0020 - 90 ed ed 4a 94 79 08 99-75 3a 81 83 7a 95 b2 fb   ...J.y..u:..z...
    0030 - 1f 20 4f 5a 0c 15 74 41-ce 1c cd 70 aa 44 43 b7   . OZ..tA...p.DC.
    0040 - c3 08 ea 01 59 3f 2d c2-42 70 5b f7 e6 60 92 1c   ....Y?-.Bp[..`..
    0050 - 21 db 54 17 a8 6a 5e bd-c6 eb fd c1 e5 60 81 d1   !.T..j^......`..
    0060 - f9 6d ee ed ac 1b 43 49-5f 4d 80 18 90 54 7e 61   .m....CI_M...T~a
    0070 - 4f cf 01 a2 d7 bb 56 e6-7d bd d0 df b6 d9 a9 a6   O.....V.}.......
    0080 - 30 1f 0b 00 14 86 72 4a-69 10 ee c9 84 f4 f2 02   0.....rJi.......
    0090 - e9 d8 fd 12 07 b7 93 3f-5a f8 85 16 b9 2c 0a 30   .......?Z....,.0
    00a0 - 8d dc 55 e4 9d f2 a8 18-9d d6 94 0e db 6b f1 7b   ..U..........k.{
    00b0 - 2d 38 8c ce 2f 57 fe 6d-90 6b 02 d0 d0 22 93 d8   -8../W.m.k..."..
    00c0 - 23 e2 30 ae 85 82 8d d8-48 64 9d ea e5 3e a6 ea   #.0.....Hd...>..

    Start Time: 1694046565
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
bandit15@bandit:~$
## Notas adicionales
ls -la
nc -v localhost 30001
openssl s_client -connect localhost:30001

openssl s_client -connect ww.uaz.edu.mx:443
## Referencias