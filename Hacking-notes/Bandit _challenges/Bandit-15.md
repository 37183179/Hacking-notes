
# Bandit challenges
# Bandit 15#

## Goal

The password for the next level can be retrieved by submitting the password of the current level to **port 30001 on localhost** using SSL encryption.

**Helpful note: Getting “HEARTBEATING” and “Read R BLOCK”? Use -ign_eof and read the “CONNECTED COMMANDS” section in the manpage. Next to ‘R’ and ‘Q’, the ‘B’ command also works in this version of that command…**

## Access data

+ Username: bandit15
+ Password: jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt
+ Port: 2220
+ Server: bandit.labs.overthewire.org
## Solution

```bash

ssh bandit15@bandit.labs.overthewire.org -p 2220
openssl s_client -connect localhost:30001
CONNECTED(00000003)
Cannot use SSL_get_servername
depth=0 CN = localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = localhost
verify error:num=10:certificate has expired
notAfter=Feb 18 10:54:16 2024 GMT
verify return:1
depth=0 CN = localhost
notAfter=Feb 18 10:54:16 2024 GMT
verify return:1
---
Certificate chain
 0 s:CN = localhost
   i:CN = localhost
   a:PKEY: rsaEncryption, 2048 (bit); sigalg: RSA-SHA1
   v:NotBefore: Feb 18 10:53:16 2024 GMT; NotAfter: Feb 18 10:54:16 2024 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIDCzCCAfOgAwIBAgIEcjY6OTANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjQwMjE4MTA1MzE2WhcNMjQwMjE4MTA1NDE2WjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQCz
TX1NLedZhpQfXiWbWWD2BlNYjANpj+TnzUOI9ZbKJnOQJAbFfWZLA6No7XOStgje
+RPIoAHrX42G95VDfWtRms+qCsCTlUaS9291dZJQ3iOjBIE+PvmRcGdUlFJXDYa6
E61L2DKLbb8YSAnSuUPG3K7CtdxJpA5DpCBCmHEA9t5gZ5HGo9Gt9Kay9lhApX78
ocytwwHG15LplXI6LQB3ykhyCAcfljR3azd90T83dz7kLyM7yIMt60k1kemuX6RW
qSvkCvxmckRFoQPjwKZUopGLlhcC58Kb2xlwEGK+9j/ibBRkmEdBkOOeb5pJol7K
Wkd9LdG0nTWrggni7EKbAgMBAAGjZTBjMBQGA1UdEQQNMAuCCWxvY2FsaG9zdDBL
BglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0ZWQgYnkgTmNhdC4g
U2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3DQEBBQUAA4IBAQCA
j53OECoyjZMkHINZj35xk2kKQc9Jj9XjoCE0HlooUWd1ETik/2TkIbdWenozDrgH
10Jqmu/zAEhQkfFALBXCR7Vo0319yvR3rlnC2TdzMeBeUQ/n6ivPsCCL6SF8UTWT
XZJoTEfmp+Ma4zup/mEs23uO/FQ0J3LmSgICtXzPCA09M/ffj2UgTENdTHDltQxl
nQpzF+U40+bg/2PQ83XOTQJbZVbU2FnP/MitSYycxemLJXzbdsIxQhQy0VmTY73E
ZFemHVTbzEzcsCJRak4AyPZ9Zpi2uozHA8r1PqtnDzsN5FBFwuJxCuc+F8QeHh9e
QoyfsotkA6BO0LBqWNvE
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
    Session-ID: 4288F5039985031F142E918E0DABAC7384B5B216C048B436E540B606998C87DB
    Session-ID-ctx:
    Resumption PSK: EF378AFC31B61AF9C00A65E3DD27C223704D0763781A794300552EBD4DA78A3A19673744A19E46F46C3C0D6613182CE5
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - dc 1b 67 7e 6b 49 ec f9-e1 0a 8a 6e cb ac b4 e6   ..g~kI.....n....
    0010 - e6 59 65 90 f2 a2 54 84-b6 fd 50 05 86 31 73 b8   .Ye...T...P..1s.
    0020 - 4f 03 95 97 a4 18 03 9d-82 a3 6d 77 6c 64 29 bb   O.........mwld).
    0030 - 7d f6 df c6 32 48 c0 74-2b be 95 79 86 35 31 b0   }...2H.t+..y.51.
    0040 - 2b 2b b1 d9 4d 91 c3 a5-b2 19 76 2d 97 7d bc bc   ++..M.....v-.}..
    0050 - d8 3f 5b b6 a9 ba 81 8c-7f 79 81 eb ec c7 b2 3d   .?[......y.....=
    0060 - 3d 2b 0c 4a ae 1b 8f 85-35 ea a5 64 89 33 20 be   =+.J....5..d.3 .
    0070 - 64 b7 e2 1d 8e cc 1e 3e-6b 53 8d 64 96 d5 86 78   d......>kS.d...x
    0080 - a0 a8 c2 0a 7c 84 11 fa-f9 b6 2b 46 40 72 c1 68   ....|.....+F@r.h
    0090 - bc fb fb 78 ef a7 70 e3-90 0e 8f ae 25 e0 92 61   ...x..p.....%..a
    00a0 - 90 68 20 19 ea 87 72 34-92 2d e7 62 ae ce 4d 0b   .h ...r4.-.b..M.
    00b0 - 15 73 33 69 bd bb 06 bd-80 6b fb 66 2d 16 ad 84   .s3i.....k.f-...
    00c0 - 23 4c d5 46 53 8b e5 49-51 38 86 75 ce 46 4e b3   #L.FS..IQ8.u.FN.

    Start Time: 1708370536
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
    Session-ID: EC162EC951029112099D079575175E7595476E1FCE0D8DD837AEB1E2B72C1694
    Session-ID-ctx:
    Resumption PSK: DD00EA6A2667A1098BADB3365F76AEE9EDFF4A03CAFDACC0377757C859FF134B13AE87F64E63C466C59DF208A2C257CD
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - dc 1b 67 7e 6b 49 ec f9-e1 0a 8a 6e cb ac b4 e6   ..g~kI.....n....
    0010 - f3 69 e1 e9 a0 5f 9a 7b-7b 01 04 98 86 d5 23 58   .i..._.{{.....#X
    0020 - 5e cd c4 83 58 24 65 86-38 d5 fe 44 7e 4d b9 df   ^...X$e.8..D~M..
    0030 - 9c b4 da e8 40 67 de c7-fd 07 91 1f 5a c7 59 52   ....@g......Z.YR
    0040 - 6e 56 96 bc 79 e0 83 55-cf da c2 73 28 5e db 88   nV..y..U...s(^..
    0050 - b6 79 36 70 45 f6 1e 2a-59 98 49 10 a4 bc d2 57   .y6pE..*Y.I....W
    0060 - 55 90 ec 5f a3 83 97 e5-13 39 7a 13 98 63 f1 6a   U.._.....9z..c.j
    0070 - 97 e2 85 de c1 2f 7b 05-2f 60 01 20 bf 07 16 54   ...../{./`. ...T
    0080 - 42 2f 2f 4b 95 49 85 39-60 04 f0 f3 47 4c 0e b4   B//K.I.9`...GL..
    0090 - 2d 8b 78 ef f4 63 b6 ad-82 f6 ee 9a f1 0e 07 e5   -.x..c..........
    00a0 - 2e 6e 64 df 91 78 6c 33-95 98 44 9f ac 49 78 a8   .nd..xl3..D..Ix.
    00b0 - ed 93 6f 9d 6d 4e bd de-9a 7e eb 83 82 4b 7c 8e   ..o.mN...~...K|.
    00c0 - 4a 89 1c 75 20 0f e4 96-a0 21 05 bd 90 23 9f bc   J..u ....!...#..

    Start Time: 1708370536
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

````

## Notes

+ **`openssl:`** This is the command-line tool for interacting with OpenSSL, a cryptography and SSL/TLS library.

+ **`s_client:`** This is a subcommand of `openssl` specifically designed for testing SSL/TLS client connections.

## References