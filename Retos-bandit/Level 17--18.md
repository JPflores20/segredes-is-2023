# Level 17--18
## Objetivo
Hay 2 archivos en el directorio de inicio: **contraseñas.old y contraseñas.nueva** . La contraseña para el siguiente nivel está en **contraseñas.nueva** y es la única línea que se ha cambiado entre **contraseñas.antiguas y contraseñas.nuevas.**
## Datos de acceso al nivel
```
Server    : bbandit17@bandit.labs.overthewire.org
Password  : 

```
## Solución
```bash
ssh bandit17@bandit.labs.overthewire.org -p 2220

bandit17@bandit:~$ ls -la
total 36
drwxr-xr-x  3 root     root     4096 Apr 23 18:04 .
drwxr-xr-x 70 root     root     4096 Apr 23 18:05 ..
-rw-r-----  1 bandit17 bandit17   33 Apr 23 18:04 .bandit16.password
-rw-r--r--  1 root     root      220 Jan  6  2022 .bash_logout
-rw-r--r--  1 root     root     3771 Jan  6  2022 .bashrc
-rw-r-----  1 bandit18 bandit17 3300 Apr 23 18:04 passwords.new
-rw-r-----  1 bandit18 bandit17 3300 Apr 23 18:04 passwords.old
-rw-r--r--  1 root     root      807 Jan  6  2022 .profile
drwxr-xr-x  2 root     root     4096 Apr 23 18:04 .ssh
bandit17@bandit:~$ diff passwords.old passwords.new --color
42c42
< glZreTEH1V3cGKL6g4conYqZqaEj0mte
---
> hga5tuuCLF6fFzUpnagiMN8ssu9LFrdg
bandit17@bandit:~$

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