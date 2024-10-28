## Descripción 
Your mission is to enter Dr. Evil's laboratory and retrieve the blueprints for his Doomsday Project. The laboratory is protected by a series of locked vault doors. Each door is controlled by a computer and requires a password to open. Unfortunately, our undercover agents have not been able to obtain the secret passwords for the vault doors, but one of our junior agents obtained the source code for each vault's computer! You will need to read the source code for each level to figure out what the password is for that vault door. As a warmup, we have created a replica vault in our training facility. The source code for the training vault is here: [VaultDoorTraining.java](https://jupiter.challenges.picoctf.org/static/03c960ddcc761e6f7d1722d8e6212db3/VaultDoorTraining.java)

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosReverse]
└─$ mkdir vault-door-training
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosReverse]
└─$ cd vault-door-training 
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosReverse/vault-door-training]
└─$ wget https://jupiter.challenges.picoctf.org/static/03c960ddcc761e6f7d1722d8e6212db3/VaultDoorTraining.java
--2024-10-27 22:26:04--  https://jupiter.challenges.picoctf.org/static/03c960ddcc761e6f7d1722d8e6212db3/VaultDoorTraining.java
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 943 [application/octet-stream]
Saving to: ‘VaultDoorTraining.java’

VaultDoorTraining.java                    100%[===================================================================================>]     943  --.-KB/s    in 0s      

2024-10-27 22:26:06 (6.86 MB/s) - ‘VaultDoorTraining.java’ saved [943/943]

                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosReverse/vault-door-training]
└─$ ls
VaultDoorTraining.java
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosReverse/vault-door-training]
└─$ cat VaultDoorTraining.java 
import java.util.*;

class VaultDoorTraining {
    public static void main(String args[]) {
        VaultDoorTraining vaultDoor = new VaultDoorTraining();
        Scanner scanner = new Scanner(System.in); 
        System.out.print("Enter vault password: ");
        String userInput = scanner.next();
        String input = userInput.substring("picoCTF{".length(),userInput.length()-1);
        if (vaultDoor.checkPassword(input)) {
            System.out.println("Access granted.");
        } else {
            System.out.println("Access denied!");
        }
   }

    // The password is below. Is it safe to put the password in the source code?
    // What if somebody stole our source code? Then they would know what our
    // password is. Hmm... I will think of some ways to improve the security
    // on the other doors.
    //
    // -Minion #9567
    public boolean checkPassword(String password) {
        return password.equals("w4rm1ng_Up_w1tH_jAv4_3808d338b46");
    }
}
       
```
- La contraseña la podemos encontrar en el mismo código, solo es cuestión de poner atención y revisar las funciones:
	- picoCTF{w4rm1ng_Up_w1tH_jAv4_3808d338b46}

## Notas Adicionales

## Referencias 
https://play.picoctf.org/practice/challenge/7?page=1&search=vault