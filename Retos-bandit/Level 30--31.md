# Level 30--31
## Objetivo
Hay un repositorio de git a `ssh://bandit30-git@localhost/home/bandit30-git/repo`través del puerto `2220`. La contraseña del usuario `bandit30-git`es la misma que la del usuario `bandit30`.

Clona el repositorio y busca la contraseña para el siguiente nivel.

```
Server    : bbandit30@bandit.labs.overthewire.org
Password  : 
```
## Solución
```bash
ssh bandit30@bandit.labs.overthewire.org -p 2220

bandit30@bandit:~$ mkdir /tmp/david2003
bandit30@bandit:~$ cd /tmp/david2003
bandit30@bandit:/tmp/david2003$ git clone ssh://bandit30-git@localhost:2220/
home/bandit30-git/repo
Cloning into 'repo'...
Receiving objects: 100% (4/4), done.
bandit30@bandit:/tmp/david2003$ cd repo/
bandit30@bandit:/tmp/david2003/repo$ cat README.md
just an epmty file... muahaha
bandit30@bandit:/tmp/david2003/repo$ git tag
secret
bandit30@bandit:/tmp/david2003/repo$ git show secret
OoffzGDlzhAlerFJ2cAiz1D41JW1Mhmt
bandit30@bandit:/tmp/david2003/repo$

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