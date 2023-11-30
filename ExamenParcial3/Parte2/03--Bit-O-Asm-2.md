## Objetivo
Can you figure out what is in the `eax` register? Put your answer in the picoCTF flag format: `picoCTF{n}` where `n` is the contents of the `eax` register in the decimal number base. If the answer was `0x11` your flag would be `picoCTF{17}`.Download the assembly dump [here](https://artifacts.picoctf.net/c/510/disassembler-dump0_b.txt).
## Datos de acceso al nivel
```
LINK: https://artifacts.picoctf.net/c/510/disassembler-dump0_b.txt

```
## Solución

```bash
┌──(kali㉿kali)-[~]
└─$ cd /home/kali/Documents/ExamenParcial3/Parte2/Bit-O-Asm-2/
                                                                                                    
┌──(kali㉿kali)-[~/Documents/ExamenParcial3/Parte2/Bit-O-Asm-2]
└─$ wget https://artifacts.picoctf.net/c/510/disassembler-dump0_b.txt
--2023-11-29 13:44:18--  https://artifacts.picoctf.net/c/510/disassembler-dump0_b.txt
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.64, 3.161.55.26, 3.161.55.100, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.64|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 270 [application/octet-stream]
Saving to: ‘disassembler-dump0_b.txt’

disassembler-dump0_b.txt 100%[==================================>]     270  --.-KB/s    in 0s      

2023-11-29 13:44:19 (5.93 MB/s) - ‘disassembler-dump0_b.txt’ saved [270/270]

                                                                                                    
┌──(kali㉿kali)-[~/Documents/ExamenParcial3/Parte2/Bit-O-Asm-2]
└─$ cat disassembler-dump0_b.txt                                                   
<+0>:     endbr64 
<+4>:     push   rbp
<+5>:     mov    rbp,rsp
<+8>:     mov    DWORD PTR [rbp-0x14],edi
<+11>:    mov    QWORD PTR [rbp-0x20],rsi
<+15>:    mov    DWORD PTR [rbp-0x4],0x9fe1a
<+22>:    mov    eax,DWORD PTR [rbp-0x4]
<+25>:    pop    rbp
<+26>:    ret
                                                                                                    
┌──(kali㉿kali)-[~/Documents/ExamenParcial3/Parte2/Bit-O-Asm-2]
└─$ python3
Python 3.11.4 (main, Jun  7 2023, 10:13:09) [GCC 12.2.0] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>> print(int("0x9fe1a",16))
654874
>>> 
*********************************
picoCTF{654874}
*********************************

```
## Notas adicionales
```bash


```