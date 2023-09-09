# Level 0--1

## Objetivo
La contraseña para el siguiente nivel se almacena en un archivo llamado Léame ubicado en el directorio de inicio. Utilice esta contraseña para iniciar sesión en bandit1 mediante SSH. Siempre que encuentres una contraseña para un nivel, usa SSH (en el puerto 2220) para iniciar sesión en ese nivel y continuar el juego.

## Datos de acceso al nivel
```
Server    : bandit.labs.overthewire.org
User      : bandit0
Password  : bandit0

```
## Solución
```cmd
bandit0@bandit:~$ pwd
/home/bandit0
bandit0@bandit:~$ ls
readme
bandit0@bandit:~$ cat readme
NH2SXQwcBdpmTEzi3bvBHMM9H66vVXjL


```
## Notas adicionales
| Comando | Descripción |
|---------|-------------|
|pwd| me indica el directorio actual|
|ls| lista de los archivos en la carpeta actual|
| cat readme| mostrar el contenido del archivo llamado "readme"|



## Referencias
