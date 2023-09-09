# Level 6--7

## Objetivo
La contraseña para el siguiente nivel se almacena **en algún lugar del servidor** y tiene todas las propiedades siguientes:

- propiedad del usuario bandit7
- propiedad del grupo bandit6
- 33 bytes de tamaño
## Datos de acceso al nivel
```
Server    : bandit.labs.overthewire.org
Password  : P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU
```
## Solución
```bash
ssh bandit6@bandit.labs.overthewire.org -p 2220

bandit6@bandit:~$ ls

bandit6@bandit:~$ pwd
/home/bandit6

bandit6@bandit:~$ man find

bandit6@bandit:~$ ls /
bin   dev      etc         home     lib    lib64   lost+found  mnt  proc  run   snap  sys  usr
boot  drifter  formulaone  krypton  lib32  libx32  media       opt  root  sbin  srv   tmp  var

bandit6@bandit:~$ find / -user bandit7 -group bandit6 -size 33c 2>/dev/null
/var/lib/dpkg/info/bandit7.password

bandit6@bandit:~$ cat /var/lib/dpkg/info/bandit7.password
z7WtoNQU2XfjmMtWA8u5rN4vzqu4v99S

bandit6@bandit:~$ exit
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
## Referencias