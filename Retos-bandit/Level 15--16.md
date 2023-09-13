# Level 15--16

## Objetivo
**Nota útil: ¿Obtienes “HEARTBEATING” y “Read R BLOCK”? Utilice -ign_eof y lea la sección "COMANDOS CONECTADOS" en la página de manual. Junto a 'R' y 'Q', el comando 'B' también funciona en esta versión de ese comando...**
## Datos de acceso al nivel
```
Server    : bbandit15@bandit.labs.overthewire.org
Password  : jN2kgmIXJ6fShzhT2avhotn4Zcka6tnt

```
## Solución
```bash
ssh bandit15@bandit.labs.overthewire.org -p 2220

bandit15@bandit:~$ openssl s_client -connect localhost:30001
CONNECTED(00000003)
Can't use SSL_get_servername
depth=0 CN = localhost
verify error:num=18:self-signed certificate
verify return:1
depth=0 CN = localhost
verify error:num=10:certificate has expired
notAfter=Sep 12 19:28:36 2023 GMT
verify return:1
depth=0 CN = localhost
notAfter=Sep 12 19:28:36 2023 GMT
verify return:1
---
Certificate chain
 0 s:CN = localhost
   i:CN = localhost
   a:PKEY: rsaEncryption, 2048 (bit); sigalg: RSA-SHA1
   v:NotBefore: Sep 12 19:27:36 2023 GMT; NotAfter: Sep 12 19:28:36 2023 GMT
---
Server certificate
-----BEGIN CERTIFICATE-----
MIIDCzCCAfOgAwIBAgIEC45O9TANBgkqhkiG9w0BAQUFADAUMRIwEAYDVQQDDAls
b2NhbGhvc3QwHhcNMjMwOTEyMTkyNzM2WhcNMjMwOTEyMTkyODM2WjAUMRIwEAYD
VQQDDAlsb2NhbGhvc3QwggEiMA0GCSqGSIb3DQEBAQUAA4IBDwAwggEKAoIBAQDm
l+M89lI121voS7dkGZ7EZ9U7lMwJDqs2PJdnUxmTCqPD7GFPoHjtWgM2q4oEmRnz
LILu0seqdj4DOHVpljo1Su0pZUIOVp/2o7WZB0OQNw4k1syYI4W0o83GZCLINGfk
Kv+jQT5+F/0/xrPlZ0c4R4v8yoIXYHn1XnXTomUPdCe1STkbfuEluPVsUYtOJLr2
JB1oM56rp614mEHUlKwZombyimmbw3K6lh73mn5rUKPYC6ZKueEhcC9v2WULSpuC
yK4JX3lYuT/I4VvAzTN6sHAsHF8a6Y4ve6WSt5id1MRChhbZbsDE7zGVUEndyneY
4PKZGinfeUcaqBI9/jepAgMBAAGjZTBjMBQGA1UdEQQNMAuCCWxvY2FsaG9zdDBL
BglghkgBhvhCAQ0EPhY8QXV0b21hdGljYWxseSBnZW5lcmF0ZWQgYnkgTmNhdC4g
U2VlIGh0dHBzOi8vbm1hcC5vcmcvbmNhdC8uMA0GCSqGSIb3DQEBBQUAA4IBAQAF
5+5M/8s5aRTQBNsmau7HRbZp+BEeprujSN+5HFxZWyfOoLlAdXFO9tlbhgyMTZ0S
VN8xQB9Oxm07xC8WUakj6yD004S+7N82Nqy9fznaE3DLVGMzwMht8c2NbByfb+iN
x8MNRcWt4GMCV9jjIbuysE6FWFG5CEzaL4T7jCQldbIQpVVHFdaeHk/TmhD4Z6uj
/8az/n1ZdT40rO+QMU1/p3cPTPIeqrQymrtQAQ3wqsGANqOvzZ0IyLo5zaWnPnZL
bO4Q37dkc8VhiDP/7ok++l/Q0qVOVKR6YbdqyqXIQBw35AlpEGvqdaNpDgI1dCgI
mLiJepQjf3IUv/q/OH59
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
    Session-ID: 934AACD662EB878219BEBE8A35D237C62A7218ECD1781446859337AE1C42BC2D
    Session-ID-ctx:
    Resumption PSK: 1B647E98D8C2951C230012F6D1985E05A64720258A42DABB84682539B209317C613411A349A158CDB496EA973FA90E99
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - ef 3c 60 dd c0 30 4a 16-cc e8 65 95 7d f5 1d 44   .<`..0J...e.}..D
    0010 - d0 f1 6f d8 b4 ac 89 f1-41 33 44 5b 0e 28 73 15   ..o.....A3D[.(s.
    0020 - 53 68 2d 6d e0 cf 81 c1-c1 af 7d 76 f4 60 86 9f   Sh-m......}v.`..
    0030 - fc 01 e6 66 b2 78 dc 85-13 ad 48 20 c7 43 be 2b   ...f.x....H .C.+
    0040 - 1d 0d 2f ec e0 6d 0f 98-eb 9f 1b e1 70 2f 15 a1   ../..m......p/..
    0050 - fd 61 24 44 0e 3f 64 d0-2c 69 eb 8b 5d 8e ba f1   .a$D.?d.,i..]...
    0060 - c7 36 a8 c9 c4 16 4b a5-ff 3b da 24 f3 0a 95 d9   .6....K..;.$....
    0070 - f5 53 af 9d 1e 99 e1 7a-a9 1b f3 85 35 8b 3f 17   .S.....z....5.?.
    0080 - fb c8 43 0a 0b 78 e3 11-17 6e ae 2f 92 fc 02 c4   ..C..x...n./....
    0090 - 3d 23 8c 00 e4 d1 9e b6-58 27 b6 d7 15 31 6f 0f   =#......X'...1o.
    00a0 - 4d ed cc 29 f6 c8 4e 3d-ab d7 88 04 35 32 49 85   M..)..N=....52I.
    00b0 - f1 e6 68 59 7b bc bd 30-10 3c 2d ff db dd 3a 2b   ..hY{..0.<-...:+
    00c0 - e4 8e b5 78 d2 01 78 2b-ea a7 3d ef dc c6 d9 e4   ...x..x+..=.....

    Start Time: 1694585536
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
    Session-ID: 4D6AA27B6011482E2777FCD4ABE16C17F1407E68E26B07A87E012B6EFB33E496
    Session-ID-ctx:
    Resumption PSK: ECC3B747FAA5F88E33B4F28330F9CB868C80883CD6DE26EB5229201B034CCCABE75C0EE9C895BA371AD78D7F3A42BE31
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - ef 3c 60 dd c0 30 4a 16-cc e8 65 95 7d f5 1d 44   .<`..0J...e.}..D
    0010 - 42 0f 21 0d e4 5e b6 d7-a1 45 24 13 68 df fc d9   B.!..^...E$.h...
    0020 - 58 ce 67 ff d3 24 64 da-9f d2 b4 c4 3f 15 4e 16   X.g..$d.....?.N.
    0030 - b5 44 29 32 1a b6 01 42-ac b1 c9 99 fa 1d 7c 4d   .D)2...B......|M
    0040 - 20 11 f1 af d9 69 e6 c9-c4 64 7f 1b 66 1b 10 80    ....i...d..f...
    0050 - 1a 35 55 5d 22 e8 34 97-95 0e 34 d6 b2 e5 08 12   .5U]".4...4.....
    0060 - 82 d8 a6 19 8f a4 39 90-aa b7 47 8a 21 18 dd fc   ......9...G.!...
    0070 - fd 0e 28 54 1c c4 c5 c9-1c 30 04 18 ca d6 2d ac   ..(T.....0....-.
    0080 - b6 9e d5 1d 05 97 9e 1d-85 e0 18 d9 5c 7f 91 e7   ............\...
    0090 - 5d 6b d0 fa fa 14 b8 0c-d1 1f d3 46 ba 3a 5c b3   ]k.........F.:\.
    00a0 - 35 94 dd ca 01 91 4f 11-ee 3c 33 02 24 22 b6 da   5.....O..<3.$"..
    00b0 - e1 2f 58 e3 e5 c1 a7 f0-f7 a7 35 9f 83 47 bf fb   ./X.......5..G..
    00c0 - 84 20 40 e5 4a dd fd 4c-54 c8 af 69 8e d2 50 b9   . @.J..LT..i..P.

    Start Time: 1694585536
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
## Notas adicionales
| Comando | Descripción |
|---------|-------------|
|ls| lista de los archivos en la carpeta actual|
|cd/| me lleva al directorio raíz|
|cat| se utiliza para concatenar y mostrar el contenido de uno o varios archivos en la salida estándar |
|file| se utiliza para determinar el tipo de archivo mediante su contenido |
|du| se utiliza para mostrar el uso del espacio en disco por archivos y directorios  |
|find| se utiliza para buscar archivos y directorios en una jerarquía de directorios determinada   |
|-a| no ignora los archivos que comienzan con .|
|-l| hacer un listado largo de archivos|
|grep| e utiliza para buscar patrones de texto en archivos o en la salida de otros comandos. |
|man| comando que se utiliza para acceder a las páginas del manual (manuales) que proporcionan documentación detallada sobre diversos comandos, utilidades y funciones del sistema.|
|sort| se utiliza para ordenar líneas de texto en orden alfabético o numérico.|
|uniq| se utiliza para eliminar o mostrar líneas duplicadas consecutivas en un archivo de texto o en la entrada estándar.|
|strings| se utiliza para extraer y mostrar las cadenas de texto legibles en archivos binarios.|
|base64| se utiliza para codificar y decodificar datos en formato base64. Base64 es un sistema de codificación que convierte datos binarios en una representación de texto compuesta por caracteres ASCII imprimibles. |
|tr| se utiliza para realizar transformaciones de caracteres en texto. |
|tar| se utiliza para crear, visualizar, extraer y manipular archivos de formato tar, que son comunes en sistemas basados en Unix |
|gzip| se utiliza para comprimir y descomprimir archivos utilizando el algoritmo de compresión GZIP|
|bzip2| se utiliza para comprimir y descomprimir archivos utilizando el algoritmo de compresión BZIP2. Al igual que GZIP, BZIP2 es un algoritmo de compresión que reduce el tamaño de los archivos para ahorrar espacio en disco y mejorar la eficiencia en la transferencia de datos. |
|xxd| se utiliza para mostrar o crear representaciones hexadecimales y ASCII de archivos binarios. |
| mkdir | Se utiliza para crear directorios o carpetas|


## Referencias