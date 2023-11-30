## Objetivo
Our data got corrupted on the way here. Luckily, nothing got replaced, but every block of 3 got scrambled around! The first word seems to be three letters long, maybe you can use that to recover the rest of the message.Download the corrupted message [here](https://artifacts.picoctf.net/c/193/message.txt).
## Datos de acceso al nivel
```
LINK: https://artifacts.picoctf.net/c/193/message.txt

```
## Solución

```bash
┌──(kali㉿kali)-[~]
└─$ cd /home/kali/Documents/ExamenParcial3/Parte1/transposition-trial/
                                                                                                    
┌──(kali㉿kali)-[~/Documents/ExamenParcial3/Parte1/transposition-trial]
└─$ wget https://artifacts.picoctf.net/c/193/message.txt                                        
--2023-11-28 20:32:39--  https://artifacts.picoctf.net/c/193/message.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.64, 3.161.55.26, 3.161.55.100, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.64|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 54 [application/octet-stream]
Saving to: ‘message.txt’

message.txt              100%[==================================>]      54  --.-KB/s    in 0s      

2023-11-28 20:32:40 (51.9 MB/s) - ‘message.txt’ saved [54/54]

                                                                                                    
┌──(kali㉿kali)-[~/Documents/ExamenParcial3/Parte1/transposition-trial]
└─$ file message.txt 
message.txt: ASCII text, with no line terminators
                                                                                                    
┌──(kali㉿kali)-[~/Documents/ExamenParcial3/Parte1/transposition-trial]
└─$ python3 cod.py        
The flag is picoCTF{7R4N5P051N6_15_3XP3N51V3_A9AFB178}
                                                                                                    
┌──(kali㉿kali)-[~/Documents/ExamenParcial3/Parte1/transposition-trial]
└─$ 


```
## Notas adicionales
```bash
******************************************************************
Contenido cod.py
******************************************************************
def main():
f = open("message.txt", "r", encoding="UTF-8")
txt = f.read()

  

n=3
txt3gram = [txt[i:i+n] for i in range(0, len(txt), n)]
decode_lst = []


for i in range(len(txt3gram)):
	decode_lst.append(txt3gram[i][2]+txt3gram[i][0]+txt3gram[i][1])
print(''.join(decode_lst))

if __name__ == '__main__':
main()
******************************************************************

```