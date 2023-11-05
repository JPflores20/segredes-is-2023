## Objetivo

## Datos de acceso al nivel
```
Link: 

```
## Solución

```bash
┌──(kali㉿kali)-[~]
└─$ cd /home/kali/Downloads/
                                                                                                   
┌──(kali㉿kali)-[~/Downloads]
└─$ ls
img.jpg  message.wav  whitepages.txt
                                                                                                   
┌──(kali㉿kali)-[~/Downloads]
└─$ xxd -l 100 whitepages.txt 
Command 'xxd' not found, but can be installed with:
sudo apt install xxd
Do you want to install it? (N/y)y
sudo apt install xxd
[sudo] password for kali: 
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following NEW packages will be installed:
  xxd
0 upgraded, 1 newly installed, 0 to remove and 545 not upgraded.
Need to get 91.3 kB of archives.
After this operation, 145 kB of additional disk space will be used.
Get:1 http://kali.download/kali kali-rolling/main amd64 xxd amd64 2:9.0.1672-1 [91.3 kB]
Fetched 91.3 kB in 2s (52.4 kB/s)                
Selecting previously unselected package xxd.
(Reading database ... 403494 files and directories currently installed.)
Preparing to unpack .../xxd_2%3a9.0.1672-1_amd64.deb ...
Unpacking xxd (2:9.0.1672-1) ...
Setting up xxd (2:9.0.1672-1) ...
Processing triggers for man-db (2.11.2-3) ...
Processing triggers for kali-menu (2023.4.3) ...
                                                                                                   
┌──(kali㉿kali)-[~/Downloads]
└─$ xxd -l 100 whitepages.txt
00000000: e280 83e2 8083 e280 83e2 8083 20e2 8083  ............ ...
00000010: 20e2 8083 e280 83e2 8083 e280 83e2 8083   ...............
00000020: 20e2 8083 e280 8320 e280 83e2 8083 e280   ...... ........
00000030: 83e2 8083 20e2 8083 e280 8320 e280 8320  .... ...... ... 
00000040: 2020 e280 83e2 8083 e280 83e2 8083 e280    ..............
00000050: 8320 20e2 8083 20e2 8083 e280 8320 e280  .  ... ...... ..
00000060: 8320 20e2                                .  .
                                                                                                   
┌──(kali㉿kali)-[~/Downloads]
└─$ cat whitepages.txt      
                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                   
┌──(kali㉿kali)-[~/Downloads]
└─$ 

2: ABRIMOS EL EDITOR DE TEXTOS Y REMPLAZAMOS EL PRIMER ESPACIO POR 0 Y LOS ESPACIOS RESTANTES EN BLANCO POR 1 NOS DARÁ EL SIGUIENTE CODIGO BINARIO:
─(kali㉿kali)-[~/Downloads]
└─$1cat1whitepages.txt111111
00001010000010010000100101110000011010010110001101101111010000110101010001000110000010100000101000001001000010010101001101000101010001010010000001010000010101010100001001001100010010010100001100100000010100100100010101000011010011110101001001000100010100110010000000100110001000000100001001000001010000110100101101000111010100100100111101010101010011100100010000100000010100100100010101010000010011110101001001010100000010100000100100001001001101010011000000110000001100000010000001000110011011110111001001100010011001010111001100100000010000010111011001100101001011000010000001010000011010010111010001110100011100110110001001110101011100100110011101101000001011000010000001010000010000010010000000110001001101010011001000110001001100110000101000001001000010010111000001101001011000110110111101000011010101000100011001111011011011100110111101110100010111110110000101101100011011000101111101110011011100000110000101100011011001010111001101011111011000010111001001100101010111110110001101110010011001010110000101110100011001010110010001011111011001010111000101110101011000010110110001011111011000110011010100110100011001100011001000110111011000110110010000110000001101010110001100110010001100010011100000111001011001100011100000110001001101000011011101100011011000110011011001100110001101010110010001100101011000100011001001100101001101010011011001111101000010100000100100001001111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111111
┌──(kali㉿kali)-[~/Downloads]
picoCTF{not_all_spaces_are_created_equal_c54f27cd05c2189f8147cc6f5deb2e56}
```
## Notas adicionales
```bash

```
