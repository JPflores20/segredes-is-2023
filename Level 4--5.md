# Level 4--5

## Objetivo
La contraseña para el siguiente nivel se almacena en el único archivo legible por humanos en el directorio **interno** . Consejo: si tu terminal está estropeado, prueba el comando “reset”.
## Datos de acceso al nivel
```
Server    : bandit.labs.overthewire.org
Password  : 2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe
```
## Solución
```bash
ssh bandit4@bandit.labs.overthewire.org -p 2220

bandit4@bandit:~/inhere$ ls
-file00  -file01  -file02  -file03  -file04  -file05  -file06  -file07  -file08  -file09

bandit4@bandit:~/inhere$ man file

bandit4@bandit:~/inhere$ file ./*
./-file00: data
./-file01: data
./-file02: data
./-file03: data
./-file04: data
./-file05: data
./-file06: data
./-file07: ASCII text
./-file08: data
./-file09: Non-ISO extended-ASCII text, with no line terminators

bandit4@bandit:~/inhere$ cat ./-file07
lrIWWI6bB37kxfiCQZqUdOIYfr6eEeqR

bandit4@bandit:~/inhere$ exit
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
	|* | es un comodin que me ayuda a aplicar el comando a todos los archivos|
	
## Referencias
