# Level 12--13

## Objetivo
La contraseña para el siguiente nivel se almacena en el archivo **data.txt** , que es un volcado hexadecimal de un archivo que se ha comprimido repetidamente. Para este nivel puede resultar útil crear un directorio en /tmp en el que pueda trabajar utilizando mkdir. Por ejemplo: mkdir /tmp/minombre123. Luego copie el archivo de datos usando cp y cámbiele el nombre usando mv (¡lea las páginas de manual!)
## Datos de acceso al nivel
```
Server    : bbandit12@bandit.labs.overthewire.org
Password  : JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv


```
## Solución
```bash
ssh bandit12@bandit.labs.overthewire.org -p 2220

bandit12@bandit:~$ ls -la
total 24
drwxr-xr-x  2 root     root     4096 Apr 23 18:04 .
drwxr-xr-x 70 root     root     4096 Apr 23 18:05 ..
-rw-r--r--  1 root     root      220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root     root     3771 Jan  6  2022 .bashrc
-rw-r-----  1 bandit13 bandit12 2642 Apr 23 18:04 data.txt
-rw-r--r--  1 root     root      807 Jan  6  2022 .profile
bandit12@bandit:~$ ls
data.txt
bandit12@bandit:~$ cat data.txt | xxd -r
4h�4M��i�"E��BZh91AY&SY{O�_���o����������������׿�����������;Vhd4�A���i�
�@�4A������ڀh4�h4�mF@��
                 C@hd2@
                        �hF���4��X����dB�GaB�~6�V;4A�Gf���͌�>��G�
                                                                           �`w�B��x)�B��׭�
                                                                                           xk�|�I�F��Ds������>R�4�^d��!P^�g�!�)������O^�����1���IF�      7�k�Fx��i�,�2�=�l� [��ĵF�7�YxX�HF��;������ň�`n%,td;PFATu3���SةY_�l��-��<��AV�P�Id��J-���Se'�y�        _1��F�t��#^�ha�X"l=�]��fw��D�Zo,A
                                                                    B�
��
   ����4@weR�I7�}���8v9���H;uH%�}�$�i
                                         �KL��1�������2���v���)�|�R�i�b�� ��A�N��]��BA�>Y|�.��Ebandit12@bandit:~$
bandit12@bandit:~$ mkdir /tmp/prueba
bandit12@bandit:~$ mkdir /tmp/otro
bandit12@bandit:~$ cat data.txt | xxd -r > /tmp/otr/arch.bin
-bash: /tmp/otr/arch.bin: No such file or directory
bandit12@bandit:~$ cat data.txt | xxd -r > /tmp/otro/arch.bin
bandit12@bandit:~$ cd /tmp/otro
bandit12@bandit:/tmp/otro$ ls
arch.bin
bandit12@bandit:/tmp/otro$ file arch.bin
arch.bin: gzip compressed data, was "data2.bin", last modified: Sun Apr 23 18:04:23 2023, max compression, from Unix, original size modulo 2^32 581
bandit12@bandit:/tmp/otro$ mv arch.bin arch.gz
bandit12@bandit:/tmp/otro$ ls
arch.gz
bandit12@bandit:/tmp/otro$ gzip -d arch.gz
bandit12@bandit:/tmp/otro$ ls
arch
bandit12@bandit:/tmp/otro$ file arch
arch: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/otro$ mv arch arch.bz2
bandit12@bandit:/tmp/otro$
bandit12@bandit:/tmp/otro$ bzip2 -d arch bz2
bzip2: Can't open input file arch: No such file or directory.
bzip2: Can't open input file bz2: No such file or directory.
bandit12@bandit:/tmp/otro$ bzip2 -d arch.bz2
bandit12@bandit:/tmp/otro$ ls
arch
bandit12@bandit:/tmp/otro$ file arch
arch: gzip compressed data, was "data4.bin", last modified: Sun Apr 23 18:04:23 2023, max compression, from Unix, original size modulo 2^32 20480
bandit12@bandit:/tmp/otro$ mv arch arch.gz
bandit12@bandit:/tmp/otro$ gzip -d arch.gz
bandit12@bandit:/tmp/otro$ ls
arch
bandit12@bandit:/tmp/otro$ file arch
arch: POSIX tar archive (GNU)
bandit12@bandit:/tmp/otro$ mv arch arch.tar
bandit12@bandit:/tmp/otro$ ls
arch.tar
bandit12@bandit:/tmp/otro$ tar xf arch.tar
bandit12@bandit:/tmp/otro$ ls
arch.tar  data5.bin
bandit12@bandit:/tmp/otro$ del arch.tar
Command 'del' not found, did you mean:
  command 'den' from snap den (1.2.0-0)
  command 'dll' from deb brickos (0.9.0.dfsg-12.2)
  command 'deal' from deb deal (3.1.9-12)
  command 'delv' from deb bind9-dnsutils (1:9.18.12-0ubuntu0.22.04.1)
  command 'dex' from deb dex (0.9.0-1)
  command 'wdel' from deb wput (0.6.2+git20130413-11)
  command 'delp' from deb fp-utils-3.2.2 (3.2.2+dfsg-9ubuntu1)
  command 'mdel' from deb mtools (4.0.33-1+really4.0.32-1build1)
  command 'el' from deb oneliner-el (0.3.6-9.1)
  command 'hdel' from deb hfsutils (3.2.6-15build2)
  command 'qdel' from deb gridengine-client (8.1.9+dfsg-10build1)
  command 'qdel' from deb slurm-wlm-torque (21.08.5-2ubuntu1)
See 'snap info <snapname>' for additional versions.
bandit12@bandit:/tmp/otro$ rm arch.tar
bandit12@bandit:/tmp/otro$ ls
data5.bin
bandit12@bandit:/tmp/otro$ file data5.bin
data5.bin: POSIX tar archive (GNU)
bandit12@bandit:/tmp/otro$ ls
data5.bin
bandit12@bandit:/tmp/otro$ file data5.bin
data5.bin: POSIX tar archive (GNU)
bandit12@bandit:/tmp/otro$ mv data5.bin data5.tar
bandit12@bandit:/tmp/otro$ ls
data5.tar
bandit12@bandit:/tmp/otro$ tar xf data5.tar
bandit12@bandit:/tmp/otro$ ls
data5.tar  data6.bin
bandit12@bandit:/tmp/otro$ rm data5.tar
bandit12@bandit:/tmp/otro$ ls
data6.bin
bandit12@bandit:/tmp/otro$ file data6.bin
data6.bin: bzip2 compressed data, block size = 900k
bandit12@bandit:/tmp/otro$ mv data6.bin data6.bz2
bandit12@bandit:/tmp/otro$ ls
data6.bz2
bandit12@bandit:/tmp/otro$ bzip2 -d data6.bz2
bandit12@bandit:/tmp/otro$ ls
data6
bandit12@bandit:/tmp/otro$ file data 6
data: cannot open `data' (No such file or directory)
6:    cannot open `6' (No such file or directory)
bandit12@bandit:/tmp/otro$ mv data6 data6.tar
bandit12@bandit:/tmp/otro$ ls
data6.tar
bandit12@bandit:/tmp/otro$ tar xf data6.tar
bandit12@bandit:/tmp/otro$ ls
data6.tar  data8.bin
bandit12@bandit:/tmp/otro$ rm data6.tar
bandit12@bandit:/tmp/otro$ ls
data8.bin
bandit12@bandit:/tmp/otro$ file data8.bin
data8.bin: gzip compressed data, was "data9.bin", last modified: Sun Apr 23 18:04:23 2023, max compression, from Unix, original size modulo 2^32 49
bandit12@bandit:/tmp/otro$ mv data8.bin data8.gz
bandit12@bandit:/tmp/otro$ gzip -d data8.gz
bandit12@bandit:/tmp/otro$ ls
data8
bandit12@bandit:/tmp/otro$ file data8
data8: ASCII text
bandit12@bandit:/tmp/otro$ cat data8
The password is wbWdlBxEir4CaE8LaPhauuOo6pwRmrDw
bandit12@bandit:/tmp/otro$ exit
logout
Connection to bandit.labs.overthewire.org closed.

```
## Notas adicionales
| Comando | Descripción |
|---------|-------------|
|ls| lista de los archivos en la carpeta actual|
|cd/| me lleva al directorio raíz|
|cat| se utiliza para concatenar y mostrar el contenido de uno o varios archivos en la salida estándar |
|file| se utiliza para determinar el tipo de archivo mediante su contenido |
|du| se utiliza para mostrar el uso del espacio en disco por archivos y directorios  |
|find| se utiliza para buscar archivos y directorios en una jerarquía de directorios determinada   |
|-a| no ignora los archivos que comienzan con .|
|-l| hacer un listado largo de archivos|
|grep| e utiliza para buscar patrones de texto en archivos o en la salida de otros comandos. |
|man| comando que se utiliza para acceder a las páginas del manual (manuales) que proporcionan documentación detallada sobre diversos comandos, utilidades y funciones del sistema.|
|sort| se utiliza para ordenar líneas de texto en orden alfabético o numérico.|
|uniq| se utiliza para eliminar o mostrar líneas duplicadas consecutivas en un archivo de texto o en la entrada estándar.|
|strings| se utiliza para extraer y mostrar las cadenas de texto legibles en archivos binarios.|
|base64| se utiliza para codificar y decodificar datos en formato base64. Base64 es un sistema de codificación que convierte datos binarios en una representación de texto compuesta por caracteres ASCII imprimibles. |
|tr| se utiliza para realizar transformaciones de caracteres en texto. |
|tar| se utiliza para crear, visualizar, extraer y manipular archivos de formato tar, que son comunes en sistemas basados en Unix |
|gzip| se utiliza para comprimir y descomprimir archivos utilizando el algoritmo de compresión GZIP|
|bzip2| se utiliza para comprimir y descomprimir archivos utilizando el algoritmo de compresión BZIP2. Al igual que GZIP, BZIP2 es un algoritmo de compresión que reduce el tamaño de los archivos para ahorrar espacio en disco y mejorar la eficiencia en la transferencia de datos. |
|xxd| se utiliza para mostrar o crear representaciones hexadecimales y ASCII de archivos binarios. |
| mkdir | Se utiliza para crear directorios o carpetas|


## Referencias
https://en.wikipedia.org/wiki/Hex_dump