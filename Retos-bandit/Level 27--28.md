# Level 27--28
## Objetivo
Hay un repositorio de git a `ssh://bandit27-git@localhost/home/bandit27-git/repo`través del puerto `2220`. La contraseña del usuario `bandit27-git`es la misma que la del usuario `bandit27`.

Clona el repositorio y busca la contraseña para el siguiente nivel.

```
Server    : bbandit27@bandit.labs.overthewire.org
Password  : YnQpBuifNMas1hcUFk70ZmqkhUU2EuaS
```
## Solución
```bash
ssh bandit27@bandit.labs.overthewire.org -p 2220

bandit27@bandit:~$ ls
bandit27@bandit:~$ ls -la
total 20
drwxr-xr-x  2 root root 4096 Apr 23 18:04 .
drwxr-xr-x 70 root root 4096 Apr 23 18:05 ..
-rw-r--r--  1 root root  220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root root 3771 Jan  6  2022 .bashrc
-rw-r--r--  1 root root  807 Jan  6  2022 .profile
bandit27@bandit:~$ mktemp -d
/tmp/tmp.8IZOQi2eUP
bandit27@bandit:~$ cd /tmp/tmp.8IZOQi2eUP
bandit27@bandit:/tmp/tmp.8IZOQi2eUP$ git clone ssh://bandit27-
git@localhost:2220/home/bandit27-git/repo
Cloning into 'bandit27-'...
fatal: no path specified; see 'git help pull' for valid url syntax
-bash: git@localhost:2220/home/bandit27-git/repo: No such file or directory
bandit27@bandit:/tmp/tmp.8IZOQi2eUP$ git clone ssh://bandit27-git@localhost:2220/home/bandit27-git/repo
Cloning into 'repo'...
kex_exchange_identification: read: Connection reset by peer
Connection reset by 127.0.0.1 port 2220
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.
bandit27@bandit:/tmp/tmp.8IZOQi2eUP$ git clone ssh://bandit27-git@localhost:2220/home/bandit27-git/repo
Cloning into 'repo'...
The authenticity of host '[localhost]:2220 ([127.0.0.1]:2220)' can't be established.
ED25519 key fingerprint is SHA256:C2ihUBV7ihnV1wUXRb4RrEcLfXC5CXlhmAAM/urerLY.
This key is not known by any other names
Are you sure you want to continue connecting (yes/no/[fingerprint])? yes
Could not create directory '/home/bandit27/.ssh' (Permission denied).
Failed to add the host to the list of known hosts (/home/bandit27/.ssh/known_hosts).
                         _                     _ _ _
                        | |__   __ _ _ __   __| (_) |_
                        | '_ \ / _` | '_ \ / _` | | __|
                        | |_) | (_| | | | | (_| | | |_
                        |_.__/ \__,_|_| |_|\__,_|_|\__|


                      This is an OverTheWire game server.
            More information on http://www.overthewire.org/wargames

bandit27-git@localhost's password:
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
Receiving objects: 100% (3/3), done.
bandit27@bandit:/tmp/tmp.8IZOQi2eUP$ ls -la
total 10564
drwx------    3 bandit27 bandit27     4096 Sep 20 16:48 .
drwxrwx-wt 2332 root     root     10801152 Sep 20 16:48 ..
drwxrwxr-x    3 bandit27 bandit27     4096 Sep 20 16:48 repo
bandit27@bandit:/tmp/tmp.8IZOQi2eUP$ cat README
cat: README: No such file or directory
bandit27@bandit:/tmp/tmp.8IZOQi2eUP$ cd repo
bandit27@bandit:/tmp/tmp.8IZOQi2eUP/repo$ cat README
The password to the next level is: AVanL161y9rsbcJIsFHuw35rjaOM19nR
bandit27@bandit:/tmp/tmp.8IZOQi2eUP/repo$
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