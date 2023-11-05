## Objetivo

## Datos de acceso al nivel
```
Link: https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery

```
## Solución

```bash
┌──(kali㉿kali)-[~/Downloads]
└─$ ls
img.jpg  message.wav  whitepages.txt
                                                                                                   
┌──(kali㉿kali)-[~/Downloads]
└─$ wget https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery
--2023-10-18 13:11:07--  https://jupiter.challenges.picoctf.org/static/ab30fcb7d47364b4190a7d3d40edb551/mystery
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 202940 (198K) [application/octet-stream]
Saving to: ‘mystery’

mystery                  100%[=================================>] 198.18K   689KB/s    in 0.3s    

2023-10-18 13:11:09 (689 KB/s) - ‘mystery’ saved [202940/202940]

                                                                                                   
┌──(kali㉿kali)-[~/Downloads]
└─$ ls
img.jpg  message.wav  mystery  whitepages.txt
                                                                                                   
┌──(kali㉿kali)-[~/Downloads]
└─$ xxd -l 100 mystery       
00000000: 8965 4e34 0d0a b0aa 0000 000d 4322 4452  .eN4........C"DR
00000010: 0000 066a 0000 0447 0802 0000 007c 8bab  ...j...G.....|..
00000020: 7800 0000 0173 5247 4200 aece 1ce9 0000  x....sRGB.......
00000030: 0004 6741 4d41 0000 b18f 0bfc 6105 0000  ..gAMA......a...
00000040: 0009 7048 5973 aa00 1625 0000 1625 0149  ..pHYs...%...%.I
00000050: 5224 f0aa aaff a5ab 4445 5478 5eec bd3f  R$......DETx^..?
00000060: 8e64 cd71                                .d.q
                                                                                                   
┌──(kali㉿kali)-[~/Downloads]
└─$ ls
img.jpg  message.wav  mystery  whitepages.txt
                                                                                                   
┌──(kali㉿kali)-[~/Downloads]
└─$ cp mystery imagen.jpg
                                                                                                   
┌──(kali㉿kali)-[~/Downloads]
└─$ open imagen.jpg 
                                                                                                   
┌──(kali㉿kali)-[~/Downloads]
└─$ hexeditor imagen.jpg 
                                                                                                   
┌──(kali㉿kali)-[~/Downloads]
└─$ open imagen.jpg     
                                                                                                   
┌──(kali㉿kali)-[~/Downloads]
└─$ xxd -l 100 mystery   
00000000: 8965 4e34 0d0a b0aa 0000 000d 4322 4452  .eN4........C"DR
00000010: 0000 066a 0000 0447 0802 0000 007c 8bab  ...j...G.....|..
00000020: 7800 0000 0173 5247 4200 aece 1ce9 0000  x....sRGB.......
00000030: 0004 6741 4d41 0000 b18f 0bfc 6105 0000  ..gAMA......a...
00000040: 0009 7048 5973 aa00 1625 0000 1625 0149  ..pHYs...%...%.I
00000050: 5224 f0aa aaff a5ab 4445 5478 5eec bd3f  R$......DETx^..?
00000060: 8e64 cd71                                .d.q
                                                                                                   
┌──(kali㉿kali)-[~/Downloads]
└─$ hexeditor imagen.jpg
                                                                                                   
┌──(kali㉿kali)-[~/Downloads]
└─$ open imagen.jpg     
                                                                                                   
┌──(kali㉿kali)-[~/Downloads]
└─$ xxd -l 100 mystery  
00000000: 8965 4e34 0d0a b0aa 0000 000d 4322 4452  .eN4........C"DR
00000010: 0000 066a 0000 0447 0802 0000 007c 8bab  ...j...G.....|..
00000020: 7800 0000 0173 5247 4200 aece 1ce9 0000  x....sRGB.......
00000030: 0004 6741 4d41 0000 b18f 0bfc 6105 0000  ..gAMA......a...
00000040: 0009 7048 5973 aa00 1625 0000 1625 0149  ..pHYs...%...%.I
00000050: 5224 f0aa aaff a5ab 4445 5478 5eec bd3f  R$......DETx^..?
00000060: 8e64 cd71                                .d.q
                                                                                                   
┌──(kali㉿kali)-[~/Downloads]
└─$ sudo apt install pngcheck     
[sudo] password for kali: 
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following NEW packages will be installed:
  pngcheck
0 upgraded, 1 newly installed, 0 to remove and 545 not upgraded.
Need to get 68.6 kB of archives.
After this operation, 208 kB of additional disk space will be used.
Ign:1 http://http.kali.org/kali kali-rolling/main amd64 pngcheck amd64 3.0.3-3
Get:1 http://kali.download/kali kali-rolling/main amd64 pngcheck amd64 3.0.3-3 [68.6 kB]
Fetched 68.6 kB in 18s (3,788 B/s)                                                                
Selecting previously unselected package pngcheck.
(Reading database ... 403506 files and directories currently installed.)
Preparing to unpack .../pngcheck_3.0.3-3_amd64.deb ...
Unpacking pngcheck (3.0.3-3) ...
Setting up pngcheck (3.0.3-3) ...
Processing triggers for man-db (2.11.2-3) ...
Processing triggers for kali-menu (2023.4.3) ...
                                                                                                   
┌──(kali㉿kali)-[~/Downloads]
└─$ pngcheck -v imagen.jpg 
File: imagen.jpg (202940 bytes)
  invalid chunk name "C"DR" (43 22 44 52)
ERRORS DETECTED in imagen.jpg
                                                                                                   
┌──(kali㉿kali)-[~/Downloads]
└─$ hexeditor imagen.jpg     
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/Downloads]
└─$ file imagen.jpg 
imagen.jpg: PNG image data, 1642 x 1095, 8-bit/color RGB, non-interlaced
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/Downloads]
└─$ 
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/Downloads]
└─$ open imagen.jpg
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/Downloads]
└─$ pngcheck -v imagen.jpg
File: imagen.jpg (202940 bytes)
  chunk IHDR at offset 0x0000c, length 13
    1642 x 1095 image, 24-bit RGB, non-interlaced
  chunk sRGB at offset 0x00025, length 1
    rendering intent = perceptual
  chunk gAMA at offset 0x00032, length 4: 0.45455
  chunk pHYs at offset 0x00042, length 9: 2852132389x5669 pixels/meter
  CRC error in chunk pHYs (computed 38d82c82, expected 495224f0)
ERRORS DETECTED in imagen.jpg
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/Downloads]
└─$ hexeditor imagen.jpg  
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/Downloads]
└─$ file imagen.jpg       
imagen.jpg: PNG image data, 1642 x 1095, 8-bit/color RGB, non-interlaced
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/Downloads]
└─$ open imagen.jpg       
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/Downloads]
└─$ pngcheck -v imagen.jpg
File: imagen.jpg (202940 bytes)
  chunk IHDR at offset 0x0000c, length 13
    1642 x 1095 image, 24-bit RGB, non-interlaced
  chunk sRGB at offset 0x00025, length 1
    rendering intent = perceptual
  chunk gAMA at offset 0x00032, length 4: 0.45455
  chunk pHYs at offset 0x00042, length 9: 5669x5669 pixels/meter (144 dpi)
:  invalid chunk length (too large)
ERRORS DETECTED in imagen.jpg
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/Downloads]
└─$ 
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/Downloads]
└─$ hexeditor imagen.jpg  
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/Downloads]
└─$ open imagen.jpg       
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/Downloads]
└─$ pngcheck -v imagen.jpg
File: imagen.jpg (202940 bytes)
  chunk IHDR at offset 0x0000c, length 13
    1642 x 1095 image, 24-bit RGB, non-interlaced
  chunk sRGB at offset 0x00025, length 1
    rendering intent = perceptual
  chunk gAMA at offset 0x00032, length 4: 0.45455
  chunk pHYs at offset 0x00042, length 9: 5669x5669 pixels/meter (144 dpi)
  invalid chunk name "�DET" (ffffffab 44 45 54)
ERRORS DETECTED in imagen.jpg
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/Downloads]
└─$ hexeditor imagen.jpg  
                                                                                                                                                                                                                                            
┌──(kali㉿kali)-[~/Downloads]
└─$ open imagen.jpg

```
## Notas adicionales
```bash
picoCTF{c0rrupt10n_1847995} 

```
![[Pasted image 20231018113433.png]]