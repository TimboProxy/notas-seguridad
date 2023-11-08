## Objetivo
In the last challenge, you mastered octal (base 8), decimal (base 10), and hexadecimal (base 16) numbers, but this vault door uses a different change of base as well as URL encoding! The source code for this vault is here: [VaultDoor5.java](https://jupiter.challenges.picoctf.org/static/d31ce4356bdfd15d33a9af7e35ab4d0a/VaultDoor5.java)
## Solución 
Este código nos presenta la siguiente contraseña que tiene dos cifrados:

String expected = JTYzJTMwJTZlJTc2JTMzJTcyJTc0JTMxJTZlJTY3JTVm"
"JTY2JTcyJTMwJTZkJTVmJTYyJTYxJTM1JTY1JTVmJTM2"
"JTM0JTVmJTY1JTMzJTMxJTM1JTMyJTYyJTY2JTM0";

Los cifrados los conocemos gracias a esta lineal:
String base64Encoded = base64Encode(urlEncoded.getBytes());
Base64 y url, por lo cual usamos a cyberchef, ponemos los dos decodificadores y obtenemos la bandera:
c0nv3rt1ng_fr0m_ba5e_64_e3152bf4
## Notas adicionales
picoCTF{c0nv3rt1ng_fr0m_ba5e_64_e3152bf4}
## Referencias
https://play.picoctf.org/practice/challenge/77