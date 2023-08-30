# Level 1--2

## Objetivo
La contraseña para el siguiente nivel se almacena en un archivo llamado - ubicado en el directorio de inicio
## Datos de acceso al nivel
```
Server    : bandit.labs.overthewire.org
Password readme: NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL

```
## Solución
```bash
ssh bandit1@bandit.labs.overthewire.org -p 2220
bandit1@bandit:~$ ls
-
bandit1@bandit:~$ cat ./-
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi

bandit1@bandit:~$ pwd
/home/bandit1

bandit1@bandit:~$ cat /home/bandit1/-
rRGizSaX8Mk1RTb1CNQoXTcYZWU6lgzi

bandit1@bandit:~$

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
https://unix.stackexchange.com/questions/16357/usage-of-dash-in-place-of-a-filename