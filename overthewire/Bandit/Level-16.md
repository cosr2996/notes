# Level-15 -> Level-16

### Level Goat
The password for the next level can be retrieved by submitting the password of the current level to **port 30001 on localhost** using SSL encryption.

**Helpful note: Getting “HEARTBEATING” and “Read R BLOCK”? Use -ign_eof and read the “CONNECTED COMMANDS” section in the manpage. Next to ‘R’ and ‘Q’, the ‘B’ command also works in this version of that command…**
### Credentials
ssh bandit15@bandit.labs.overthewire.org -p 2220
password: **jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt**

### Solution
```shell
bandit15@bandit:~$ openssl s_client -connect localhost:30001
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
MIIDCzCCAfOgAwIBAgIENdM2CzANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjMwODI0MTAyMzM4WhcNMjMwODI0MTAyNDM4WjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQC8
tsFynIwW0A3/9sYlv/DlII3PoY7n06w4oA9jXWBuVos2EkYitIUt7oPZbmKHIUr4
ROyiGDtj0YxjZfamWOkPgYmiIJFzy0rhqwyjKH+Dcod5nh4MJehZ8FOJeedByWKL
turSTPPJh98q1xB2KQ4Bwk7wA5hpkXzIGg4OKN1VicuB7CIw3JMnua63a0KxSOLt
ERvXi5kPa4Ad2rMwT9ZlYCoPr91RZ8qmutsfurnTG7dTOuVfz40pqvTxQL8FkVwt
iPbmBiigsJux1jFIZeX3NWYPZcpYwTY2OoOdQ+T+OK1u0irykopfpWIVCk7sQBon
oI23/7iyASdsPkQd7x4jAgMBAAGjZTBjMBQGA1UdEQQNMAuCCWxvY2FsaG9zdDBL
BglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0ZWQgYnkgTmNhdC4g
U2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3DQEBBQUAA4IBAQCP
sK5Xp9yJA8QmkGAod+FxDYWEDzjhX5b1P4AprtOjtalM6Ms5BbmE417ya/5Awijc
xhtlgHRH4r3ViBT4BrVeNiM24ISiUqQpqBr9Y4GRfcbd5ZRjHYl6XadwPjmmnltR
LZ2II5QSOrdsCoH5JsiovR2WiuD+oc2XoYMqqAMGZxsZw+Z1do8t0nSr4qA7bjxe
v869epRoDfBuGuQTVU5kkyxi+oJ2Xpx43ZRcBUpuXT4CiSBENXaaZUEQpelSpP3w
5HjLBvUWkc/KV4GAO4irrxFcjxKcpukznmgpUgkJONFLn2XPJvtf011OG9eJWYNA
tuBsXM83BxPj5MWKpCed
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
    Session-ID: 111C81201395EA76890F9633AB8F5D58519B3B6DEFBC8BE29406F7BB00CC035A
    Session-ID-ctx:
    Resumption PSK: 7368B0E82E4D28DAED42C03FA1CE375F47D467CF7DB55D7DD7735BA4FD4FA728A81FD09540EE477B892E06E8E74C087F
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 21 32 55 da 61 f6 6f 3b-d2 1c fd 80 cd 9e b0 23   !2U.a.o;.......#
    0010 - f0 b5 44 0d ec 88 ba 3f-f6 87 0f 2c b8 3d 4a 43   ..D....?...,.=JC
    0020 - ef 0f 68 b0 d9 cf a7 be-88 64 97 ee 07 1d e0 40   ..h......d.....@
    0030 - af e5 2c ee 14 00 78 8e-7c 6d 68 d6 f6 0b 5d d3   ..,...x.|mh...].
    0040 - 85 1b 8c 97 91 61 70 19-ec 41 68 9e f8 2f 76 56   .....ap..Ah../vV
    0050 - cb 0f b4 84 be d9 97 b4-87 b4 73 c1 c4 21 2c 00   ..........s..!,.
    0060 - c4 57 f7 9f d3 b2 a4 b4-d8 3e 5d 33 54 dd fd f3   .W.......>]3T...
    0070 - 9c 93 a9 71 5d c6 4e 7e-8f 25 27 e2 40 66 9d f2   ...q].N~.%'.@f..
    0080 - 8f df a5 b6 fb 31 0e 3b-83 5e ef 41 08 bd b0 c1   .....1.;.^.A....
    0090 - 14 0a 81 1a 43 96 27 1d-5c 7b fe 79 e5 80 cf 9a   ....C.'.\{.y....
    00a0 - 13 b9 e0 86 91 77 31 91-f8 26 2b 21 de 58 ad 42   .....w1..&+!.X.B
    00b0 - 89 63 1b 52 a3 17 2f 54-b5 2b f7 e4 55 b2 cb c8   .c.R../T.+..U...
    00c0 - f5 22 ae 95 d7 52 6f f3-e0 f8 2e 23 78 c1 e5 33   ."...Ro....#x..3

    Start Time: 1692897397
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
    Session-ID: 61A2E9F1599F8B112C087919E3ED3BAE67E9196D82E6E3DFBA9BBF708DF61928
    Session-ID-ctx:
    Resumption PSK: 313BFDD12855FA878A79C536C8F08FF05E12D45FEA54A20F1F7A18FB7182920E19E7C1F9D5EE7F8E4182B191E76F35ED
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 21 32 55 da 61 f6 6f 3b-d2 1c fd 80 cd 9e b0 23   !2U.a.o;.......#
    0010 - fa 28 34 92 bd 15 11 83-53 04 3a 9f e3 5e 15 0a   .(4.....S.:..^..
    0020 - d9 87 6b 93 b3 f8 22 ca-e5 24 c5 87 6a 7f 57 d2   ..k..."..$..j.W.
    0030 - 87 19 1d 8a cf 09 c9 dc-1e 5f e1 fa cb 95 de 8f   ........._......
    0040 - bf 2a c6 a0 8a b7 4a 55-94 53 ce 35 89 4a f8 2d   .*....JU.S.5.J.-
    0050 - 39 51 ec 36 ac 17 c6 6b-f5 38 e9 52 fc b2 0d f0   9Q.6...k.8.R....
    0060 - 94 ad 8a 47 22 f9 a6 d4-08 f1 21 97 92 46 0f e5   ...G".....!..F..
    0070 - db e7 1b 07 b9 d4 e7 bb-3e 05 8a 31 b1 e6 23 69   ........>..1..#i
    0080 - 0f 8a 5b d8 80 2e e2 1a-25 f5 2c 73 e9 81 62 82   ..[.....%.,s..b.
    0090 - 15 39 dc 26 88 18 69 d9-11 30 26 c5 a1 47 8e 83   .9.&..i..0&..G..
    00a0 - 17 29 83 0d 5c f0 1b 76-83 82 97 8f cd 24 d8 dc   .)..\..v.....$..
    00b0 - 4f 2c e9 87 d2 52 35 e6-bd 37 0f a3 f9 d1 96 30   O,...R5..7.....0
    00c0 - ad bb 0f fa 02 35 86 d4-69 d6 6a 5e 68 a5 8a 54   .....5..i.j^h..T

    Start Time: 1692897397
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
```
### Summary
OpenSSL es una biblioteca para la comunicación segura a través de redes. Implementa los protocolos criptográficos Transport Layer **Security** (TLS) y **Secure Sockets Layer** (SSL) que, por ejemplo, se utilizan en HTTPS para proteger el tráfico web.

`openssl s_client` es la implementación de un cliente simple que se conecta a un servidor mediante SSL/TLS.

para eso usamos el comando openssl s_client -connect host:pueto y le pasamos la contraseña actual 
### FLAG
**JQttfApK4SeyHwDlI9SXGR50qclOAil1** 