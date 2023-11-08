## Objetivo
Your mission is to enter Dr. Evil's laboratory and retrieve the blueprints for his Doomsday Project. The laboratory is protected by a series of locked vault doors. Each door is controlled by a computer and requires a password to open. Unfortunately, our undercover agents have not been able to obtain the secret passwords for the vault doors, but one of our junior agents obtained the source code for each vault's computer! You will need to read the source code for each level to figure out what the password is for that vault door. As a warmup, we have created a replica vault in our training facility. The source code for the training vault is here: [VaultDoorTraining.java](https://jupiter.challenges.picoctf.org/static/a4a1ca9c54d8fac9404f9cbc50d9751a/VaultDoorTraining.java)
## Solución 
Estos retos de vault-door estan muy sencillos, las respuestas están en el código de una u otra forma, este de aquí esta en un método:

    public boolean checkPassword(String password) {
        return password.equals("w4rm1ng_Up_w1tH_jAv4_be8d9806f18");
    }
## Notas adicionales
picoCTF{w4rm1ng_Up_w1tH_jAv4_be8d9806f18}
## Referencias
https://play.picoctf.org/practice/challenge/7