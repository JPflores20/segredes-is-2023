## Objetivo

## Datos de acceso al nivel
```
LINK: https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png

```
## Solución

```bash
                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/extensions]
└─$ cd ..        
                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos]
└─$ mkdir WhatLiesWithin
                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos]
└─$ cd WhatLiesWithin 
                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/WhatLiesWithin]
└─$ wget https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png
--2023-10-22 13:34:09--  https://jupiter.challenges.picoctf.org/static/011955b303f293d60c8116e6a4c5c84f/buildings.png
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 625219 (611K) [application/octet-stream]
Saving to: ‘buildings.png’

buildings.png            100%[=================================>] 610.57K  1003KB/s    in 0.6s    

2023-10-22 13:34:10 (1003 KB/s) - ‘buildings.png’ saved [625219/625219]

                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/WhatLiesWithin]
└─$ ls           
buildings.png
                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/WhatLiesWithin]
└─$ file buildings.png 
buildings.png: PNG image data, 657 x 438, 8-bit/color RGBA, non-interlaced
                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/WhatLiesWithin]
└─$ 


```
## Notas adicionales
```bash
picoCTF{h1d1ng_1n_th3_b1t5}


```
![[Pasted image 20231022124045.png]]