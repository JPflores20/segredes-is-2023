## Objetivo

## Datos de acceso al nivel
```
LINK: https://jupiter.challenges.picoctf.org/static/43c4743b3946f427e883f6b286f47467/garden.jpg

```
## Solución

```bash
┌──(kali㉿kali)-[~]
└─$ cd /home/kali/Documents/Retos/
                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos]
└─$ mkdir gloriofthegarden                                     
                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos]
└─$ cd gloriofthegarden           
                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/gloriofthegarden]
└─$ wget https://jupiter.challenges.picoctf.org/static/43c4743b3946f427e883f6b286f47467/garden.jpg
--2023-10-22 12:59:06--  https://jupiter.challenges.picoctf.org/static/43c4743b3946f427e883f6b286f47467/garden.jpg
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2295192 (2.2M) [application/octet-stream]
Saving to: ‘garden.jpg’

garden.jpg               100%[=================================>]   2.19M  4.89MB/s    in 0.4s    

2023-10-22 12:59:06 (4.89 MB/s) - ‘garden.jpg’ saved [2295192/2295192]

                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/gloriofthegarden]
└─$ ls
garden.jpg       
┌──(kali㉿kali)-[~/Documents/Retos/gloriofthegarden]
└─$ file garden.jpg                      
garden.jpg: JPEG image data, JFIF standard 1.01, resolution (DPI), density 72x72, segment length 16, baseline, precision 8, 2999x2249, components 3
                                                                                                   
┌──(kali㉿kali)-[~/Documents/Retos/gloriofthegarden]
└─$ hexeditor garden.jpg 

abrimos hexeditor
buscamos con ctrl + w la palabra picoCTF en formato de texto y nos arrojaa la bandera
pi
00230570  63 6F 43 54  46 7B 6D 6F   72 65 5F 74  68 61 6E 5F                      coCTF{more_than_
00230580  6D 33 33 74  73 5F 74 68   65 5F 33 79  33 36 35 37                      m33ts_the_3y3657
00230590  42 61 42 32  43 7D 22 0A                                                 BaB2C}
```
## Notas adicionales
```bash

picoCTF{more_than_m33ts_the_3y3657BaB2C}
```
