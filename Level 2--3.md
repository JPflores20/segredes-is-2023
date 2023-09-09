# Level 2--3

## Objetivo
La contraseña para el siguiente nivel se almacena en un archivo llamado **espacios en este nombre de archivo** ubicado en el directorio de inicio.
## Datos de acceso al nivel
```
Server    : bandit.labs.overthewire.org
Password  : rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi

```
## Solución
```bash
ssh bandit2@bandit.labs.overthewire.org -p 2220
bandit2@bandit:~$ ls
spaces in this filename

bandit2@bandit:~$ cat "spaces in this filename"
aBZ0W5EmUfAf7kHTQeOwd8bauFJ2lAiG

bandit2@bandit:~$ exit

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

## Referencias
https://linuxopsys.com/topics/how-to-read-filename-with-spaces-in-linux