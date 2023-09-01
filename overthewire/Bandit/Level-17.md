# Level-16 -> Level-17

### Level Goat
The credentials for the next level can be retrieved by submitting the password of the current level to **a port on localhost in the range 31000 to 32000**. First find out which of these ports have a server listening on them. Then find out which of those speak SSL and which don’t. There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it.
### Credentials
ssh bandit16@bandit.labs.overthewire.org -p 2220
password: **JQttfApK4SeyHwDlI9SXGR50qclOAil1**
### Solution
```shell
bandit16@bandit:~$ nmap -sV localhost -p 31000-32000
Starting Nmap 7.80 ( https://nmap.org ) at 2023-08-24 17:38 UTC
Nmap scan report for localhost (127.0.0.1)
Host is up (0.00013s latency).
Not shown: 996 closed ports
PORT      STATE SERVICE     VERSION
31046/tcp open  echo
31518/tcp open  ssl/echo
31691/tcp open  echo
31790/tcp open  ssl/unknown
31960/tcp open  echo
1 service unrecognized despite returning data. If you know the service/version, please submit the following fingerprint at https://nmap.org/cgi-bin/submit.cgi?new-service :
SF-Port31790-TCP:V=7.80%T=SSL%I=7%D=8/24%Time=64E795B1%P=x86_64-pc-linux-g
SF:nu%r(GenericLines,31,"Wrong!\x20Please\x20enter\x20the\x20correct\x20cu
SF:rrent\x20password\n")%r(GetRequest,31,"Wrong!\x20Please\x20enter\x20the
SF:\x20correct\x20current\x20password\n")%r(HTTPOptions,31,"Wrong!\x20Plea
SF:se\x20enter\x20the\x20correct\x20current\x20password\n")%r(RTSPRequest,
SF:31,"Wrong!\x20Please\x20enter\x20the\x20correct\x20current\x20password\
SF:n")%r(Help,31,"Wrong!\x20Please\x20enter\x20the\x20correct\x20current\x
SF:20password\n")%r(SSLSessionReq,31,"Wrong!\x20Please\x20enter\x20the\x20
SF:correct\x20current\x20password\n")%r(TerminalServerCookie,31,"Wrong!\x2
SF:0Please\x20enter\x20the\x20correct\x20current\x20password\n")%r(TLSSess
SF:ionReq,31,"Wrong!\x20Please\x20enter\x20the\x20correct\x20current\x20pa
SF:ssword\n")%r(Kerberos,31,"Wrong!\x20Please\x20enter\x20the\x20correct\x
SF:20current\x20password\n")%r(FourOhFourRequest,31,"Wrong!\x20Please\x20e
SF:nter\x20the\x20correct\x20current\x20password\n")%r(LPDString,31,"Wrong
SF:!\x20Please\x20enter\x20the\x20correct\x20current\x20password\n")%r(LDA
SF:PSearchReq,31,"Wrong!\x20Please\x20enter\x20the\x20correct\x20current\x
SF:20password\n")%r(SIPOptions,31,"Wrong!\x20Please\x20enter\x20the\x20cor
SF:rect\x20current\x20password\n");

Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 98.51 seconds
bandit16@bandit:~$ openssl s_client -connect localhost:31790
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = localhost
verify error:num=10:certificate has expired
notAfter=Aug 24 10:24:38 2023 GMT
verify return:1
depth=0 CN = localhost
notAfter=Aug 24 10:24:38 2023 GMT
verify return:1
---
Certificate chain
 0 s:CN = localhost
   i:CN = localhost
   a:PKEY: rsaEncryption, 2048 (bit); sigalg: RSA-SHA1
   v:NotBefore: Aug 24 10:23:38 2023 GMT; NotAfter: Aug 24 10:24:38 2023 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIDCzCCAfOgAwIBAgIEYE8BcDANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjMwODI0MTAyMzM4WhcNMjMwODI0MTAyNDM4WjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQC4
iGiRkLj4/4N8SUh4tWuolh4+fbx7Bvjod7lbN/3mTSTRP3kbMCPe6mbPE2MxxTn4
dI0tbwFvo2N1Iv7zuLZHs2U8FTexZqZd0OPkJ9vZn5/TczGS4Uhu2mP9fVOn9gXo
6sHPdUpFoUo6Am4dPOY8qmiyVIbFNn3aRVcGAd8KNV6+p4nfrYQL98DJcCaXsWzO
Cc06SLSyEbSz8fJprUIQtZ81amhnCo21TWu3LVi3cv3QFl/X2Z5T3CcLNW3CtaqH
hwdWGOJh3u+DBH7+W0OcToDtCFZQ4g19/+qFUy14AWVveaa5r694ohjTdMPfJrue
znfpDfnSnItQpJMuEqB1AgMBAAGjZTBjMBQGA1UdEQQNMAuCCWxvY2FsaG9zdDBL
BglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0ZWQgYnkgTmNhdC4g
U2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3DQEBBQUAA4IBAQC2
FmFnG+nhWYYJC6uj70vNqJj6bNZffOT+HB3iPy686+bWb2hV4fayDnhjLJ/RXJql
daTA98yfHZ6mvgAmZE65tBCuf51GWAWt90cVV4u8NQR3unO9ut8C5nOSPfj6Gx65
Yy34+fTaB/vj+oP3gbpfvN8M+pTcM5NGT1WVrBQPm4OE4I3q+J9PdCVz+7nIN/+K
d+0cLEwzRFY+EJY0oMy4SdiQjZHQL4eR0/Uhxw15mJUrVLbrYro2Uo4Lyxhvnhu6
cxsS50ZN9YPgkuFWqUZXQCzVG3cFMctADcbHYzp7Y6B44H9iTR30U9iOZzSAhnZ3
gTTxxLtsR46KiWj8EJwq
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
    Session-ID: 58ABF4505D054E74E223735F720A4DA1AEABD6393BF47A8AFBAEDB568CAA79EF
    Session-ID-ctx:
    Resumption PSK: 7E03A9276A083A5C879B23D3D35AEFC1CE970133121EACABEBF28094EB54AEDF2E5883B0693106CFD535D0735AC2055D
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 0e 88 a9 fe 74 9a 43 ea-b6 fb 58 5f 44 8e ac 3b   ....t.C...X_D..;
    0010 - 4b 01 7f e9 a2 11 d0 8c-67 99 45 2b 32 2a 73 b8   K.......g.E+2*s.
    0020 - 90 9d 66 e6 bd b1 ff 5a-7e 2a 27 ca 4c e1 61 58   ..f....Z~*'.L.aX
    0030 - a2 0b 90 1c b7 c5 45 71-ca 8f 87 a4 e2 da 92 a6   ......Eq........
    0040 - 2f 45 01 62 30 ce e7 91-f5 9d 5a af 42 01 02 bb   /E.b0.....Z.B...
    0050 - c8 ad b1 d7 ba 1c 4f 12-1f a9 20 b8 33 79 69 a8   ......O... .3yi.
    0060 - 52 4d 15 68 b3 c5 63 46-e1 4b 53 4d 3c 6a 87 c3   RM.h..cF.KSM<j..
    0070 - fa ed 95 f1 e2 aa c3 cf-da b7 63 36 a2 5a 14 21   ..........c6.Z.!
    0080 - 1b 6b 81 6c b7 f2 44 cf-cb 2a 54 91 ae de 91 c9   .k.l..D..*T.....
    0090 - 40 18 f5 79 01 fb be 0e-44 c6 03 09 cd 91 50 3a   @..y....D.....P:
    00a0 - 90 93 43 47 7b 06 83 12-91 ca 4b 31 e0 de 6c 9b   ..CG{.....K1..l.
    00b0 - 8c fa f6 13 39 cb 8b 85-4e c0 a4 10 83 7a 01 72   ....9...N....z.r
    00c0 - 95 5d 42 e9 09 44 83 26-e4 e5 ec 2b 9e 0c 75 fa   .]B..D.&...+..u.

    Start Time: 1692899090
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
    Session-ID: 7F5BE6BA9147C0174FDCA6FA123C6DED4C2F42F678AB96EC3F413C70E42AFAFA
    Session-ID-ctx:
    Resumption PSK: D4FFF54BE667E23B020E3E34F93212A067414EE60C0E39E6BE988AFFD333D8F7CF5B70E4D5B2B9691EC75F2D4417129C
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 0e 88 a9 fe 74 9a 43 ea-b6 fb 58 5f 44 8e ac 3b   ....t.C...X_D..;
    0010 - 85 af df e7 b1 57 ae 3f-50 54 a5 8a 00 fe 8f b4   .....W.?PT......
    0020 - 0d 97 22 0a 36 c6 61 13-06 0e c1 3f f1 db d5 19   ..".6.a....?....
    0030 - 81 0a 16 d9 9a 50 f8 3f-ea 63 06 01 bf a3 bf d5   .....P.?.c......
    0040 - ff 80 8a 39 2f 7c 3f ef-c8 94 51 c4 7b 36 11 78   ...9/|?...Q.{6.x
    0050 - a8 73 bf 30 0c 4f 83 d2-e8 3e 6a 7c 06 70 be dd   .s.0.O...>j|.p..
    0060 - 25 4a dc ce e2 26 f8 38-fc 92 85 51 41 ff 81 a3   %J...&.8...QA...
    0070 - d2 8d ff 31 52 ba 9d b7-22 07 bb a3 c2 b8 44 bb   ...1R...".....D.
    0080 - dd 00 db c4 dd 28 ae 81-b0 83 ed 7f 28 cf 47 75   .....(......(.Gu
    0090 - c9 72 0d 40 dc 68 6f e7-7a 20 7c f3 a2 53 1a 12   .r.@.ho.z |..S..
    00a0 - c0 3c 71 78 26 82 19 81-89 58 c0 dd 88 5c 8f ef   .<qx&....X...\..
    00b0 - ef d9 96 2d 26 a3 93 37-bc 26 47 56 78 a4 86 ad   ...-&..7.&GVx...
    00c0 - 81 be f6 30 5e 16 3f 25-4d b3 5f 86 41 54 c5 ba   ...0^.?%M._.AT..

    Start Time: 1692899090
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
```
### Summary
Primero, necesitamos encontrar puertos abiertos entre 31000 y 32000 en localhost y verificar qué servicios se están ejecutando en ellos. He utilizado la detección de servicios de . (Esta tarea podría dividirse buscando primero los puertos abiertos y, a continuación, haciendo el descubrimiento del servicio sólo en estos puertos

Entonces, nos dice que cinco puertos están abiertos. Sólo dos puertos (31518 y 31790) utilizan SSL. Nmap también nos dice que el puerto 31518 ejecuta solo el servicio de eco. El puerto prometedor parece ser el puerto 31790, que ejecuta un servicio desconocido.

Ahora usamos OpenSSL nuevamente para conectarnos a este puerto en localhost y enviar la contraseña.

nmap:
	-sV: Sondear puertos abiertos, para obtener información de servicio/versión

El resultado es una clave SSH privada. Entonces, creamos un archivo (lo llamé 'sshkey17.private') para poner la clave y, como en el [nivel 14](https://mayadevbe.me/posts/overthewire/bandit/level14/), debemos asegurarnos de que el archivo solo tenga permisos para el usuario.
### FLAG
**-----BEGIN RSA PRIVATE KEY-----
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
-----END RSA PRIVATE KEY-----** 