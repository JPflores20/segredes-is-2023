## Objetivo
Can you get the flag?Download this [binary](https://artifacts.picoctf.net/c/87/gdbme).Here's the test drive instructions:

- `$ chmod +x gdbme`
- `$ gdb gdbme`
- `(gdb) layout asm`
- `(gdb) break *(main+99)`
- `(gdb) run`
- `(gdb) jump *(main+104)`
## Datos de acceso al nivel
```
LINK: https://artifacts.picoctf.net/c/87/gdbme

```
## Solución

```bash
┌──(kali㉿kali)-[~]
└─$ cd /home/kali/Documents/Retos/REVERSING/Parte3/GDBTestDrive/
                                                                                                    
┌──(kali㉿kali)-[~/…/Retos/REVERSING/Parte3/GDBTestDrive]
└─$ wget https://artifacts.picoctf.net/c/87/gdbme                                             
--2023-11-15 00:14:36--  https://artifacts.picoctf.net/c/87/gdbme
Resolving artifacts.picoctf.net (artifacts.picoctf.net)... 3.161.55.64, 3.161.55.61, 3.161.55.26, ...
Connecting to artifacts.picoctf.net (artifacts.picoctf.net)|3.161.55.64|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 17048 (17K) [application/octet-stream]
Saving to: ‘gdbme’

gdbme                    100%[==================================>]  16.65K  --.-KB/s    in 0s      

2023-11-15 00:14:37 (186 MB/s) - ‘gdbme’ saved [17048/17048]

                                                                                                    
┌──(kali㉿kali)-[~/…/Retos/REVERSING/Parte3/GDBTestDrive]
└─$ gdb gdbme 
Command 'gdb' not found, but can be installed with:
sudo apt install gdb        
sudo apt install gdb-minimal
                                                                                                    
┌──(kali㉿kali)-[~/…/Retos/REVERSING/Parte3/GDBTestDrive]
└─$ sudo apt-get update          
[sudo] password for kali: 
Get:1 http://packages.microsoft.com/repos/code stable InRelease [3,569 B]
Get:3 http://packages.microsoft.com/repos/code stable/main amd64 Packages [21.6 kB]
Get:4 http://packages.microsoft.com/repos/code stable/main arm64 Packages [21.7 kB]
Get:5 http://packages.microsoft.com/repos/code stable/main armhf Packages [21.9 kB]
Get:2 http://kali.download/kali kali-rolling InRelease [41.2 kB]
Get:6 http://kali.download/kali kali-rolling/main amd64 Packages [19.5 MB]
Get:7 http://kali.download/kali kali-rolling/main amd64 Contents (deb) [46.0 MB]
Get:8 http://kali.download/kali kali-rolling/contrib amd64 Packages [124 kB]
Get:9 http://kali.download/kali kali-rolling/contrib amd64 Contents (deb) [297 kB]
Get:10 http://kali.download/kali kali-rolling/non-free amd64 Packages [226 kB]
Get:11 http://kali.download/kali kali-rolling/non-free amd64 Contents (deb) [913 kB]
Fetched 67.1 MB in 8s (8,923 kB/s)                                                                 
Reading package lists... Done
                                                                                                    
┌──(kali㉿kali)-[~/…/Retos/REVERSING/Parte3/GDBTestDrive]
└─$ sudo apt-get install gdb     
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following additional packages will be installed:
  libbabeltrace1 libboost-iostreams1.74.0 libboost-regex1.74.0 libboost-thread1.74.0
  libboost1.74-dev libc-bin libc-dev-bin libc-devtools libc-l10n libc6 libc6-dbg libc6-dev
  libc6-i386 libdebuginfod-common libdebuginfod1 libipt2 libsource-highlight-common
  libsource-highlight4v5 locales
Suggested packages:
  gdb-doc gdbserver libboost1.74-doc libboost-atomic1.74-dev libboost-chrono1.74-dev
  libboost-container1.74-dev libboost-context1.74-dev libboost-contract1.74-dev
  libboost-coroutine1.74-dev libboost-date-time1.74-dev libboost-exception1.74-dev
  libboost-fiber1.74-dev libboost-filesystem1.74-dev libboost-graph1.74-dev
  libboost-graph-parallel1.74-dev libboost-iostreams1.74-dev libboost-locale1.74-dev
  libboost-log1.74-dev libboost-math1.74-dev libboost-mpi1.74-dev libboost-mpi-python1.74-dev
  libboost-numpy1.74-dev libboost-program-options1.74-dev libboost-python1.74-dev
  libboost-random1.74-dev libboost-regex1.74-dev libboost-serialization1.74-dev
  libboost-stacktrace1.74-dev libboost-system1.74-dev libboost-test1.74-dev
  libboost-thread1.74-dev libboost-timer1.74-dev libboost-type-erasure1.74-dev
  libboost-wave1.74-dev libboost1.74-tools-dev libmpfrc++-dev libntl-dev libboost-nowide1.74-dev
  glibc-doc libnss-nis libnss-nisplus
The following NEW packages will be installed:
  gdb libbabeltrace1 libboost-regex1.74.0 libc6-dbg libdebuginfod-common libdebuginfod1 libipt2
  libsource-highlight-common libsource-highlight4v5
The following packages will be upgraded:
  libboost-iostreams1.74.0 libboost-thread1.74.0 libboost1.74-dev libc-bin libc-dev-bin
  libc-devtools libc-l10n libc6 libc6-dev libc6-i386 locales
11 upgraded, 9 newly installed, 0 to remove and 1056 not upgraded.
Need to get 34.9 MB of archives.
After this operation, 28.4 MB of additional disk space will be used.
Do you want to continue? [Y/n] y
Get:1 http://kali.download/kali kali-rolling/main amd64 libc-devtools amd64 2.37-12 [53.9 kB]
Get:2 http://kali.download/kali kali-rolling/main amd64 libc6-dev amd64 2.37-12 [1,905 kB]
Get:3 http://kali.download/kali kali-rolling/main amd64 libc-dev-bin amd64 2.37-12 [46.3 kB]
Get:4 http://kali.download/kali kali-rolling/main amd64 libc6-i386 amd64 2.37-12 [2,457 kB]
Get:5 http://kali.download/kali kali-rolling/main amd64 libc6 amd64 2.37-12 [2,753 kB]
Get:6 http://kali.download/kali kali-rolling/main amd64 libc-bin amd64 2.37-12 [601 kB]
Get:7 http://kali.download/kali kali-rolling/main amd64 libdebuginfod-common all 0.189-4 [22.2 kB]
Get:8 http://kali.download/kali kali-rolling/main amd64 libc-l10n all 2.37-12 [708 kB]
Get:9 http://kali.download/kali kali-rolling/main amd64 locales all 2.37-12 [3,906 kB]
Get:10 http://kali.download/kali kali-rolling/main amd64 libbabeltrace1 amd64 1.5.11-3 [176 kB]
Get:11 http://kali.download/kali kali-rolling/main amd64 libdebuginfod1 amd64 0.189-4 [27.6 kB]
Get:12 http://kali.download/kali kali-rolling/main amd64 libipt2 amd64 2.0.6-1 [43.2 kB]
Get:13 http://kali.download/kali kali-rolling/main amd64 libsource-highlight-common all 3.1.9-4.2 [77.4 kB]
Get:14 http://http.kali.org/kali kali-rolling/main amd64 libboost-regex1.74.0 amd64 1.74.0+ds1-23 [487 kB]
Get:15 http://http.kali.org/kali kali-rolling/main amd64 libsource-highlight4v5 amd64 3.1.9-4.2+b3 [257 kB]
Get:16 http://kali.download/kali kali-rolling/main amd64 gdb amd64 13.2-1 [3,968 kB]
Get:17 http://http.kali.org/kali kali-rolling/main amd64 libboost-iostreams1.74.0 amd64 1.74.0+ds1-23 [241 kB]
Get:18 http://http.kali.org/kali kali-rolling/main amd64 libboost-thread1.74.0 amd64 1.74.0+ds1-23 [258 kB]
Get:19 http://http.kali.org/kali kali-rolling/main amd64 libboost1.74-dev amd64 1.74.0+ds1-23 [9,511 kB]
Get:20 http://kali.download/kali kali-rolling/main amd64 libc6-dbg amd64 2.37-12 [7,439 kB]
Fetched 34.9 MB in 3s (11.7 MB/s)     
Preconfiguring packages ...
(Reading database ... 405102 files and directories currently installed.)
Preparing to unpack .../libc-devtools_2.37-12_amd64.deb ...
Unpacking libc-devtools (2.37-12) over (2.37-6) ...
Preparing to unpack .../libc6-dev_2.37-12_amd64.deb ...
Unpacking libc6-dev:amd64 (2.37-12) over (2.37-6) ...
Preparing to unpack .../libc-dev-bin_2.37-12_amd64.deb ...
Unpacking libc-dev-bin (2.37-12) over (2.37-6) ...
Preparing to unpack .../libc6-i386_2.37-12_amd64.deb ...
Unpacking libc6-i386 (2.37-12) over (2.37-6) ...
Preparing to unpack .../libc6_2.37-12_amd64.deb ...
Unpacking libc6:amd64 (2.37-12) over (2.37-6) ...
Setting up libc6:amd64 (2.37-12) ...
(Reading database ... 405102 files and directories currently installed.)
Preparing to unpack .../libc-bin_2.37-12_amd64.deb ...
Unpacking libc-bin (2.37-12) over (2.37-6) ...
Setting up libc-bin (2.37-12) ...
Selecting previously unselected package libdebuginfod-common.
(Reading database ... 405102 files and directories currently installed.)
Preparing to unpack .../00-libdebuginfod-common_0.189-4_all.deb ...
Unpacking libdebuginfod-common (0.189-4) ...
Preparing to unpack .../01-libc-l10n_2.37-12_all.deb ...
Unpacking libc-l10n (2.37-12) over (2.37-6) ...
Preparing to unpack .../02-locales_2.37-12_all.deb ...
Unpacking locales (2.37-12) over (2.37-6) ...
Selecting previously unselected package libbabeltrace1:amd64.
Preparing to unpack .../03-libbabeltrace1_1.5.11-3_amd64.deb ...
Unpacking libbabeltrace1:amd64 (1.5.11-3) ...
Selecting previously unselected package libdebuginfod1:amd64.
Preparing to unpack .../04-libdebuginfod1_0.189-4_amd64.deb ...
Unpacking libdebuginfod1:amd64 (0.189-4) ...
Selecting previously unselected package libipt2.
Preparing to unpack .../05-libipt2_2.0.6-1_amd64.deb ...
Unpacking libipt2 (2.0.6-1) ...
Selecting previously unselected package libsource-highlight-common.
Preparing to unpack .../06-libsource-highlight-common_3.1.9-4.2_all.deb ...
Unpacking libsource-highlight-common (3.1.9-4.2) ...
Selecting previously unselected package libboost-regex1.74.0:amd64.
Preparing to unpack .../07-libboost-regex1.74.0_1.74.0+ds1-23_amd64.deb ...
Unpacking libboost-regex1.74.0:amd64 (1.74.0+ds1-23) ...
Selecting previously unselected package libsource-highlight4v5:amd64.
Preparing to unpack .../08-libsource-highlight4v5_3.1.9-4.2+b3_amd64.deb ...
Unpacking libsource-highlight4v5:amd64 (3.1.9-4.2+b3) ...
Selecting previously unselected package gdb.
Preparing to unpack .../09-gdb_13.2-1_amd64.deb ...
Unpacking gdb (13.2-1) ...
Preparing to unpack .../10-libboost-iostreams1.74.0_1.74.0+ds1-23_amd64.deb ...
Unpacking libboost-iostreams1.74.0:amd64 (1.74.0+ds1-23) over (1.74.0+ds1-22) ...
Preparing to unpack .../11-libboost-thread1.74.0_1.74.0+ds1-23_amd64.deb ...
Unpacking libboost-thread1.74.0:amd64 (1.74.0+ds1-23) over (1.74.0+ds1-22) ...
Preparing to unpack .../12-libboost1.74-dev_1.74.0+ds1-23_amd64.deb ...
Unpacking libboost1.74-dev:amd64 (1.74.0+ds1-23) over (1.74.0+ds1-22) ...
Selecting previously unselected package libc6-dbg:amd64.
Preparing to unpack .../13-libc6-dbg_2.37-12_amd64.deb ...
Unpacking libc6-dbg:amd64 (2.37-12) ...
Setting up libc-l10n (2.37-12) ...
Setting up libboost1.74-dev:amd64 (1.74.0+ds1-23) ...
Setting up libdebuginfod-common (0.189-4) ...
Setting up libboost-iostreams1.74.0:amd64 (1.74.0+ds1-23) ...
Setting up libdebuginfod1:amd64 (0.189-4) ...
Setting up locales (2.37-12) ...
Generating locales (this might take a while)...
  en_US.UTF-8... done
Generation complete.
Setting up libsource-highlight-common (3.1.9-4.2) ...
Setting up libc6-dbg:amd64 (2.37-12) ...
Setting up libboost-regex1.74.0:amd64 (1.74.0+ds1-23) ...
Setting up libipt2 (2.0.6-1) ...
Setting up libbabeltrace1:amd64 (1.5.11-3) ...
Setting up libc6-i386 (2.37-12) ...
Setting up libc-dev-bin (2.37-12) ...
Setting up libsource-highlight4v5:amd64 (3.1.9-4.2+b3) ...
Setting up libc-devtools (2.37-12) ...
Setting up libboost-thread1.74.0:amd64 (1.74.0+ds1-23) ...
Setting up gdb (13.2-1) ...
Setting up libc6-dev:amd64 (2.37-12) ...
Processing triggers for libc-bin (2.37-12) ...
Processing triggers for man-db (2.11.2-3) ...
Processing triggers for kali-menu (2023.4.3) ...
                                                                                                    
┌──(kali㉿kali)-[~/…/Retos/REVERSING/Parte3/GDBTestDrive]
└─$ sudo dnf install gdb

sudo: dnf: command not found
                                                                                                    
┌──(kali㉿kali)-[~/…/Retos/REVERSING/Parte3/GDBTestDrive]
└─$ sudo dnf install gdb

sudo: dnf: command not found
                                                                                                    
┌──(kali㉿kali)-[~/…/Retos/REVERSING/Parte3/GDBTestDrive]
└─$ 
                                                                                                    
┌──(kali㉿kali)-[~/…/Retos/REVERSING/Parte3/GDBTestDrive]
└─$ gdb --version

GNU gdb (Debian 13.2-1) 13.2
Copyright (C) 2023 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.
                                                                                                    
┌──(kali㉿kali)-[~/…/Retos/REVERSING/Parte3/GDBTestDrive]
└─$ gdb gdbme               
GNU gdb (Debian 13.2-1) 13.2
Copyright (C) 2023 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.
Type "show copying" and "show warranty" for details.
This GDB was configured as "x86_64-linux-gnu".
Type "show configuration" for configuration details.
For bug reporting instructions, please see:
<https://www.gnu.org/software/gdb/bugs/>.
Find the GDB manual and other documentation resources online at:
    <http://www.gnu.org/software/gdb/documentation/>.

For help, type "help".
Type "apropos word" to search for commands related to "word"...
Reading symbols from gdbme...
(No debugging symbols found in gdbme)
(gdb) layout asm

zsh: suspended  gdb gdbme
                                                                                                    
┌──(kali㉿kali)-[~/…/Retos/REVERSING/Parte3/GDBTestDrive]
└─$ chmod +x gdbme
                                                                                                    
┌──(kali㉿kali)-[~/…/Retos/REVERSING/Parte3/GDBTestDrive]
└─$ gdb gdbme     
GNU gdb (Debian 13.2-1) 13.2
Copyright (C) 2023 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.
Type "show copying" and "show warranty" for details.
This GDB was configured as "x86_64-linux-gnu".
Type "show configuration" for configuration details.
For bug reporting instructions, please see:
<https://www.gnu.org/software/gdb/bugs/>.
Find the GDB manual and other documentation resources online at:
    <http://www.gnu.org/software/gdb/documentation/>.

For help, type "help".
Type "apropos word" to search for commands related to "word"...
Reading symbols from gdbme...
(No debugging symbols found in gdbme)
(gdb) layout asm

zsh: suspended  gdb gdbme
                                                                                                    
┌──(kali㉿kali)-[~/…/Retos/REVERSING/Parte3/GDBTestDrive]
└─$ 

picoCTF{d3bugg3r_dr1v3_7776d758}
```
## Notas adicionales
```bash


```
![[Pasted image 20231114233236.png]]