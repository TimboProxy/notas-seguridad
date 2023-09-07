# Bandit Level 12 → Level 13
## Objetivo
The password for the next level is stored in the file **data.txt**, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under /tmp in which you can work using mkdir. For example: mkdir /tmp/myname123. Then copy the datafile using cp, and rename it using mv (read the manpages!)
## Datos de acceso al nivel
```
Server : bandit12.labs.overthewire.org
User : bandit12
Password : JVNBBFSmZwKKOP0XbFXOoW8chDz5yVRv
Comando: SSH bandit12@bandit.labs.overthewire.org -p 2220
```
## Solución 




## Notas adicionales
-Vaciado hexadecimal - Hex dump
-Se puede revertir ese proceso antes de que se le aplicara el vacío hexadecimal y se hace con el comando:
xxd -r (me parece que xxd es el comando que realiza el vacío hexadecimal)
-mkdir /tmp/Nombrequequerramosponerdelacarpeta (así se crea una carpeta)
- cat data.txt | xxd -r -> /tmp/Nombrequequerramosponerdelacarpeta/datos
- (Aqui estamos mandando la salida en reversa de cat en la carpeta y además en un archivo llamado datos)
-File nos deja ver el tipo de archivo y por lo tanto, para ver si esta comprimido
-
-
gzip -d datos
mv datos datos.bz2 
bzip2 -d datos.bz2
mv datos datos.gz
gzip .d datos.gz
mv datos datos.tar
tar xf datos.tar
rm datos.tar
mv data5.bin data5.tar
tar xf data5.tar
rm data5.tar (rm borra)
mv data6.bin data6.bz2
bzip2 -d data6.bz2
mv data6 data6.tar
tar xf data6.tar
rm data6.tar
mv ------------
gzip -d data8.gz

-d descomprime
-mv renombra el archivo
entre cada descomprimiento tenemos que estar:
-viendo el tipo de archivo
-descomprimir el archivo (necesita el comando correcto y la extension del archivo)
-borrar si es necesario archivos para no confundirnos 

Otra forma mas rapida es usando piping:
file data.txt
xxd -r data.txt | file -
e irle aumentando la descomprensión necesaria cada que la consola nos diga el nuevo tipo de comprensión, hasta que quede así: 

xxd -r data.txt | zcat | bzcat | zcat | tar xO | tar xO | bzcat | tar xO | zcat 
## Referencias