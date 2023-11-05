## Objetivo
We found this weird message being passed around on the servers, we think we have a working decryption scheme.Download the message [here](https://artifacts.picoctf.net/c/127/message.txt).Take each number mod 37 and map it to the following character set: 0-25 is the alphabet (uppercase), 26-35 are the decimal digits, and 36 is an underscore.Wrap your decrypted message in the picoCTF flag format (i.e. `picoCTF{decrypted_message}`)
## Datos de acceso al nivel
```
LINK: 

```
## Solución

```bash
──(kali㉿kali)-[~]
└─$ cd /home/kali/Documents/Retos/CRYPTO/Parte3/basic-mod1/
                                                                                                    
┌──(kali㉿kali)-[~/…/Retos/CRYPTO/Parte3/basic-mod1]
└─$ wget https://artifacts.picoctf.net/c/127/message.txt                           
--2023-11-05 02:47:33--  https://artifacts.picoctf.net/c/127/message.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 18.160.124.38, 18.160.124.108, 18.160.124.34, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|18.160.124.38|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 85 [application/octet-stream]
Saving to: ‘message.txt’

message.txt              100%[==================================>]      85  --.-KB/s    in 0s      

2023-11-05 02:47:34 (150 MB/s) - ‘message.txt’ saved [85/85]

                                                                                                    
┌──(kali㉿kali)-[~/…/Retos/CRYPTO/Parte3/basic-mod1]
└─$ cat message.txt                                        
128 322 353 235 336 73 198 332 202 285 57 87 262 221 218 405 335 101 256 227 112 140                                                                                                     
┌──(kali㉿kali)-[~/…/Retos/CRYPTO/Parte3/basic-mod1]
└─$ nano exp.py     

┌──(kali㉿kali)-[~]
└─$ cd /home/kali/Documents/Retos/CRYPTO/Parte3/
                                                                                                     
┌──(kali㉿kali)-[~/Documents/Retos/CRYPTO/Parte3]
└─$ cd basic-mod1 
                                                                                                     
┌──(kali㉿kali)-[~/…/Retos/CRYPTO/Parte3/basic-mod1]
└─$ ls
message.txt
                                                                                                     
┌──(kali㉿kali)-[~/…/Retos/CRYPTO/Parte3/basic-mod1]
└─$ cat message.txt 
128 322 353 235 336 73 198 332 202 285 57 87 262 221 218 405 335 101 256 227 112 140                                                                                                      
┌──(kali㉿kali)-[~/…/Retos/CRYPTO/Parte3/basic-mod1]
└─$ python3 exp.py
python3: can't open file '/home/kali/Documents/Retos/CRYPTO/Parte3/basic-mod1/exp.py': [Errno 2] No such file or directory
                                                                                                     
┌──(kali㉿kali)-[~/…/Retos/CRYPTO/Parte3/basic-mod1]
└─$ python3 exp.py
python3: can't open file '/home/kali/Documents/Retos/CRYPTO/Parte3/basic-mod1/exp.py': [Errno 2] No such file or directory
                                                                                                     
┌──(kali㉿kali)-[~/…/Retos/CRYPTO/Parte3/basic-mod1]
└─$ python3 exp.py
['128', '322', '353', '235', '336', '73', '198', '332', '202', '285', '57', '87', '262', '221', '218', '405', '335', '101', '256', '227', '112', '140']
                                                                                                     
┌──(kali㉿kali)-[~/…/Retos/CRYPTO/Parte3/basic-mod1]
└─$ python3 exp.py
['128', '322', '353', '235', '336', '73', '198', '332', '202', '285', '57', '87', '262', '221', '218', '405', '335', '101', '256', '227', '112', '140']
17
26
20
13
3
36
13
36
17
26
20
13
3
36
33
35
2
27
34
5
1
29
                                                                                                     
┌──(kali㉿kali)-[~/…/Retos/CRYPTO/Parte3/basic-mod1]
└─$ python3 -c 'print(ord(A))'
Traceback (most recent call last):
  File "<string>", line 1, in <module>
NameError: name 'A' is not defined
                                                                                                     
┌──(kali㉿kali)-[~/…/Retos/CRYPTO/Parte3/basic-mod1]
└─$ python3 exp.py            
['128', '322', '353', '235', '336', '73', '198', '332', '202', '285', '57', '87', '262', '221', '218', '405', '335', '101', '256', '227', '112', '140']

                                                                                                     
┌──(kali㉿kali)-[~/…/Retos/CRYPTO/Parte3/basic-mod1]
└─$ python3 exp.py
['128', '322', '353', '235', '336', '73', '198', '332', '202', '285', '57', '87', '262', '221', '218', '405', '335', '101', '256', '227', '112', '140']
Traceback (most recent call last):
  File "/home/kali/Documents/Retos/CRYPTO/Parte3/basic-mod1/exp.py", line 10, in <module>
    s = cnr(c+65)
        ^^^
NameError: name 'cnr' is not defined. Did you mean: 'chr'?
                                                                                                     
┌──(kali㉿kali)-[~/…/Retos/CRYPTO/Parte3/basic-mod1]
└─$ python3 exp.py
['128', '322', '353', '235', '336', '73', '198', '332', '202', '285', '57', '87', '262', '221', '218', '405', '335', '101', '256', '227', '112', '140']

                                                                                                     
┌──(kali㉿kali)-[~/…/Retos/CRYPTO/Parte3/basic-mod1]
└─$ python3 exp.py
  File "/home/kali/Documents/Retos/CRYPTO/Parte3/basic-mod1/exp.py", line 13
    elif c=36:
         ^^^^
SyntaxError: invalid syntax. Maybe you meant '==' or ':=' instead of '='?
                                                                                                     
┌──(kali㉿kali)-[~/…/Retos/CRYPTO/Parte3/basic-mod1]
└─$ python3 exp.py
['128', '322', '353', '235', '336', '73', '198', '332', '202', '285', '57', '87', '262', '221', '218', '405', '335', '101', '256', '227', '112', '140']

                                                                                                     
┌──(kali㉿kali)-[~/…/Retos/CRYPTO/Parte3/basic-mod1]
└─$ python3 exp.py
['128', '322', '353', '235', '336', '73', '198', '332', '202', '285', '57', '87', '262', '221', '218', '405', '335', '101', '256', '227', '112', '140']
 
                                                                                                     
┌──(kali㉿kali)-[~/…/Retos/CRYPTO/Parte3/basic-mod1]
└─$ python3 exp.py
['128', '322', '353', '235', '336', '73', '198', '332', '202', '285', '57', '87', '262', '221', '218', '405', '335', '101', '256', '227', '112', '140']
R_UND_N_R_UND_79C18FB3
                                                                                                     
┌──(kali㉿kali)-[~/…/Retos/CRYPTO/Parte3/basic-mod1]
└─$ 
picoCTF{R0UND_N_R0UND_79C18FB3}



```
## Notas adicionales
```bash
exp.py:


datos = open('message.txt').read().split()

  

print(datos)

  

flag = ''

  

for n in datos:

c = int(n) % 37

if 0 < c < 26:

s = chr(c + 65)

elif 26 < c < 36:

s = chr(c + 22)

else:

s = '_'

flag += s

  

print(f"picoCTF{{{flag}}}")

```