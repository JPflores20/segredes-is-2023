## Objetivo

## Datos de acceso al nivel
```
LINK: 

```
## Solución

```bash
┌──(kali㉿kali)-[~]
└─$ cd /home/kali/Documents/Retos/
                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos]
└─$ mkdir WebNet0                                              
                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos]
└─$ cd WebNet0                    
                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/WebNet0]
└─$ wget https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/capture.pcap
--2023-10-22 22:33:07--  https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/capture.pcap
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 13163 (13K) [application/octet-stream]
Saving to: ‘capture.pcap’

capture.pcap             100%[=================================>]  12.85K  --.-KB/s    in 0s      

2023-10-22 22:33:08 (319 MB/s) - ‘capture.pcap’ saved [13163/13163]

                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/WebNet0]
└─$ wget https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/picopico.key
--2023-10-22 22:33:26--  https://jupiter.challenges.picoctf.org/static/0c84d3636dd088d9fe4efd5d0d869a06/picopico.key
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1704 (1.7K) [application/octet-stream]
Saving to: ‘picopico.key’

picopico.key             100%[=================================>]   1.66K  --.-KB/s    in 0s      

2023-10-22 22:33:26 (58.0 MB/s) - ‘picopico.key’ saved [1704/1704]

                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/WebNet0]
└─$ ls
capture.pcap  picopico.key
                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/WebNet0]
└─$ ls -la
total 28
drwxr-xr-x 2 kali kali  4096 Oct 22 22:33 .
drwxr-xr-x 9 kali kali  4096 Oct 22 22:32 ..
-rw-r--r-- 1 kali kali 13163 Oct 26  2020 capture.pcap
-rw-r--r-- 1 kali kali  1704 Oct 26  2020 picopico.key
                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/WebNet0]
└─$ file capture.pcap                    
capture.pcap: pcap capture file, microsecond ts (little-endian) - version 2.4 (Ethernet, capture length 65535)
                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/WebNet0]
└─$ cat picopico.key 
-----BEGIN PRIVATE KEY-----
MIIEvQIBADANBgkqhkiG9w0BAQEFAASCBKcwggSjAgEAAoIBAQCwKlFPNKjseJF5
puCJU5x38XcT1eQge5zOKNahAlYudvGVOEs61TnIgvcER4ko8i3OCwak2/atcGk3
oz9jFKep7XFEYNP31IwwD9j/YazlKy4DRLGObOyIZUU1f2WRA7Uhf0POQXsDT1oU
X32jMKZkQSSDW4MRZd9trJYdO2TrcEPMsBiZQlFlvgnNwl3QlawozTHLAJKI36j1
cPwSMMeNca1e0Zi1s7R5IxfhpNXOBF0FmxiWvmeOHbaspyHg8UEmGBrkd4k4wXSK
GQvrc8QjycP4ScEdquxJiYnDT8iEbAq70/7f/5NIN1DE9YoGJqKYjTS9nRPB4Yvj
JN/SJnhvAgMBAAECggEACCnd3LrG/TZVH3sROqvqO1CwQPYPfUXdLVyNHab7EWon
pc+XBOHurJENG2CpRYF7h+nQ5ADhfIYSCicBf/jsEB7VueJ20CxEVtHVL3h6R6Bp
oHMle0Em8OcofuMpdL/kO+om3T8BkVSzCvCl5NMTUuAF7iRmfX7oDLALwM0IzzQv
2un+2UmT15rgAZfl3IL1PGvJhbhLxfeeyPE9MBy1SqBjQ9rNFn8sQv959J6BHz4b
EpK//ErtNP2yh7oiVBBgKEQ1gEuOjQC/4oxoqCFfZaf9XNRCxB/zY1nUprvJyz09
NMQWNF2EmvmBVGfoTxmuut5N0GbVr2UyHxWMKm2sOQKBgQDpb2+AWgWlGtetuLKJ
fJs8dnd6LhnafbKCOXMOT68qMBRoTpBtVTLRVSNvWCm8m4TTEazX4+ZA+bJFwUFw
aATDmHcr6lMI3tNKrcsnY2F7o5I4z6mwuRuSeszq/ndxZqCzwCu4nKixh3cznp7j
JiElNG0d8Lu5eQgmVAK1AhWXfQKBgQDBMa9ga7VJUP4pzcHnWAoi34OpfjvQYeGl
IKL3AKO4OedaHdH9qid41PQHnL7O3xzN669SkLZ5s0d88A/LFLk4oZNMKdkSTQIQ
+AMbXH01HGFvnCOuPg/FbNp1wS7zJEg5u5HFQWyMPNJLr/hZ6g2Yp+UGpAcGTwM/
RCPVAPhLWwKBgQDAB0OaOnPaVjKGXiHAqBirrGiswa/S5QQrzEaxxys5cUPYaoi0
6BldysPTnJr45JZna2rcTkXjvYTBjTDf3zHMFWgzYBfefC8kh8NPK5nNs8ldorbd
AemEnjBkP+DSELKyK6vLulOrdtzAQgRCp+MsT+xTbO2ArefeX826SXSpoQKBgC2v
nDOHBQXje1dTawlUToFUrgQE8AwlOYEdKKyUoCLOvqEW8DO2a0MtyM+MB6tQI7Wm
iH1T73L0LHGlK3bw3aRAwV5/fu/O+jAdFk8AHjPTFE+acu2fi4c6aKb0GjAxYksU
yjIFeK/pKinv4SESMkjpW0WowGiDgtcRPBAA/LaFAoGAfEM1rfM0v3UmB7PS6u0m
P3ckP2CFCdaryXPfC52GBcJ3Q46YpsQvLTVotM+teHvTjNw2jwwZxIl4NenGSEj3
KDhQoOiQC9BrDD+DB4I9+T9nxT3g7R6MrgITghB4We7TVhL/PljnJTyDqpjNA4kY
TveAJPv6Xq1ERt5PUtX3BqQ=
-----END PRIVATE KEY-----
                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/WebNet0]
└─$ 
Abrimos wireshark y desencriptamos los paquetes TLC con la key que se nos proporciona, al final buscamos la bandera en los paquetes tls
picoCTF{nongshim.shrimp.crackers}

```
## Notas adicionales
```bash

https://youtu.be/9uflLPoETOc
```