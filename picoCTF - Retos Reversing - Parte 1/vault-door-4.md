## Objetivo
This vault uses ASCII encoding for the password. The source code for this vault is here: [VaultDoor4.java](https://jupiter.challenges.picoctf.org/static/c695ee23309d453a3ef369c34cc1bccb/VaultDoor4.java)
## Solución 
Este código nos presenta la siguiente situación:

      byte[] myBytes = {
            106 , 85  , 53  , 116 , 95  , 52  , 95  , 98  ,
            0x55, 0x6e, 0x43, 0x68, 0x5f, 0x30, 0x66, 0x5f,
            0142, 0131, 0164, 063 , 0163, 0137, 070 , 0146,
            '4' , 'a' , '6' , 'c' , 'b' , 'f' , '3' , 'b' ,
        };

La primera fila es decimal, la segunda es hexadecimal y la tercera es octal. la cuarta es codigo ASCII así que debemos de hacer las debidas transformaciones a codigo ASCII para obtener la bandera:
106 , 85  , 53  , 116 , 95  , 52  , 95  , 98  
jU5t_4_b

0x55, 0x6e, 0x43, 0x68, 0x5f, 0x30, 0x66, 0x5f,
UnCh_0f_

0142, 0131, 0164, 063 , 0163, 0137, 070 , 0146,
B9t?s_8F

'4' , 'a' , '6' , 'c' , 'b' , 'f' , '3' , 'b' ,

uniendo todas las partes obtenemos la bandera
## Notas adicionales
picoCTF{jU5t_4_bUnCh_0f_B9t?s_8F4a6cbf3b}
## Referencias
https://play.picoctf.org/practice/challenge/71