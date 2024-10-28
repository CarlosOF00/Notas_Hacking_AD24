## Descripción 
This vault uses ASCII encoding for the password. The source code for this vault is here: [VaultDoor4.java](https://jupiter.challenges.picoctf.org/static/c695ee23309d453a3ef369c34cc1bccb/VaultDoor4.java)

## Datos de Acceso al Nivel
user: carlosof / kali
password:

## Solución
```bash
                                                                                                                                                                        
┌──(kali㉿kali)-[~/retosReverse]
└─$ mkdir vault-door-4
                                                                                                                                                                        
┌──(kali㉿kali)-[~/retosReverse]
└─$ cd vault-door-4
                                                                                                                                                                        
┌──(kali㉿kali)-[~/retosReverse/vault-door-4]
└─$ wget https://jupiter.challenges.picoctf.org/static/c695ee23309d453a3ef369c34cc1bccb/VaultDoor4.java
--2024-10-27 23:26:54--  https://jupiter.challenges.picoctf.org/static/c695ee23309d453a3ef369c34cc1bccb/VaultDoor4.java
Resolving jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)... 3.131.60.8
Connecting to jupiter.challenges.picoctf.org (jupiter.challenges.picoctf.org)|3.131.60.8|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 1497 (1.5K) [application/octet-stream]
Saving to: ‘VaultDoor4.java’

VaultDoor4.java                           100%[=====================================================================================>]   1.46K  --.-KB/s    in 0s      

2024-10-27 23:26:55 (23.6 MB/s) - ‘VaultDoor4.java’ saved [1497/1497]

                                                                                                                                                                        
┌──(kali㉿kali)-[~/retosReverse/vault-door-4]
└─$ cat VaultDoor4.java 
import java.util.*;

class VaultDoor4 {
    public static void main(String args[]) {
        VaultDoor4 vaultDoor = new VaultDoor4();
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

    // I made myself dizzy converting all of these numbers into different bases,
    // so I just *know* that this vault will be impenetrable. This will make Dr.
    // Evil like me better than all of the other minions--especially Minion
    // #5620--I just know it!
    //
    //  .:::.   .:::.
    // :::::::.:::::::
    // :::::::::::::::
    // ':::::::::::::'
    //   ':::::::::'
    //     ':::::'
    //       ':'
    // -Minion #7781
    public boolean checkPassword(String password) {
        byte[] passBytes = password.getBytes();
        byte[] myBytes = {
            106 , 85  , 53  , 116 , 95  , 52  , 95  , 98  ,
            0x55, 0x6e, 0x43, 0x68, 0x5f, 0x30, 0x66, 0x5f,
            0142, 0131, 0164, 063 , 0163, 0137, 070 , 0146,
            '4' , 'a' , '6' , 'c' , 'b' , 'f' , '3' , 'b' ,
        };
        for (int i=0; i<32; i++) {
            if (passBytes[i] != myBytes[i]) {
                return false;
            }
        }
        return true;
    }
}
                                                                                                                                                                        
┌──(kali㉿kali)-[~/retosReverse/vault-door-4]
└─$ 
```

- Podemos abrir una ventana del navegador y utilizar la consola para el siguiente paso, ya que usaremos `javascript` así debe quedar el código:
```bash
String.fromCharCode(106 , 85  , 53  , 116 , 95  , 52  , 95  , 98  ,
            0x55, 0x6e, 0x43, 0x68, 0x5f, 0x30, 0x66, 0x5f,
            0142, 0131, 0164, 063 , 0163, 0137, 070 , 0146) + ['4' , 'a' , '6' , 'c' , 'b' , 'f' , '3' , 'b' ].join('')
```
- La salida queda así:
```bash
String.fromCharCode(106 , 85  , 53  , 116 , 95  , 52  , 95  , 98  ,
            0x55, 0x6e, 0x43, 0x68, 0x5f, 0x30, 0x66, 0x5f,
            0142, 0131, 0164, 063 , 0163, 0137, 070 , 0146) + ['4' , 'a' , '6' , 'c' , 'b' , 'f' , '3' , 'b' ].join('')
"jU5t_4_bUnCh_0f_bYt3s_8f4a6cbf3b"
```
- Ahora solo le damos el formato a la bandera:
	- Flag: picoCTF{jU5t_4_bUnCh_0f_bYt3s_8f4a6cbf3b}

## Notas Adicionales


## Referencias 
https://play.picoctf.org/practice/challenge/71?page=1&search=vault