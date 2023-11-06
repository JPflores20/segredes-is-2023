## Objetivo
I have these 2 images, can you make a flag out of them? [scrambled1.png](https://mercury.picoctf.net/static/49743139fb7c10765dbf462d40987d2a/scrambled1.png) [scrambled2.png](https://mercury.picoctf.net/static/49743139fb7c10765dbf462d40987d2a/scrambled2.png)
## Datos de acceso al nivel
```
LINK: https://mercury.picoctf.net/static/49743139fb7c10765dbf462d40987d2a/scrambled2.png

```
## Solución

```bash
┌──(kali㉿kali)-[~]
└─$ cd /home/kali/Documents/Retos/CRYPTO/Parte3/Pixelated/ 
                                                                                                    
┌──(kali㉿kali)-[~/…/Retos/CRYPTO/Parte3/Pixelated]
└─$ wget https://mercury.picoctf.net/static/49743139fb7c10765dbf462d40987d2a/scrambled1.png
--2023-11-05 18:10:58--  https://mercury.picoctf.net/static/49743139fb7c10765dbf462d40987d2a/scrambled1.png
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 197173 (193K) [application/octet-stream]
Saving to: ‘scrambled1.png’

scrambled1.png            100%[==================================>] 192.55K  --.-KB/s    in 0.1s    

2023-11-05 18:10:59 (1.37 MB/s) - ‘scrambled1.png’ saved [197173/197173]

                                                                                                     
┌──(kali㉿kali)-[~/…/Retos/CRYPTO/Parte3/Pixelated]
└─$ python3 exp.py 
Traceback (most recent call last):
  File "/home/kali/Documents/Retos/CRYPTO/Parte3/Pixelated/exp.py", line 1, in <module>
    from Pil import Image
ModuleNotFoundError: No module named 'Pil'
                                                                                                     
┌──(kali㉿kali)-[~/…/Retos/CRYPTO/Parte3/Pixelated]
└─$ python3 exp.py
Traceback (most recent call last):
  File "/home/kali/Documents/Retos/CRYPTO/Parte3/Pixelated/exp.py", line 4, in <module>
    imagen1 = np.asarray( Imagen.open('scrambled1.png') )
                          ^^^^^^
NameError: name 'Imagen' is not defined. Did you mean: 'Image'?
                                                                                                     
┌──(kali㉿kali)-[~/…/Retos/CRYPTO/Parte3/Pixelated]
└─$ python3 exp.py
[[[ 84 183   4]
  [156  62  39]
  [122 202  87]
  ...
  [109  23  70]
  [ 16  42 114]
  [253 233 201]]

 [[120 171  36]
  [203   5   7]
  [ 51 194 163]
  ...
  [ 18  79  80]
  [ 77 181 216]
  [ 36 215 193]]

 [[ 42 157  55]
  [102 129  46]
  [206  37  55]
  ...
  [252 232 197]
  [106 140 221]
  [139 232 192]]

 ...

 [[200  34 241]
  [ 56 147  94]
  [ 89  45  44]
  ...
  [ 46  32 129]
  [ 29  88 171]
  [102 200 147]]

 [[ 34  44 255]
  [193 103  78]
  [246 247 147]
  ...
  [ 87 224  48]
  [101 155  18]
  [ 56 219  59]]

 [[122  58  52]
  [122 240  82]
  [ 86 130  84]
  ...
  [ 52 198  63]
  [231  94   1]
  [111 146   8]]]
[[[171  72 251]
  [ 99 193 216]
  [133  53 168]
  ...
  [146 232 185]
  [239 213 141]
  [  2  22  54]]

 [[135  84 219]
  [ 52 250 248]
  [204  61  92]
  ...
  [237 176 175]
  [178  74  39]
  [219  40  62]]

 [[213  98 200]
  [153 126 209]
  [ 49 218 200]
  ...
  [  3  23  58]
  [149 115  34]
  [116  23  63]]

 ...

 [[ 55 221  14]
  [199 108 161]
  [166 210 211]
  ...
  [209 223 126]
  [226 167  84]
  [153  55 108]]

 [[221 211   0]
  [ 62 152 177]
  [  9   8 108]
  ...
  [168  31 207]
  [154 100 237]
  [199  36 196]]

 [[133 197 203]
  [133  15 173]
  [169 125 171]
  ...
  [203  57 192]
  [ 24 161 254]
  [144 109 247]]]
                                                                                                     
┌──(kali㉿kali)-[~/…/Retos/CRYPTO/Parte3/Pixelated]
└─$ python3 exp.py
                                                                                                     
┌──(kali㉿kali)-[~/…/Retos/CRYPTO/Parte3/Pixelated]
└─$ python3 exp.py
Traceback (most recent call last):
  File "/home/kali/Documents/Retos/CRYPTO/Parte3/Pixelated/exp.py", line 16, in <module>
    nueva = Image.fromarray(datos)
                            ^^^^^
NameError: name 'datos' is not defined. Did you mean: 'data1'?
                                                                                                     
┌──(kali㉿kali)-[~/…/Retos/CRYPTO/Parte3/Pixelated]
└─$ python3 exp.py
Traceback (most recent call last):
  File "/home/kali/Documents/Retos/CRYPTO/Parte3/Pixelated/exp.py", line 16, in <module>
    nueva = Image.fromarray(datos)
                            ^^^^^
NameError: name 'datos' is not defined. Did you mean: 'data1'?
                                                                                                     
┌──(kali㉿kali)-[~/…/Retos/CRYPTO/Parte3/Pixelated]
└─$ python3 exp.py
[[[ 84 183   4]
  [156  62  39]
  [122 202  87]
  ...
  [109  23  70]
  [ 16  42 114]
  [253 233 201]]

 [[120 171  36]
  [203   5   7]
  [ 51 194 163]
  ...
  [ 18  79  80]
  [ 77 181 216]
  [ 36 215 193]]

 [[ 42 157  55]
  [102 129  46]
  [206  37  55]
  ...
  [252 232 197]
  [106 140 221]
  [139 232 192]]

 ...

 [[200  34 241]
  [ 56 147  94]
  [ 89  45  44]
  ...
  [ 46  32 129]
  [ 29  88 171]
  [102 200 147]]

 [[ 34  44 255]
  [193 103  78]
  [246 247 147]
  ...
  [ 87 224  48]
  [101 155  18]
  [ 56 219  59]]

 [[122  58  52]
  [122 240  82]
  [ 86 130  84]
  ...
  [ 52 198  63]
  [231  94   1]
  [111 146   8]]]
[[[171  72 251]
  [ 99 193 216]
  [133  53 168]
  ...
  [146 232 185]
  [239 213 141]
  [  2  22  54]]

 [[135  84 219]
  [ 52 250 248]
  [204  61  92]
  ...
  [237 176 175]
  [178  74  39]
  [219  40  62]]

 [[213  98 200]
  [153 126 209]
  [ 49 218 200]
  ...
  [  3  23  58]
  [149 115  34]
  [116  23  63]]

 ...

 [[ 55 221  14]
  [199 108 161]
  [166 210 211]
  ...
  [209 223 126]
  [226 167  84]
  [153  55 108]]

 [[221 211   0]
  [ 62 152 177]
  [  9   8 108]
  ...
  [168  31 207]
  [154 100 237]
  [199  36 196]]

 [[133 197 203]
  [133  15 173]
  [169 125 171]
  ...
  [203  57 192]
  [ 24 161 254]
  [144 109 247]]]
                                                                                                     
┌──(kali㉿kali)-[~/…/Retos/CRYPTO/Parte3/Pixelated]
└─$ 

picoCTF{2a4d45c7}

```
## Notas adicionales
```bash
picoCTF{2a4d45c7}

------------------------------------------------------------------
from PIL import Image

import numpy as np

  

imagen1 = np.asarray( Image.open('scrambled1.png'))

imagen2 = np.asarray(Image.open('scrambled2.png'))

  

print(imagen1)

print(imagen2)

  

datos= imagen1.copy() + imagen2.copy()

  

nueva = Image.fromarray(datos)

  

nueva.save('nueva.png', 'PNG')

------------------------------------------------------------------
```