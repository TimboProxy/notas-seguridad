# # Bandit Level 8 → Level 9
## Objetivo
The password for the next level is stored in the file **data.txt** and is the only line of text that occurs only once
## Datos de acceso al nivel
```
Server : bandit8.labs.overthewire.org
User : bandit8
Password : TESKZC0XvTetK0S9xNwm25STk5iWrBvP
Comando: SSH bandit8@bandit.labs.overthewire.org -p 2220
```
## Solución 
bandit8@bandit:~$ whoami
bandit8
bandit8@bandit:~$ pwd
/home/bandit8
bandit8@bandit:~$ ls
data.txt
bandit8@bandit:~$ cat data.txt | sort | uniq -c
     10 08Jd2vmb6FjR4zXPteGHhpJm8A0OOA5B
     10 0dEKX1sDwYtc4vyjrKpGu30ecWBsDDa9
     10 0YDTDPCLc585IaFu911ukE9QfD6Ykrlz
     10 0zP9wfUcMKjZM2hiQUYR1nTfmaRdYSQE
     10 11FFcDRW5ZXXmX7geZORYRwiJfj8B3Gh
     10 1jZv2X1O2JypCBIgDNRwWQzS1CyhvByt
     10 1MUdfR7bGGCpNfGEOXaIEdrA8hT2L8Tk
     10 2fepTygKSkWHQJS2GrmGwjyl36eXSWJe
     10 3cTCUFe6MTl1FDAL0Z49cRByfq1MRlxJ
     10 3PB0nBOh1WKb1K6MImHdvwQjItFcxfdF
     10 3QXFsSepZUIOznxndwnQNnxvbpcXG05c
     10 47eFxPAuZ4tlWbT4P5ADs1tC0twlr51V
     10 4aOtDpqjXGIMOcyqirndla7J8S3jZZAy
     10 4Fi1Ig3hG4mDdl64v3gRPre3qNx26k0U
     10 4u67BT7FonRZeibEb9iOl6pHcMtzq03H
     10 6R258gRryXf9CBoG6erTEgGjb8ykWYrV
     10 7J5LX5IxjJ75DSStY7k9QTXgY8Hcygxu
     10 7rUrQcuUE8W3u7sHw6GqIw5KIm1vnvT0
     10 8fa6npI57h2Bc2yVSHJTKYwkGF1f25nm
     10 8mUGsbsFDyMVhqsbCIu5VQdKyNS6B4yK
     10 9b0fkcvfVG8ClmKfqmzFFSxszfYoGje3
     10 9rdQWtaWPaCwsiYUmcR7DZsTjlDzCIDk
     10 9uChpqBSAkMtOSNBVj1HAzRR5SQePFZe
     10 a6SMGsFpTKq8UGdndarh86o0ohHccjb0
     10 AWuhqidoTFNEaYmsX7njF8elfk6UTt8V
     10 Bap5iwr9yiz7NNLdn2pRIBDuzjS4apt6
     10 bbFQ44ZGHTUPiPEBvfADGWpwXzdhco23
     10 cBuyMeLeTl5bFQMjlzWIGHpbVwqQZkWQ
     10 cmtlazWcnfmS07dz52EdwhfVXD5hm8Ox
     10 DCEBvsEhDdFKdhuYgoK5615G0hkxkRbS
     10 dMNfFW0t7tDLsN6jM4t15q7sGdXIJlDO
      1 EN632PlfYiZbn3PhVK3XOGSlNInNE00t
## Notas adicionales
Aquí hacemos uso del "piping" para redirigir la salida de un comando a otro comando
el resultado de cat se lo pasa a sort y ese a uniq.
Sort - ordena lineas similares 
Uniq - puede contar las ocurrencias de las lineas o puede mostrar solo las repetidas.

uniq -c Cuenta cuantas veces se repite cada linea y ademas las muestra
uniq -d Muestra nada mas las lineas que se repiten y no muestra cuantas veces lo hacen
uniq -u Para que funcione este parametro las lineas tienen que estar ordenadas.
## Referencias