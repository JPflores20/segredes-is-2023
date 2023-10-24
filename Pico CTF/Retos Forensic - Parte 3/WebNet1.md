## Objetivo

## Datos de acceso al nivel
```
LINK: https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap
LINK 2: https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key

```
## Solución

```bash
┌──(kali㉿kali)-[~]
└─$ cd /home/kali/Documents/Retos/WebNet0/
                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/WebNet0]
└─$ wireshark capture.pcap              
 ** (wireshark:1949) 01:28:23.122923 [GUI WARNING] -- FIX Add drag reordering to UAT dialog
                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/WebNet0]
└─$ cd ..                                 
                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos]
└─$ mkdir WebNet  
                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos]
└─$ wget https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap
--2023-10-23 01:36:42--  https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/capture.pcap
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 92525 (90K) [application/octet-stream]
Saving to: ‘capture.pcap’

capture.pcap             100%[=================================>]  90.36K  --.-KB/s    in 0.07s   

2023-10-23 01:36:43 (1.29 MB/s) - ‘capture.pcap’ saved [92525/92525]

                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos]
└─$ wget https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key
--2023-10-23 01:36:59--  https://jupiter.challenges.picoctf.org/static/fbf98e695555a2a48fe42c9a245de376/picopico.key
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1704 (1.7K) [application/octet-stream]
Saving to: ‘picopico.key’

picopico.key             100%[=================================>]   1.66K  --.-KB/s    in 0s      

2023-10-23 01:36:59 (30.7 MB/s) - ‘picopico.key’ saved [1704/1704]

                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos]
└─$ wireshark capture.pcap 
 ** (wireshark:7699) 01:39:52.824106 [GUI WARNING] -- FIX Add drag reordering to UAT dialog

                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos]
└─$ 
                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos]
└─$ strings vulture.jpg -n15
picoCTF{honey.roasted.peanuts}
 )/'%'/9339GDG]]}
 )/'%'/9339GDG]]}
%&'()*456789:CDEFGHIJSTUVWXYZcdefghijstuvwxyz
&'()*56789:CDEFGHIJSTUVWXYZcdefghijstuvwxyz
         
```
## Notas adicionales
```bash


```