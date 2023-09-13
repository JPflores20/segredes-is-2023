# Level 16--17
## Objetivo
Las credenciales para el siguiente nivel se pueden recuperar enviando la contraseña del nivel actual a **un puerto en localhost en el rango 31000 a 32000** . Primero averigüe cuál de estos puertos tiene un servidor escuchando. Luego averigüe cuáles de ellos hablan SSL y cuáles no. Solo hay 1 servidor que le dará las siguientes credenciales, los demás simplemente le enviarán todo lo que les envíe.
## Datos de acceso al nivel
```
Server    : bbandit16@bandit.labs.overthewire.org
Password  : JQttfApK4SeyHwDlI9SXGR50qclOAil1

```
## Solución
```bash
ssh bandit16@bandit.labs.overthewire.org -p 2220

bandit16@bandit:~$ nmap -p31000-32000 localhost
Starting Nmap 7.80 ( https://nmap.org ) at 2023-09-13 06:14 UTC
Nmap scan report for localhost (127.0.0.1)
Host is up (0.00017s latency).
Not shown: 996 closed ports
PORT      STATE SERVICE
31046/tcp open  unknown
31518/tcp open  unknown
31691/tcp open  unknown
31790/tcp open  unknown
31960/tcp open  unknown

Nmap done: 1 IP address (1 host up) scanned in 0.08 seconds
bandit16@bandit:~$ openssl s_client -connect localhost:31790
CONNECTED(00000003)
Can't use SSL_get_servername
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
    Session-ID: E7828DD796D73FA0C28B03C142F4925F4763F4BFF6861218BA5D694CD1BF8F84
    Session-ID-ctx:
    Resumption PSK: A5C94389A2E5B7AF930CF2F8B165B3EF714F4160062DD36068539E8AB649DF2894E4A63B68D02F3EC3DD4AD1B968444F
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 8a 53 79 53 f7 5d bc c9-dd 02 bc 88 5e 20 c6 eb   .SyS.]......^ ..
    0010 - 05 e4 76 ad a5 0a 5c cb-ca d4 f0 38 2c f5 db f5   ..v...\....8,...
    0020 - f5 07 bc b6 0b 23 f5 9b-54 4d 71 0f 0d 50 a4 cf   .....#..TMq..P..
    0030 - ad b8 d6 06 0a 98 a6 dd-ae 53 30 9d 8e e3 cd 63   .........S0....c
    0040 - 3e 53 c8 e7 fd 2f be 3f-71 23 b0 a0 cb 65 53 ba   >S.../.?q#...eS.
    0050 - f9 65 b8 d9 37 87 61 24-6f ca 87 93 bd e0 d8 fa   .e..7.a$o.......
    0060 - 60 de d7 de 88 0d d3 c8-19 4b b7 9a da 01 74 69   `........K....ti
    0070 - b0 f1 90 c4 5e f1 3a d5-1e e1 fa 25 37 87 1c df   ....^.:....%7...
    0080 - e0 ef e0 6c 2a 76 b6 8b-e8 28 14 c7 bc de b5 c1   ...l*v...(......
    0090 - 05 5c 39 4c 31 27 ce 85-be ff 9a a0 c4 44 5c 85   .\9L1'.......D\.
    00a0 - b9 65 66 44 9f c2 91 91-1d 87 32 a9 1d 8f e7 04   .efD......2.....
    00b0 - 16 cf b2 43 cc a8 76 62-7d 13 6a fe 54 50 55 fd   ...C..vb}.j.TPU.
    00c0 - 96 2f 80 da 0d 08 7c 88-89 9d c2 83 ca 1c 6f 29   ./....|.......o)

    Start Time: 1694585767
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
    Session-ID: 728969C8A02403F9663CCA87DE4C167E932EEB7373075C373F72E4D5D9B8791D
    Session-ID-ctx:
    Resumption PSK: 29B6F221EB3FAF840E365AEE5A7BDF06AE26C4C070A78689C12C734A1F55F375421243C9F3651D7CA06F38875481E646
    PSK identity: None
    PSK identity hint: None
    SRP username: None
    TLS session ticket lifetime hint: 7200 (seconds)
    TLS session ticket:
    0000 - 8a 53 79 53 f7 5d bc c9-dd 02 bc 88 5e 20 c6 eb   .SyS.]......^ ..
    0010 - 76 37 44 a0 fb 71 78 af-71 d0 1d cc 8c cc 32 64   v7D..qx.q.....2d
    0020 - 05 bb 1d 47 bb d0 0f 6c-78 95 82 47 db 36 e5 17   ...G...lx..G.6..
    0030 - a6 84 64 bc 83 9f 1e 28-ae b8 86 dc 0d 85 2d ba   ..d....(......-.
    0040 - 37 fa c8 bd a5 84 34 28-f7 97 57 3f fb 9c 9a 77   7.....4(..W?...w
    0050 - b6 1f a8 c2 04 3d ff 93-b9 b3 70 2d 67 42 9c 4a   .....=....p-gB.J
    0060 - 0c 14 17 f6 5d 74 84 ab-8b d8 6b 44 e8 6d 9d 73   ....]t....kD.m.s
    0070 - f6 72 d5 df 28 fe d8 2b-1a 27 80 db fc c1 74 8b   .r..(..+.'....t.
    0080 - c9 d2 7b e1 3b e7 b5 3b-f9 35 44 6f 34 e3 61 60   ..{.;..;.5Do4.a`
    0090 - 58 59 ff 9b 53 28 2d 3f-81 4a b6 6e 85 19 77 89   XY..S(-?.J.n..w.
    00a0 - 61 68 52 36 c9 0b 0f 1e-24 95 28 72 63 8c e7 8c   ahR6....$.(rc...
    00b0 - 9f 64 91 d6 2b 31 72 22-fb e2 59 04 7b 3f 12 f7   .d..+1r"..Y.{?..
    00c0 - 3a 58 b2 92 e2 27 37 86-a5 3d 98 df 62 67 0f f4   :X...'7..=..bg..

    Start Time: 1694585767
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