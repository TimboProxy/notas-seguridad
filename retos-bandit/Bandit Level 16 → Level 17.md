# Level 16 → Level 17
## Objetivo
The credentials for the next level can be retrieved by submitting the password of the current level to **a port on localhost in the range 31000 to 32000**. First find out which of these ports have a server listening on them. Then find out which of those speak SSL and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it.
## Datos de acceso al nivel
```
Server : bandit16.labs.overthewire.org
User : bandit16
Password : JQttfApK4SeyHwDlI9SXGR50qclOAil1
Comando: SSH bandit16@bandit.labs.overthewire.org -p 2220
```
## Solución 
```
bandit16@bandit:~$
bandit16@bandit:~$ pwd
/home/bandit16
bandit16@bandit:~$ nmap -p 31000-32000 localhost
Starting Nmap 7.80 ( https://nmap.org ) at 2023-09-15 02:23 UTC
Nmap scan report for localhost (127.0.0.1)
Host is up (0.00011s latency).
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
Can't use SSL_get_servername
depth=0 CN = localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = localhost
verify error:num=10:certificate has expired
notAfter=Sep 14 08:51:16 2023 GMT
verify return:1
depth=0 CN = localhost
notAfter=Sep 14 08:51:16 2023 GMT
verify return:1
---
Certificate chain
 0 s:CN = localhost
   i:CN = localhost
   a:PKEY: rsaEncryption, 2048 (bit); sigalg: RSA-SHA1
   v:NotBefore: Sep 14 08:50:16 2023 GMT; NotAfter: Sep 14 08:51:16 2023 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIDCzCCAfOgAwIBAgIEWKbz8jANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjMwOTE0MDg1MDE2WhcNMjMwOTE0MDg1MTE2WjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQCl
BpyEB+3ppzXakesgIOxQxHtl/qQF2CbhbpVkseVlFHhXBNSgB99LIKkAfBQ9Vl6V
+6q2Y+AJPy+ZB0lYm+/a8X//Qal67URUkmZzChS+4KMAtgH2uzkosp2fl+DWEMu3
253FNieJ0OWSukhmmzu5OV3yzfPNgVDW40eKSRyAbjBjQY0C8LLezUQO1VMGNsfd
Wne2TfhZVnds/XS1Sx83JYFtfJNTpMEO4FNUKU7U039PKFRuuihl9LqxdsgDMhZQ
+mEKMR024murxxM+05k7Gq1bZd4SyT+sYHJ3KGIm7pMrq0UAM8FZCVIW0/10CsC5
btDNWQIeV/PRGH4f9FDDAgMBAAGjZTBjMBQGA1UdEQQNMAuCCWxvY2FsaG9zdDBL
BglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0ZWQgYnkgTmNhdC4g
U2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3DQEBBQUAA4IBAQCI
c6QpnY8dYzUlfgBEH55avSDqY3BCEcRC3XFT/G4GpQRYdJSHVaPwopGplQKldi4m
yxnmoN6GlhpJw0dFFU5CMnrKmtH3KFYaf0yUH9KnEjo5cDYBXk21UHAucMlVw9Mi
Ws60vLMzo6hjgIQTEIMnuSQzumrToWKAJa91tBPHBcjTHxVNtmJqZtOEuuWDI2m8
H3ua/Y0B5vKvTuQE0nBHFE1T1CvYG+VRGzgZXzvfeWrDViDtTdk3sgHfPO6AeSCE
nnalrItvtFSE0PWTMKUQX2ETPviprJ+bi1+zXSp3WNbz2adoLVPlu8x3dW3lnOj7
o4nUHdk5JAt6siyaEWIn
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
    Session-ID: 6C7D2EA4D73687D8F2F3D8F89AB53BBBDD10AD5A3024FA8D7207BBDA092F4F6D
    Session-ID-ctx:
    Resumption PSK: 115CB5817873845A4226956472FE7851CF51678BF3CD63F2F07F0DD81FF58A3D5D8EAE0F4C281CB2A5BF69DD47017E86
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - d7 30 5d 8c ad 50 97 43-d7 8b a9 6e 48 80 50 cd   .0]..P.C...nH.P.
    0010 - 6b 3a 6d ad 83 66 f4 bd-02 47 d3 46 2e b2 99 10   k:m..f...G.F....
    0020 - 8b a5 5c 0e ca 24 70 29-52 88 95 35 be 26 85 a3   ..\..$p)R..5.&..
    0030 - b1 ba c3 78 90 5d 6d df-75 f0 18 95 f9 61 a6 59   ...x.]m.u....a.Y
    0040 - 3a 9b ba 22 6b 3b e1 ee-48 c0 b7 3c 80 b1 ed 7d   :.."k;..H..<...}
    0050 - b9 5f 99 d5 bc 69 bb 7d-aa 83 17 7e 4f fb 73 2c   ._...i.}...~O.s,
    0060 - fe bc b8 88 b4 ef 75 c0-45 9b 8c b8 12 09 02 63   ......u.E......c
    0070 - ae 30 69 7a 57 36 3a 84-c3 22 6e 55 97 a6 96 0b   .0izW6:.."nU....
    0080 - 4a 28 be fb 50 6f b2 5e-a2 31 30 e3 28 08 f5 4a   J(..Po.^.10.(..J
    0090 - cf 03 32 08 cd 62 fa e4-b7 82 31 44 c0 dc a9 4e   ..2..b....1D...N
    00a0 - de a7 82 8d 45 c0 9d 82-47 3d ee 9c ba 7f 45 e7   ....E...G=....E.
    00b0 - 62 47 5d 1d 1d 11 3d c0-eb 23 0c d1 ae fe 86 34   bG]...=..#.....4
    00c0 - ed 69 bf 8a 85 96 67 02-65 90 9c 73 5f 37 34 41   .i....g.e..s_74A

    Start Time: 1694744637
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
    Session-ID: 7652104B873F3824808DB042388C7BDA186243CE676AB3AD29B541A1B631D0B2
    Session-ID-ctx:
    Resumption PSK: 25F9B2A2311970D93F11334DF53B808A4589380630768C47356DCB89BDE31D116A1BED5773269317E473A82F8DC9167C
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - d7 30 5d 8c ad 50 97 43-d7 8b a9 6e 48 80 50 cd   .0]..P.C...nH.P.
    0010 - a6 91 28 98 f4 c3 8b 31-fc 04 ac 31 ee e1 b2 5e   ..(....1...1...^
    0020 - e7 ee 59 3b 32 6c a7 e8-91 b0 d0 7f e1 38 cc b1   ..Y;2l.......8..
    0030 - b7 fe 1e 55 5a 7b 27 0a-92 19 b2 38 9e 61 3f fe   ...UZ{'....8.a?.
    0040 - e9 c0 1b 69 cd ab 95 a8-64 ec a4 cc bb 56 a8 19   ...i....d....V..
    0050 - c6 f8 84 b0 40 3c 16 06-a3 d6 60 1a e7 aa 6c 00   ....@<....`...l.
    0060 - e8 56 69 38 c9 1e bd 6e-af 64 ed 4e 1b 99 dd c6   .Vi8...n.d.N....
    0070 - 17 da cf ed b0 ef 5a b7-89 d8 3d 01 8e ee 7c a3   ......Z...=...|.
    0080 - fa ea f0 b9 40 34 fe 15-30 22 37 7f a4 71 74 67   ....@4..0"7..qtg
    0090 - cb a9 a1 75 25 d8 82 33-b3 78 8e 93 35 be 48 49   ...u%..3.x..5.HI
    00a0 - cf 58 81 83 2c c3 4d d4-d9 a7 5b 04 d2 41 0c d9   .X..,.M...[..A..
    00b0 - e8 91 26 a9 98 42 d1 57-82 04 90 e8 1d b2 3b 67   ..&..B.W......;g
    00c0 - 28 e3 57 17 ca aa d7 2f-28 16 82 40 33 71 96 90   (.W..../(..@3q..

    Start Time: 1694744637
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
bandit16@bandit:~$

C:\Users\Timbo>notepad llave.txt
C:\Users\Timbo>type llave.txt
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
C:\Users\Timbo>ssh -i llave.txt

bandit17@bandit.labs.overthewire.org -p2220

bandit17@bandit:~$ cat /etc/bandit_padd/bandit17
cat: /etc/bandit_padd/bandit17: No such file or directory
bandit17@bandit:~$ cat /etc/bandit_pass/bandit17
VwOSWtCA7lRKkTfbr2IDh6awj9RNZM5e
bandit17@bandit:~$ exit
```

## Notas adicionales
`openssl s_client` y `nmap` son dos herramientas de línea de comandos que se utilizan para diferentes propósitos relacionados con la seguridad y la administración de redes.

1. **openssl s_client**:
    
    `openssl s_client` es una herramienta que se utiliza para establecer conexiones seguras a servidores que utilizan el protocolo SSL/TLS. Esto es útil para verificar la seguridad de un servidor web o correo electrónico, por ejemplo. Cuando ejecutas `openssl s_client`, puedes conectarte a un servidor y ver detalles sobre el certificado SSL/TLS que utiliza, verificar la cadena de certificados y asegurarte de que la comunicación sea segura.
    
    Por ejemplo, si deseas verificar el certificado SSL de un sitio web, puedes ejecutar:
    
    `openssl s_client -connect example.com:443`
    
    Esto te mostrará información sobre el certificado SSL del sitio web.
    
2. **nmap**:
    
    `nmap`, por otro lado, es una herramienta de escaneo de redes. Se utiliza para explorar y mapear redes informáticas, descubrir dispositivos en una red y determinar qué servicios están disponibles en esos dispositivos. Es una herramienta poderosa para los administradores de redes y los profesionales de seguridad informática.
    
    Por ejemplo, para escanear una red y ver qué dispositivos están conectados y qué puertos están abiertos en esos dispositivos, puedes ejecutar:
    
    `nmap 192.168.1.0/24`
    
    Esto escaneará todos los dispositivos en la red con la dirección IP que comienza con "192.168.1" y mostrará información sobre los servicios que están en ejecución en esos dispositivos.
    
En resumen, `openssl s_client` se utiliza para verificar la seguridad de las conexiones SSL/TLS, mientras que `nmap` se utiliza para explorar y mapear redes y descubrir servicios en dispositivos de red. Ambas herramientas son importantes para administrar y asegurar redes y servidores.
`ssh -i llave.txt`, se utiliza para iniciar una conexión SSH a un servidor remoto utilizando una clave privada específica llamada "llave.txt".
- `ssh`: Este es el comando principal utilizado para iniciar una conexión SSH (Secure Shell) a un servidor remoto. SSH es un protocolo de seguridad utilizado para acceder y administrar sistemas de forma segura a través de una red.
    
- `-i llave.txt`: Esta parte del comando especifica la clave privada que se utilizará para autenticarse en el servidor remoto. La opción `-i` se utiliza para proporcionar la ubicación de la clave privada. En este caso, estás indicando que la clave privada se encuentra en un archivo llamado "llave.txt" en el directorio actual.
- Por lo tanto, cuando ejecutas este comando, SSH intentará establecer una conexión segura con un servidor remoto utilizando la clave privada "llave.txt" para la autenticación. Si la clave privada es válida y corresponde a la clave pública configurada en el servidor remoto, se te permitirá acceder al servidor de forma segura.

Es importante tener en cuenta que este comando es una parte de una instrucción más completa para establecer una conexión SSH. Generalmente, se incluiría también el nombre de usuario y la dirección IP o el nombre de dominio del servidor remoto. Por ejemplo: ssh -i llave.txt usuario@direccion_ip_del_servidor
## Referencias