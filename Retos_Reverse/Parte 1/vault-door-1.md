## Descripción 
This vault uses some complicated arrays! I hope you can make sense of it, special agent. The source code for this vault is here: [VaultDoor1.java](https://jupiter.challenges.picoctf.org/static/ff2585f7afd21b81f69d2fbe37c081ae/VaultDoor1.java)

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
┌──(kali㉿kali)-[~/retosReverse]
└─$ mkdir vault-door-1          
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosReverse]
└─$ cd vault-door-1       
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosReverse/vault-door-1]
└─$ wget https://jupiter.challenges.picoctf.org/static/ff2585f7afd21b81f69d2fbe37c081ae/VaultDoor1.java       
--2024-10-27 22:56:48--  https://jupiter.challenges.picoctf.org/static/ff2585f7afd21b81f69d2fbe37c081ae/VaultDoor1.java
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 2264 (2.2K) [application/octet-stream]
Saving to: ‘VaultDoor1.java’

VaultDoor1.java                           100%[===================================================================================>]   2.21K  --.-KB/s    in 0s      

2024-10-27 22:56:49 (42.1 MB/s) - ‘VaultDoor1.java’ saved [2264/2264]

                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosReverse/vault-door-1]
└─$ cat VaultDoor1.java       
import java.util.*;

class VaultDoor1 {
    public static void main(String args[]) {
        VaultDoor1 vaultDoor = new VaultDoor1();
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

    // I came up with a more secure way to check the password without putting
    // the password itself in the source code. I think this is going to be
    // UNHACKABLE!! I hope Dr. Evil agrees...
    //
    // -Minion #8728
    public boolean checkPassword(String password) {
        return password.length() == 32 &&
               password.charAt(0)  == 'd' &&
               password.charAt(29) == '9' &&
               password.charAt(4)  == 'r' &&
               password.charAt(2)  == '5' &&
               password.charAt(23) == 'r' &&
               password.charAt(3)  == 'c' &&
               password.charAt(17) == '4' &&
               password.charAt(1)  == '3' &&
               password.charAt(7)  == 'b' &&
               password.charAt(10) == '_' &&
               password.charAt(5)  == '4' &&
               password.charAt(9)  == '3' &&
               password.charAt(11) == 't' &&
               password.charAt(15) == 'c' &&
               password.charAt(8)  == 'l' &&
               password.charAt(12) == 'H' &&
               password.charAt(20) == 'c' &&
               password.charAt(14) == '_' &&
               password.charAt(6)  == 'm' &&
               password.charAt(24) == '5' &&
               password.charAt(18) == 'r' &&
               password.charAt(13) == '3' &&
               password.charAt(19) == '4' &&
               password.charAt(21) == 'T' &&
               password.charAt(16) == 'H' &&
               password.charAt(27) == '5' &&
               password.charAt(30) == '2' &&
               password.charAt(25) == '_' &&
               password.charAt(22) == '3' &&
               password.charAt(28) == '0' &&
               password.charAt(26) == '7' &&
               password.charAt(31) == 'e';
    }
}
                                                                                                                                                                      
┌──(kali㉿kali)-[~/retosReverse/vault-door-1]
└─$ nano bandera  

┌──(kali㉿kali)-[~/retosReverse/vault-door-1]
└─$ cat bandera | sort | awk '{print($3)}' | tr -d " ' " | tr -d "\n"
d35cr4mbl3_tH3_cH4r4cT3r5_75092e                                                          
┌──(kali㉿kali)-[~/retosReverse/vault-door-1]
└─$ echo 'picoCTF{d35cr4mbl3_tH3_cH4r4cT3r5_75092e}'
picoCTF{d35cr4mbl3_tH3_cH4r4cT3r5_75092e}

```

## Notas Adicionales
- **`cat bandera`**: Este comando muestra el contenido del archivo llamado `bandera`. 
    
- **`| sort`**: El símbolo `|` (pipe) redirige la salida del comando anterior como entrada del siguiente comando. `sort` ordena las líneas del texto que recibe de `cat`. Por defecto, ordena alfabéticamente.
    
- **`| awk '{print($3)}'`**: Aquí, `awk` es una herramienta de procesamiento de texto. Esta parte del comando selecciona la tercera columna de cada línea (la que se encuentra en la posición 3, separada por espacios). `print($3)` imprime solo esa tercera columna.
    
- **`| tr -d " ' "`**: El comando `tr` se utiliza para traducir o eliminar caracteres. En este caso, `-d` indica que se deben eliminar los caracteres especificados. Aquí se están eliminando espacios ( ) y comillas simples (`'`).
    
- **`| tr -d "\n"`**: Finalmente, este segundo uso de `tr` elimina los saltos de línea (`\n`) de la salida, de modo que todo el texto final se presente en una sola línea.

## Referencias 
https://play.picoctf.org/practice/challenge/12?category=3&page=1&search=vault