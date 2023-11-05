## Objetivo
In RSA, a small `e` value can be problematic, but what about `N`? Can you decrypt this? [values](https://mercury.picoctf.net/static/b9ddda080c56fb421bf30409bec3460d/values)
## Datos de acceso al nivel
```
LINK: https://mercury.picoctf.net/static/b9ddda080c56fb421bf30409bec3460d/values

```
## Solución

```bash
┌──(kali㉿kali)-[~]
└─$ cd /home/kali/Documents/Retos/CRYPTO/Parte3/
                                                                                                    
┌──(kali㉿kali)-[~/Documents/Retos/CRYPTO/Parte3]
└─$ wget https://mercury.picoctf.net/static/b9ddda080c56fb421bf30409bec3460d/values               
--2023-11-05 02:36:00--  https://mercury.picoctf.net/static/b9ddda080c56fb421bf30409bec3460d/values
Resolving mercury.picoctf.net (mercury.picoctf.net)... 18.189.209.142
Connecting to mercury.picoctf.net (mercury.picoctf.net)|18.189.209.142|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 206 [application/octet-stream]
Saving to: ‘values’

values                   100%[==================================>]     206  --.-KB/s    in 0s      

2023-11-05 02:36:01 (436 MB/s) - ‘values’ saved [206/206]

                                                                                                    
┌──(kali㉿kali)-[~/Documents/Retos/CRYPTO/Parte3]
└─$ values
values: command not found
                                                                                                    
┌──(kali㉿kali)-[~/Documents/Retos/CRYPTO/Parte3]
└─$ cat values                                  
Decrypt my super sick RSA:
c: 964354128913912393938480857590969826308054462950561875638492039363373779803642185
n: 1584586296183412107468474423529992275940096154074798537916936609523894209759157543
e: 65537                                                                                                    
┌──(kali㉿kali)-[~/Documents/Retos/CRYPTO/Parte3]
└─$ sudo python3 -m pip install gmpy2
[sudo] password for kali: 
DEPRECATION: Loading egg at /usr/local/lib/python3.11/dist-packages/PySoundFile-0.9.0.post1-py3.11.egg is deprecated. pip 23.3 will enforce this behaviour change. A possible replacement is to use pip for package installation..
DEPRECATION: Loading egg at /usr/local/lib/python3.11/dist-packages/sstv-0.1-py3.11.egg is deprecated. pip 23.3 will enforce this behaviour change. A possible replacement is to use pip for package installation..
Requirement already satisfied: gmpy2 in /usr/local/lib/python3.11/dist-packages (2.1.5)
WARNING: Running pip as the 'root' user can result in broken permissions and conflicting behaviour with the system package manager. It is recommended to use a virtual environment instead: https://pip.pypa.io/warnings/venv
                                                                                                    
┌──(kali㉿kali)-[~/Documents/Retos/CRYPTO/Parte3]
└─$ sudo python3 -m pip install pycryptodome
DEPRECATION: Loading egg at /usr/local/lib/python3.11/dist-packages/PySoundFile-0.9.0.post1-py3.11.egg is deprecated. pip 23.3 will enforce this behaviour change. A possible replacement is to use pip for package installation..
DEPRECATION: Loading egg at /usr/local/lib/python3.11/dist-packages/sstv-0.1-py3.11.egg is deprecated. pip 23.3 will enforce this behaviour change. A possible replacement is to use pip for package installation..
Requirement already satisfied: pycryptodome in /usr/local/lib/python3.11/dist-packages (3.19.0)
WARNING: Running pip as the 'root' user can result in broken permissions and conflicting behaviour with the system package manager. It is recommended to use a virtual environment instead: https://pip.pypa.io/warnings/venv                                                                               
                                                                                                    
┌──(kali㉿kali)-[~/Documents/Retos/CRYPTO/Parte3]
└─$ python3
Python 3.11.4 (main, Jun  7 2023, 10:13:09) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> from Crypto.Util.number import long_to_bytes
>>> from Crypto.Util.number import inverse
>>> c = 964354128913912393938480857590969826308054462950561875638492039363373779803642185
>>> e = 65537
>>> p = 2434792384523484381583634042478415057961
>>> q = 650809615742055581459820253356987396346063
>>> n = p * q
>>> n
1584586296183412107468474423529992275940096154074798537916936609523894209759157543
>>> tn = (p-1)*(q-1)
>>> d = inverse(e,tn)
>>> d
935562844569036545560296463739101898548923569077653917264816483618391559307175713
>>> m = pow(c,d,n)
>>> m
13016382529449106065927291425342535437996222135352905256639684640304028661985917
>>> long_to_bytes(m)
b'picoCTF{sma11_N_n0_g0od_73918962}'
>>> 


```
## Notas adicionales
```bash


```