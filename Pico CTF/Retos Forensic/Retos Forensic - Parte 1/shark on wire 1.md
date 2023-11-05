## Objetivo

## Datos de acceso al nivel
```
LINK: https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap

```
## Solución

```bash
                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos]
└─$ mkdir SharkOnWire
                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos]
└─$ cd SharkOnWire 
                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/SharkOnWire]
└─$ wget https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap
--2023-10-22 13:09:51--  https://jupiter.challenges.picoctf.org/static/483e50268fe7e015c49caf51a69063d0/capture.pcap
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 239455 (234K) [application/octet-stream]
Saving to: ‘capture.pcap’

capture.pcap             100%[=================================>] 233.84K   869KB/s    in 0.3s    

2023-10-22 13:09:51 (869 KB/s) - ‘capture.pcap’ saved [239455/239455]

                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/SharkOnWire]
└─$ file capture.pcap 
capture.pcap: pcap capture file, microsecond ts (little-endian) - version 2.4 (Ethernet, capture length 262144)
                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/SharkOnWire]
└─$ 
                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/SharkOnWire]
└─$ 

Abrimos WireShark y buscamos dentro de los paquetes udp la bandera

```
## Notas adicionales
```bash

https://youtu.be/q8cM4sY0izw?list=PLDo9DMLZyP6kTZ8Td37-LdbAx4-yNfHBl

picoCTF{StaT31355_636f6e6e}
```