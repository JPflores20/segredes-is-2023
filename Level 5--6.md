# Level 5--6

## Objetivo
La contraseña para el siguiente nivel se almacena en un archivo en algún lugar del directorio **interno** y tiene todas las siguientes propiedades:

- legible por humanos
- 1033 bytes de tamaño
- no ejecutable
## Datos de acceso al nivel
```
Server    : bandit.labs.overthewire.org
Password  : lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR
```
## Solución
```bash
ssh bandit5@bandit.labs.overthewire.org -p 2220
bandit5@bandit:~/inhere$ ls
maybehere00  maybehere02  maybehere04  maybehere06  maybehere08  maybehere10  maybehere12  maybehere14  maybehere16  maybehere18
maybehere01  maybehere03  maybehere05  maybehere07  maybehere09  maybehere11  maybehere13  maybehere15  maybehere17  maybehere19

bandit5@bandit:~/inhere$ man ls

bandit5@bandit:~/inhere$ man find

bandit5@bandit:~/inhere$ find . -size 1033c -type f
./maybehere07/.file2

bandit5@bandit:~/inhere$ cat  ./maybehere07/.file2
P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU

bandit5@bandit:~/inhere$ exit
logout
Connection to bandit

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

## Referencias
CONTRASEÑA NIVEL 6
P4L4vucdmLnm8I7Vl7jG1ApGSfjYKqJU