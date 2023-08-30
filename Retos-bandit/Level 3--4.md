# Level 3--4

## Objetivo
La contraseña para el siguiente nivel se almacena en un archivo oculto en el directorio **interno** .
## Datos de acceso al nivel
```
Server    : bandit.labs.overthewire.org
Password  : aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG

```
## Solución
```bash
ssh bandit3@bandit.labs.overthewire.org -p 2220

bandit3@bandit:~$ ls
inhere

bandit3@bandit:~$ cd inhere

bandit3@bandit:~/inhere$ ls

bandit3@bandit:~/inhere$ man ls

bandit3@bandit:~/inhere$ ls -a
.  ..  .hidden

bandit3@bandit:~/inhere$ cat .hidden
2EW7BBsr6aMMoJ2HjW067dm8EgX26xNe

bandit3@bandit:~/inhere$ exit
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

## Referencias
