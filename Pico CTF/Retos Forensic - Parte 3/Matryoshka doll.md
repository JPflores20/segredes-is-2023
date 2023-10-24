## Objetivo

## Datos de acceso al nivel
```
LINK: 

```
## Solución

```bash
                                                                                                                                
┌──(kali㉿kali)-[~/Documents/Retos]
└─$ mkdir MatryoshkaDoll 
                                                                                                                                
┌──(kali㉿kali)-[~/Documents/Retos]
└─$ cd MatryoshkaDoll 
                                                                                                                                
┌──(kali㉿kali)-[~/Documents/Retos/MatryoshkaDoll]
└─$ wget https://mercury.picoctf.net/static/2978e1270538613cd8181c7b0dabe9bd/dolls.jpg              
--2023-10-23 01:52:29--  https://mercury.picoctf.net/static/2978e1270538613cd8181c7b0dabe9bd/dolls.jpg
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 651622 (636K) [application/octet-stream]
Saving to: ‘dolls.jpg’

dolls.jpg                       100%[=======================================================>] 636.35K  2.14MB/s    in 0.3s    

2023-10-23 01:52:31 (2.14 MB/s) - ‘dolls.jpg’ saved [651622/651622]

                                                                                                                                
┌──(kali㉿kali)-[~/Documents/Retos/MatryoshkaDoll]
└─$ binwalk dolls.jpeg                         

General Error: Cannot open file dolls.jpeg (CWD: /home/kali/Documents/Retos/MatryoshkaDoll) : [Errno 2] No such file or directory: 'dolls.jpeg'

                                                                                                                                
┌──(kali㉿kali)-[~/Documents/Retos/MatryoshkaDoll]
└─$ binwalk dolls.jpg 

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 594 x 1104, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
272492        0x4286C         Zip archive data, at least v2.0 to extract, compressed size: 378942, uncompressed size: 383937, name: base_images/2_c.jpg
651600        0x9F150         End of Zip archive, footer length: 22

                                                                                                                                
┌──(kali㉿kali)-[~/Documents/Retos/MatryoshkaDoll]
└─$ binwalk -e  dolls.jpg

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 594 x 1104, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
272492        0x4286C         Zip archive data, at least v2.0 to extract, compressed size: 378942, uncompressed size: 383937, name: base_images/2_c.jpg
651600        0x9F150         End of Zip archive, footer length: 22

                                                                                                                                
┌──(kali㉿kali)-[~/Documents/Retos/MatryoshkaDoll]
└─$ ls
dolls.jpg  _dolls.jpg.extracted
                                                                                                                                
┌──(kali㉿kali)-[~/Documents/Retos/MatryoshkaDoll]
└─$ cd _dolls.jpg.extracted 
                                                                                                                                
┌──(kali㉿kali)-[~/Documents/Retos/MatryoshkaDoll/_dolls.jpg.extracted]
└─$ ls
4286C.zip  base_images
                                                                                                                                
┌──(kali㉿kali)-[~/Documents/Retos/MatryoshkaDoll/_dolls.jpg.extracted]
└─$ cd base_images         
                                                                                                                                
┌──(kali㉿kali)-[~/…/Retos/MatryoshkaDoll/_dolls.jpg.extracted/base_images]
└─$ ls
2_c.jpg
                                                                                                                                
┌──(kali㉿kali)-[~/…/Retos/MatryoshkaDoll/_dolls.jpg.extracted/base_images]
└─$ open 2_c.jpg 
                                                                                                                                
┌──(kali㉿kali)-[~/…/Retos/MatryoshkaDoll/_dolls.jpg.extracted/base_images]
└─$ binwalk 2_c.jpg      

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 526 x 1106, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
187707        0x2DD3B         Zip archive data, at least v2.0 to extract, compressed size: 196042, uncompressed size: 201444, name: base_images/3_c.jpg
383804        0x5DB3C         End of Zip archive, footer length: 22
383915        0x5DBAB         End of Zip archive, footer length: 22

                                                                                                                                
┌──(kali㉿kali)-[~/…/Retos/MatryoshkaDoll/_dolls.jpg.extracted/base_images]
└─$ binwalk -e 2_c.jpg   

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 526 x 1106, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
187707        0x2DD3B         Zip archive data, at least v2.0 to extract, compressed size: 196042, uncompressed size: 201444, name: base_images/3_c.jpg
383804        0x5DB3C         End of Zip archive, footer length: 22
383915        0x5DBAB         End of Zip archive, footer length: 22

                                                                                                                                
┌──(kali㉿kali)-[~/…/Retos/MatryoshkaDoll/_dolls.jpg.extracted/base_images]
└─$ ls
2_c.jpg  _2_c.jpg.extracted
                                                                                                                                
┌──(kali㉿kali)-[~/…/Retos/MatryoshkaDoll/_dolls.jpg.extracted/base_images]
└─$ cd _2_c.jpg.extracted 
                                                                                                                                
┌──(kali㉿kali)-[~/…/MatryoshkaDoll/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted]
└─$ ls
2DD3B.zip  base_images
                                                                                                                                
┌──(kali㉿kali)-[~/…/MatryoshkaDoll/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted]
└─$ cd base_images       
                                                                                                                                
┌──(kali㉿kali)-[~/…/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images]
└─$ 
                                                                                                                                
┌──(kali㉿kali)-[~/…/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images]
└─$ ls
3_c.jpg
                                                                                                                                
┌──(kali㉿kali)-[~/…/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images]
└─$ binwalk -e 3_c.jpg   

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 428 x 1104, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
123606        0x1E2D6         Zip archive data, at least v2.0 to extract, compressed size: 77650, uncompressed size: 79806, name: base_images/4_c.jpg
201422        0x312CE         End of Zip archive, footer length: 22

                                                                                                                                
┌──(kali㉿kali)-[~/…/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images]
└─$ ls
3_c.jpg  _3_c.jpg.extracted
                                                                                                                                
┌──(kali㉿kali)-[~/…/_dolls.jpg.extracted/base_images/_2_c.jpg.extracted/base_images]
└─$ cd _3_c.jpg.extracted 
                                                                                                                                
┌──(kali㉿kali)-[~/…/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted]
└─$ ls                          
1E2D6.zip  base_images
                                                                                                                                
┌──(kali㉿kali)-[~/…/base_images/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted]
└─$ cd base_images       
                                                                                                                                
┌──(kali㉿kali)-[~/…/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images]
└─$ ls
4_c.jpg
                                                                                                                                
┌──(kali㉿kali)-[~/…/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images]
└─$ open 4_c.jpg 
                                                                                                                                
┌──(kali㉿kali)-[~/…/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images]
└─$ binwalk -e 4_c.jpg   

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 320 x 768, 8-bit/color RGBA, non-interlaced
3226          0xC9A           TIFF image data, big-endian, offset of first image directory: 8
79578         0x136DA         Zip archive data, at least v2.0 to extract, compressed size: 62, uncompressed size: 81, name: flag.txt
79784         0x137A8         End of Zip archive, footer length: 22

                                                                                                                                
┌──(kali㉿kali)-[~/…/_2_c.jpg.extracted/base_images/_3_c.jpg.extracted/base_images]
└─$ cd _4_c.jpg.extracted 
                                                                                                                                
┌──(kali㉿kali)-[~/…/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted]
└─$ ls
136DA.zip  flag.txt
                                                                                                                                
┌──(kali㉿kali)-[~/…/base_images/_3_c.jpg.extracted/base_images/_4_c.jpg.extracted]
└─$ cat flag.txt          
picoCTF{4cf7ac000c3fb0fa96fb92722ffb2a32}                                                                                                                                


```
## Notas adicionales
```bash

picoCTF{4cf7ac000c3fb0fa96fb92722ffb2a32}  
```