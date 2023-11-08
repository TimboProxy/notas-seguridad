## Objetivo
This vault uses some complicated arrays! I hope you can make sense of it, special agent. The source code for this vault is here: [VaultDoor1.java](https://jupiter.challenges.picoctf.org/static/ff2585f7afd21b81f69d2fbe37c081ae/VaultDoor1.java)
## Solución 
El archivo java nos pone la contraseña de esta forma (no es toda la contraseña):

    public boolean checkPassword(String password) {
        return password.length() == 32 &&
               password.charAt(0)  == 'd' &&
               password.charAt(29) == '9' &&
               password.charAt(4)  == 'r' &&
               password.charAt(2)  == '5' &&

Lo unico que hay que hacer es ordenar de 0 a 31, hay diversas maneras de hacerlo pero yo le dije a chatgpt que lo hiciera y al unir cada carácter se obtiene lo siguiente:
d35c r4mbl3_tH3_cH4r4cT3r57092e
## Notas adicionales
picoCTF{d35c r4mbl3_tH3_cH4r4cT3r57092e}
## Referencias
https://play.picoctf.org/practice/challenge/12